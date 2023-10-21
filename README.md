# ASP .NET CORE

**ASP .Net Core is a**<br/>
•	cross platform (Can be hosted on Windows, Linux, Mac and different servers like Kestrel, IIS, Nginx, Docker Apache) high performance<br/>
•	open-source framework for building modern(https://github.com/dotnet/aspnetcore)<br/>
•	cloud enabled web application and services<br/>
<br/><br/>
ASP.NET Core is not an upgraded version of ASP.NET. ASP.NET Core is completely rewriting that work with the .net Core framework. It is much faster, configurable, modular, scalable, extensible, and has cross-platform support. It is best suitable for developing cloud-based such as web applications, mobile applications, and IoT applications.
<br/><br/>
**Features of Asp.Net Core Following are the core features that are provided by the ASP.NET Core**<br/>
•	Built-in supports for the logging framework and it can be extensible<br/>
•	Built-in supports for Dependency Injection<br/>
•	Introduced a new, fast and cross-platform web server - Kestrel. So, a web application can run without IIS, Apache, and Nginx.<br/>
•	Multiple hosting platforms are supported<br/>
•	It supports modularity, so the developer needs to include the module required by the application.<br/>
•	Command-line supports to creating, building, and running of the application<br/>
•	There is no web .config file. We can store the custom configuration into an appsettings.json file<br/>
•	It has good support for asynchronous programming.<br/>
<br/><br/>
**ASP .Net Core Modules**
1.	MVC: For creating medium to complex web application.
2.	Web API: For creating RESTful services for all types of client applications.
3.	Razor Pages: For creating Simple & Page focussed web applications.
4.	Blazor: For creating Web applications with C# code both on client-side and server-side.

<br/><br/>
**ASP .Net Web Forms vs ASP .Net MVC vs ASP .Net Core ASP .Net Web Forms (2002)**
<br/><br/>
<table>
<thead>
 <tr>
  <th>ASP .Net Web Forms (2002)</th>
  <th>ASP .Net MVC (2009)</th>
  <th>ASP .Net Core (2016)</th>
 </tr>
</thead>
<tbody>
 <tr>
  <td>Performance issue due to server events and view-state</td>
  <td>Performance issue due to some dependencies with ASP .Net Web forms (.Net Framework)</td>
  <td>Faster Performance</td>
 </tr>
  <tr>
  <td>Good for small application</td>
  <td>Not Cross Platform i.e., Only for Windows</td>
  <td>cloud friendly</td>
 </tr>
  <tr>
  <td>Not Cross Platform i.e., Only for Windows</td>
  <td>Slightly cloud friendly</td>
  <td>Open-source (https://github.com/dotnet/aspnetcore)</td>
 </tr>
  <tr>
  <td>Not cloud friendly</td>
  <td>Open Source</td>
  <td>MVC Pattern</td>
 </tr>
   <tr>
  <td>Not open-source</td>
  <td>MVC Pattern</td>
  <td>Built-in support for Dependency Injection</td>
 </tr>
</tbody>
</table>

# Servers
A web application requires a server to in order to receive a request and send a reponse. <br/><br/>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/7ba5585a-1dab-44a2-9909-ef4ca004dff2)
<br/>
**Kestrel**</br>
Kestrel is the default Cross-Platform Http Server used in  ASP .Net Application. It acts as both Development Server as well the the real application Server. Kestrel does not support load balancing, URL rewriting command name. Kestrel act as intermediate between Local Network/Internet and Application. It receive the request and prepare an object with request details (called HttpContext) and send it to the application and receive the response from the application and send back to the Local Network/Internet.

**Reverse Proxy Server (IIS, Ngnix and Apache)**</br>
Production Server IIS - Internet Information Services Benefits: Load Balancing, Caching, URL Rewriting, Decompressing the request, Authentication, Decryption of SSL Certificates
<br/><br/>
**IIS express**<br/>
IISExpress is a dummy IIS Server. It is a light weight version of IIS Server.<br/>
•	HTTP access logs<br/>
•	Port sharing<br/>
•	Windows authentication<br/>
•	Management console<br/>
•	Process activation<br/>
•	Configuration API<br/>
•	Request filters<br/>
•	HTTP redirect rules<br/>

```
Note:
Allowed Port Number (> 1024 & < 65536) Other ports are reserved.
In order to start the server app.Run() should be called.
```

 <br/><br/>
**launchSettings.json file**</br>
launchSettings.json is file which has the profiles configuration of the servers. The file is present in the ‘\Properties’ folder of the project. Profile is the collection of settings which are used to run the server.

<table>
 <tr>
  <td>commandName</td>
  <td>Project means Kestrel and IISExpress means IIS</td>
 </tr>
 <tr>
  <td>launchBrowser</td>
  <td>True/False</td>
 </tr>
 <tr>
  <td>applicationUrl</td>
  <td>Contains the URL</td>
 </tr>
 <tr>
  <td>dotnetRunMessages</td>
  <td>True/False</td>
 </tr>
</table>

**Sample launchSettings.json file**</br>
```
{
  "iisSettings": {
    "windowsAuthentication": false,
    "anonymousAuthentication": true,
    "iisExpress": {
      "applicationUrl": "http://localhost:48362",
      "sslPort": 44310
    }
  },
  "profiles": {
    "Application1": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "applicationUrl": "https://localhost:7019;http://localhost:5299",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "IIS Express": {
      "commandName": "IISExpress",
      "launchBrowser": true,
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}
```
# HTTP
HTTP is an application-protocol that defines set of rules to send request from browser to server and send response from server to browser.
Initially developed by Tim Berners Lee, later standardized by IETF (Internet Engineering Task Force) and W3C (World Wide Web Consortium)</br></br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/a77613c2-fcbd-4f88-98a0-aab746451f01)
</br>

