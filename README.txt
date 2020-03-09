EE 250 Lab Recap1
Ruiyi Shen
ruiyishe@usc.edu

1. Why do we want to use VMs? What are the pros and cons? (2)
Because production systems in the field almost always use Linux, the VM environment will expose us to the environment. VM provides us with a Linux system that we can work on, but they are less efficient than the real machines because they access hardware indirectly.

2. What is docker and how does it compare to VMs? (2) (https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)
Docker containers are similar to VMs, but they have relaxed isolation properties to share the Operating System (OS) among the applications. Therefore, containers are considered lightweight

3. How do you upload your work using git (3 steps)? How do you retrieve others’ work? (1)
Upload: git add, git commit -m, git push
Retrieve: git pull

4. What’s a pull request in git workflow? (1)
It is a request that asks the remote server for data and fetches the content that is uploaded to the remote server, and then merge the local version of the repo with the remote server at the selected branch.

5. What is authentication? What is authorization? (1+1)
Authentication is the process to recognize a user’s identity. It is the mechanism of associating an incoming request with a set of identifying credentials. This is the process of granting or denying access to a network resource that allows the user access to various resources based on the user's identity. It usually preceded by the process of authentication.

6. What are the 3 common ways of authentication? What did we use in ssh into RPIs and AWS EC2? (2+1)
Password, Keys, and biometric authentication
For RPI, we used password. For AWS EC2, we used private SSH keys.

7. What’s TCP congestion control and flow control? Why is TCP slow compared with UDP? (2+1)
Congestion control means that TCP will ensure traffics in the network are not too much for the receiver to create congestion. It is implemented by slowing the speed of transmitting by the transport layer. Flow Control basically means that TCP will ensure that a sender is not overwhelming a receiver by sending packets faster than it can consume. It is implemented by slow sending the payload from the sender side.
TCP is slower because it provides many more functions for the user than UDP does, which requires more time in sending the data.

8. What is SSL/TLS? Explain how it works. (such as ssh, https) (3, can give partial credits)
SSL stands for secure socket layer. TLS, the transport layer security, is essentially another name that is given to an updated version of SSL. This protocol encrypts internet traffic of all types. SSL works through an SSL certificate. SSL/TLS certificates work by digitally tying a cryptographic key to a company’s identifying information. Only when the certificates are verified can a secure connection be established. For example in https, this bi-directional encryption and authentication process is required between the client and the server to ensure data security in transmission. Similarly in SSH, the key pairs can are also forms of SSL certificates that are required when establishing a secure connection.

9. Imagine you have a server code running in localhost:5000 in a virtual box VM, and the VM is running in your physical host. A client program is running in RPI. Your RPI and host are connected to the same LAN. Can your client talk to the server? What do you have to do to make it work? (3, can give partial credits)
No. Because the VM runs on network address translating(NAT) service. For the client to connect to the server, port forwarding to redirect a communication request from one address and port number combination to another is required to establish a connection between the RPi and the VM.

10. What is a REST API? (1)
REST is Representational State Transfer, a way for two computer systems to communicate over HTTP in a similar way to web browsers and servers. A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.

11. Are HTTP and MQTT stateful or stateless? Stateful meaning that the server maintains the client’s request state. (1)
HTTP is stateless, but MQTT is stateful.

12. When you run MQTT pub sub, you can see that the subscriber gets a message real time when the publisher publishes a message. Is MQTT synchronous? (Think about what a synchronous function call implies) (1)
MQTT is asynchronous. As the client issues the request, it does not wait for the server for a response.

13. Is HTTP client-server a synchronous model? Why? If synchronous, how can you make it asynchronous? (1+1) (https://en.wikipedia.org/wiki/Ajax_(programming))
HTTP is synchronous. Because the client issues a request and waits for a response in real-time. By decoupling the data interchange layer from the presentation layer, Ajax allows web pages and, by extension, web applications, to change content dynamically without the need to reload the entire page. Therefore, web applications can send and retrieve data from a server asynchronously (in the background) without interfering with the display and behavior of the existing page, or in other words, without refreshing the page.

14. What is a process? What is a thread? (1+1)
In computing, a process is the instance of a computer program that is being executed by one or many threads. It contains the program code and its activity. A thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler, which is typically a part of the operating system

15. Summarize briefly three common data object formats (1) (https://stackoverflow.com/questions/14028293/google-protocol-buffers-vs-json-vs-xml)
JSON is is a human readable/editable data object format that can be parsed without knowing schema in advance. It provides excellent browser support and it is less verbose than XML. Meanwhile, XML is also a human readable/editable data object format can be parsed without knowing schema in advance. It provides good tooling support, and it is verbose. Google protocol buffers have very dense data. It is hard to decode without knowing the schema. It processes very fast but it is not intended for human eyes,

16. What are the three parts of a full-stack web application? (1)
Front-end, back-end and database development.

17. What’s the difference between memory and disk (size, speed, persistency, where to run program, where to load program from)? What’s the abstraction of disk data? (3+1)
Memory refers to the random access memory (RAM) inside a computer. RAM consists of small chips also known as memory modules. A computer uses memory (RAM) to store actively running programs on the computer, including the operating system. It has a comparatively small size ranging from 4GB to 16GB nowadays, but operates at a very high speed. On the other hand, the disk, sometimes referred to as hard drive, is a spindle of magnetic discs that can hold up to several thousands of gigabytes of data. Disk space is used for storing files instead of running programs. It has a much slower access speed than RAMs. Data abstraction is the reduction of a particular body of data to a simplified representation of the whole. Abstraction, in general, is the process of taking away or removing characteristics from something in order to reduce it to a set of essential characteristics.

18. What are the two most common types of HTTP request method? If you want to buy a ticket, what type of request is sent? What if you hit anrg.usc.edu in a browser? (1+1+1)
GET and POST. To buy a ticket, the POST request is sent. To access a webpage, the GET method will be used.

19. What’s the structure of a URL? For example when I type something in the search bar, this pops up in the browser. Explain each part of this URL (3, can give partial credits) https://www.google.com/search?q=wasd&sourceid=chrome&ie=UTF-8
A URL consists of five parts -- the scheme, subdomain, top-level domain, second-level domain, and subdirectory.
“https://” is the scheme,
“www” is the subdomain,
“google” is the second-level domain,
“com” is the top-level domain, 
and “/search?q=wasd&sourceid=chrome&ie=UTF-8” is the subdirectory.
