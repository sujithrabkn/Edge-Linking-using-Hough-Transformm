# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:

```
Developed By : SUJITHRA B K N
Register Number : 212222230153
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('cartoon.jpeg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output

### Input image and grayscale image

![Screenshot 2024-09-30 214421](https://github.com/user-attachments/assets/483ee8f1-5ba4-47de-bd8f-02d66496f997)

![Screenshot 2024-09-30 214439](https://github.com/user-attachments/assets/24c4e26e-2462-48c0-85d1-2f2dc0e141ee)

### Canny Edge detector output


![Screenshot 2024-09-30 214513](https://github.com/user-attachments/assets/a082ba5a-d7fd-4cc6-8b61-1dbcaa8a159a)

### Display the result of the Hough transform


![Screenshot 2024-09-30 214606](https://github.com/user-attachments/assets/1f5300b3-3b5e-4066-bb0b-5665b8b34703)


## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
