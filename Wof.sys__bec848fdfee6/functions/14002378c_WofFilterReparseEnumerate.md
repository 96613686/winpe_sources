# WofFilterReparseEnumerate

- ea: `0x14002378c`
- end: `0x140023826`
- name: `WofFilterReparseEnumerate`
- size: `154`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int, __int64, unsigned int, char, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140036e70`

## callees

- `0x140011590`
- `0x140022fcc`
- `0x14002378c`

## pseudocode

```c
__int64 __fastcall WofFilterReparseEnumerate(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        _DWORD *a7)
{
  _DWORD *v8; // rbx
  unsigned __int64 v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // esi
  void *v12; // rcx

  v8 = a2;
  v9 = (unsigned __int64)a2 + a3;
  v10 = 0;
  while ( (unsigned __int64)v8 < v9 )
  {
    v11 = v10 + 16;
    if ( (int)v10 + 16 > a5 )
      break;
    if ( v8[2] != FileTag )
    {
      v12 = (void *)(a4 + v10);
      if ( a6 )
        RtlCopyToUser(v12, v8, 0x10u);
      else
        RtlCopyVolatileMemory(v12, v8, 0x10u);
      v10 = v11;
    }
    v8 += 4;
  }
  *a7 = v10;
  return 0;
}

```

## disassembly

```asm
0x14002378c  push    rbx
0x14002378e  push    rsi
0x14002378f  push    rdi
0x140023790  push    r14
0x140023792  push    r15
0x140023794  sub     rsp, 30h
0x140023798  mov     r15, r9
0x14002379b  mov     rbx, rdx
0x14002379e  mov     [rsp+58h+var_38], 0
0x1400237a3  xor     edi, edi
0x1400237a5  mov     r14d, r8d
0x1400237a8  add     r14, rdx
0x1400237ab  xor     ecx, ecx
0x1400237ad  cmp     rbx, r14
0x1400237b0  jnb     short loc_140023806
0x1400237b2  lea     esi, [rcx+10h]
0x1400237b5  cmp     esi, [rsp+58h+arg_20]
0x1400237bc  ja      short loc_140023806
0x1400237be  mov     eax, cs:FileTag
0x1400237c4  cmp     [rbx+8], eax
0x1400237c7  jz      short loc_1400237FB
0x1400237c9  add     rcx, r15; void *
0x1400237cc  mov     [rsp+58h+var_38], 1
0x1400237d1  mov     r8d, 10h; Size
0x1400237d7  mov     rdx, rbx; Src
0x1400237da  cmp     [rsp+58h+arg_28], 0
0x1400237e2  jz      short loc_1400237EB
0x1400237e4  call    RtlCopyToUser
0x1400237e9  jmp     short loc_1400237F0
0x1400237eb  call    RtlCopyVolatileMemory
0x1400237f0  mov     [rsp+58h+var_38], 0
0x1400237f5  mov     ecx, esi
0x1400237f7  mov     [rsp+58h+var_34], ecx
0x1400237fb  add     rbx, 10h
0x1400237ff  mov     [rsp+58h+var_30], rbx
0x140023804  jmp     short loc_1400237AD
0x140023806  mov     rax, [rsp+58h+arg_30]
0x14002380e  mov     [rax], ecx
0x140023810  jmp     short loc_140023817
0x140023812  mov     edi, 0C00000E8h
0x140023817  mov     eax, edi
0x140023819  add     rsp, 30h
0x14002381d  pop     r15
0x14002381f  pop     r14
0x140023821  pop     rdi
0x140023822  pop     rsi
0x140023823  pop     rbx
0x140023824  retn
0x14003f118  push    rbp
0x14003f11a  sub     rsp, 20h
0x14003f11e  mov     rbp, rdx
0x14003f121  xor     eax, eax
0x14003f123  cmp     [rbp+20h], al
0x14003f126  setnz   al
0x14003f129  add     rsp, 20h
0x14003f12d  pop     rbp
0x14003f12e  retn
```
