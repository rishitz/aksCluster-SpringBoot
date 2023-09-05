## What is it?
This source code is an Spring Boot web application).
 
Tested with
* Docker 19.03
* Ubuntu 19
* Java 8 or Java 11
* Spring Boot 2.2.4.RELEASE
* Maven

For explanation, please visit this article - [Docker and Spring Boot](https://mkyong.com/docker/docker-spring-boot-examples/)

## How to run this?
```bash
$ git clone https://github.com/mkyong/docker-java
$ cd docker-spring-boot
$ mvn clean package
$ java -jar target/spring-boot-web.jar

  access http://localhost:8080

//dockerize

// create a docker image


**Shell Script:**

#!/bin/sh

# This is the shell script for creating AKS cluster, ACR Repo, and a namespace

# Create Resource Group
AKS_RESOURCE_GROUP=aks-rg
AKS_REGION=eastus

# Set Cluster Name
AKS_CLUSTER=aks-cluster

# Set ACR name
ACR_NAME=myacrrepo1996

echo $AKS_RESOURCE_GROUP, $AKS_REGION, $AKS_CLUSTER, $ACR_NAME

# Create Resource Group
az group create --location $AKS_REGION --name $AKS_RESOURCE_GROUP

# Create AKS cluster with two worker nodes
az aks create --resource-group $AKS_RESOURCE_GROUP \
              --name $AKS_CLUSTER \
              --node-count 2

# Create Azure Container Registry
az acr create --resource-group $AKS_RESOURCE_GROUP \
              --name $ACR_NAME \
              --sku Standard \
              --location $AKS_REGION

# Providing required permission for downloading Docker image from ACR into AKS Cluster
az aks update -n $AKS_CLUSTER \
              -g $AKS_RESOURCE_GROUP \
              --attach-acr $ACR_NAME

# Configure Kube Credentials
az aks get-credentials --name $AKS_CLUSTER \
                      --resource-group $AKS_RESOURCE_GROUP

# Create a namespace in AKS cluster for Helm deployment
kubectl create namespace helm-deployment


$ sudo docker build -t spring-boot:1.0 .
// run it
$ sudo docker run -d -p 8080:8080 -t spring-boot:1.0

  access http://localhost:8080
```
