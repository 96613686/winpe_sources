# XC_WriteT1PStackValue

- ea: `0x1800548bc`
- end: `0x180054940`
- name: `XC_WriteT1PStackValue`
- size: `132`
- prototype: `void __fastcall(__int64, _DWORD *, unsigned int)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180050274`
- `0x180050960`
- `0x1800512b8`
- `0x1800513f8`
- `0x180051538`
- `0x1800517bc`
- `0x180051880`
- `0x180051af4`
- `0x180051f98`
- `0x18005201c`
- `0x1800520e8`
- `0x180052758`
- `0x1800527fc`
- `0x180052ea8`
- `0x180053ad4`
- `0x180053cf0`

## callees

- `0x180052608`
- `0x180054864`
- `0x1800548bc`

## pseudocode

```c
void __fastcall XC_WriteT1PStackValue(__int64 a1, _DWORD *a2, unsigned int a3)
{
  int v5; // edx
  int v7; // r14d
  int i; // ebp

  v5 = a2[1];
  if ( *a2 )
  {
    WriteFixed((_JBTYPE *)a1, v5, a3);
    v7 = a2[1];
    for ( i = 1; i < *(_DWORD *)(a1 + 488); ++i )
      WriteFixed((_JBTYPE *)a1, a2[i + 1] - v7, a3);
    WriteFixed((_JBTYPE *)a1, 393216, a3);
    XC_WriteT1OpCode(a1, 10, a3);
  }
  else
  {
    WriteFixed((_JBTYPE *)a1, v5, a3);
  }
}

```

## disassembly

```asm
0x1800548bc  push    rbx
0x1800548be  push    rbp
0x1800548bf  push    rsi
0x1800548c0  push    rdi
0x1800548c1  push    r14
0x1800548c3  sub     rsp, 20h
0x1800548c7  mov     rsi, rdx
0x1800548ca  mov     edi, r8d
0x1800548cd  mov     edx, [rdx+4]
0x1800548d0  mov     rbx, rcx
0x1800548d3  cmp     dword ptr [rsi], 0
0x1800548d6  jnz     short loc_1800548DF
0x1800548d8  call    WriteFixed
0x1800548dd  jmp     short loc_180054934
0x1800548df  call    WriteFixed
0x1800548e4  mov     r14d, [rsi+4]
0x1800548e8  mov     ebp, 1
0x1800548ed  cmp     [rbx+1E8h], ebp
0x1800548f3  jle     short loc_180054914
0x1800548f5  movsxd  rax, ebp
0x1800548f8  mov     r8d, edi
0x1800548fb  mov     rcx, rbx
0x1800548fe  mov     edx, [rsi+rax*4+4]
0x180054902  sub     edx, r14d
0x180054905  call    WriteFixed
0x18005490a  inc     ebp
0x18005490c  cmp     ebp, [rbx+1E8h]
0x180054912  jl      short loc_1800548F5
0x180054914  mov     r8d, edi
0x180054917  mov     edx, 60000h
0x18005491c  mov     rcx, rbx
0x18005491f  call    WriteFixed
0x180054924  mov     edx, 0Ah
0x180054929  mov     r8d, edi
0x18005492c  mov     rcx, rbx
0x18005492f  call    XC_WriteT1OpCode
0x180054934  add     rsp, 20h
0x180054938  pop     r14
0x18005493a  pop     rdi
0x18005493b  pop     rsi
0x18005493c  pop     rbp
0x18005493d  pop     rbx
0x18005493e  retn
```
