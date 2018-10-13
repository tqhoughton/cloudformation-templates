# CloudFormation Templates

This is a repository for some of my commonly used CloudFormation templates that I use to deploy serverless applications on AWS. Most of the time, you will need some basic infrastructure set up to deploy serverless applications efficiently. Lucky for you, I've already done the hard part of creating the templates.

## Static Site with SSL
[template here](https://github.com/tqhoughton/cloudformation-templates/blob/master/static-site-ssl.yaml)

Most of the time, you don't want to just deploy your site to an S3 bucket and leave it at that. There are a few problems, namely:
1) You have an ugly S3 generated link to your site
2) You don't have SSL on your site, so your users will not be able to log in securely if you have some kind of auth flow

This template requires you to have a hosted zone in Route53, a valid ACM Certificate for your domain, and the full domain name of your site. Once you provide that, this template will automatically create an S3 bucket, Route53 record, and CloudFront distribution that uses your SSL certificate. Takes ~20 minutes to deploy (the CloudFront distribution takes a while.)

## Simple Pipeline
[template here](https://github.com/tqhoughton/cloudformation-templates/blob/master/pipeline_simple.yaml)

This is a simple pipeline that packages and deploys a SAM template. You can find a demo application to deploy [here](https://github.com/tqhoughton/sam-api-demo).

## Advanced Pipeline
[template here](https://github.com/tqhoughton/cloudformation-templates/blob/master/pipeline_simple.yaml)

This is an advanced pipeline that packages and deploys a SAM template, while also deploying an index.html to a predefined S3 bucket in the `s3/` directory, and also running unit tests defined in the `test/` directory. You can find a demo application to deploy [here](https://github.com/tqhoughton/sam-api-demo).
