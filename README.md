# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure:

It can be implemented using two half subtractors and one OR gate as:


1.) Giving one half subtractor the inputs A and B that gives outputs Diff1 and B1.


2.) Giving second half subtractor inputs Bin and Diff1 from first subtractor that gives outputs B2 and D (difference for the full subtractor).

## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: shalini v
RegisterNumber: 212222240096

HALF_SUBTRACTOR :

input x,y;
output x1,d,b;
xor(d,x,y);
not(x1,x);
and(b,x1,y);
endmodule

FULL_SUBTRACTOR :

module fulladder(x,y,z,s,c,x1,x2,x3,x4);
input x,y,z;
output s,c,x1,x2,x3,x4;
xor(x1,x,y);
xor(s,x1,z);
and(x3,x,y);
and(x4,x1,z);
or(c,x3,z);
endmodule 

```

## Output:

## Truthtable:
![image](https://user-images.githubusercontent.com/118720291/233423799-b44f0a14-d24c-4067-883c-445c6ecfef31.png)
![image](https://user-images.githubusercontent.com/118720291/233423977-49d68cd4-0f3b-4fea-a848-6cf2b529ac7d.png)

##  RTL realization:
![image](https://user-images.githubusercontent.com/118720291/233424262-a80afdd0-3572-4d6b-bf7c-112497aa669c.png)
![image](https://user-images.githubusercontent.com/118720291/233424423-33eb32e5-2914-4bb8-93c1-4afd41433aed.png)

## Timing diagram :
![image](https://user-images.githubusercontent.com/118720291/233424585-572a745a-81c1-461d-9c11-c0d648ee22ac.png)
![image](https://user-images.githubusercontent.com/118720291/233424685-9fc2655d-3b3a-4e83-ae34-95a42c99a5e9.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
