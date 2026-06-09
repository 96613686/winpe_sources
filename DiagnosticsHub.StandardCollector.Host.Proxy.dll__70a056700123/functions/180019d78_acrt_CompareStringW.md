# __acrt_CompareStringW

- ea: `0x180019d78`
- end: `0x180019e35`
- name: `__acrt_CompareStringW`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800135a0`
- `0x180013740`

## callees

- `0x18000cf0c`
- `0x180018500`
- `0x180019d78`

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
0x180019d78  mov     rax, rsp
0x180019d7b  mov     [rax+8], rbx
0x180019d7f  mov     [rax+10h], rbp
0x180019d83  mov     [rax+18h], rsi
0x180019d87  mov     [rax+20h], rdi
0x180019d8b  push    r14
0x180019d8d  sub     rsp, 50h
0x180019d91  movsxd  rbx, r9d
0x180019d94  mov     rsi, r8
0x180019d97  mov     ebp, edx
0x180019d99  mov     r14, rcx
0x180019d9c  test    r9d, r9d
0x180019d9f  jle     short loc_180019DAF
0x180019da1  mov     rdx, rbx; MaxCount
0x180019da4  mov     rcx, r8; Source
0x180019da7  call    wcsnlen
0x180019dac  mov     rbx, rax
0x180019daf  movsxd  rax, [rsp+58h+arg_28]
0x180019db7  mov     rdi, [rsp+58h+Source]
0x180019dbf  test    eax, eax
0x180019dc1  jle     short loc_180019DCE
0x180019dc3  mov     rdx, rax; MaxCount
0x180019dc6  mov     rcx, rdi; Source
0x180019dc9  call    wcsnlen
0x180019dce  test    ebx, ebx
0x180019dd0  jz      short loc_180019E03
0x180019dd2  test    eax, eax
0x180019dd4  jz      short loc_180019E03
0x180019dd6  and     [rsp+58h+var_18], 0
0x180019ddc  mov     r9d, ebx
0x180019ddf  and     [rsp+58h+var_20], 0
0x180019de5  mov     r8, rsi
0x180019de8  and     [rsp+58h+var_28], 0
0x180019dee  mov     edx, ebp
0x180019df0  mov     [rsp+58h+var_30], eax
0x180019df4  mov     rcx, r14
0x180019df7  mov     [rsp+58h+var_38], rdi
0x180019dfc  call    __acrt_CompareStringEx
0x180019e01  jmp     short loc_180019E1A
0x180019e03  sub     ebx, eax
0x180019e05  mov     ecx, 2
0x180019e0a  mov     eax, ebx
0x180019e0c  sar     eax, 1Fh
0x180019e0f  and     eax, 0FFFFFFFEh
0x180019e12  add     eax, 3
0x180019e15  test    ebx, ebx
0x180019e17  cmovz   eax, ecx
0x180019e1a  mov     rbx, [rsp+58h+arg_0]
0x180019e1f  mov     rbp, [rsp+58h+arg_8]
0x180019e24  mov     rsi, [rsp+58h+arg_10]
0x180019e29  mov     rdi, [rsp+58h+arg_18]
0x180019e2e  add     rsp, 50h
0x180019e32  pop     r14
0x180019e34  retn
```
