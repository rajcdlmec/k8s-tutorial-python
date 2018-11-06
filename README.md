# Kubernetes 101 for Python Programmers
Welcome to the [__Kubernetes 101 for Python Programmers__](https://2018.pycon.ca/talks/talk-PC-51523/) tutorial. This repository contains a [sample Django application](django-poll-project) that can be deployed into a Kubernetes (abbreviated k8s) cluster using the included k8s spec files. 

The application can be launched on your local laptop in development mode using a [Minikube](https://kubernetes.io/docs/setup/minikube/) k8s cluster. We have also included [Terraform](https://www.terraform.io/) scripts that can help you spin up a k8s cluster in [Amazon cloud EKS](https://aws.amazon.com/eks/) to highlight a few integration points between your k8s resident application and the underlying cloud provider. 

You can also download the [slides](tutorial/kubernetes101forPython.pdf) accompanying the code. We will add the link to the accompanying tutorial video when it becomes available. 

# Your Kubernetes Learning Plan 

1. Browse through the [slides](tutorial/kubernetes101forPython.pdf) in this tutorial to get a condensed start to the concepts around Docker and k8s, and understanding how a Python/Django application can live inside k8s.
2. If you want to try out k8s without installing anything or creating a cloud provider account, spend time on the official [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/); these include interactive tools to let you actually play with a k8s cluster without spinning one up on your own machine/cloud account:
    *   [Create a k8s cluster](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-interactive/)
    *  [Deploy a nodejs app](https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-app/deploy-interactive/)
    *  [Other basic k8s operations such as scaling, rolling versions etc.](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
3. If you are ready to take the next step - and commit to installing a k8s-all-in-one VM on your PC, head over to the [Minikube installation page](https://kubernetes.io/docs/tasks/tools/install-minikube/) to install the single-node k8s instance on your PC. This is useful for development work. You can then try to deploy the django application [included](django-poll-project/) in this tutorial on your local PC k8s cluster.
4. The next step is moving toward Kubernetes for production. We strongly recommend creating a cloud-provider-managed k8s cluster unless you have a strict requirement for an in-house production-grade [do-it-yourself k8s cluster](https://kubernetes.io/docs/setup/scratch/).  
5. We have included [Terraform scripts](aws-k8s-pgdb-with-terraform/aws-kubernetes) to create a [Amazon cloud EKS](https://aws.amazon.com/eks/) cluster. You will need AWS credentials and a credit card - __warning__: running a k8s cluster is not cheap (see our [slides](tutorial/kubernetes101forPython.pdf) for an example).

# What is Where?
Here are links to key resources in this repository
* [Slides](tutorial/kubernetes101forPython.pdf) for the tutorial
* [Minikube installation instructions](https://kubernetes.io/docs/tasks/tools/install-minikube/) 
* [Docker setup and commands](django-poll-project/poll-app-README.md) to interact with minikube
* [Amazon AWS EKS k8s setup](aws-k8s-pgdb-with-terraform/aws-kubernetes/aws-k8s-README.md) - you will need an AWS account (credit card required).
* [Amazon AWS RDS setup](aws-k8s-pgdb-with-terraform/aws-kubernetes/aws-k8s-README.md)  to create a simple postgres database instance - you will need an AWS account (credit card required). We separated the terraform scripts for EKS and RDS setup because you probably don't want to create and tear down your production database and EKS cluster at the same time!



# FAQ
1. Why did you choose AWS EKS and not Google or Azure as the managed k8s cluster provider? And why not Flask instead of Django?

_K8s evolved from an internal project in Google, and it is widely believed that the Google cloud managed k8s product is the most polished and easy to use (as of late 2018). Google has also done a phenomenal job of creating documentation for Python developers using their k8s product (see: [a Python Flask app on Google cloud k8s](https://cloud.google.com/python/tutorials/bookshelf-on-kubernetes-engine)).

We decided to go with AWS EKS for this tutorial to complement Google's [Flask example]((https://cloud.google.com/python/tutorials/bookshelf-on-kubernetes-engine)). In addition, there is a large installed base of AWS users who may find this tutorial helpful.
    

# LICENSE
This repository is licensed under the Apache License - see the [LICENSE.md](LICENSE.md) file for details

Copyright 2018 BigBitBus Inc. http://bigbitbus.com

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.