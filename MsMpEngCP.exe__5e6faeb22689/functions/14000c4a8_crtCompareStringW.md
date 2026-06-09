# __crtCompareStringW

- ea: `0x14000c4a8`
- end: `0x14000c565`
- name: `__crtCompareStringW`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b1e0`

## callees

- `0x140008bb0`
- `0x1400095fc`
- `0x14000c4a8`

## pseudocode

```c
int __fastcall _crtCompareStringW(__int64 a1, DWORD a2, const WCHAR *a3, int a4, const WCHAR *a5, int a6)
{
  unsigned int v6; // ebx
  int v10; // eax
  int result; // eax
  int v12; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = sub_140008BB0(a3, a4);
  v10 = a6;
  if ( a6 > 0 )
    v10 = sub_140008BB0(a5, a6);
  if ( v6 && v10 )
    return sub_1400095FC(a1, a2, a3, v6, a5, v10, 0, 0, 0);
  v12 = v6 - v10;
  result = ((v12 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v12 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x14000c4a8  mov     rax, rsp
0x14000c4ab  mov     [rax+8], rbx
0x14000c4af  mov     [rax+10h], rbp
0x14000c4b3  mov     [rax+18h], rsi
0x14000c4b7  mov     [rax+20h], rdi
0x14000c4bb  push    r14
0x14000c4bd  sub     rsp, 50h
0x14000c4c1  movsxd  rbx, r9d
0x14000c4c4  mov     rsi, r8
0x14000c4c7  mov     ebp, edx
0x14000c4c9  mov     r14, rcx
0x14000c4cc  test    r9d, r9d
0x14000c4cf  jle     short loc_14000C4DF
0x14000c4d1  mov     rdx, rbx
0x14000c4d4  mov     rcx, r8
0x14000c4d7  call    sub_140008BB0
0x14000c4dc  mov     rbx, rax
0x14000c4df  movsxd  rax, [rsp+58h+arg_28]
0x14000c4e7  mov     rdi, [rsp+58h+arg_20]
0x14000c4ef  test    eax, eax
0x14000c4f1  jle     short loc_14000C4FE
0x14000c4f3  mov     rdx, rax
0x14000c4f6  mov     rcx, rdi
0x14000c4f9  call    sub_140008BB0
0x14000c4fe  test    ebx, ebx
0x14000c500  jz      short loc_14000C533
0x14000c502  test    eax, eax
0x14000c504  jz      short loc_14000C533
0x14000c506  and     [rsp+58h+var_18], 0
0x14000c50c  mov     r9d, ebx
0x14000c50f  and     [rsp+58h+var_20], 0
0x14000c515  mov     r8, rsi
0x14000c518  and     [rsp+58h+var_28], 0
0x14000c51e  mov     edx, ebp
0x14000c520  mov     [rsp+58h+var_30], eax
0x14000c524  mov     rcx, r14
0x14000c527  mov     [rsp+58h+var_38], rdi
0x14000c52c  call    sub_1400095FC
0x14000c531  jmp     short loc_14000C54A
0x14000c533  sub     ebx, eax
0x14000c535  mov     ecx, 2
0x14000c53a  mov     eax, ebx
0x14000c53c  sar     eax, 1Fh
0x14000c53f  and     eax, 0FFFFFFFEh
0x14000c542  add     eax, 3
0x14000c545  test    ebx, ebx
0x14000c547  cmovz   eax, ecx
0x14000c54a  mov     rbx, [rsp+58h+arg_0]
0x14000c54f  mov     rbp, [rsp+58h+arg_8]
0x14000c554  mov     rsi, [rsp+58h+arg_10]
0x14000c559  mov     rdi, [rsp+58h+arg_18]
0x14000c55e  add     rsp, 50h
0x14000c562  pop     r14
0x14000c564  retn
```
