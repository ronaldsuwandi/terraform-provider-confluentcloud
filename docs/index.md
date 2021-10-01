---
page_title: "Provider: Confluent Cloud"
subcategory: ""
description: |-
  
---

# Confluent Cloud Provider

Use the Confluent Cloud provider to deploy and manage [Confluent Cloud](https://www.confluent.io/confluent-cloud/) infrastructure. You must provide appropriate credentials to use the provider. The navigation menu provides details about the resources that you can interact with (_Resources_), and a guide (_Guides_) for how you can get started.

-> **Note:** The Confluent Terraform provider is available in an **Early Access Program** for early adopters. Early Access features are introduced to gather customer feedback. This feature should be used only for evaluation and non-production testing purposes or to provide feedback to Confluent, particularly as it becomes more widely available in follow-on preview editions. If you would like to participate in the Early Access Program, [email us](mailto:cflt-tf-access@confluent.io?subject=Request%20to%20join%20the%20Early%20Access%20Program&amp;body=I%E2%80%99d%20like%20to%20participate%20in%20the%20Early%20Access%20Program%20to%20provide%20feedback%21%20My%20Cloud%20Organization%20ID%20is%20%3Cretrieve%20from%20https%3A//confluent.cloud/settings/billing/payment%3E.).  
**Early Access Program** features are intended for evaluation use in development and testing environments only, and not for production use. The warranty, SLA, and Support Services provisions of your agreement with Confluent do not apply to Early Access Program features. Early Access Program features are considered to be a Proof of Concept as defined in the Confluent Cloud Terms of Service. Confluent may discontinue providing preview releases of the Early Access Program features at any time in Confluent’s sole discretion.

## Example Usage

```terraform
# Configure the Confluent Cloud Provider
provider "confluentcloud" {
  username = var.confluent_cloud_api_key    # optionally use CONFLUENT_CLOUD_API_KEY env var
  password = var.confluent_cloud_api_secret # optionally use CONFLUENT_CLOUD_API_SECRET env var
}
# Create the resources
```

## Enable Confluent Cloud Access

Confluent Cloud requires API keys to manage access and authentication to different parts of the service. An API key consists of a key and a secret. You can create and manage API keys by using either the [Confluent Cloud CLI](https://docs.confluent.io/ccloud-cli/current/index.html) or the [Confluent Cloud Console](https://confluent.cloud/). Learn more about Confluent Cloud API Key access [here](https://docs.confluent.io/cloud/current/client-apps/api-keys.html#ccloud-api-keys).

## Provider Authentication

Confluent Cloud Terraform provider allows authentication by using environment variables or static credentials.

### Environment Variables

Run the following commands to set the `CONFLUENT_CLOUD_API_KEY` and `CONFLUENT_CLOUD_API_SECRET` environment variables:

```shell
$ export CONFLUENT_CLOUD_API_KEY="<cloud_api_key>"
$ export CONFLUENT_CLOUD_API_SECRET="<cloud_api_secret>"
```

-> **Note:** Quotation marks are required around the API key and secret strings.

### Static Credentials

You can also provide static credentials in-line directly, or by input variable (do not forget to declare the variables as [sensitive](https://learn.hashicorp.com/tutorials/terraform/sensitive-variables#refactor-database-credentials)):

```terraform
provider "confluentcloud" {
  username = var.confluent_cloud_api_key
  password = var.confluent_cloud_api_secret
}
```

!> **Warning:** Hardcoding credentials into a Terraform configuration is not recommended. Hardcoded credentials increase the risk of accidentally publishing secrets to public repositories.

## Helpful Links/Information

* [Report Bugs](https://github.com/confluentinc/terraform-provider-confluentcloud/issues)

* [Request Features](mailto:cflt-tf-access@confluent.io?subject=Feature%20Request)