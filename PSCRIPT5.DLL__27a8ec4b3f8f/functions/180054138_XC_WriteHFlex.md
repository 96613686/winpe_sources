# XC_WriteHFlex

- ea: `0x180054138`
- end: `0x180054213`
- name: `XC_WriteHFlex`
- size: `219`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180051af4`

## callees

- `0x18004f8e4`
- `0x180050dd4`
- `0x1800520e8`
- `0x180054138`

## pseudocode

```c
__int64 __fastcall XC_WriteHFlex(__int64 a1, unsigned int a2)
{
  if ( *(_WORD *)(a1 + 22736) != 7 )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 14);
  PSVSubtract(a1, *(unsigned int **)(a1 + 26064), *(unsigned int **)(a1 + 26048), *(unsigned int **)(a1 + 21984));
  return WriteExpandedFlexCurveTo(
           a1,
           *(unsigned int **)(a1 + 21968),
           *(unsigned int **)(a1 + 26048),
           *(unsigned int **)(a1 + 21976),
           *(unsigned int **)(a1 + 21984),
           *(unsigned int **)(a1 + 21992),
           *(unsigned int **)(a1 + 26048),
           *(_DWORD **)(a1 + 22000),
           *(_DWORD **)(a1 + 26048),
           *(_DWORD **)(a1 + 22008),
           *(_DWORD **)(a1 + 26064),
           *(_DWORD **)(a1 + 22016),
           *(_DWORD **)(a1 + 26048),
           *(_DWORD **)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x180054138  mov     [rsp+arg_0], rbx
0x18005413d  push    rdi
0x18005413e  sub     rsp, 80h
0x180054145  cmp     word ptr [rcx+58D0h], 7
0x18005414d  mov     edi, edx
0x18005414f  mov     rbx, rcx
0x180054152  jnz     loc_180054208
0x180054158  mov     r9, [rcx+55E0h]
0x18005415f  mov     r8, [rcx+65C0h]
0x180054166  mov     rdx, [rcx+65D0h]
0x18005416d  call    PSVSubtract
0x180054172  mov     r8, [rbx+65C0h]
0x180054179  mov     rcx, rbx
0x18005417c  mov     rax, [rbx+65C8h]
0x180054183  mov     r9, [rbx+55D8h]
0x18005418a  mov     rdx, [rbx+55D0h]
0x180054191  mov     [rsp+88h+var_18], edi
0x180054195  mov     [rsp+88h+var_20], rax
0x18005419a  mov     rax, [rbx+5600h]
0x1800541a1  mov     [rsp+88h+var_28], r8
0x1800541a6  mov     [rsp+88h+var_30], rax
0x1800541ab  mov     rax, [rbx+65D0h]
0x1800541b2  mov     [rsp+88h+var_38], rax
0x1800541b7  mov     rax, [rbx+55F8h]
0x1800541be  mov     [rsp+88h+var_40], rax
0x1800541c3  mov     rax, [rbx+55F0h]
0x1800541ca  mov     [rsp+88h+var_48], r8
0x1800541cf  mov     [rsp+88h+var_50], rax
0x1800541d4  mov     rax, [rbx+55E8h]
0x1800541db  mov     [rsp+88h+var_58], r8
0x1800541e0  mov     [rsp+88h+var_60], rax
0x1800541e5  mov     rax, [rbx+55E0h]
0x1800541ec  mov     [rsp+88h+var_68], rax
0x1800541f1  call    WriteExpandedFlexCurveTo
0x1800541f6  mov     rbx, [rsp+88h+arg_0]
0x1800541fe  add     rsp, 80h
0x180054205  pop     rdi
0x180054206  retn
0x180054208  mov     edx, 0Eh
0x18005420d  call    XCF_FatalErrorHandler
```
