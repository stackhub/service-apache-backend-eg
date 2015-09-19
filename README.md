# Purpose

The sole purpose of this container is to provide the Apache httpd server 
as a simple backend for a load balancer.  

# Usage

Production: *No*
StackEngine Only: *No*

# StackEngine Controller

To launch three (3) of these containers in a resource pool, copy and 
paste the contents of `stack.yml` in the Application Advanced Editor 
and launch it.

# CLI

This container is useful outside the StackEngine ecosystem.  To run it, it is 
necessary to ensure the internal port is 80:

`docker run -d -p :80 stackhub/apache-backend-eg`

`b139cd126fb7        stackhub/apache-backend-eg   "/start.sh"         5 seconds ago       Up 4 minutes        443/tcp, 0.0.0.0:32790->80/tcp   angry_leakey`

Then curl the address:

`curl http://localhost:32790`

and you will see as a response:

`<h1>b139cd126fb7</h1>`

By returning the container hash, you will easily be able to tell which backend
responded in a multicontainer situation such as using the 
[`servcie-haproxy`](http://github.com/stackhub-haproxy) 
for the StackEngine Container Application Center.

# License 

MIT