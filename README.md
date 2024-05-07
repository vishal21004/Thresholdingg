
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: VISHAL M.A
REGISTER NO: 21222230177
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("spi.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("spi.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output
### Original Image
![ORGIN IMG](https://github.com/vishal21004/Thresholdingg/assets/119560110/c0844f65-09bc-4e69-8895-a6702ff15350)



### Global Thresholding
![GLOBAL THRES](https://github.com/vishal21004/Thresholdingg/assets/119560110/c1caaff5-c47f-42c0-9ee3-d337f3e3e949)
![THRES 2](https://github.com/vishal21004/Thresholdingg/assets/119560110/aeb5c30e-4e43-4516-8c86-ad87964d7483)
![THRES 3](https://github.com/vishal21004/Thresholdingg/assets/119560110/d4b2de8b-9cd4-47db-9542-850ae338e3c3)
![THRES 4](https://github.com/vishal21004/Thresholdingg/assets/119560110/97d17885-113e-4e43-bda5-bb3eaf15542a)
![THRES 5](https://github.com/vishal21004/Thresholdingg/assets/119560110/070d85c6-6b96-46ad-a487-a5442ba49389)





### Adaptive Thresholding
![ADAPTIVE THRES](https://github.com/vishal21004/Thresholdingg/assets/119560110/8f70cab5-1591-434a-be19-2415c5c91147)
![ADAPTIVE THRES 2](https://github.com/vishal21004/Thresholdingg/assets/119560110/e9ec6f96-4003-4096-96d9-e3c8916e590e)



### Optimum Global Thesholding using Otsu's Method
![OTSU THRES](https://github.com/vishal21004/Thresholdingg/assets/119560110/e8c786bd-467e-480f-a64e-ca8d4a35e220)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
