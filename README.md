# AWS-projects

# Serverless- Convert TextToVoice-Using-Lambda

Site Link: https://s3.amazonaws.com/pollymp3storagebucket77/index.html

## Resources:
- Amazon Polly
- API Gateway
- S3
- DynamoDB
- AMI
- SNS
- Lambda



## Setup

- Create a DynamoDB database with default settings.
- Create  2 S3 buckets to store the posts and the mp3s for the posts. Modify one of the S3 bucket settings to public since it  will contain the webpage. 
- Create topic in SNS for scheduling different parts of AWS.
	- Create a topic to ensure the posts are added to DynamoDB and  a lambda function is triggered to obtain the post from the DB to Amazon Polly for converting  text to voice(mp3s).
	- Create a topic for text to voice (mp3s) conversion when mp3 is written into S3 bucket.
- Create a AMI role which allows lambda to interact with different  AWS services such as Polly,S3, DynamoDB and SNS.

- Create a Lambda function to insert new text posts into DynamoDB and send notification to SNS after inserting the record.
- Create a Lambda function to convert text to voice, taking text from DynamoDB to Amazon Polly and storing mp3s to S3 bucket after conversion by Polly.
- Create a Lambda function to get post from DynamoDB and play the mp3.
- Create the API using API Gateway, creating GET and POST methods calling the lambda functions.
- In order to access API Gateway from S3, where the webpages are, Enable CORS so that S3 can interact with API Gateway.
- Setup the query strings and mapping setting of the GET method depending on the scripts.js of the project.
- Once done with  setting up of the methods, deploy the API.
- Upload  script, css and webpage in the public S3 bucket.
- Provide  API endpoint to the script, so that S3 bucket can interact with API gateway.
