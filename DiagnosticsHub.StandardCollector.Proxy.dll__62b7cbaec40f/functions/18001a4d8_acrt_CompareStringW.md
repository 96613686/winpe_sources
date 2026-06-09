# __acrt_CompareStringW

- ea: `0x18001a4d8`
- end: `0x18001a595`
- name: `__acrt_CompareStringW`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013d00`
- `0x180013ea0`

## callees

- `0x18000d66c`
- `0x180018c60`
- `0x18001a4d8`

## pseudocode

```c
int __fastcall _acrt_CompareStringW(__int64 a1, DWORD a2, const wchar_t *a3, int a4, wchar_t *Source, int a6)
{
  unsigned int v6; // ebx
  int v10; // eax
  int result; // eax
  int v12; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = wcsnlen(a3, a4);
  v10 = a6;
  if ( a6 > 0 )
    v10 = wcsnlen(Source, a6);
  if ( v6 && v10 )
    return _acrt_CompareStringEx(a1, a2, a3, v6, Source, v10, 0, 0, 0);
  v12 = v6 - v10;
  result = ((v12 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v12 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x18001a4d8  mov     rax, rsp
0x18001a4db  mov     [rax+8], rbx
0x18001a4df  mov     [rax+10h], rbp
0x18001a4e3  mov     [rax+18h], rsi
0x18001a4e7  mov     [rax+20h], rdi
0x18001a4eb  push    r14
0x18001a4ed  sub     rsp, 50h
0x18001a4f1  movsxd  rbx, r9d
0x18001a4f4  mov     rsi, r8
0x18001a4f7  mov     ebp, edx
0x18001a4f9  mov     r14, rcx
0x18001a4fc  test    r9d, r9d
0x18001a4ff  jle     short loc_18001A50F
0x18001a501  mov     rdx, rbx; MaxCount
0x18001a504  mov     rcx, r8; Source
0x18001a507  call    wcsnlen
0x18001a50c  mov     rbx, rax
0x18001a50f  movsxd  rax, [rsp+58h+arg_28]
0x18001a517  mov     rdi, [rsp+58h+Source]
0x18001a51f  test    eax, eax
0x18001a521  jle     short loc_18001A52E
0x18001a523  mov     rdx, rax; MaxCount
0x18001a526  mov     rcx, rdi; Source
0x18001a529  call    wcsnlen
0x18001a52e  test    ebx, ebx
0x18001a530  jz      short loc_18001A563
0x18001a532  test    eax, eax
0x18001a534  jz      short loc_18001A563
0x18001a536  and     [rsp+58h+var_18], 0
0x18001a53c  mov     r9d, ebx
0x18001a53f  and     [rsp+58h+var_20], 0
0x18001a545  mov     r8, rsi
0x18001a548  and     [rsp+58h+var_28], 0
0x18001a54e  mov     edx, ebp
0x18001a550  mov     [rsp+58h+var_30], eax
0x18001a554  mov     rcx, r14
0x18001a557  mov     [rsp+58h+var_38], rdi
0x18001a55c  call    __acrt_CompareStringEx
0x18001a561  jmp     short loc_18001A57A
0x18001a563  sub     ebx, eax
0x18001a565  mov     ecx, 2
0x18001a56a  mov     eax, ebx
0x18001a56c  sar     eax, 1Fh
0x18001a56f  and     eax, 0FFFFFFFEh
0x18001a572  add     eax, 3
0x18001a575  test    ebx, ebx
0x18001a577  cmovz   eax, ecx
0x18001a57a  mov     rbx, [rsp+58h+arg_0]
0x18001a57f  mov     rbp, [rsp+58h+arg_8]
0x18001a584  mov     rsi, [rsp+58h+arg_10]
0x18001a589  mov     rdi, [rsp+58h+arg_18]
0x18001a58e  add     rsp, 50h
0x18001a592  pop     r14
0x18001a594  retn
```
