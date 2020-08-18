# AWS - Threat Detection and Automated Prevention 
This project will show the real-time threat detection by AWS GuardDuty and remediation by AWS Lambda functions.

## GuardDuty
A GuardDuty finding represents a potential security issue detected within the network. GuardDuty generates a finding whenever it detects unexpected and potentially malicious activity in your AWS environment.

## Work Flow Diagram 

![Work-Flow Diagram](https://github.com/roshangami/aws_threat_prevention/blob/master/images/DFD-guardDuty.png "Threat detection and remediation diagram")


## Brief Steps
**Detailed AWS Lab setup, attack and remediation in working is available [here](https://)** 
1. Create findings for AWS GuardDuty.
2. Create CloudWatch rules to invoke Targets based on GuardDuty findings.
3. Select Target as SNS and Lambda to invoke when an event matches your event pattern or when the schedule is triggered.
   - AWS SNS will be used for email notification alert in case of any finding detected by GuardDuty.
   - AWS Lambda will be used for remediation purposes and will make use of the boto3 framework for Programmatic access to AWS resources.
4. Create and configure SNS Topics subscribers.
5. Create an IAM role for the Lambda function and a Lambda function with lambda.py python code(Update the lambda.py file with isolated_sg id).
```
import boto3
ec2 = boto3.resource('ec2')
isolated_sg = '' # ID of Security group "compromised-ec2-sg"
```

## Author 
Roshan Gami
