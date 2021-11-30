# EC2-CFn Templates

図のような構成の HTTPS 化した EC2 の Coudformation テンプレート<be/><br/>

![overview](./public/overview.jpg)
<br/>

## Getting started

Route53 でドメイン（このチュートリアルでは souhub-example.com）を取得し、NameSpace を作成。<br/>
ACM で証明書発行。<br/>
以下のコマンド実行後、Route53 に CNAME レコードを作成（ACM のページから手動で）。<be/>

```
$ make acm
```

<br/>

VPC、Subnet、Internet Gateway、Route など作成

```
$ make vpc
```

<br/>
SecurityGroup 作成

```
$ make sg
```

<br/>
EC2 インスタンス作成

```
$ make ec2
```

<br/>
ALB、TargetGroup、Lisner 作成

```
$ make alb
```

<br/>
手動で Route53 で Alias に ALB の DNS を選択し、[www.souhub-example.com](https://www.souhub.example.com)と紐づける
