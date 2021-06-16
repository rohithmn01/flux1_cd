# flux1_cd
Demo about flux - GitOps




kubectl create ns flux

install flux CLI 
    brew install fluxctl


fluxctl install \
--git-user=rohithmn01 \
--git-email=rohithmn01@gmail.com \
--git-url=git@github.com:rohithmn01/flux1_cd.git \
--git-path=kubernetes \
--namespace=flux \
--manifest-generation=true --git-branch=main | kubectl apply -f -


kubectl get pods -n flux


Add deploy key to github repo
Get the public key
    fluxctl identity --k8s-fwd-ns flux


Synchronize by force
    fluxctl sync --k8s-fwd-ns flux
