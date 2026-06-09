# TSWPathQuoteSpaces(ushort *,uint,ushort const *)

- ea: `0x180046358`
- end: `0x1800465dd`
- name: `?TSWPathQuoteSpaces@@YAJPEAGIPEBG@Z`
- size: `645`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002a9a4`

## callees

- `0x180006cc8`
- `0x18000b1d8`
- `0x18000ec94`
- `0x180045908`
- `0x180046358`
- `0x18009a520`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180046408`
- `msvcrt!wcscpy_s` at `0x1800464f7`
- `msvcrt!wcscpy_s` at `0x180046408`
- `msvcrt!wcscpy_s` at `0x1800464f7`
- `msvcrt!free` at `0x180046582`
- `msvcrt!free` at `0x180046599`
- `msvcrt!free` at `0x1800465af`
- `msvcrt!free` at `0x180046582`
- `msvcrt!free` at `0x180046599`
- `msvcrt!free` at `0x1800465af`
- `msvcrt!memcpy_s` at `0x1800463e0`
- `msvcrt!memcpy_s` at `0x1800464da`
- `msvcrt!memcpy_s` at `0x1800463e0`
- `msvcrt!memcpy_s` at `0x1800464da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004646f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004646f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046562`
- `SHLWAPI!PathQuoteSpacesW` at `0x180046490`
- `SHLWAPI!PathQuoteSpacesW` at `0x180046490`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TSWPathQuoteSpaces(wchar_t *Destination, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned int v7; // ebx
  errno_t v8; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v12; // eax
  unsigned int v13; // ebx
  errno_t v14; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  signed int v18; // eax
  wchar_t *Source; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v21[264]; // [rsp+50h] [rbp-B8h] BYREF
  void *Destinationa; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v23[264]; // [rsp+160h] [rbp+58h] BYREF
  wchar_t sz[264]; // [rsp+268h] [rbp+160h] BYREF

  *Destination = 0;
  Destinationa = v23;
  v5 = -1;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = v6 + 1;
    ATL::AtlConvAllocMemory<unsigned short>(&Destinationa, v7, v23);
    v8 = memcpy_s(Destinationa, 2LL * (int)v7, a3, 2LL * (int)v7);
    ATL::AtlCrtErrorCheck(v8);
  }
  else
  {
    Destinationa = 0;
  }
  sz[0] = 0;
  if ( wcscpy_s(sz, 0x107u, (const wchar_t *)Destinationa) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids,
        CurrentThreadActivityIdPrefix,
        v10);
    }
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
  }
  else
  {
    PathQuoteSpacesW(sz);
    Source = (wchar_t *)v21;
    do
      ++v5;
    while ( sz[v5] );
    ATL::AtlConvAllocMemory<unsigned short>(&Source, (unsigned int)(v5 + 1), v21);
    v14 = memcpy_s(Source, 2LL * ((int)v5 + 1), sz, 2LL * ((int)v5 + 1));
    ATL::AtlCrtErrorCheck(v14);
    *Destination = 0;
    if ( wcscpy_s(Destination, 0x107u, Source) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids, v17, v16);
      }
      v18 = GetLastError();
      v13 = v18;
      if ( v18 > 0 )
        v13 = (unsigned __int16)v18 | 0x80070000;
      if ( Source != (wchar_t *)v21 )
        free(Source);
    }
    else
    {
      if ( Source != (wchar_t *)v21 )
        free(Source);
      v13 = 0;
    }
  }
  if ( Destinationa != v23 )
    free(Destinationa);
  return v13;
}

