## **Fleet demo exercise**

The goal of this demo is to deploy differant apps in downstream clusters from a single initial gitRepo.  
In this example, I deployed a [Redis app](https://artifacthub.io/packages/helm/bitnami/redis) and a [WordSmish app](https://github.com/dockersamples/wordsmith).  
I also used the [SUSE Rancher local-path-provisionner](https://github.com/rancher/local-path-provisioner) for PVC to avoid deploying Longhorn in the demo.


So in basics steps, here what you could do to achieve the same:

* Create a local cluster with 2 downstreams.
* Prepare 2 GIT repositories.
  * one called gitops repo to deploy the differant *gitRepo*
  * one called fleet-apps for the *fleet.yaml* applications source, you can off course use one GIT repository per application as well.  Here I used the same one and filter the apps with the ***path*** *key/values*

* In the gitops GIT repository, you define the applications gitRepo[s] and filter the cluster(s) target(s)
* In the fleet-apps/application repositories, you configure the app with the fleet.yaml if needed to make them work on the destination cluster(s).

In my demo, I used Fleet to deploy Helm charts, YAML and [Kustomization](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/)  
Feel free to use whataver you feel confortable with.


