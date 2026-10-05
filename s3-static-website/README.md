# Task 1: Static Website Hosting on Amazon S3

## 1. Objective
Host an HTML website and a React application on Amazon S3 using static website hosting.

## 2. Architecture
User (browser) -> S3 website endpoint -> S3 bucket (index.html, error.html)

## 3. Prerequisites
- AWS account with S3 permissions
- Node.js and npm (Part B only)

## 4. Project Structure
- `html-site/` : HTML website files (index.html, error.html)
- `react-site/` : React application source (Part B)
- `policies/` : bucket policy JSON files
- `screenshots/` : proof of each step

## 5. Part A: HTML Website

### Steps
1. Create the S3 bucket
2. Upload `index.html` and `error.html`
3. Enable static website hosting (index document: `index.html`, error document: `error.html`)
4. Disable "Block all public access" for the bucket
5. Attach the bucket policy below
6. Open the website endpoint and test

### Bucket policy
Replace `<bucket-name>` with your bucket name.

    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "PublicReadGetObject",
          "Effect": "Allow",
          "Principal": "*",
          "Action": "s3:GetObject",
          "Resource": "arn:aws:s3:::<bucket-name>/*"
        }
      ]
    }

### Result
- Website endpoint:
- Home page test:
- Error page test:

## 6. Part B: React Website

### Steps
1. Create the React app and run `npm run build`
2. Create a second bucket
3. Upload the contents of the `build/` folder
4. Enable static website hosting (index and error document: `index.html`)
5. Attach the bucket policy
6. Open the website endpoint and test

### Result
- Website endpoint:

## 7. Issues and Fixes
| Issue | Cause | Fix |
|-------|-------|-----|

## 8. Cleanup
Empty and delete the buckets after the task to avoid charges.
