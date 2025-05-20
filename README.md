# DevOps-Learning-Networking
Repository Networking concepts I learnt in the CoderCo Networking Module.

## Overview of Computer Networks
A computer network are a set of devices which are connected to share information. The purpose of a computer network is to communicate and share resources between the devices. There are different types of computer networks such as LAN (Local Area Network) and WAN (Wide Area Network).

### Types of Networks
- LAN:
    - Small area such as a home or office.
    - Connects devices to share resources. For example, a laptop connects to a printer to print a document over WIFI.
    - Can also be used to provide internal access within a small area.
- WAN:
    - Large area like a city, country or larger region.
    - Connects multiple LANs, enabling communication and data transfer over long distances.

### Switches, Routers and Firewalls
- Switch:
    - Like a manager for your LAN.
    - Connects devices within the same network.
    - Manages data flow within a LAN. Prevents congestion and ensuring efficient communication.
- Routers:
    - Routers are like the traffic cop for your network.
    - Its main role is to direct traffic between different networks. For example, a home router connects the home network to the internet.
    - Ensures that data gets to the right place whether you're browsing or streaming a movie.
    - Connects different networks together.
- Firewalls:
    - Acts as a security guard for your network. 
    - Monitors and controls incoming and outgoing network traffic based on pre-determined security rules.
    - Vital for protecting network from unauthorised access.

### IP Addresses and MAC addresses
An IP address is a unique identifier for a device on a network. Allows devices to locate and communicate with each other. There are two types:
- IPV4: 32 bit address. Four decimal numbers, separated by dots. Each number can range from 0 to 255.
- IPV6: 128 bt addresses. Eight groups of four hexadecimal digits, separated by colons. Provides enhancements like simplified address assignment and improved security features.

MAC addresses are media access control addresses. These are unique identifiers assigned to a network interface. Like a fingerprint to a network device. 48 bit hexadecimal address. MAC addresses operate at the data link layer. Facilitate device identification within a local network. Essential for network communication and security. Ensure data packets get to the right place.

### Ports and Protocols: TCP, UDP
Ports are logicial endpoints for communication. They are like numbered doors on a device and each number is used for a specific type of network communication. These ports help facilitate communication between devices. When a computer wants to send or receive data, it uses ports to make sure the data goes to the right place. 

Protocols are rules governing data transmission. Similar to rules of the road. They define how data is formatted and transmitted across a network. These include HTTP, SFTP, FTP and much more. These protocols ensure devices can communicate effectively by following the same set of rules.

#### TCP (Transmission Control Protocol)
Like a postman of the internet. Ensures data sent from one device reaches another device accurately and in the correct order. 

Characteristics of TCP:
    - Connection-oriented: Before any data is sent, a connection is established between the devices.
    - Requires "handshake": An agreement between the two devices that they wish to communicate. 3 step process.
    - Reliable data transfer: Ensures all data sent is received correctly on the other end. If data is lost or corrupted, TCP will resend.

Functions of TCP:
    - Ensures data is delivered in order.
    - Error-checking and flow control: Checks for errors in the data and controls the flow of data to prevent congestion. 
    - Any bidirectional communication.

#### UDP (User Datagram Protocol)
Used to send and receive data. Unlike TCP, UDP is connectionless.

Characteristics of UDP:
    - Simple protocol to send and receive data.
    - Prior communication is not required. Can be a benefit and a drawback. Quick but no guarantee the data will reach its destination.
    - Connectionless: No formal connection established between sender and receiver, each packet is sent independantly.
    - Fast but less reliable.

Functions of UDP:
    - Suitable for real-time applications (e.g. video streaming)
    - DNS
    - VPN

Both UDP and TCP are layer 4 protocols.

## OSI Model (Open Systems Interconnection Model)

### Why do we need a communication model?
- A communication model provides a standard framework that simplifies the way devices and applications communicate over a network. 
- Without a standard model, applications must understand the underlying network i.e. we would have to have different versions of the applicaton for Wifi, ethernet, fiber etc. 
- Upgrading network equipment is difficult without a standard model.
- Innovations can happen in each layer independantly, without affecting the entire system (Like upgrading an engine without having to having to redesign the whole system), leading to faster and efficient improvements.

### 7 Layers of the OSI Model
- Application: End user layer (Network services are given directly to applications); HTTP, FTP, IRC, SSH, DNS.
- Presentation: Syntax user Layer (Data is translated to a readable format and where encryption is handled); SSL, SSH, IMAP, FTP, MPEG, JPEG.
- Session: Synch & send to port (Manages sessions between different applications); API's, Sockets, Winsock.
- Transport: End to end connections and data integrity is managed; TCP, UDP.
- Network: Routing and forwarding of data packets are managed; IP, ICMP, IPSec, IGMP.
- Data Link: Node to node transfer and error detection; Frames, Ethernet, PPP, Switch, Bridge.
- Physical: Physical connection between devices; Coax, Fibre, Wireless, Hubs, Repeaters.

