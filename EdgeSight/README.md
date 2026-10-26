# EdgeSight

**Computer vision that runs entirely in your browser. No servers, no uploads, works offline.**

Submission for the OpenCV AI Competition 2026, powered by AWS.

## Overview
EdgeSight is a static web app that applies core computer vision operations to photos directly on the user's device: grayscale, blur, Sobel edge detection and thresholding. Images are never uploaded anywhere, so they stay private, and the tool keeps working offline once loaded.

## The problem
Many students, schools, clinics and farms lack GPU servers, paid vision APIs and fast internet. Sending photos to a remote server also raises privacy concerns.

## How it works
- Pure HTML, CSS and JavaScript (single file: `index.html`)
- Image processing with the Canvas API, using 3x3 convolution kernels (the same maths OpenCV uses for Sobel and blur)
- No backend, no database, no physical servers

## AWS architecture
User's browser -> Amazon CloudFront -> Amazon S3 (static website hosting)

## Run locally
Open `index.html` in any modern browser. No install or build step.

## Deploy on AWS
1. Create an S3 bucket and upload `index.html`.
2. Enable static website hosting and set `index.html` as the index document.
3. Allow public read access to the bucket.
4. (Optional) Create a CloudFront distribution with the bucket as origin for HTTPS and global delivery.

## Contents
- `index.html` - the full website and live demo
- `images/` - gallery images (cover, filters, architecture, benefits)
- `edgesight-demo.mp4` - short demo video

## Roadmap
OpenCV.js integration (contours, object detection), plant leaf checks, document edge detection, classroom learning mode.

## Built with
HTML5, CSS3, JavaScript, Canvas API, Amazon S3, Amazon CloudFront
