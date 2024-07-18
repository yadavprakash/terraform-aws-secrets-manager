# Terraform-aws-secrets-manager

# Terraform AWS Cloud secrets-manager Module

## Table of Contents
- [Introduction](#introduction)
- [Usage](#usage)
- [Examples](#examples)
- [License](#license)
- [Author](#Author)
- [Inputs](#inputs)
- [Outputs](#outputs)

## Introduction
This Terraform module creates an AWS Elastic Compute Cloud (EC2) along with additional configuration options.
## Usage
To use this module, you should have Terraform installed and configured for AWS. This module provides the necessary Terraform configuration for creating AWS resources, and you can customize the inputs as needed. Below is an example of how to use this module:

# Examples

# Example: binary

```hcl
# Create EC2 instances
module "secrets_manager" {

  source      = "git::https://github.com/yadavprakash/terraform-aws-secrets-manager.git?ref=v1.0.0"
  name        = local.name
  environment = local.environment

  secrets = [
    {
      name          = "secret-binary-1"
      description   = "This is a binary secret"
      secret_binary = "ssh-rsa /+ZHJ4gx0gB8yQ/JWPhG1Xi2AWrMqfkidHOh5cp/H+sXYAY8nHzRFfirfSk8o8i4WIlq/vSgD47xHID0JqOOugkN96fBY4/PbvoI6UfPFDGQxfE7LaqGsPf2QZcEJlYxK3f+io/uHDKrq6Q5KnZw2+DdsBxuDfM1BlJqoWRfmcB9wKPWBvm9xMUVm8T2BIcwWikgNuzssy6p63ab7HOzCyl4i7y8V4v8ouIHDM5QA29oVLHz40Nc0JS6ahVQta4JEOHUTf3hgvw9vCAWyyjlJScLSPyQtLXTuBh2FbtG9YouiDv1SszFHStYPvWdq+6CQY5bWfzqyVXZ9lqQhHUkOaW0FJbGGfBMmwQ5WO15925OF53YgtltwSBb9SIF4k9fHjDJ9YUr4bSiIB6oDwoJmWGjS9eI8pxdTAgJ4+IXj+F/Q+AxtDiRsSUKRp2EhIoxxpy+xXMZjGyMDCSLtntzu8yF3SMiZewpR7dWZ8PzDWY7hei3M6kH6BNAy0SX9GRbT3JwGar3OilqZOoCfjjDcakgFDc1vcZnHwBarXnXP520D1hXxP+TCiemAhcFugp7FHAQdhs4+cYk3hJexpU3+SQxizoSkmd7JszO5YlJUtd9k93Q4wWnTk4rmukIJWFsGX8R9Uhb14J0mWDZAvuldnpaO3ASInl2o7r8CvQGcAavnAhBOWHs6AoSUX4ZMG0pk41sM7r7EgKsPG2J5aCpnI9Ht1od7UGaCBtcQv2yZVWrGT1yRJVwGi5Fk+IemFqbIzd5I1HldZvouvQ7Qy5Ezba2y8aYbKY9bvA4nqcCH9eA38671+Ykho/3LpZ5tLt120XGnBfMhMqNtHewzhtdv4y39iEFa+AFa5MXxx7uJe5EcoT/z3WXGIWaC9oIOLpedhsrDyKOvrzwcQ3r+PF6cZuskAaM0j/DgAVmwFke0Iqz2Blq6BnDBmTzXS5yOqr2jebNbFQq3btM6m5zUYTRFkJ/fYBL8nujkPJtE2b1PFIPKX2SDMhIlLcH9SKxlAOxzmF7xu0LsAQENtSawcm3rIZzuBJsV2IlaBuAPP2c01k6upc6VXoMScWZ3a/RZTfmRLPiumkrsmL5xTyK8P4qohUGzPAXWz8Aq0GrHjbu7MPveXiVstFBhtVzeq5G4O2A+BqIu9Paq/lKF9AhQEaM6Ipjo8fTQ1yJIjjj6mCyL51b1cLd7NsKh50WCJBYArhV+5uUTxw9Qih+nvITHoF7q8lNfigVMaACbWqHpE0kMGPqNXhXhtXPhTkMoc4BPBS4aBaVdFqrp6cxGwVsfHOrsk8L1gzuOu8ovjgBfNdcdHGFB4D9joJ test-ssh-key"
    },
    {
      name                    = "secret-binary-2"
      description             = "Another binary secret"
      secret_binary           = "ssh-rsa /+ZHJ4gx0gB8yQ/JWPhG1Xi2AWrMqfkidHOh5cp/H+/vSgD47xHID0JqOOugkN96fBY4/PbvoI6UfPFDGQxfE7LaqGsPf2QZcEJlYxK3f+io/uHDKrq6Q5KnZw2+DdsBxuDfM1BlJqoWRfmcB9wKPWBvm9xMUVm8T2BIcwWikgNuzssy6p63ab7HOzCyl4i7y8V4v8ouIHDM5QA29oVLHz40Nc0JS6ahVQta4JEOHUTf3hgvw9vCAWyyjlJScLSPyQtLXTuBh2FbtG9YouiDv1SszFHStYPvWdq+6CQY5bWfzqyVXZ9lqQhHUkOaW0FJbGGfBMmwQ5WO15925OF53YgtltwSBb9SIF4k9fHjDJ9YUr4bSiIB6oDwoJmWGjS9eI8pxdTAgJ4+IXj+F/Q+AxtDiRsSUKRp2EhIoxxpy+xXMZjGyMDCSLtntzu8yF3SMiZewpR7dWZ8PzDWY7hei3M6kH6BNAy0SX9GRbT3JwGar3OilqZOoCfjjDcakgFDc1vcZnHwBarXnXP520D1hXxP+TCiemAhcFugp7FHAQdhs4+cYk3hJexpU3+SQxizoSkmd7JszO5YlJUtd9k93Q4wWnTk4rmukIJWFsGX8R9Uhb14J0mWDZAvuldnpaO3ASInl2o7r8CvQGcAavnAhBOWHs6AoSUX4ZMG0pk41sM7r7EgKsPG2J5aCpnI9Ht1od7UGaCBtcQv2yZVWrGT1yRJVwGi5Fk+IemFqbIzd5I1HldZvouvQ7Qy5Ezba2y8aYbKY9bvA4nqcCH9eA38671+Ykho/3LpZ5tLt120XGnBfMhMqNtHewzhtdv4y39iEFa+AFa5MXxx7uJe5EcoT/z3WXGIWaC9oIOLpedhsrDyKOvrzwcQ3r+PF6cZuskAaM0j/DgAVmwFke0Iqz2Blq6BnDBmTzXS5yOqr2jebNbFQq3btM6m5zUYTRFkJ/fYBL8nujkPJtE2b1PFIPKX2SDMhIlLcH9SKxlAOxzmF7xu0LsAQENtSawcm3rIZzuBJsV2IlaBuAPP2c01k6upc6VXoMScWZ3a/RZTfmRLPiumkrsmL5xTyK8P4qohUGzPAXWz8Aq0GrHjbu7MPveXiVstFBhtVzeq5G4O2A+BqIu9Paq/lKF9AhQEaM6Ipjo8fTQ1yJIjjj6mCyL51b1cLd7NsKh50WCJBYArhV+5uUTxw9Qih+nvITHoF7q8lNfigVMaACbWqHpE0kMGPqNXhXhtXPhTkMoc4BPBS4aBaVdFqrp6cxGwVsfHOrsk8L1gzuOu8ovjgBfNdcdHGFB4D9joJ test-ssh-key-2"
      recovery_window_in_days = 7
    }
  ]
}
```

This example demonstrates how to create various AWS resources using the provided modules. Adjust the input values to suit your specific requirements.

# Example: complete

```hcl
module "secrets_manager" {
  source      = "git::https://github.com/yadavprakash/terraform-aws-secrets-manager.git?ref=v1.0.0"

  name        = local.name
  environment = local.environment
  secrets = [
    {
      name                    = "secret-11"
      description             = "My secret 1"
      recovery_window_in_days = 7
      secret_string           = "This is an example"
    },
    {
      name                    = "secret-12"
      description             = "My secret 2"
      recovery_window_in_days = 7
      secret_string           = "This is another example"
    }
  ]
}
```

# Example: key-value

```hcl
module "secrets_manager" {
  source      = "git::https://github.com/yadavprakash/terraform-aws-secrets-manager.git?ref=v1.0.0"

  name        = local.name
  environment = local.environment
  secrets = [
    {
      name        = "secret-kv-1"
      description = "This is a key/value secret"
      secret_key_value = {
        key1  = "value1"
        key2  = "value2"
        key3  = "value2"
        key4  = "value2"
        key5  = "value2"
        key6  = "value2"
        key7  = "value2"
        key8  = "value2"
        key89 = "value2"

      }
      recovery_window_in_days = 7
    },
    {
      name        = "secret-kv-2"
      description = "Another key/value secret"
      secret_key_value = {
        username = "user"
        password = "topsecret"
      }
      recovery_window_in_days = 7
    },
  ]
}
```

## Examples
For detailed examples on how to use this module, please refer to the [examples](https://github.com/yadavprakash/terraform-aws-secrets-manager/tree/master/_example) directory within this repository.

## License
This Terraform module is provided under the **MIT** License. Please see the [LICENSE](https://github.com/yadavprakash/terraform-aws-secrets-manager/blob/master/LICENSE) file for more details.

## Author
Your Name
Replace **MIT** and **yadavprakash** with the appropriate license and your information. Feel free to expand this README with additional details or usage instructions as needed for your specific use case.


<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.6.1 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 5.21.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 5.21.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_labels"></a> [labels](#module\_labels) | git::https://github.com/yadavprakash/terraform-aws-labels.git | v1.0.0 |

## Resources

| Name | Type |
|------|------|
| [aws_secretsmanager_secret.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret) | resource |
| [aws_secretsmanager_secret_rotation.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret_rotation) | resource |
| [aws_secretsmanager_secret_version.sm-sv](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret_version) | resource |
| [aws_secretsmanager_secret_version.sm-svu](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret_version) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_attributes"></a> [attributes](#input\_attributes) | Additional attributes (e.g. `1`). | `list(any)` | `[]` | no |
| <a name="input_enable_rotation"></a> [enable\_rotation](#input\_enable\_rotation) | Determines whether secret rotation is enabled | `bool` | `false` | no |
| <a name="input_enabled"></a> [enabled](#input\_enabled) | Flag to control the vpc creation. | `bool` | `true` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| <a name="input_label_order"></a> [label\_order](#input\_label\_order) | Label order, e.g. `name`. | `list(any)` | <pre>[<br>  "name",<br>  "environment"<br>]</pre> | no |
| <a name="input_managedby"></a> [managedby](#input\_managedby) | ManagedBy, eg 'yadavprakash' | `string` | `"yadavprakash"` | no |
| <a name="input_name"></a> [name](#input\_name) | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |
| <a name="input_recovery_window_in_days"></a> [recovery\_window\_in\_days](#input\_recovery\_window\_in\_days) | Specifies the number of days that AWS Secrets Manager waits before it can delete the secret. This value can be 0 to force deletion without recovery or range from 7 to 30 days. | `number` | `30` | no |
| <a name="input_replica"></a> [replica](#input\_replica) | Configuration block to support secret replication | `map(any)` | `{}` | no |
| <a name="input_repository"></a> [repository](#input\_repository) | Terraform current module repo | `string` | `"https://github.com/yadavprakash/terraform-aws-secrets-manager"` | no |
| <a name="input_rotation_lambda_arn"></a> [rotation\_lambda\_arn](#input\_rotation\_lambda\_arn) | Specifies the ARN of the Lambda function that can rotate the secret | `string` | `""` | no |
| <a name="input_rotation_rules"></a> [rotation\_rules](#input\_rotation\_rules) | A structure that defines the rotation configuration for this secret | `map(any)` | `{}` | no |
| <a name="input_secrets"></a> [secrets](#input\_secrets) | List of secrets to keep in AWS Secrets Manager | `any` | `[]` | no |
| <a name="input_unmanaged"></a> [unmanaged](#input\_unmanaged) | Terraform must ignore secrets lifecycle. Using this option you can initialize the secrets and rotate them outside Terraform, thus, avoiding other users to change or rotate the secrets by subsequent runs of Terraform | `bool` | `false` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_secret_arns"></a> [secret\_arns](#output\_secret\_arns) | Secret arn list |
| <a name="output_secret_ids"></a> [secret\_ids](#output\_secret\_ids) | Secret id list |
| <a name="output_version_id"></a> [version\_id](#output\_version\_id) | The unique identifier of the version of the secret. |
<!-- END_TF_DOCS -->