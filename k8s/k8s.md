# K8s
## Get Namespaces
### kubectl get namespaces
## Details of specific namespace
### kubectl get namespaces grafana-prometheus
## Full details
### kubectl describe namespaces grafana-prometheus
## Create Namespace uwing yaml
### Create yaml file add bellow code 
`

apiVersion: v1

kind: Namespace

metadata:

&nbsp; &nbsp;&nbsp;name: insert-namespace-name-here
`
### Then run kubectl create -f ./my-namespace.yaml
## Create namespace without yaml
### kubectl create namespace insert-namespace-name-here
## Delete namespace
### kubectl delete namespaces insert-some-namespace-name
##  Command to deploy application to k8s cluster
### kubectl create deployment new-proms-proj --image=dasari508201/grafana-prometheus:0.0.1
## Expose service to outside world
### kubectl expose deployment new-proms-proj --type=LoadBalancer --port=8008
## Events that occured 
## What is pod
### Pod is the smallest deployable unit or basic building blocks of Kubernetes that can be managed serve as the unit of scaling. 
### Pods can contain one or multiple tightly coupled containers that are scheduled together on the same node and share the same context, including IP address and port space.
### Pods are designed to be ephemeral and disposable, which means they can be created, destroyed, and replaced easily.
### They are often managed by higher-level controllers like Deployments or StatefulSets, which provide functionalities like replication, scaling, and rolling updates, ensuring the desired number of Pods are running at any given time.
### Each Pod in Kubernetes has its unique IP address, allowing containers within the Pod to communicate with each other using localhost. 
### Pods also share the same lifecycle, so they are scheduled, deployed, scaled, and managed as a single unit.
### Pods are not intended to be accessed directly from outside the cluster. Services are used to expose Pods to other services within or outside the Kubernetes cluster.
### kubectl get pods -o wide
### kubectl get events
### Get available pods:- kubectl get pods
### Get replica set:- kubectl get replicaSet
### Deployment:- kubectl get deployment
### Get service:- kubectl get service
## ReplicaSet
### ReplicaSet is a controller object used to ensure that a specified number of identical Pods are running at all times.
### It's a higher-level abstraction that helps maintain a defined number of Pod replicas, enabling high availability and scalability for applications.
### Key features of ReplicaSets:
### Pods Management: They manage identical Pods based on a template specified within the ReplicaSet definition.
### Scaling: They can scale the number of replicas up or down by adjusting the desired count in the configuration. This allows for easy horizontal scaling of applications.
### Self-Healing: In case a Pod fails or becomes unresponsive, the ReplicaSet ensures that a new Pod is created to replace it, maintaining the desired number of replicas.
### Selectors: ReplicaSets use label selectors to identify the Pods they are responsible for managing. They continuously monitor and reconcile the number of Pods with matching labels.

### Create replicas :- kubectl scale  deployment new-proms-proj --replicas=3
### get replica info:- kubectl get replicaset
### Get replica more info:- kubectl get replicaset -o wide
## Events occured in K8s
### kubectl get events --sort-by=.metadata.creationTimestamp
### Deploying pod with new image version:- kubectl set image deployment new-proms-proj grafana-prometheus=DUMMY:TEST

