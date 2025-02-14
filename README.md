# DNS client / server
DNS query equivelent to function of Windows command prompt 'nslookup' command or Unix 'dig' command, motivations were to purse understanding the DNS protocol from the a transport layer perspective

Important Concepts:

1. Schema and implementation towards the solution involved: research DNS Query Message Structure (RFC 1035) and packet manipulation (WireShark) packet analysis (testing)
2. Solution was mainly composed use of: DNS Web Sockets (sockets library)
  
  2.1. Hexadecimal to bit /bytes conversion and manipulation
  
  2.2. Working with DNS Query packet metadata
  
  2.3. Parse DNS query message for answer section A record (import binascii)

Note: several .py files are written to demonstrate prototyping the implementation. The final solution is running: mydns-solution.py

How to Run (using pipelines, and args):
Usage: python mydns.py <domain_name_to_query> <root_dns_ip>

The DNS lookup client uses iterative queries to resolve a given domain name. It should be started by typing:
mydns domain-name root-dns-ip 

e.g python mydns.py domain-name root-dns-ip
where domain-name is the domain name (e.g., google.com) to be resolved and root-dns-ip is the IPv4 address (e.g., 202.12.27.33) of a root DNS server on the Internet. The list of current root DNS servers can be found at: https://www.iana.org/domains/root/servers.

example input to run the program: python mydns-solution.py google.com 202.12.27.33

expected output as of 2/14/2025:
Intermediate IP addresses:


192.55.83.30

216.239.34.10

192.178.50.46



 Answer IP: 192.178.50.46
