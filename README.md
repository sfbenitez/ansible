# ansible playbook for install docker and kubeadm

## Set vars
---
File [playbooks/group_vars/all](kubeadm-docker/playbooks/group_vars/all)

```
# Set a admin toker for your cluster
k8s_token: 175fe3.88578757ad352a58
# Unprivileged user to use kubectl
non_root_user: debian
# Master IP where the clusternodes will join
master_bind_node_ip: 10.0.0.8
```
## Set your nodes
File [nodes](kubeadm-docker/nodes)


## Install docker only
---
Set the dockers group with your respectives servers.

```
## Dockeronly scenario
# [dockers]
# pandora ansible_ssh_host=10.0.5.2 ansible_ssh_user=ferrete ansible_become=true
```
And uncomment in [playbooks/site.yml](kubeadm-docker/playbooks/site.yml) dockers block.

```
# - hosts: dockers
#   roles:
#     - docker
```
