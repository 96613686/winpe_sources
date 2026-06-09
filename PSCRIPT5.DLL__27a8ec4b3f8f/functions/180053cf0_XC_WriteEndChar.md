# XC_WriteEndChar

- ea: `0x180053cf0`
- end: `0x180053df1`
- name: `XC_WriteEndChar`
- size: `257`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180051af4`

## callees

- `0x18004f8e4`
- `0x180051880`
- `0x180053cf0`
- `0x180054864`
- `0x1800548bc`

## pseudocode

```c
void __fastcall XC_WriteEndChar(__int64 a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbp
  _DWORD *v6; // rdx
  _DWORD *v7; // rdi
  _DWORD *v8; // rbx
  __int16 v9; // dx
  __int64 v10; // rcx

  if ( *(_WORD *)(a1 + 22736) < 4u )
  {
    StateChange(a1, 1, 1, 1, 0, a2);
    v9 = 14;
    v10 = a1;
    if ( *(_WORD *)(a1 + 22736) )
      XCF_FatalErrorHandler((_JBTYPE *)a1, 14);
  }
  else
  {
    StateChange(a1, 0, 0, 1, 4u, a2);
    v4 = *(_QWORD *)(a1 + 21984);
    v5 = *(_QWORD *)(a1 + 21992);
    v6 = *(_DWORD **)(a1 + 26048);
    v7 = *(_DWORD **)(a1 + 21976);
    v8 = *(_DWORD **)(a1 + 21968);
    *(_WORD *)(a1 + 21944) = *(_WORD *)(v4 + 6);
    *(_WORD *)(a1 + 21946) = *(_WORD *)(v5 + 6);
    XC_WriteT1PStackValue(a1, v6, a2);
    XC_WriteT1PStackValue(a1, v8, a2);
    XC_WriteT1PStackValue(a1, v7, a2);
    XC_WriteT1PStackValue(a1, (_DWORD *)v4, a2);
    XC_WriteT1PStackValue(a1, (_DWORD *)v5, a2);
    v9 = 3078;
    v10 = a1;
  }
  XC_WriteT1OpCode(v10, v9, a2);
}

```

## disassembly

```asm
0x180053cf0  push    rbx
0x180053cf2  push    rbp
0x180053cf3  push    rsi
0x180053cf4  push    rdi
0x180053cf5  push    r14
0x180053cf7  push    r15
0x180053cf9  sub     rsp, 38h
0x180053cfd  mov     eax, 4
0x180053d02  mov     [rsp+68h+var_40], edx
0x180053d06  mov     r15d, edx
0x180053d09  mov     r14, rcx
0x180053d0c  cmp     [rcx+58D0h], ax
0x180053d13  jb      loc_180053DB3
0x180053d19  lea     r9d, [rax-3]
0x180053d1d  mov     [rsp+68h+var_48], eax
0x180053d21  xor     r8d, r8d
0x180053d24  xor     edx, edx
0x180053d26  call    StateChange
0x180053d2b  mov     rsi, [r14+55E0h]
0x180053d32  mov     r8d, r15d
0x180053d35  mov     rbp, [r14+55E8h]
0x180053d3c  mov     rcx, r14
0x180053d3f  mov     rdx, [r14+65C0h]
0x180053d46  mov     rdi, [r14+55D8h]
0x180053d4d  movzx   eax, word ptr [rsi+6]
0x180053d51  mov     rbx, [r14+55D0h]
0x180053d58  mov     [r14+55B8h], ax
0x180053d60  movzx   eax, word ptr [rbp+6]
0x180053d64  mov     [r14+55BAh], ax
0x180053d6c  call    XC_WriteT1PStackValue
0x180053d71  mov     r8d, r15d
0x180053d74  mov     rdx, rbx
0x180053d77  mov     rcx, r14
0x180053d7a  call    XC_WriteT1PStackValue
0x180053d7f  mov     r8d, r15d
0x180053d82  mov     rdx, rdi
0x180053d85  mov     rcx, r14
0x180053d88  call    XC_WriteT1PStackValue
0x180053d8d  mov     r8d, r15d
0x180053d90  mov     rdx, rsi
0x180053d93  mov     rcx, r14
0x180053d96  call    XC_WriteT1PStackValue
0x180053d9b  mov     r8d, r15d
0x180053d9e  mov     rdx, rbp
0x180053da1  mov     rcx, r14
0x180053da4  call    XC_WriteT1PStackValue
0x180053da9  mov     edx, 0C06h
0x180053dae  mov     rcx, r14
0x180053db1  jmp     short loc_180053DD7
0x180053db3  xor     ebx, ebx
0x180053db5  mov     [rsp+68h+var_48], ebx
0x180053db9  lea     edx, [rbx+1]
0x180053dbc  mov     r9d, edx
0x180053dbf  mov     r8d, edx
0x180053dc2  call    StateChange
0x180053dc7  lea     edx, [rbx+0Eh]
0x180053dca  mov     rcx, r14
0x180053dcd  cmp     [r14+58D0h], bx
0x180053dd5  jnz     short loc_180053DEB
0x180053dd7  mov     r8d, r15d
0x180053dda  add     rsp, 38h
0x180053dde  pop     r15
0x180053de0  pop     r14
0x180053de2  pop     rdi
0x180053de3  pop     rsi
0x180053de4  pop     rbp
0x180053de5  pop     rbx
0x180053de6  jmp     XC_WriteT1OpCode
0x180053deb  call    XCF_FatalErrorHandler
```
