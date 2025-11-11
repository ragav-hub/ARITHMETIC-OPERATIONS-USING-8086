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
9. 
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

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   12                     | 
|  2001                   |   34                     |
|  2002                   |   12                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   68                     | 
|  2005                   |   24                     |
|  2006                   |   00                     |
         
#### Manual Calculations

![WhatsApp Image 2025-09-22 at 09 08 55](https://github.com/user-attachments/assets/988f8125-c6f0-4ef3-bda1-7a436d52f237)

---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="627" height="413" alt="Screenshot 2025-09-12 085908" src="https://github.com/user-attachments/assets/93f834a7-3c51-4548-97a5-3c6bb5a1ad2d" />

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

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   56                     | 
|  2001                   |   78                     |
|  2002                   |   56|
|  2003                   |   78                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   32                     | 
|  2005                   |   44                     |
|  2006                   |   34                     |

#### Manual Calculations
![WhatsApp Image 2025-09-22 at 09 08 56](https://github.com/user-attachments/assets/7b09e63b-8815-4ff5-925f-7ae7d39097d9)


---
## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="665" height="458" alt="Screenshot 2025-09-22 083740" src="https://github.com/user-attachments/assets/e2ff0bdc-dcd0-407c-836e-04e89db05696" />

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

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   56                     | 
|  2001                   |   78                     |
|  2002                   |   56                     |
|  2003                   |   78                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   48                     | 
|  2005                   |   D8                     |
|  2006                   |   34                     |

#### Manual Calculations
![WhatsApp Image 2025-09-22 at 09 08 56 (1)](https://github.com/user-attachments/assets/96494372-5fae-49b7-ac35-7c7b3a6d19d4)


---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="634" height="409" alt="Screenshot 2025-09-12 093330" src="https://github.com/user-attachments/assets/9e41dc6d-537f-470c-9c6d-107b5249bbe3" />

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

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   68                     | 
|  2001                   |   24                     |
|  2002                   |   34                     |
|  2003                   |   11                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   00                     | 
|  2005                   |   02                     |
|  2006                   |   02                     |

#### Manual Calculations
![WhatsApp Image 2025-09-22 at 09 08 57](https://github.com/user-attachments/assets/f3c14140-809f-47e0-bd3c-ebd8255e2937)

---
## OUTPUT FROM MASM SOFTWARE
<img width="644" height="440" alt="Screenshot 2025-09-22 090922" src="https://github.com/user-attachments/assets/c9138179-86a8-43f3-8373-2559498bfe5d" />

## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

