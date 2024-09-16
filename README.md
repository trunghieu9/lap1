import numpy as np
X = np.array([180, 162, 183, 174, 160, 163, 180, 165, 175, 170, 170, 169,
 168, 175, 169, 171, 155, 158, 175, 165]).reshape(-1,1)

y = np.array([86, 55, 86.5, 70, 62, 54, 60, 72, 93, 89, 60, 82, 59, 75,
 56, 89, 45, 60, 60, 72]).reshape((-1,1))

X = np.insert(X, 0, 1, axis=1)
import matplotlib.pyplot as plt
theta = np.linalg.inv(X.T @ X) @ X.T @ y
print(theta[0])
print(theta[1])

x1 = 150
y1 = theta[0] + theta[1] * x1
x2 = 190
y2 = theta[0] + theta[1] * x2
plt.plot([x1, x2], [y1, y2], 'r-')
plt.plot(X[:,1], y[:,0], 'bo')
plt.xlabel('Chiều cao')
plt.ylabel('Cân nặng')
plt.title('Chiều cao và cân nặng của sinh viên VLU')
[-114.75365641]
[1.08667645]
Text(0.5, 1.0, 'Chiều cao và cân nặng của sinh viên VLU')
