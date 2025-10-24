# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2000                   |   79                     | 
|  2001                   |   88                     |
|  2002                   |   23                     |
|  2003                   |   02                     |


| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2004                   |   9C                     | 
|  2005                   |   8A                     |
|  2006                   |   00                     |

#### Manual Calculations

![Manual Calculation Direct Addition](https://github.com/user-attachments/assets/f0ead0cf-d82c-4abe-9ff9-5f10fbaf6a52)

---
## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="642" height="432" alt="Indirect Addition" src="https://github.com/user-attachments/assets/80fd9b33-bc63-4ac8-8117-008b9c7c8556" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2000                   |   79                     | 
|  2001                   |   88                     |
|  2002                   |   23                     |
|  2003                   |   02                     |


| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2004                   |   56                     | 
|  2005                   |   86                     |
|  2006                   |   00                     |
#### Manual Calculations

![Indirect Substraction](https://github.com/user-attachments/assets/14c4971e-5ff7-4c52-a290-0758bdfcbc25)


---
## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="642" height="432" alt="Indirect substraction" src="https://github.com/user-attachments/assets/ff315210-1db4-4b78-84ab-c4a89b1edbaf" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2000                   |   02                     | 
|  2001                   |   00                     |
|  2002                   |   03                     |
|  2003                   |   00                     |


| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2004                   |   06                     | 
|  2005                   |   00                     |
|  2006                   |   00                     |

#### Manual Calculations

![Manual Calculation Indirect Multiplication](https://github.com/user-attachments/assets/777aadf1-1d9a-420d-a77e-917c9d013cea)

---
## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="642" height="432" alt="Indirect Multiplication" src="https://github.com/user-attachments/assets/701adf8c-d3b4-4e83-9c86-a38bf51c98b0" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2000                   |   69                     | 
|  2001                   |   24                     |
|  2002                   |   34                     |
|  2003                   |   12                     |


| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  2004                   |   02                     | 
|  2005                   |   00                     |
|  2006                   |   01                     |
#### Manual Calculations

![Manual Calculation Indirect Division](https://github.com/user-attachments/assets/49e06176-89eb-4f87-bafc-7ae29ef21b82)


---
## OUTPUT FROM MASM SOFTWARE

<img width="642" height="432" alt="Indirect division" src="https://github.com/user-attachments/assets/5e0f48fd-663e-48b9-802b-48ae1d3f799e" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

