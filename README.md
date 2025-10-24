 Write an assembly language program in 8086 to generate the Fibonacci series up to N terms and store the sequence in memory

## AIM
To develop an 8086 Assembly Language program that generates the Fibanoacci series to N terms and store the sequence in memory.

## APPARATUS REQUIRED
8086 Microprocessor Emulator (e.g., EMU8086, DOSBox, or MASM/TASM assembler). PC or laptop with Windows/macOS/Linux. Text editor or IDE to write assembly code. Basic knowledge of 8086 instructions and registers.

## ALGORITHM
Start the program and initialize the data segment, then load the number of terms N. Initialize the first two terms F0 = 0 and F1 = 1, and store them in memory. Add the previous two terms to get the next term and store it. Continue this process until N terms are generated and stored sequentially in memory.

## PROGRAM
```asm
.model small
.stack 10h
data segment
cnt db 10
fib db 10 dup(0)
data ends
code segment
assume cs: code, ds: data
start: mov ax,data
mov ds,ax
mov al, 00h
lea si,fib
mov [si],al
mov cl,cnt
mov ch, 00h
sub cx, 02h
l:
mov al, [si-1]
add al, [si]
laa
inc si
mov [si],al
loop l
mov ah, 4ch
int 21h
code ends
end start
```

## OUTPUT


<img width="640" height="480" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/619159cb-dc88-4c6a-a8ba-cb4bebbea84e" />

<img width="640" height="480" alt="Screenshot (38)" src="https://github.com/user-attachments/assets/8cf789d7-1c1c-4641-88b8-242bfd84c2e3" />

<img width="640" height="480" alt="Screenshot (36)" src="https://github.com/user-attachments/assets/b6248685-44ba-429a-8563-8a8bdd0d0b43" />


# RESULT
The program successfully generates the Fibanoacci series to N terms and store the sequence in memory , demonstrating correct use of loop and arithmetic instructions in the8086 microprocessor .
