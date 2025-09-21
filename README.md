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

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   98                     | 
|  2001                   |   76                     |
|  2002                   |   12                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   AA                     | 
|  2005                   |   AA                     |
|  2006                   |   00                     |
#### Manual Calculations

![WhatsApp Image 2025-09-21 at 22 35 52_aaf9333f](https://github.com/user-attachments/assets/00fcb3ae-63c9-4c94-a1d7-873923756104)

---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="637" height="428" alt="indadd op" src="https://github.com/user-attachments/assets/51e062d4-bd7e-454e-911c-5bd56a70363e" />


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

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   89                     | 
|  2001                   |   76                     |
|  2002                   |   34                     |
|  2003                   |   12                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   42                     | 
|  2005                   |   77                     |
|  2006                   |   00                     |
#### Manual Calculations

![WhatsApp Image 2025-09-21 at 22 35 52_760036d7](https://github.com/user-attachments/assets/8cb0f4aa-6e34-4c77-a311-d63f601f1613)


---


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="640" height="427" alt="indsub op 1" src="https://github.com/user-attachments/assets/ac7a9021-0820-41de-a477-b5f3263c0165" />

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
|  2000                   |   12                     | 
|  2001                   |   34                     |
|  2002                   |   12                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   90                     | 
|  2005                   |   5A                     |
|  2006                   |   4B                     |

#### Manual Calculations

![WhatsApp Image 2025-09-21 at 22 35 51_560205fc](https://github.com/user-attachments/assets/28303b46-b1e2-4715-aae5-6ae94c39335f)

---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="642" height="421" alt="indmul op 1" src="https://github.com/user-attachments/assets/c70c5344-5ef6-463a-bc41-af411f86c829" />

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
|  2004                   |   02                     | 
|  2005                   |   00                     |
|  2006                   |   02                     |

#### Manual Calculations

![WhatsApp Image 2025-09-21 at 22 35 51_3acf7131](https://github.com/user-attachments/assets/6e3623c2-3fba-4b95-8b98-5eb33ad05d6d)

---
## OUTPUT FROM MASM SOFTWARE
<img width="647" height="432" alt="inddiv 1" src="https://github.com/user-attachments/assets/9808657c-e3b3-47a3-938a-4b4de327431d" />

## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