#### Layer 1 - Physical Layer
Transmits raw bit stream over a physical medium (Deals with the hardware connection between the cables, switches and network interface cards). There is no device addressing here. All data is processed by all devices (Like shouting in a room without saying any names and everyone hears it).

#### Layer 2 - Data Layer
Provides node to node data transfer and detects, possibly corrects errors that may occur in the Physical Layer. Ensures that data is transferred correctly between adjacent network nodes (Like a traffic cop that ensures data packets are sent and received correctly between different network nodes). At layer one, everything is a mess, data layer puts everything into frames, where its actually organised (like envelopes).

Components include Mac addresses, switches and bridges.

#### Layer 3 - Network Layer
Responsible for determining how data is sent to a recipient. Manages packet forwarding including routing through intermediate routers. Data in this layer are organised into packets (Like little parcels that carry data from one device to another, IP addresses handle where packets go to and routers are the components that direct data packets along the best path).

Components include IP addresses and routers.

#### Layer 4 - Transport Layer
Responsible for providing reliable data transfer services to the upper layers (Like a delivery service that ensures your data parcels arrive safely and in the right sequence).

Components include TCP and UDP.

#### Layer 5 - Session
Manages, establishes, maintains and terminates connections (Similar to logging in, staying logged in and logging out).

Components include session management protocols.

#### Layer 6 - Presentation
Sometimes known as the syntax layer. Translates data between the application layer and the network. Ensures data is in a usable format.

Components include encryption and data formatting.

#### Layer 7 - Application
Provides network services directly to applications. Known as the end user layer where everything happens that we interact with. Handles tasks like web browsing, file transfer and emails.

Components include HTTP, FTP, SMTP.

### TCP/IP Model
Backbone of the internet. A condensed format of the OSI model. Only 4 layers:
- Application Layer
- Transport Layer
- Internet Layer
- Network Access Layer

## DNS (Domain Name System)
Low level networking only understands the IP addresses to identify a host or a machine. DNS allows us to keep track of websites and hosts by name rather than by IP address (Similar to a contacts list, we know the name, not the number).

### DNS Components: Nameservers and Zone Files
- Nameservers: Crucial for DNS functionality. Load DNS settings and configurations and respond to queries from clients or other servers about domain names. There are two types:
    - Authoritative Name Servers: Hold the actual DNS records. Provide the definitive answer when queried such as the IP address for the domain name.
    - Recursive Name Servers: Do not hold the final answer, they query other servers on behalf of the client to find the correct DNS record. They also cache the informaton they retreive to speed up future queries.

To find the name servers of a certain domain, we use the `dig ns example.com` command which gives a detailed output, for a shorter output, we can use `dig +short ns example.com`.

- Zone files: Stored inside the name servers. Store information about the domain. Help nameservers answer queries about how to get to a domain if the name server does not know the answer directly. Organise your DNS information in a readable and manageable way.

### DNS Components: Records
A zone file is comprised of multiple resource records. Each record contains information about hosts, name servers, and various other resources. 

Components of a resource record include 
- Record name: The domain name being queried.
- TTL: Indicates how long the record is valid before a refresh is required.
- Class: Namespace of the record information
- Type: Type of record (A or MX or AAAA etc)
- NS: Name server record.
- Data: Actual information corresponding to the record type. Like IP address for an A record.

#### Types of DNS Records
- A: Maps a domain name to an IPv4 address.
- AAAA: Maps a domain name to an IPv6 address.
- CNAME: Alias of one name to another. It allows you to point multiple domain names to the same address.
- MX: Specifies the mail server responsible for receiving email for the domain. Include a priority value (When you have multiple mail servers that are specified, the priority determines the order in which servers are tried. Low values are higher priority).
    - Crucial for making sure emails are sent to the correct mail servers, ensuring email delivery is reliable.
- TXT: Allows domain administrators to insert any text into DNS. Commonly used for verification purposes and to hold SPF (Sender policy framework) data.

### How does DNS work?
- DNS Resolution: The process of converting domain names to IP Addresses. Involves multiple steps and servers.
- DNS Hierarchy and Distribution:
    - DNS Root (The Boss): Top of the hierarchy. Does not keep details about specific domains, rather it keeps high level information on where to find the top level domains underneath it.
    - Top Level Domain: .com, .net, .gov. These are like calling your department heads. Each TLD stores information about domains within its scope. 
    - Authoritative Name servers: Like managers who oversee specific teams. Each authoritative name server hosts zones for domains, meaning they have the detailed DNS records for those domains.
    - Domain: Each domain has a zone and a zone file. This zone is like a team within a department and the zone file is a detailed list of records for that domain. This is where specific information like IP addresses, mail servers and domains are stored.

#### Domain Registrar vs DNS Hosting Provider
- Registrar: Purchase and register domains. Have relationships with TLD registries for various TLDs. Communicates with TLD registries to manage domain registration. E.g. GoDaddy, Route 53, Cloudflare.

