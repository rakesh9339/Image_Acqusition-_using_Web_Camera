# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Import the cv2 and numpy package.

### Step 2:
<br>
Read the Video frame using the cv2.VideoCapture(0).

### Step 3:
<br>
Write the image using imwrite().

### Step 4:
<br>
Display the frame using the imshow().

### Step 5:
<br>
Divide the frame into halves and assign the smaller frame.

### Step 6:
<br>
Rotate the frame using the cv2.rotate().

## Program:
``` Python
### Developed By: RAKESH
### Register No:212222230115
```
## i) Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("RAK.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```



## ii) Display the video
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('RAK',frame)
    cv2.imwrite("butterfly.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('RAK',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```




## iv) Rotate and display the video
```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('RAK', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
</br>


![image](https://github.com/SriramS22/Image_Acqusition-_using_Web_Camera/assets/119094390/ef5c3b06-505a-4b44-a187-95038e5f992b)

</br>


### ii) Display the video
</br>

![Screenshot 2024-03-06 101852](https://github.com/SriramS22/Image_Acqusition-_using_Web_Camera/assets/119094390/6cbff6ea-e0ce-4a89-8317-2dd345924535)

</br>


### iii) Display the video by resizing the window
</br>

![Screenshot 2024-03-06 102129](https://github.com/SriramS22/Image_Acqusition-_using_Web_Camera/assets/119094390/7c30e78a-261c-4bfe-aaac-f70d2ece6215)

</br>



### iv) Rotate and display the video
</br>

![Screenshot 2024-03-06 102203](https://github.com/SriramS22/Image_Acqusition-_using_Web_Camera/assets/119094390/a5843b49-5ede-43e6-8831-2b2194b5b1cc)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
