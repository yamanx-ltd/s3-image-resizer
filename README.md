
# S3 Image Resizer

S3 Image Resizer is an open-source project built with .NET 6.0 that allows you to serve images directly from Amazon S3. The key feature of this resizer is its ability to create and serve requested images on the fly. If the requested image does not exist in S3, the code is invoked to generate and store the image.

## Features

### 1. Direct S3 Image Serving

Easily serve images directly from your Amazon S3 bucket. The system checks if the requested image exists in S3, and if not, it generates the image on-the-fly.

### 2. On-the-Fly Image Resizing

The S3 Image Resizer works dynamically, resizing images in real-time based on the requested dimensions. This eliminates the need to pre-generate multiple versions of an image, saving storage space and simplifying your workflow.

### 3. Configurable Resolutions

Customize the allowed resolutions by setting the `ALLOWED_RESOLUTIONS` property via environment variables. This provides flexibility in controlling the sizes of images that can be requested and generated.

### 4. Built with .NET 6.0

The project is developed using the latest .NET 6.0 framework, ensuring compatibility with the latest technologies and taking advantage of the newest features and optimizations.

### 5. Serverless Architecture

Designed to work seamlessly in serverless environments, the S3 Image Resizer is well-suited for cloud-based deployments. It can efficiently scale based on demand and handle image resizing without the need for a dedicated server.

## Deployment with AWS CloudFormation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/fehmianac/s3-image-resizer.git
   ```

2. **Set Environment Variables:**
   Customize the behavior of the resizer by setting the required environment variables, including `ALLOWED_RESOLUTIONS`.

3. **Deploy with AWS CloudFormation:**
   Use the provided CloudFormation template (`s3-image-resizer-template.yaml`) to automate the setup of your S3 Image Resizer. Replace `<YOUR-BUCKET-NAME>` with the desired S3 bucket name.
   ```bash
   aws cloudformation deploy --template-file s3-image-resizer-template.yaml --stack-name S3ImageResizerStack --parameter-overrides ImageResizerBucketName=<YOUR-BUCKET-NAME>
   ```

4. **Configure S3 Access:**
   Ensure the application has the necessary permissions to read from and write to your S3 bucket.

5. **Usage:**
   Start using the S3 Image Resizer by making requests to the specified CloudFormation-deployed endpoint with the desired image parameters.

## Environment Variables

- **ALLOWED_RESOLUTIONS:** Define the allowed image resolutions separated by commas.

## Contributing

If you would like to contribute to the project or report issues, please check the [contribution guidelines](CONTRIBUTING.md).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