- DNS Hosting Provider: Operates DNS Nameservers that hosts DNS zones. Allow you to manage DNS records within these zones. E.g. Draft Three, Hosting zone etc.

When you purchase a domain, you need DNS zone to be hosted on a DNS name server. The process varies, depending on if the DNS hosting provider is the same as the registrar. If they are the same, the DNS zone is automatically created and hosted. If they are different, you need to provide the name server information on where the DNS zone is already hosted. The information is configured separately.

#### DNS Query Process
The client (your computer) wants to visit a .com website. Here is the process:
- First the local caches are checked and the host file `/etc/hosts` to see if it already knows the IP address. If it is found, no need to go further.
- If the IP address isn't cached locally, the client sends a query to the configured DNS Resolver. The DNS Resolver checks its own cache. If found, it returns the result to the client and does not go further.
- The DNS Resolver asks the Root server for the .com TLD. The root server responds with the address of the .com registry name server.
- The DNS resolver queries the .com name server to find the authoritative name server. The .com name server responds with an address for the authoritative name server.
- The resolver then asks the authoritative name server for the DNS records of the website. The authoritative name server responds with the , including the IP address. The resolver caches this for next time and returns the DNS record to the client.

### Network Debugging Tools
- `nslookup google.com` - Basic DNS Query tool. Can be used to look up information about DNS records for the specified domain.
- `dig google.com` - Advanced DNS Query tool. Much more detailed for querying a DNS.

### /etc/hosts File
`/etc/hosts` is a local file found on Linux systems which map domain names to IP Addresses. Takes precedence over DNS. Useful for testing, development and troubleshooting.

You first open the file in a tect editor and type in the IP address, followed by the hostname you wish to give it.

## Routing

### What is Routing?
The process of determining the paths for data to travel across networks (Like a GPS for data). Ensures data reaches its destination efficiently. Fundamental for internet functionality.

### How routing works
Routers determine the best path. Use routing tables to make decisions. 

### Static vs Dynamic Routing
Static Routing is where routes are manually set up by network admins. Have a set map of instructions to follow. Reliable but does not adapt well when routes change. Have to be manually updated. Simple but not scalable (can be a headache if network traffic grows).

Dynamic routing uses algorithms and complex protocols to find the best route for data. Flexible and adapts to network changes. Adjusts routes based on network conditions. Scalable and adaptable, suitable for large complex networks.

### Common Routing Protocols
Routing Protocols: Automate the process of determining the best route for data to travel across a network. Enhance network efficiency. Automate route updates and improve network resilience by finding alternative routes if one goes down. Common routing protocols:
- OSPF: Open Shortest Path First. Finds the shortest path for data to travel. Fast conversions (quickly recalculates routes when there are changes in the network)
- BGP: Border Gateway Protocol. Routes data between different autonomous systems (Large networks managed by single organisations). Uses path vector mechanism (It maintains the path formation that gets updated dynamically as the network topology changes). Allows network admins to define routing policies based on various attributes, providing a better control on how traffic flows through the network.

## Subnetting and CIDR
- Subnetting: Dividing a network into smaller networks. Improves network management and efficiency.
- CIDR (Classless Inter-Domain Routing): Method for allocating IP addresses and routing IP packets.

### Subnets and Host Ranges
Subnetting helps us determine which part is network portion and which part is host portion. To calculate the host range, we take the subnet mask away from 32. The rest will be the network range.

For example, 192.168.1.0/26:
- Host range: 32 - 26 = 6
- Network range: 26

Therefore, total host addresses are 2^6 = 64 but two will be reserved for the broadcast address and the network address, meaning there are 62 usable host addresses / IP addresses.

Another example is `255.255.255.0`. The host portion is 8 bits as the last number is a zero, therefore, the total host addresses are 2^8.

The host portion of `255.0.0.0` is 24 bits. Therefore the total number of host addresses will be 2^24.

### NAT (Network Address Translation)
Translates private IP addresses to a public IP address. Facilitates communication between internal network and the internet. E.g. you have a laptops at home with private IP addresses, the NAT would give it a public IP address.

The NAT process:
- Internal devices use private IP addresses.
- Router translate private IP addresses to public IP.
- Facilitates communication with external networks.

Types of NAT:
- Static NAT: Maps a single private IP address to a single public IP address. Useful if you have a device that needs to be accessible from the internet with the same IP at all time.
- Dynamic NAT: Maps a private IP address to one of many public IP addresses from a pool. A public IP address is assigned only when it needs to communicate with the internet. Once done, it goes back into the pool for someone else to use.
- PAT (Port Address Translation): Super efficient. Allows multiple devices on the local network to be mapped to a single public IP address but with different port numbers.

## Troubleshooting
- `ping google.com`: Used to test any connectivity between devices.
- `traceroute google.com`: Tracks the path your data takes to reach a certain destination.
- `nslookup google.com`: Basic tool for querying DNS.