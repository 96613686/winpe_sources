# __crtCompareStringW

- ea: `0x18005fe58`
- end: `0x18005ff17`
- name: `__crtCompareStringW`
- size: `191`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800563d0`

## callees

- `0x18005fe58`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005fee3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005fee3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005fe80`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005fea3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005fe80`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005fea3`

## pseudocode

```c
int __fastcall _crtCompareStringW(LPCWSTR lpLocaleName, __int64 a2, const wchar_t *a3, int a4, wchar_t *Source, int a6)
{
  int v6; // ebx
  int cchCount2; // eax
  int result; // eax
  int v11; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = wcsnlen(a3, a4);
  cchCount2 = a6;
  if ( a6 > 0 )
    cchCount2 = wcsnlen(Source, a6);
  if ( v6 && cchCount2 )
    return CompareStringEx(lpLocaleName, 0x1000u, a3, v6, Source, cchCount2, 0, 0, 0);
  v11 = v6 - cchCount2;
  result = ((v11 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v11 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x18005fe58  mov     [rsp+arg_0], rbx
0x18005fe5d  mov     [rsp+arg_8], rbp
0x18005fe62  mov     [rsp+arg_10], rsi
0x18005fe67  push    rdi
0x18005fe68  sub     rsp, 50h
0x18005fe6c  movsxd  rbx, r9d
0x18005fe6f  mov     rsi, r8
0x18005fe72  mov     rbp, rcx
0x18005fe75  test    r9d, r9d
0x18005fe78  jle     short loc_18005FE89
0x18005fe7a  mov     rdx, rbx; MaxCount
0x18005fe7d  mov     rcx, r8; Source
0x18005fe80  call    cs:__imp_wcsnlen
0x18005fe86  mov     rbx, rax
0x18005fe89  movsxd  rax, [rsp+58h+arg_28]
0x18005fe91  mov     rdi, [rsp+58h+Source]
0x18005fe99  test    eax, eax
0x18005fe9b  jle     short loc_18005FEA9
0x18005fe9d  mov     rdx, rax; MaxCount
0x18005fea0  mov     rcx, rdi; Source
0x18005fea3  call    cs:__imp_wcsnlen
0x18005fea9  test    ebx, ebx
0x18005feab  jz      short loc_18005FEEB
0x18005fead  test    eax, eax
0x18005feaf  jz      short loc_18005FEEB
0x18005feb1  mov     [rsp+58h+lParam], 0; lParam
0x18005feba  mov     r9d, ebx; cchCount1
0x18005febd  mov     [rsp+58h+lpReserved], 0; lpReserved
0x18005fec6  mov     r8, rsi; lpString1
0x18005fec9  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x18005fed2  mov     edx, 1000h; dwCmpFlags
0x18005fed7  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18005fedb  mov     rcx, rbp; lpLocaleName
0x18005fede  mov     [rsp+58h+lpString2], rdi; lpString2
0x18005fee3  call    cs:__imp_CompareStringEx
0x18005fee9  jmp     short loc_18005FF02
0x18005feeb  sub     ebx, eax
0x18005feed  mov     ecx, 2
0x18005fef2  mov     eax, ebx
0x18005fef4  sar     eax, 1Fh
0x18005fef7  and     eax, 0FFFFFFFEh
0x18005fefa  add     eax, 3
0x18005fefd  test    ebx, ebx
0x18005feff  cmovz   eax, ecx
0x18005ff02  mov     rbx, [rsp+58h+arg_0]
0x18005ff07  mov     rbp, [rsp+58h+arg_8]
0x18005ff0c  mov     rsi, [rsp+58h+arg_10]
0x18005ff11  add     rsp, 50h
0x18005ff15  pop     rdi
0x18005ff16  retn
```
