# XC_WriteEndChar

- ea: `0x180052370`
- end: `0x180052471`
- name: `XC_WriteEndChar`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005017c`

## callees

- `0x18004e048`
- `0x18004ff08`
- `0x180052370`
- `0x180052ed8`
- `0x180052f30`

## pseudocode

```c
__int64 __fastcall XC_WriteEndChar(__int64 a1, unsigned int a2)
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
      XCF_FatalErrorHandler(a1, 14);
  }
  else
  {
    StateChange(a1, 0, 0, 1, 4, a2);
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
  return XC_WriteT1OpCode(v10, v9, a2);
}

```

## disassembly

```asm
0x180052370  push    rbx
0x180052372  push    rbp
0x180052373  push    rsi
0x180052374  push    rdi
0x180052375  push    r14
0x180052377  push    r15
0x180052379  sub     rsp, 38h
0x18005237d  mov     eax, 4
0x180052382  mov     [rsp+68h+var_40], edx
0x180052386  mov     r15d, edx
0x180052389  mov     r14, rcx
0x18005238c  cmp     [rcx+58D0h], ax
0x180052393  jb      loc_180052433
0x180052399  lea     r9d, [rax-3]
0x18005239d  mov     [rsp+68h+var_48], eax
0x1800523a1  xor     r8d, r8d
0x1800523a4  xor     edx, edx
0x1800523a6  call    StateChange
0x1800523ab  mov     rsi, [r14+55E0h]
0x1800523b2  mov     r8d, r15d
0x1800523b5  mov     rbp, [r14+55E8h]
0x1800523bc  mov     rcx, r14
0x1800523bf  mov     rdx, [r14+65C0h]
0x1800523c6  mov     rdi, [r14+55D8h]
0x1800523cd  movzx   eax, word ptr [rsi+6]
0x1800523d1  mov     rbx, [r14+55D0h]
0x1800523d8  mov     [r14+55B8h], ax
0x1800523e0  movzx   eax, word ptr [rbp+6]
0x1800523e4  mov     [r14+55BAh], ax
0x1800523ec  call    XC_WriteT1PStackValue
0x1800523f1  mov     r8d, r15d
0x1800523f4  mov     rdx, rbx
0x1800523f7  mov     rcx, r14
0x1800523fa  call    XC_WriteT1PStackValue
0x1800523ff  mov     r8d, r15d
0x180052402  mov     rdx, rdi
0x180052405  mov     rcx, r14
0x180052408  call    XC_WriteT1PStackValue
0x18005240d  mov     r8d, r15d
0x180052410  mov     rdx, rsi
0x180052413  mov     rcx, r14
0x180052416  call    XC_WriteT1PStackValue
0x18005241b  mov     r8d, r15d
0x18005241e  mov     rdx, rbp
0x180052421  mov     rcx, r14
0x180052424  call    XC_WriteT1PStackValue
0x180052429  mov     edx, 0C06h
0x18005242e  mov     rcx, r14
0x180052431  jmp     short loc_180052457
0x180052433  xor     ebx, ebx
0x180052435  mov     [rsp+68h+var_48], ebx
0x180052439  lea     edx, [rbx+1]
0x18005243c  mov     r9d, edx
0x18005243f  mov     r8d, edx
0x180052442  call    StateChange
0x180052447  lea     edx, [rbx+0Eh]
0x18005244a  mov     rcx, r14
0x18005244d  cmp     [r14+58D0h], bx
0x180052455  jnz     short loc_18005246B
0x180052457  mov     r8d, r15d
0x18005245a  add     rsp, 38h
0x18005245e  pop     r15
0x180052460  pop     r14
0x180052462  pop     rdi
0x180052463  pop     rsi
0x180052464  pop     rbp
0x180052465  pop     rbx
0x180052466  jmp     XC_WriteT1OpCode
0x18005246b  call    XCF_FatalErrorHandler
```
