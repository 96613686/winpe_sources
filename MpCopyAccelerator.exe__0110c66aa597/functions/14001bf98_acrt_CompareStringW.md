# __acrt_CompareStringW

- ea: `0x14001bf98`
- end: `0x14001c055`
- name: `__acrt_CompareStringW`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001b230`

## callees

- `0x140010f20`
- `0x140015f10`
- `0x14001bf98`

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
0x14001bf98  mov     rax, rsp
0x14001bf9b  mov     [rax+8], rbx
0x14001bf9f  mov     [rax+10h], rbp
0x14001bfa3  mov     [rax+18h], rsi
0x14001bfa7  mov     [rax+20h], rdi
0x14001bfab  push    r14
0x14001bfad  sub     rsp, 50h
0x14001bfb1  movsxd  rbx, r9d
0x14001bfb4  mov     rsi, r8
0x14001bfb7  mov     ebp, edx
0x14001bfb9  mov     r14, rcx
0x14001bfbc  test    r9d, r9d
0x14001bfbf  jle     short loc_14001BFCF
0x14001bfc1  mov     rdx, rbx; MaxCount
0x14001bfc4  mov     rcx, r8; Source
0x14001bfc7  call    wcsnlen
0x14001bfcc  mov     rbx, rax
0x14001bfcf  movsxd  rax, [rsp+58h+arg_28]
0x14001bfd7  mov     rdi, [rsp+58h+Source]
0x14001bfdf  test    eax, eax
0x14001bfe1  jle     short loc_14001BFEE
0x14001bfe3  mov     rdx, rax; MaxCount
0x14001bfe6  mov     rcx, rdi; Source
0x14001bfe9  call    wcsnlen
0x14001bfee  test    ebx, ebx
0x14001bff0  jz      short loc_14001C023
0x14001bff2  test    eax, eax
0x14001bff4  jz      short loc_14001C023
0x14001bff6  and     [rsp+58h+var_18], 0
0x14001bffc  mov     r9d, ebx
0x14001bfff  and     [rsp+58h+var_20], 0
0x14001c005  mov     r8, rsi
0x14001c008  and     [rsp+58h+var_28], 0
0x14001c00e  mov     edx, ebp
0x14001c010  mov     [rsp+58h+var_30], eax
0x14001c014  mov     rcx, r14
0x14001c017  mov     [rsp+58h+var_38], rdi
0x14001c01c  call    __acrt_CompareStringEx
0x14001c021  jmp     short loc_14001C03A
0x14001c023  sub     ebx, eax
0x14001c025  mov     ecx, 2
0x14001c02a  mov     eax, ebx
0x14001c02c  sar     eax, 1Fh
0x14001c02f  and     eax, 0FFFFFFFEh
0x14001c032  add     eax, 3
0x14001c035  test    ebx, ebx
0x14001c037  cmovz   eax, ecx
0x14001c03a  mov     rbx, [rsp+58h+arg_0]
0x14001c03f  mov     rbp, [rsp+58h+arg_8]
0x14001c044  mov     rsi, [rsp+58h+arg_10]
0x14001c049  mov     rdi, [rsp+58h+arg_18]
0x14001c04e  add     rsp, 50h
0x14001c052  pop     r14
0x14001c054  retn
```
