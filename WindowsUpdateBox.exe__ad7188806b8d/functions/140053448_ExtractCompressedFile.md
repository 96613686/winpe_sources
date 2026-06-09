# ExtractCompressedFile

- ea: `0x140053448`
- end: `0x14005363f`
- name: `ExtractCompressedFile`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140054258`

## callees

- `0x140002116`
- `0x140053160`
- `0x140053304`
- `0x140053448`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetShortPathNameW` at `0x1400534bb`
- `KERNEL32!GetShortPathNameW` at `0x1400534bb`
- `Cabinet!__imp_FDICreate` at `0x140053562`
- `Cabinet!__imp_FDICreate` at `0x140053562`
- `Cabinet!__imp_FDICopy` at `0x1400535ad`
- `Cabinet!__imp_FDICopy` at `0x1400535ad`
- `Cabinet!__imp_FDIDestroy` at `0x1400535e8`
- `Cabinet!__imp_FDIDestroy` at `0x1400535e8`

## pseudocode

```c
__int64 __fastcall ExtractCompressedFile(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  const WCHAR *v6; // rcx
  WCHAR *v7; // rdx
  int erfType; // ebx
  HFDI v9; // rax
  LPSTR v10; // rdi
  void *v11; // rsi
  LPSTR pszCabinet; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pvUser; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v15; // [rsp+68h] [rbp-98h]
  ERF perf; // [rsp+78h] [rbp-88h] BYREF
  WCHAR szShortPath[264]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  pszCabinet = 0;
  memset_0(szShortPath, 0, 0x208u);
  v6 = *(const WCHAR **)(a1 + 8);
  pvUser = 0;
  v15 = 0;
  if ( !GetShortPathNameW(v6, szShortPath, 0x104u) || (v7 = szShortPath, !szShortPath[0]) )
    v7 = *(WCHAR **)(a1 + 8);
  erfType = StrAnsiAllocString(&pszCabinet, v7);
  if ( erfType < 0 )
  {
    v10 = pszCabinet;
  }
  else
  {
    pvUser = a3;
    *(_QWORD *)&v15 = 0;
    DWORD2(v15) = 0;
    qword_1400A5DA8 = a1;
    qword_1400A5DA0 = a2;
    v9 = FDICreate(
           CDlpCabHelperT<CEmptyType>::FdiAlloc,
           BoxCabFree,
           (PFNOPEN)BoxCabOpen,
           (PFNREAD)BoxCabRead,
           (PFNWRITE)BoxCabWrite,
           BoxCabClose,
           (PFNSEEK)BoxCabSeek,
           -1,
           &perf);
    v10 = pszCabinet;
    v11 = v9;
    if ( v9 )
    {
      if ( !FDICopy(v9, pszCabinet, (LPSTR)pszCabPath, 0, (PFNFDINOTIFY)BoxCabCallback, 0, &pvUser) || perf.fError )
      {
        erfType = DWORD2(v15);
        if ( (SDWORD2(v15) & 0x80000000) == 0 )
        {
          erfType = perf.erfType;
          if ( perf.erfType )
          {
            if ( perf.erfType > 0 )
              erfType = LOWORD(perf.erfType) | 0x80070000;
          }
          else
          {
            erfType = -2147467259;
          }
        }
      }
      FDIDestroy(v11);
    }
    else
    {
      erfType = -2147467259;
    }
  }
  qword_1400A5DA8 = 0;
  qword_1400A5DA0 = 0;
  if ( v10 )
    MemFree(v10);
  return (unsigned int)erfType;
}

```

## disassembly

