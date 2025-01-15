# My-New-AWS-AudioBook-Projecy
#Transforming Text into Speech: My AWS Polly Project with Lambda and Python

# Overview:
Amazon Polly is a cloud-based service provided by Amazon Web Services (AWS) that turns text into lifelike speech. It is designed to enable developers to build applications that can speak and create a more engaging user experience. Polly supports a variety of languages and voices, allowing developers to tailor the speech to suit the desired context.

# Key Features
1. Multilingual Support: Polly supports a wide range of languages, making it a versatile solution for global applications. Developers can choose from a variety of voices, each designed to sound natural and lifelike in their respective languages.

2. Choice of Voices: AWS Polly offers a diverse selection of voices, including male and female options, to enhance the user experience. Users can choose voices that match the tone and style they want for their applications.

3. SSML Support: Speech Synthesis Markup Language (SSML) is supported by Polly, allowing developers to have fine-grained control over the generated speech. This enables the manipulation of speech features such as pitch, rate, and volume, as well as the inclusion of pauses and emphasis.

4. Neural Text-to-Speech (NTTS): Polly's Neural Text-to-Speech (NTTS) technology provides high-quality and natural-sounding speech. NTTS allows for dynamic adjustments, making the speech more expressive and enhancing the overall user experience.

# Steps to Build the Project:

Step 1: Set Up an AWS Account

Step 2: Create two S3 Buckets (Source S3 Bucket Name: amc-polly-source-bucket, Destination S3 Bucket Name: amc-polly-destination-bucket)

Step 3: Create an IAM Policy (IAM Policy Name: amc-polly-lambda-policy)
```json
{
  "Version": "2012-10-17",
  "Statement": [
      {
          "Effect": "Allow",
          "Action": [
              "s3:GetObject",
              "s3:PutObject"
          ],
          "Resource": [
              "arn:aws:s3:::amc-polly-source-bucket/*",
              "arn:aws:s3:::amc-polly-destination-bucket/*"
          ]
      },
      {
          "Effect": "Allow",
          "Action": [
              "polly:SynthesizeSpeech"
          ],
          "Resource": "*"
      }
  ]
}





