for managed cluster:
For cluster: eksctl create cluster -f eks-cluster.yaml


remember to chnage the subnet setting and give them ipv6 enabled only the private subnets in the ipv6 cluster creation.


------------------
Standard requirements before creating a cluster

all given subnets must be in the same VPC, within the same block of IPs
a sufficient number IP addresses are available, based on needs
sufficient number of subnets (minimum 2), based on needs
subnets are tagged with at least the following:
kubernetes.io/cluster/<name> tag set to either shared or owned
kubernetes.io/role/internal-elb tag set to 1 for private subnets
kubernetes.io/role/elb tag set to 1 for public subnets
correctly configured internet and/or NAT gateways
routing tables have correct entries and the network is functional
NEW: all public subnets should have the property MapPublicIpOnLaunch enabled (i.e. Auto-assign public IPv4 address in the AWS console)
There may be other requirements imposed by EKS or Kubernetes, and it is entirely up to you to stay up-to-date on any requirements and/or recommendations, and implement those as needed/possible.
