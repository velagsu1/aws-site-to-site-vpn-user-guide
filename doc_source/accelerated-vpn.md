# Accelerated Site\-to\-Site VPN connections<a name="accelerated-vpn"></a>

You can optionally enable acceleration for your Site\-to\-Site VPN connection\. An accelerated Site\-to\-Site VPN connection \(accelerated VPN connection\) uses AWS Global Accelerator to route traffic from your on\-premises network to an AWS edge location that is closest to your customer gateway device\. AWS Global Accelerator optimizes the network path, using the congestion\-free AWS global network to route traffic to the endpoint that provides the best application performance \(for more information, see [AWS Global Accelerator](https://aws.amazon.com/global-accelerator/)\)\. You can use an accelerated VPN connection to avoid network disruptions that might occur when traffic is routed over the public internet\.

When you create an accelerated VPN connection, we create and manage two accelerators on your behalf, one for each VPN tunnel\.

Acceleration is only supported for Site\-to\-Site VPN connections that are attached to a transit gateway\. Virtual private gateways do not support accelerated VPN connections\.

Accelerated VPN connections are supported in the following AWS Regions: US East \(N\. Virginia\), US East \(Ohio\), US West \(Oregon\), US West \(N\. California\), Europe \(Ireland\), Europe \(Frankfurt\), Europe \(London\), Europe \(Paris\), Asia Pacific \(Singapore\), Asia Pacific \(Tokyo\), Asia Pacific \(Sydney\), Asia Pacific \(Seoul\), Asia Pacific \(Mumbai\), and Canada \(Central\)\.

**Topics**
+ [Enabling acceleration](#accelerated-vpn-enabling)
+ [Pricing](#accelerated-vpn-pricing)

## Enabling acceleration<a name="accelerated-vpn-enabling"></a>

By default, when you create a Site\-to\-Site VPN connection, acceleration is disabled\. You can optionally enable acceleration when you create a new Site\-to\-Site VPN attachment on a transit gateway\. For more information, see [Creating a transit gateway VPN attachment](create-tgw-vpn-attachment.md)\.

You cannot enable or disable acceleration for an existing Site\-to\-Site VPN connection\. Instead, you can create a new Site\-to\-Site VPN connection with acceleration enabled or disabled as needed\. Then, configure your customer gateway device to use the new Site\-to\-Site VPN connection and delete the old Site\-to\-Site VPN connection\. 

NAT\-traversal \(NAT\-T\) is required for an accelerated VPN connection and is enabled by default\.

Accelerated VPN connections use a separate pool of IP addresses for the tunnel endpoint IP addresses\. The IP addresses for the two VPN tunnels are selected from two separate [network zones](https://docs.aws.amazon.com/global-accelerator/latest/dg/introduction-components.html)\.

## Pricing<a name="accelerated-vpn-pricing"></a>

Hourly charges apply for a Site\-to\-Site VPN connection\. For more information, see [AWS VPN pricing](https://aws.amazon.com/vpn/pricing/)\. When you create an accelerated VPN connection, we create and manage two accelerators on your behalf\. You are charged an hourly rate and data transfer costs for each accelerator\. For more information, see [AWS Global Accelerator pricing](https://aws.amazon.com/global-accelerator/pricing/)\. 