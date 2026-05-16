# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Vemareddygari Pallavi
RegisterNumber: 212225230293
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
          u[:,i]-=(A[:,i]@q[:,j]*q[:,j])
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    r=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            r[i,j]=A[:,j]@q[:,i]
    print("The Q Matrix is\n",q)
    print("The R Matrix is \n",r)
x=eval(input())
a=np.array(x)

QR_Decomposition(a)






```
## Output
```
<img width="1284" height="783" alt="image" src="https://github.com/user-attachments/assets/de4c029a-35b8-464c-be49-621f9daa861b" />


<img width="1416" height="766" alt="image" src="https://github.com/user-attachments/assets/96ff3dcf-cd46-4e14-adc2-78372683f743" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
