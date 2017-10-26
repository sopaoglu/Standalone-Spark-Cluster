The first step is to install docker on your machines.

We assume that you have 4 nodes clusters. 

IP Addresses of our machines are :
Node 1: 192.168.100.100
Node 2: 192.168.100.101
Node 3: 192.168.100.102
Node 4: 192.168.100.102

We select one of them as Manager Node for docker swarm.
For instance; Node 1 is manager node for our cluster.

On Node 1, run following command:

docker swarm init --advertise-addr=192.168.100.100

Now, we can other nodes on our clusters. To do that, 

Run following command on Node 1

docker swarm join-token worker

The result of the command like that

docker swarm join --token SWMTKN-1-31erm2z4d7ffzj1w57ziiqtyx46ptwollw4xqbkqfsdfotqaomsd-5l4xcg4bfvsfsdfufh72qxi0u5snp 192.168.100.100:2377

Copy the result of previous command and paste and run it on Node 2, Node 3 and Node 4.
After running the command, you see message on each node like that

"This node joined a swarm as a worker."

if you run following command on Node 1 machine,

docker node ls

You see list of machines which exists on your cluster

ID              HOSTNAME  STATUS  AVAILABILITY MANAGER STATUS

6v4ddxl3uj... * spark     Ready   Active       Leader

qqhb6uzkb3...   spark1    Ready   Active

wjh0x6n5gd...   spark2    Ready   Active

3kq85vylsd...   spark3    Ready   Active





