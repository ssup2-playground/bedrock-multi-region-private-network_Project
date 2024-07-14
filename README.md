# bedrock-multi-region-private-network

bedrock-multi-region-private-network is a prototyping project that uses multi-region bedrock using a private network rather than a public network.

* [aws-terraform](https://github.com/ssup2-playground/bedrock-cross-region_aws-terraform) : Terraform for network infra and bedrock

## Architecture

<img src="/images/architecture.png" width="600"/>

Architecture for using bedrock API of virginia and oregon region in seoul region

* VPCs between cross-regions are connected through VPC peering
* Client calls bedrock through bedrock runtime VPC endpoint
* Client accesses bedrock runtime vpc endpoint through private hosted zone

## Disable SSL Certificate Vertification

<img src="/images/ssl-disable.png" width="600"/>

* AWS cli : `--no-verfiy-ssl --endpoint-url "https://virginia.runtime.bedrock.in”`
* Python Boto3 : `client(verify=false, endpoint_url=https://virginia.runtime.bedrock.in)`
