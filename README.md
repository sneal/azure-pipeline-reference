# PCF on Azure install & upgrade reference pipeline

This repo contains a reference pipelines for installing and upgrading PCF on Azure.
These instructions assume you already created an
[OpsMan control plane complete with Concourse](https://github.com/pivotal/control-plane).
The pipeline here assumes you're using the new
[Pivotal platform automation tooling](http://docs.pivotal.io/pcf-automation/unreleased/)
which is currently in Alpha.

## Usage

Create a folder for each foundation, for example `sbox`. In that folder create the following files:

- [env.yml](https://docs.pivotal.io/pcf-automation/alpha/task-reference.html#env)
- [auth.yml](https://docs.pivotal.io/pcf-automation/alpha/task-reference.html#auth)

Ensure these the repository and the files are in a private git repository that only
the platform team has access too.

Execute the terraforming-azure templates to configure the IaaS. The Terraform output is needed
to configure the bosh director. You can automatically generate the environment's
`director-vars.yml` using the `terraform-2-director-vars.sh` script.


