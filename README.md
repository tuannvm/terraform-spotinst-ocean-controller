# Spot Ocean Controller Terraform Module

A Terraform module to install Ocean Controller.

## Table of Contents

- [Usage](#usage)
- [Examples](#examples)
- [Resources](#resources)
- [Requirements](#requirements)
- [Providers](#providers)
- [Inputs](#inputs)
- [Outputs](#outputs)
- [Documentation](#documentation)
- [Getting Help](#getting-help)
- [Community](#community)
- [Contributing](#contributing)
- [License](#license)

## Usage

```hcl
module "ocean-controller" {
  source = "spotinst/ocean-controller/spotinst"

  # Credentials.
  spotinst_token   = var.spotinst_token
  spotinst_account = var.spotinst_account

  # Configuration.
  cluster_identifier = var.cluster_identifier
}
```

## Examples

- [Simple Installation](https://github.com/spotinst/terraform-spotinst-ocean-controller/tree/master/examples/simple-installation)

## Resources

This module creates and manages the following resources:

- kubernetes_secret
- kubernetes_config_map
- kubernetes_service_account
- kubernetes_cluster_role
- kubernetes_cluster_role_binding
- kubernetes_deployment

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.26 |
| kubernetes | >= 1.13.0 |
| null | >= 3.0.0 |

## Providers

| Name | Version |
|------|---------|
| kubernetes | >= 1.13.0 |
| null | >= 3.0.0 |

## Modules

No Modules.

## Resources

| Name |
|------|
| [kubernetes_cluster_role](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/cluster_role) |
| [kubernetes_cluster_role_binding](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/cluster_role_binding) |
| [kubernetes_config_map](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/config_map) |
| [kubernetes_deployment](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/deployment) |
| [kubernetes_secret](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/secret) |
| [kubernetes_service_account](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/service_account) |
| [null_resource](https://registry.terraform.io/providers/hashicorp/null/latest/docs/resources/resource) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| base\_url | Base URL to be used by the HTTP client | `string` | `""` | no |
| cluster\_identifier | Cluster identifier | `string` | n/a | yes |
| controller\_image | Set the Docker image name for the Ocean Controller that should be deployed | `string` | `"spotinst/kubernetes-cluster-controller"` | no |
| controller\_version | Set the Docker version for the Ocean Controller that should be deployed | `string` | `"1.0.73"` | no |
| create\_controller | Controls whether Ocean Controller should be created (it affects all resources) | `bool` | `true` | no |
| disable\_auto\_update | Disable the auto-update feature | `bool` | `false` | no |
| enable\_csr\_approval | Enable the CSR approval feature | `bool` | `false` | no |
| image\_pull\_policy | Image pull policy (one of: Always, Never, IfNotPresent) | `string` | `"IfNotPresent"` | no |
| image\_pull\_secrets | List of references to secrets in the same namespace to use for pulling the image | `list(string)` | `[]` | no |
| module\_depends\_on | List of modules or resources this module depends on | `list(any)` | `[]` | no |
| proxy\_url | Proxy server URL to communicate through | `string` | `""` | no |
| spotinst\_account | Spot account ID | `string` | n/a | yes |
| spotinst\_token | Spot Personal Access token | `string` | n/a | yes |

## Outputs

No output.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Documentation

If you're new to [Spot](https://spot.io/) and want to get started, please checkout our [Getting Started](https://docs.spot.io/connect-your-cloud-provider/) guide, available on the [Spot Documentation](https://docs.spot.io/) website.

## Getting Help

We use GitHub issues for tracking bugs and feature requests. Please use these community resources for getting help:

- Ask a question on [Stack Overflow](https://stackoverflow.com/) and tag it with [terraform-spotinst](https://stackoverflow.com/questions/tagged/terraform-spotinst/).
- Join our [Spot](https://spot.io/) community on [Slack](http://slack.spot.io/).
- Open an issue.

## Community

- [Slack](http://slack.spot.io/)
- [Twitter](https://twitter.com/spot_hq/)

## Contributing

Please see the [contribution guidelines](CONTRIBUTING.md).

## License

Code is licensed under the [Apache License 2.0](LICENSE).
