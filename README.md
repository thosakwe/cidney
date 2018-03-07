# cidney
Vain attempt at a distributed file system in Dart. The name "Cidney" is dervied from "CDN."

The concept is simple: the root Cidney server is a load balancer that delegates traffic to an infinite number of child server. The root server never stores files; only the child servers do.

In addition to functioning as a load balancer, the root server acts as a simple database. It keeps tracks of which instances are hosting files (or which portions of a file), and seamlessly streams them out to clients.

In reality, larger CDN's will need more than one root server as load increases. Thus, root servers support storing file information in databases, so that the failure of one server will not lead to the downing of the entire CDN.