```

## disassembly

```asm
0x180046358  mov     rax, rsp
0x18004635b  push    rbp
0x18004635c  push    rsi
0x18004635d  push    rdi
0x18004635e  push    r14
0x180046360  push    r15
0x180046362  lea     rbp, [rax-3A8h]
0x180046369  sub     rsp, 480h
0x180046370  mov     qword ptr [rsp+30h], 0FFFFFFFFFFFFFFFEh
0x180046379  mov     [rax+10h], rbx
0x18004637d  mov     rax, cs:__security_cookie
0x180046384  xor     rax, rsp
0x180046387  mov     [rbp+3A0h+var_30], rax
0x18004638e  mov     rsi, r8
0x180046391  mov     r14, rcx
0x180046394  xor     r15d, r15d
0x180046397  mov     [rcx], r15w
0x18004639b  lea     rax, [rbp+3A0h+var_348]
0x18004639f  mov     [rbp+3A0h+Destination], rax
0x1800463a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800463a7  test    r8, r8
0x1800463aa  jnz     short loc_1800463B2
0x1800463ac  mov     [rbp+3A0h+Destination], r15
0x1800463b0  jmp     short loc_1800463EE
0x1800463b2  mov     rbx, rdi
0x1800463b5  inc     rbx
0x1800463b8  cmp     [r8+rbx*2], r15w
0x1800463bd  jnz     short loc_1800463B5
0x1800463bf  inc     ebx
0x1800463c1  lea     r8, [rbp+3A0h+var_348]
0x1800463c5  mov     edx, ebx
0x1800463c7  lea     rcx, [rbp+3A0h+Destination]
0x1800463cb  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x1800463d0  movsxd  rdx, ebx
0x1800463d3  add     rdx, rdx; DestinationSize
0x1800463d6  mov     r9, rdx; SourceSize
0x1800463d9  mov     r8, rsi; Source
0x1800463dc  mov     rcx, [rbp+3A0h+Destination]; Destination
0x1800463e0  call    cs:__imp_memcpy_s
0x1800463e6  mov     ecx, eax; int
0x1800463e8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800463ed  nop
0x1800463ee  mov     [rbp+3A0h+sz], r15w
0x1800463f6  mov     r8, [rbp+3A0h+Destination]; Source
0x1800463fa  mov     esi, 107h
0x1800463ff  mov     edx, esi; SizeInWords
0x180046401  lea     rcx, [rbp+3A0h+sz]; Destination
0x180046408  call    cs:__imp_wcscpy_s
0x18004640e  test    eax, eax
0x180046410  jz      short loc_180046489
0x180046412  lea     rcx, WPP_GLOBAL_Control
0x180046419  mov     edi, 80070000h
0x18004641e  mov     rax, cs:WPP_GLOBAL_Control
0x180046425  cmp     rax, rcx
0x180046428  jz      short loc_18004646F
0x18004642a  test    byte ptr [rax+1Ch], 8
0x18004642e  jz      short loc_18004646F
0x180046430  cmp     byte ptr [rax+19h], 2
0x180046434  jb      short loc_18004646F
0x180046436  call    cs:__imp_GetLastError
0x18004643c  mov     ebx, eax
0x18004643e  test    eax, eax
0x180046440  jle     short loc_180046447
0x180046442  movzx   ebx, ax
0x180046445  or      ebx, edi
0x180046447  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004644c  mov     edx, 0Ch
0x180046451  mov     [rsp+20h], ebx
0x180046455  mov     r9d, eax
0x180046458  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x18004645f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046466  mov     rcx, [rcx+10h]
0x18004646a  call    WPP_SF_Dd
0x18004646f  call    cs:__imp_GetLastError
0x180046475  mov     ebx, eax
0x180046477  test    eax, eax
0x180046479  jle     loc_1800465A2
0x18004647f  movzx   ebx, ax
0x180046482  or      ebx, edi
0x180046484  jmp     loc_1800465A2
0x180046489  lea     rcx, [rbp+3A0h+sz]; lpsz
0x180046490  call    cs:__imp_PathQuoteSpacesW
0x180046496  lea     rax, [rsp+48h]
0x18004649b  mov     [rsp+4A0h+Source], rax
0x1800464a0  lea     rax, [rbp+3A0h+sz]
0x1800464a7  inc     rdi
0x1800464aa  cmp     [rax+rdi*2], r15w
0x1800464af  jnz     short loc_1800464A7
0x1800464b1  lea     ebx, [rdi+1]
0x1800464b4  lea     r8, [rsp+48h]
0x1800464b9  mov     edx, ebx
0x1800464bb  lea     rcx, [rsp+4A0h+Source]
0x1800464c0  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x1800464c5  movsxd  rdx, ebx
0x1800464c8  add     rdx, rdx; DestinationSize
0x1800464cb  mov     r9, rdx; SourceSize
0x1800464ce  lea     r8, [rbp+3A0h+sz]; Source
0x1800464d5  mov     rcx, [rsp+4A0h+Source]; Destination
0x1800464da  call    cs:__imp_memcpy_s
0x1800464e0  mov     ecx, eax; int
0x1800464e2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800464e7  nop
0x1800464e8  mov     [r14], r15w
0x1800464ec  mov     r8, [rsp+4A0h+Source]; Source
0x1800464f1  mov     rdx, rsi; SizeInWords
0x1800464f4  mov     rcx, r14; Destination
0x1800464f7  call    cs:__imp_wcscpy_s
0x1800464fd  test    eax, eax
0x1800464ff  jz      loc_18004658A
0x180046505  lea     rcx, WPP_GLOBAL_Control
0x18004650c  mov     edi, 80070000h
0x180046511  mov     rax, cs:WPP_GLOBAL_Control
0x180046518  cmp     rax, rcx
0x18004651b  jz      short loc_180046562
0x18004651d  test    byte ptr [rax+1Ch], 8
0x180046521  jz      short loc_180046562
0x180046523  cmp     byte ptr [rax+19h], 2
0x180046527  jb      short loc_180046562
0x180046529  call    cs:__imp_GetLastError
0x18004652f  mov     ebx, eax
0x180046531  test    eax, eax
0x180046533  jle     short loc_18004653A
0x180046535  movzx   ebx, ax
0x180046538  or      ebx, edi
0x18004653a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004653f  mov     edx, 0Dh
0x180046544  mov     [rsp+20h], ebx
0x180046548  mov     r9d, eax
0x18004654b  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180046552  mov     rcx, cs:WPP_GLOBAL_Control
0x180046559  mov     rcx, [rcx+10h]
0x18004655d  call    WPP_SF_Dd
0x180046562  call    cs:__imp_GetLastError
0x180046568  mov     ebx, eax
0x18004656a  test    eax, eax
0x18004656c  jle     short loc_180046573
0x18004656e  movzx   ebx, ax
0x180046571  or      ebx, edi
0x180046573  mov     rcx, [rsp+4A0h+Source]; Block
0x180046578  lea     rax, [rsp+48h]
0x18004657d  cmp     rcx, rax
0x180046580  jz      short loc_1800465A2
0x180046582  call    cs:__imp_free
0x180046588  jmp     short loc_1800465A2
0x18004658a  mov     rcx, [rsp+4A0h+Source]; Block
0x18004658f  lea     rax, [rsp+48h]
0x180046594  cmp     rcx, rax
0x180046597  jz      short loc_18004659F
0x180046599  call    cs:__imp_free
0x18004659f  mov     ebx, r15d
0x1800465a2  mov     rcx, [rbp+3A0h+Destination]; Block
0x1800465a6  lea     rax, [rbp+3A0h+var_348]
0x1800465aa  cmp     rcx, rax
0x1800465ad  jz      short loc_1800465B5
0x1800465af  call    cs:__imp_free
0x1800465b5  mov     eax, ebx
0x1800465b7  mov     rcx, [rbp+3A0h+var_30]
0x1800465be  xor     rcx, rsp; StackCookie
0x1800465c1  call    __security_check_cookie
0x1800465c6  mov     rbx, [rsp+4A0h+arg_8]
0x1800465ce  add     rsp, 480h
0x1800465d5  pop     r15
0x1800465d7  pop     r14
0x1800465d9  pop     rdi
0x1800465da  pop     rsi
0x1800465db  pop     rbp
0x1800465dc  retn
```