**Properties:** </br>
•	Foundation of the Web</br>
•	Simple: Human readable format</br>
•	Extensible using the Headers to send/receive extra information</br>
•	Stateless, doesn’t maintain state unless HTTP Cookies are introduced to hold the communication session or state</br>

</br></br>
**HTTP Headers**</br>
A collection of key and value pairs (or dictionary) of meta-data that can be passed with each request or response.
Headers are categorized by context:</br>
<ins>Request Headers:</ins> such as AcceptLanguage, Authorization</br>
<ins>Response Headers:</ins> such as Connection, Server</br>
<ins>Representation Headers:</ins> such as content-type, content-language</br>
<ins>Payload Headers:</ins> such as ContentLength, transfer-encoding</br>
</br></br>
**Http statuses**</br>
Http status represents the status of the RESTful service after HTTP Request is completed Status codes are represented as 3 digits, where the first digit represents the category:</br></br>
****1xx:**** Informational Responses</br>
****2xx:**** Successful Responses</br>
****3xx:**** Redirection (action to be taken by browser or user)</br>
****4xx:**** Invalid request by client, data incomplete or invalid</br>
****5xx:**** Server-side error (API crash, misconfigurations, app pool shutdown)</br>
</br></br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/a7297218-52cc-4094-8b06-b840648f93f7)
</br></br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/97ec1e18-f431-4019-a2b6-fe0dec27c563)


**HTTP Cookies**</br>
•	Used to maintain the state or session between multiple HTTP communications</br>
•	A Cookie is a small piece of data passed from server to user’s browser via the set-cookie response header</br>
•	Cookies can also be restricted via the use of Secure attribute and HttpOnly Attribute, this is used to prevent Cross-site scripting attack (XSS)</br>
•	Cookies are used mainly for Session Management, Personalization and Tracking</br>
</br>

