#EX-07: Record-HOUGH-TRANSFORM
# NAME: KONDURU SANTHOSH
# REG.No: 212225240074
##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections


---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---
## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program 
##  Developed By

* **Name:** MUTHUKUMARAN NM
* **Register No:** 212225040268

### Input image and grayscale image
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('image.jpg')  # Replace 'image.jpg' with your image path
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
<img width="548" height="386" alt="image" src="https://github.com/user-attachments/assets/a66e7e53-db48-4d58-b03d-d7f18215df53" />

```python
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

```
<img width="544" height="394" alt="image" src="https://github.com/user-attachments/assets/06906388-d923-46d7-9763-149dba7c307d" />


### Canny Edge detector output
```python
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```
<img width="561" height="388" alt="image" src="https://github.com/user-attachments/assets/e8fa59b5-51d8-49a6-9801-99e44fcaf19f" />



### Display the result of Hough transform
```python
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# The lines variable contains the endpoints of the detected lines
for line in lines:
    line = line.flatten()
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')



```<img width="550" height="389" alt="image" src="https://github.com/user-attachments/assets/25ad7050-e8dd-4491-b246-9ba25b445fb5" />







---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
