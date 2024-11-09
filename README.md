# service-discovery-consul

A Service Discovery implementing Hashicorp Consul using docker

### Commands

**Buld and run the container**

`docker-compose up -d`

**Accessing the container shell**

`docker exec -it consul01 sh`

**Installing "dig" inside the container to run DNS commands**

`apk -U add bind-tools`

**Curl node catalogs**

`curl localhost:8500/v1/catalog/nodes`

**Getting DNS info**

`dig @localhost -p 8600 consul01.node.consul`

---

# Creating a cluster

1. Acessar primeiro datacenter/cluster

   docker exec -it consulserver01 sh
2. Executar o comando para rodar o agent no modo "server"




Ifconfig para localizar o IP da máquina (docker) - usar o inet addr:******

Criar pasta mkdir /etc/consul.d

Criar pasta mkdir /var/lib/consul

Execute o comando:

consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.19.0.2 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
