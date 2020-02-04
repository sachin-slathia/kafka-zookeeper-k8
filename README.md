Project Title :-
This configuration is for creating cassandra cluster statefulset in kubernetes and also this configuration is for creating dynamic provision of volumes for pod when you are using baremetal that is own vm's. You can create new replicas of cassandra also and descale it.

Prerequisites:-
kubectl installed on your machine from  where you want to trigger commands
kubectl is configured with your cluster.

Deployment:-
Just see the storage class you are using i am using openebs for provision of dynamic volumes for my pods. If you on cloud or minikube there are provisioners for them. You can use them.

Create cluster:-
kubectl create -f cassandra-service.yaml -f cassandra-statefulset.yaml 

Verify cluster:-
kubectl exec -it  cassandra-0 nodetool status

Scale up cluster:-
kubectl scale statefulset cassandra --replicas=4

Verify cluster:-
kubectl exec -it  cassandra-0 nodetool status


