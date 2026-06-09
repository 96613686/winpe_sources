# __crtCompareStringW

- ea: `0x1800efa8c`
- end: `0x1800efb33`
- name: `__crtCompareStringW`
- size: `167`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ef8ec`

## callees

- `0x1800efa8c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800efb0c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800efb0c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800efaa9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800efacc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800efaa9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800efacc`

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
  if ( !v11 )
    return 2;
  result = 3;
  if ( v11 < 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800efa8c  push    rbx
0x1800efa8e  push    rbp
0x1800efa8f  push    rsi
0x1800efa90  push    rdi
0x1800efa91  sub     rsp, 58h
0x1800efa95  movsxd  rbx, r9d
0x1800efa98  mov     rsi, r8
0x1800efa9b  mov     rbp, rcx
0x1800efa9e  test    r9d, r9d
0x1800efaa1  jle     short loc_1800EFAB2
0x1800efaa3  mov     rdx, rbx; MaxCount
0x1800efaa6  mov     rcx, r8; Source
0x1800efaa9  call    cs:__imp_wcsnlen
0x1800efaaf  mov     rbx, rax
0x1800efab2  movsxd  rax, [rsp+78h+arg_28]
0x1800efaba  mov     rdi, [rsp+78h+Source]
0x1800efac2  test    eax, eax
0x1800efac4  jle     short loc_1800EFAD2
0x1800efac6  mov     rdx, rax; MaxCount
0x1800efac9  mov     rcx, rdi; Source
0x1800efacc  call    cs:__imp_wcsnlen
0x1800efad2  test    ebx, ebx
0x1800efad4  jz      short loc_1800EFB14
0x1800efad6  test    eax, eax
0x1800efad8  jz      short loc_1800EFB14
0x1800efada  mov     [rsp+78h+lParam], 0; lParam
0x1800efae3  mov     r9d, ebx; cchCount1
0x1800efae6  mov     [rsp+78h+lpReserved], 0; lpReserved
0x1800efaef  mov     r8, rsi; lpString1
0x1800efaf2  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x1800efafb  mov     edx, 1000h; dwCmpFlags
0x1800efb00  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1800efb04  mov     rcx, rbp; lpLocaleName
0x1800efb07  mov     [rsp+78h+lpString2], rdi; lpString2
0x1800efb0c  call    cs:__imp_CompareStringEx
0x1800efb12  jmp     short loc_1800EFB2A
0x1800efb14  sub     ebx, eax
0x1800efb16  jnz     short loc_1800EFB1D
0x1800efb18  lea     eax, [rbx+2]
0x1800efb1b  jmp     short loc_1800EFB2A
0x1800efb1d  mov     eax, 3
0x1800efb22  test    ebx, ebx
0x1800efb24  lea     ecx, [rax-2]
0x1800efb27  cmovs   eax, ecx
0x1800efb2a  add     rsp, 58h
0x1800efb2e  pop     rdi
0x1800efb2f  pop     rsi
0x1800efb30  pop     rbp
0x1800efb31  pop     rbx
0x1800efb32  retn
```
