# ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::FormatV(char const *,char *)

- ea: `0x182d3ca40`
- end: `0x182d3cb19`
- name: `?FormatV@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAXPEBDPEAD@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x182d3c790`

## callees

- `0x1815ce4b0`
- `0x182d3c4e0`
- `0x182d3c7c0`
- `0x182d3ca40`
- `0x182d3d110`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x182d3ca88`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x182d3ca88`

## pseudocode

```c
char *__fastcall ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::FormatV(
        char **a1,
        char *a2,
        va_list a3)
{
  unsigned __int64 *v6; // rax
  int v7; // ebx
  char *result; // rax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v6 = _local_stdio_printf_options();
  v7 = __stdio_common_vsprintf(*v6 | 2, 0, 0, a2, 0, a3);
  if ( v7 < 0 )
    v7 = -1;
  if ( v7 < 0 )
    ATL::AtlThrowImpl(-2147467259);
  if ( ((*((_DWORD *)*a1 - 3) - v7) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<char,0>::PrepareWrite2(a1, (unsigned int)v7);
  ATL::ChTraitsCRT<char>::Format(*a1, v7 + 1, a2, a3);
  if ( v7 > *((_DWORD *)*a1 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v7;
  result = *a1;
  (*a1)[v7] = 0;
  return result;
}

```

## disassembly

```asm
0x182d3ca40  mov     [rsp+arg_8], rbp
0x182d3ca45  mov     [rsp+arg_10], rsi
0x182d3ca4a  push    rdi
0x182d3ca4b  sub     rsp, 30h
0x182d3ca4f  mov     rbp, r8
0x182d3ca52  mov     rsi, rdx
0x182d3ca55  mov     rdi, rcx
0x182d3ca58  test    rdx, rdx
0x182d3ca5b  jz      loc_182D3CAF8
0x182d3ca61  mov     [rsp+38h+arg_0], rbx
0x182d3ca66  call    __local_stdio_printf_options
0x182d3ca6b  mov     [rsp+38h+ArgList], rbp; ArgList
0x182d3ca70  mov     r9, rsi; Format
0x182d3ca73  xor     r8d, r8d; BufferCount
0x182d3ca76  mov     [rsp+38h+Locale], 0; Locale
0x182d3ca7f  xor     edx, edx; Buffer
0x182d3ca81  mov     rcx, [rax]
0x182d3ca84  or      rcx, 2; Options
0x182d3ca88  call    cs:__imp___stdio_common_vsprintf
0x182d3ca8e  mov     ebx, eax
0x182d3ca90  or      eax, 0FFFFFFFFh
0x182d3ca93  test    ebx, ebx
0x182d3ca95  cmovs   ebx, eax
0x182d3ca98  test    ebx, ebx
0x182d3ca9a  js      short loc_182D3CB03
0x182d3ca9c  mov     rax, [rdi]
0x182d3ca9f  mov     ecx, 1
0x182d3caa4  sub     ecx, [rax-8]
0x182d3caa7  mov     eax, [rax-0Ch]
0x182d3caaa  sub     eax, ebx
0x182d3caac  or      ecx, eax
0x182d3caae  jge     short loc_182D3CABA
0x182d3cab0  mov     edx, ebx
0x182d3cab2  mov     rcx, rdi
0x182d3cab5  call    ?PrepareWrite2@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite2(int)
0x182d3caba  mov     rcx, [rdi]; Buffer
0x182d3cabd  lea     eax, [rbx+1]
0x182d3cac0  movsxd  rdx, eax; BufferCount
0x182d3cac3  mov     r9, rbp; ArgList
0x182d3cac6  mov     r8, rsi; Format
0x182d3cac9  call    ?Format@?$ChTraitsCRT@D@ATL@@SAHPEAD_KPEBD0@Z; ATL::ChTraitsCRT<char>::Format(char *,unsigned __int64,char const *,char *)
0x182d3cace  mov     rax, [rdi]
0x182d3cad1  cmp     ebx, [rax-0Ch]
0x182d3cad4  jg      short loc_182D3CB0E
0x182d3cad6  mov     rbp, [rsp+38h+arg_8]
0x182d3cadb  mov     rsi, [rsp+38h+arg_10]
0x182d3cae0  mov     [rax-10h], ebx
0x182d3cae3  mov     rax, [rdi]
0x182d3cae6  movsxd  rcx, ebx
0x182d3cae9  mov     rbx, [rsp+38h+arg_0]
0x182d3caee  mov     byte ptr [rcx+rax], 0
0x182d3caf2  add     rsp, 30h
0x182d3caf6  pop     rdi
0x182d3caf7  retn
0x182d3caf8  mov     ecx, 80070057h; int
0x182d3cafd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x182d3cb03  mov     ecx, 80004005h; int
0x182d3cb08  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x182d3cb0e  mov     ecx, 80070057h; int
0x182d3cb13  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