**HTTPS Vs HTTP/2 Vs HTTP/3**
<table>
 <thead>
  <tr>
   <th>HTTPS</th>
   <th>HTTP/2</th>
   <th>HTTP/3</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>S stands for Secure, which means the HTTP communication between the client (like browser) and the website will happen via a secure channel, using an SSL/TLS encryption protocol</td>
   <td>HTTP/2 is a major revision of the HTTP, introduced in 2015</td>
   <td>Though not officially announced, HTTP/3 is the 3rd major revision of the HTTP</td>
  </tr>
  <tr>
   <td>TLS is the successor of SSL</td>
   <td>Its purpose is to improve the web performance by decreasing latency</td>
   <td>Introduces data transmission on a new transport protocol - Quic or (pronounced as Quick)</td>
  </tr>
  <tr>
   <td>TLS v1.2 is the minimum recommended version of TLS that websites should use to maintain a secure website.</td>
   <td>Over 97% of browsers now support HTTP/2</td>
   <td>Quick UDP Internet Connections or Quic relies on UDP protocol rather than TCP</td>
  </tr>
  <tr>
   <td>TLS v1.3 is the latest version.</td>
   <td>Key Features Include: Multiplexing, Weighted Prioritization, Server Push, Headers Compression</td>
   <td>Quic on UDP provides a faster and more efficient communication than TCP which leads to improved web performance and user experience</td>
  </tr>
  <tr>
   <td>Your site, including your web API must always use HTTPS</td>
   <td></td>
   <td>Over 75% of browsers now support HTTP/3, more and more sites have started adopting it</td>
  </tr>
 </tbody>
</table>

**HTTP/2 Key Features**</br>
Multiplexing: Request and Response messages can be transmitted between client and server via bidirectional and concurrent streams (Over the same TCP Connection)
Weighted prioritization: streams can be assigned weighted value and dependency for the client to display the responses from the streams accordingly
Server Push: When client requests a resource, the server can push extra resources to be cached on the client and used when needed 
Headers Compression: using HPACK specification to compress HTTP headers to optimize streams multiplexing</br></br>

**HTTP/3 Key Features**</br>
•	Faster connection setup and reduced Round-Trip Time by combining the cryptographic and transport handshakes 
•	With the use of Connection IDs, a communication can be maintained between client and server even when device’s network switches to another
•	Solves the TCP head-of-line blocking issue: If a packet is lost, the streamaware Quic communication will know which stream is exactly loss and it will retransmit it
•	Enhanced security with transport-level default encryption: which means connections will always be encrypted, which will include data and meta-data about the connection
</br></br>

**HTTP Request**</br>
The Browser request to Server.
General Syntax of HTTP Request
 ![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/8442562d-bbb3-495f-a47a-9b8563347764)


Sample Request
 ![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/45212ab5-3ac3-4116-9b2d-3c927e895c89)

**HTTP Request Headers**</br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/0fb458d5-926c-49d2-8689-4398fc0e8bdf)

More on Header: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/b66bf92d-0137-4624-8abb-27d996c739a3)

**HTTP Request Methods**</br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/774065c9-8479-4013-85e5-94a1b71c9d46)
Other Method: OPTIONS, TRACE, HEAD, TUNNEL

**Get Vs Post**</br>
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/a0b6bb90-a255-462c-bf9c-bb87aad59726)

**HTTP Response**</br>
The Server response to the request of the Browser.
General Syntax of HTTP Response
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/0e4cc7c0-5e6c-4620-b405-3379845b8185)
Sample HTTP Response
![image](https://github.com/rahul-jha-official/asp_dot_net_core/assets/138975150/897674ea-e09f-4a19-b499-cd9dd2b10041)

**Response Start Line**</br>
Includes HTTP version, status code and status description.
HTTP Version: 1/1 | 2 | 3
Status Code: 101 | 200 | 201 | 302 | 400 | 401 | 404 | 500
Status Description: Switching Protocols | OK | Created | Found | Bad Request | Unauthorized | Not Found | Internal Server Error

