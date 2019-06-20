```shell
$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '          "(.*?)"' | sort | uniq -c | sort -nr
# missing a few https://github.com/awsdocs/aws-cloudformation-user-guide/issues/4#issuecomment-503828259
5443 UpdateType
5443 Required
5443 Documentation
4283 PrimitiveType
1493 Type
 448 ItemType
 445 DuplicatesAllowed
 352 PrimitiveItemType

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("UpdateType": ".*?)"' | sort | uniq -c | sort -nr
4030 "UpdateType": "Mutable
1370 "UpdateType": "Immutable
  47 "UpdateType": "Conditional

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("Required": .*?),' | sort | uniq -c | sort -nr
3689 "Required": false
1758 "Required": true

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("DuplicatesAllowed": .*?),' | sort | uniq -c | sort -nr
 313 "DuplicatesAllowed": false
 132 "DuplicatesAllowed": true

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("PrimitiveType": .*?),' | sort | uniq -c | sort -nr
3046 "PrimitiveType": "String"
 382 "PrimitiveType": "Integer"
 368 "PrimitiveType": "Boolean"
  99 "PrimitiveType": "Json"
  63 "PrimitiveType": "Double"
   8 "PrimitiveType": "Long"
   4 "PrimitiveType": "Timestamp"
   1 "PrimitiveType": "Map"

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("PrimitiveItemType": .*?),' | sort | uniq -c | sort -nr
 349 "PrimitiveItemType": "String"
   2 "PrimitiveItemType": "Boolean"
   1 "PrimitiveItemType": "Json"

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("Type": .*?),' | sort | uniq -c | sort -nr
 735 "Type": "List"
  48 "Type": "Map"
  ..

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("ItemType": .*?),' | sort | uniq -c | sort -nr
 108 "ItemType": "Tag"
 ...

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '"(.*?)::' | sort | uniq -c | sort -nr
1389 AWS
   4 Alexa

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '::(.*)::' | sort | uniq -c | sort -nr
 129 EC2
  64 Greengrass
  52 EMR
  49 Glue
  45 S3
  44 Pinpoint
  42 KinesisAnalyticsV2
  38 ApiGateway
  37 AppMesh
  36 IoTAnalytics
  32 ECS
  30 ElasticLoadBalancingV2
  28 KinesisFirehose
  28 KinesisAnalytics
  25 WAFRegional
  25 OpsWorks
  25 Cognito
  24 SSM
  24 IoT
  23 CloudFront
  22 SES
  22 CodeDeploy
  22 AppSync
  21 AutoScaling
  19 WAF
  18 PinpointEmail
  18 CodePipeline
  17 CodeBuild
  17 Batch
  16 Route53
  16 AppStream
  16 ApiGatewayV2
  15 ServiceCatalog
  15 Lambda
  14 RDS
  13 IAM
  13 ElasticBeanstalk
  12 RoboMaker
  12 Config
  11 DynamoDB
  11 DMS
  10 MSK
  10 Events
  10 AutoScalingPlans
  10 ApplicationAutoScaling
  10 Amplify
  10 AmazonMQ
   9 ServiceDiscovery
   9 SageMaker
   9 ElasticLoadBalancing
   8 GuardDuty
   8 Budgets
   7 Redshift
   7 Elasticsearch
   7 ElastiCache
   7 DataPipeline
   6 SecretsManager
   6 Logs
   6 GameLift
   6 DLM
   6 CloudWatch
   5 Transfer
   5 Route53Resolver
   5 Neptune
   5 IoT1Click
   5 CloudFormation
   4 StepFunctions
   4 SNS
   4 EFS
   4 DocDB
   4 DirectoryService
   4 DAX
   4 CodeCommit
   4 ASK
   3 Kinesis
   3 Inspector
   3 FSx
   3 CloudTrail
   2 WorkSpaces
   2 SQS
   2 OpsWorksCM
   2 MediaStore
   2 KMS
   2 IoTThingsGraph
   2 EKS
   2 ECR
   2 Cloud9
   2 CertificateManager
   1 SDB
   1 RAM
   1 Athena
```