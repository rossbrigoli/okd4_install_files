
## Openshift Bootstrap Process

1. The bootstrap machine boots and starts hosting the remote resources required for the master machines to boot. (Requires manual intervention if you provision the infrastructure)

2. The master machines fetch the remote resources from the bootstrap machine and finish booting. (Requires manual intervention if you provision the infrastructure)

3. The master machines use the bootstrap machine to form an etcd cluster.

4. The bootstrap machine starts a temporary Kubernetes control plane using the new etcd cluster.

5. The temporary control plane schedules the production control plane to the master machines.

6. The temporary control plane shuts down and passes control to the production control plane.

7. The bootstrap machine injects OpenShift Container Platform components into the production control plane.

8. The installation program shuts down the bootstrap machine. (Requires manual intervention if you provision the infrastructure)

9. The control plane sets up the worker nodes.

10. The control plane installs additional services in the form of a set of Operators.