```asm
0x140053448  mov     [rsp-8+arg_8], rbx
0x14005344d  push    rbp
0x14005344e  push    rsi
0x14005344f  push    rdi
0x140053450  push    r14
0x140053452  push    r15
0x140053454  lea     rbp, [rsp-1B0h]
0x14005345c  sub     rsp, 2B0h
0x140053463  mov     rax, cs:__security_cookie
0x14005346a  xor     rax, rsp
0x14005346d  mov     [rbp+1D0h+var_30], rax
0x140053474  xor     eax, eax
0x140053476  mov     r14, r8
0x140053479  mov     rsi, rdx
0x14005347c  mov     qword ptr [rsp+2D0h+var_258.erfOper], rax
0x140053481  mov     rdi, rcx
0x140053484  mov     [rbp+1D0h+var_258.fError], eax
0x140053487  xor     r15d, r15d
0x14005348a  lea     rcx, [rbp+1D0h+szShortPath]; void *
0x14005348e  xor     edx, edx; Val
0x140053490  mov     [rsp+2D0h+pszCabinet], r15
0x140053495  mov     r8d, 208h; Size
0x14005349b  call    memset_0
0x1400534a0  mov     rcx, [rdi+8]; lpszLongPath
0x1400534a4  lea     rdx, [rbp+1D0h+szShortPath]; lpszShortPath
0x1400534a8  xorps   xmm0, xmm0
0x1400534ab  mov     r8d, 104h; cchBuffer
0x1400534b1  movups  [rsp+2D0h+pvUser], xmm0
0x1400534b6  movups  [rsp+2D0h+var_268], xmm0
0x1400534bb  call    cs:__imp_GetShortPathNameW
0x1400534c2  nop     dword ptr [rax+rax+00h]
0x1400534c7  test    eax, eax
0x1400534c9  jz      short loc_1400534D6
0x1400534cb  lea     rdx, [rbp+1D0h+szShortPath]
0x1400534cf  cmp     [rbp+1D0h+szShortPath], r15w
0x1400534d4  jnz     short loc_1400534DA
0x1400534d6  mov     rdx, [rdi+8]
0x1400534da  lea     rcx, [rsp+2D0h+pszCabinet]
0x1400534df  call    StrAnsiAllocString
0x1400534e4  mov     ebx, eax
0x1400534e6  test    eax, eax
0x1400534e8  js      loc_1400535F6
0x1400534ee  lea     rax, [rsp+2D0h+var_258]
0x1400534f3  mov     qword ptr [rsp+2D0h+pvUser], r14
0x1400534f8  mov     [rsp+2D0h+perf], rax; perf
0x1400534fd  lea     r9, ?BoxCabRead@@YAI_JPEAXI@Z; pfnread
0x140053504  mov     [rsp+2D0h+cpuType], 0FFFFFFFFh; cpuType
0x14005350c  lea     rax, ?BoxCabSeek@@YAJ_JJH@Z; BoxCabSeek(__int64,long,int)
0x140053513  mov     [rsp+2D0h+pfnseek], rax; pfnseek
0x140053518  lea     r8, ?BoxCabOpen@@YA_JPEADHH@Z; pfnopen
0x14005351f  lea     rax, ?BoxCabClose@@YAH_J@Z; BoxCabClose(__int64)
0x140053526  mov     qword ptr [rsp+2D0h+pvUser+8], r15
0x14005352b  mov     [rsp+2D0h+pfnclose], rax; pfnclose
0x140053530  lea     rdx, ?BoxCabFree@@YAXPEAX@Z; pfnfree
0x140053537  lea     rax, ?BoxCabWrite@@YAI_JPEAXI@Z; BoxCabWrite(__int64,void *,uint)
0x14005353e  mov     qword ptr [rsp+2D0h+var_268], r15
0x140053543  lea     rcx, ?FdiAlloc@?$CDlpCabHelperT@VCEmptyType@@@@CAPEAXK@Z; pfnalloc
0x14005354a  mov     [rsp+2D0h+pfnwrite], rax; pfnwrite
0x14005354f  mov     dword ptr [rsp+2D0h+var_268+8], r15d
0x140053554  mov     cs:qword_1400A5DA8, rdi
0x14005355b  mov     cs:qword_1400A5DA0, rsi
0x140053562  call    cs:__imp_FDICreate
0x140053569  nop     dword ptr [rax+rax+00h]
0x14005356e  mov     rdi, [rsp+2D0h+pszCabinet]
0x140053573  mov     rsi, rax
0x140053576  test    rax, rax
0x140053579  jnz     short loc_140053582
0x14005357b  mov     ebx, 80004005h
0x140053580  jmp     short loc_1400535FB
0x140053582  lea     rax, [rsp+2D0h+pvUser]
0x140053587  xor     r9d, r9d; flags
0x14005358a  mov     [rsp+2D0h+pfnseek], rax; pvUser
0x14005358f  lea     r8, pszCabPath; pszCabPath
0x140053596  lea     rax, ?BoxCabCallback@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; BoxCabCallback(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x14005359d  mov     [rsp+2D0h+pfnclose], r15; pfnfdid
0x1400535a2  mov     rdx, rdi; pszCabinet
0x1400535a5  mov     [rsp+2D0h+pfnwrite], rax; pfnfdin
0x1400535aa  mov     rcx, rsi; hfdi
0x1400535ad  call    cs:__imp_FDICopy
0x1400535b4  nop     dword ptr [rax+rax+00h]
0x1400535b9  test    eax, eax
0x1400535bb  jz      short loc_1400535C3
0x1400535bd  cmp     [rbp+1D0h+var_258.fError], r15d
0x1400535c1  jz      short loc_1400535E5
0x1400535c3  mov     ebx, dword ptr [rsp+2D0h+var_268+8]
0x1400535c7  test    ebx, ebx
0x1400535c9  js      short loc_1400535E5
0x1400535cb  mov     ebx, [rsp+2D0h+var_258.erfType]
0x1400535cf  test    ebx, ebx
0x1400535d1  jz      short loc_1400535E0
0x1400535d3  jle     short loc_1400535E5
0x1400535d5  movzx   ebx, bx
0x1400535d8  or      ebx, 80070000h
0x1400535de  jmp     short loc_1400535E5
0x1400535e0  mov     ebx, 80004005h
0x1400535e5  mov     rcx, rsi; hfdi
0x1400535e8  call    cs:__imp_FDIDestroy
0x1400535ef  nop     dword ptr [rax+rax+00h]
0x1400535f4  jmp     short loc_1400535FB
0x1400535f6  mov     rdi, [rsp+2D0h+pszCabinet]
0x1400535fb  mov     cs:qword_1400A5DA8, r15
0x140053602  mov     cs:qword_1400A5DA0, r15
0x140053609  test    rdi, rdi
0x14005360c  jz      short loc_140053616
0x14005360e  mov     rcx, rdi; lpMem
0x140053611  call    MemFree
0x140053616  mov     eax, ebx
0x140053618  mov     rcx, [rbp+1D0h+var_30]
0x14005361f  xor     rcx, rsp; StackCookie
0x140053622  call    __security_check_cookie
0x140053627  mov     rbx, [rsp+2D0h+arg_8]
0x14005362f  add     rsp, 2B0h
0x140053636  pop     r15
0x140053638  pop     r14
0x14005363a  pop     rdi
0x14005363b  pop     rsi
0x14005363c  pop     rbp
0x14005363d  retn
```
