Terraform module which creates DBFS resources on Alibaba Cloud.

terraform-alicloud-dbfs
=====================================================================

English | [简体中文](README-CN.md)

This module is used to create DBFS resources on Alibaba Cloud.

These types of resources are supported:

* [alicloud_dbfs_service_linked_role](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/dbfs_service_linked_role)
* [alicloud_dbfs_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/dbfs_instance)
* [alicloud_dbfs_instance_attachment](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/dbfs_instance_attachment)
* [alicloud_dbfs_snapshot](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/dbfs_snapshot)

## Usage

```hcl
module "example" {
  source                  = "terraform-alicloud-modules/dbfs/alicloud"
  #alicloud_dbfs_service_linked_role
  product_name      = "AliyunServiceRoleForDbfs"
  #alicloud_dbfs_instance
  category          = "standard"
  zone_id           = "cn-beijing-k"
  performance_level = "PL1"
  instance_name     = "tf-test-dbfs"
  size              = 100
  #alicloud_dbfs_instance_attachment
  ecs_id            = "your_ecs_id"
  #alicloud_dbfs_snapshot
  snapshot_name     = "tf-test-dbfs"
  description       = "tf-test-dbfs"
  retention_days    = 30
  force             = false
}
```

## Examples

* [complete example](https://github.com/terraform-alicloud-modules/terraform-alicloud-dbfs/tree/main/examples/complete)

## Notes

* This module using AccessKey and SecretKey are from `profile` and `shared_credentials_file`. If you have not set them
  yet, please install [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) and configure it.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | > = 1.0.11 |
| <a name="requirement_alicloud"></a> [alicloud](#requirement\_alicloud) | > = 1.157.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alicloud"></a> [alicloud](#provider\_alicloud) | > = 1.157.0 |

## Submit Issues

If you have any problems when using this module, please opening
a [provider issue](https://github.com/aliyun/terraform-provider-alicloud/issues/new) and let us know.

**Note:** There does not recommend opening an issue on this repo.

## Authors

Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com).

## License

MIT Licensed. See LICENSE for full details.

## Reference

* [Terraform-Provider-Alicloud Github](https://github.com/aliyun/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs)