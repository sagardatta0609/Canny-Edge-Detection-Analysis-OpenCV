## Canny Edge Detection – Stage Analysis & Sensitivity Study

This project demonstrates a complete breakdown and analysis of the Canny Edge Detection Algorithm using OpenCV in Google Colab.

It includes:

✅ Stage-by-stage visualization of Canny

✅ Manual gradient magnitude & orientation

✅ Sensitivity analysis with noise and threshold variations

✅ Comparison under Gaussian and Salt & Pepper noise

## Objective

Understand how Canny Edge Detection works internally

Visualize intermediate stages

Analyze sensitivity to:

Gaussian blur (σ)

Threshold values

Image noise

## Technologies Used

Python

OpenCV (cv2)

NumPy

Matplotlib

Google Colab

## Theory: Canny Edge Detection

Canny edge detection consists of 4 main stages:

🔹 Stage 1: Gaussian Blur

Purpose:

Remove noise

Smooth image

Kernel Size: 5×5
Sigma: 1.4 (standard)

🔹 Stage 2: Gradient Calculation (Sobel)

We compute:

Gradient in X direction

Gradient in Y direction

Then:

Magnitude

Orientation (using atan2)

Magnitude formula:

|G| = √(Gx² + Gy²)

Orientation formula:

θ = atan2(Gy, Gx)

🔹 Stage 3: Non-Maximum Suppression (NMS)

Thins edges

Keeps only strongest edge pixels

(OpenCV handles this internally)

🔹 Stage 4: Hysteresis Thresholding

Uses two thresholds:

Low threshold

High threshold

Strong edges are kept.
Weak edges are kept only if connected to strong ones.

## Project Structure

Canny-Edge-Detection-Analysis-OpenCV/
│
├── canny_lab4.py
└── README.md
## Part A – Stage Visualization

For each uploaded image:

Convert to Grayscale

Apply Gaussian Blur

Compute Sobel Gradients

Calculate:

Gradient Magnitude

Gradient Orientation

Apply Final Canny Edge Detection

Output displayed:

Original Image

Blurred Image

Gradient Magnitude

Gradient Orientation (HSV)

Final Edge Map

## Part B – Sensitivity Analysis

We test multiple scenarios:

Case	Sigma	Thresholds	Noise
1	0	(50,150)	None
2	1	(50,150)	None
3	1	(100,200)	None
4	1	(50,150)	Gaussian
5	1	(50,150)	Salt & Pepper
## Observations

Increasing σ reduces noise but blurs edges

Higher thresholds detect fewer edges

Gaussian noise causes false edges

Salt & Pepper noise severely affects edge detection

Proper blur improves performance under noise

▶️ How to Run (Google Colab)

Open Google Colab

Paste the full script

Run the cell

Upload 3 images:

Shapes image

Natural scene

Text / QR code image

Observe Part A and Part B results

## Learning Outcomes

After completing this experiment, you will understand:

Internal working of Canny Edge Detector

Importance of Gaussian smoothing

Role of gradient magnitude and orientation

Effect of thresholds

Impact of different noise types

Practical parameter tuning

## Academic Relevance

This project is suitable for:

Digital Image Processing Lab

Computer Vision Coursework

OpenCV Practical Exams

Image Filtering Experiments

Edge Detection Analysis

## Possible Improvements

Add Laplacian edge detection comparison

Add Prewitt operator comparison

Add automatic threshold selection

Add edge density measurement

Add histogram analysis

Save outputs automatically

Build interactive Streamlit UI
