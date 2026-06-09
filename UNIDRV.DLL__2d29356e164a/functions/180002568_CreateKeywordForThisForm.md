# CreateKeywordForThisForm

- ea: `0x180002568`
- end: `0x1800027f1`
- name: `CreateKeywordForThisForm`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003340`
- `0x1800039fc`

## callees

- `0x180002568`
- `0x18003bbac`
- `0x180049128`
- `0x1800491dc`
- `0x180075010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x1800026e7`
- `WINSPOOL!GetPrinterDataW` at `0x180002738`
- `WINSPOOL!GetPrinterDataW` at `0x1800026e7`
- `WINSPOOL!GetPrinterDataW` at `0x180002738`
- `KERNEL32!WideCharToMultiByte` at `0x180002780`
- `KERNEL32!WideCharToMultiByte` at `0x180002780`
- `KERNEL32!LocalFree` at `0x1800026f7`
- `KERNEL32!LocalFree` at `0x1800027c3`
- `KERNEL32!LocalFree` at `0x1800026f7`
- `KERNEL32!LocalFree` at `0x1800027c3`
- `KERNEL32!LocalAlloc` at `0x1800026b1`
- `KERNEL32!LocalAlloc` at `0x180002709`
- `KERNEL32!LocalAlloc` at `0x1800026b1`
- `KERNEL32!LocalAlloc` at `0x180002709`

## pseudocode

```c
__int64 __fastcall CreateKeywordForThisForm(
        __int64 a1,
        __int64 (__fastcall **a2)(__int64),
        char *a3,
        __int64 a4,
        _DWORD *a5,
        int a6)
{
  _DWORD *v6; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  const char *v12; // rdi
  __int64 v13; // r13
  HRESULT v14; // ebx
  STRSAFE_LPSTR v15; // r14
  size_t v16; // r15
  BYTE *v17; // rdi
  CHAR *v18; // r14
  const wchar_t *v19; // r13
  __int64 v20; // rax
  void *v21; // rsi
  DWORD PrinterDataW; // eax
  BYTE *v23; // rax
  unsigned __int64 v24; // rsi
  DWORD pcbNeeded; // [rsp+28h] [rbp-28h]
  DWORD pType; // [rsp+40h] [rbp-10h] BYREF
  size_t pcchRemaining; // [rsp+48h] [rbp-8h] BYREF
  STRSAFE_LPSTR ppszDestEnd; // [rsp+A0h] [rbp+50h] BYREF
  DWORD nSize; // [rsp+A8h] [rbp+58h] BYREF
  int v31; // [rsp+ACh] [rbp+5Ch]

  v31 = HIDWORD(a4);
  ppszDestEnd = a3;
  v6 = a5;
  pType = 0;
  pcchRemaining = 64;
  nSize = 0;
  if ( a5 && a3 )
  {
    memset_0(a3, 0, 0x40u);
    v10 = a2[3](a1);
    if ( v10 )
    {
      if ( *(_DWORD *)(v10 + 56) )
      {
        v11 = *(unsigned int *)(v10 + 56) + v10;
        if ( v11 )
        {
          if ( *v6 )
          {
            v12 = (const char *)((unsigned int)*v6 + *(_QWORD *)(v11 + 320));
            if ( v12 )
            {
              v13 = a2[9](a1);
              if ( v13 )
              {
                v14 = StringCchCopyExA(a3, 0x40u, v12, &ppszDestEnd, &pcchRemaining, pcbNeeded);
                if ( v14 < 0 )
                  return (unsigned int)v14;
                if ( pcchRemaining >= (unsigned __int64)(a6 != 0) + 3 )
                {
                  v15 = ppszDestEnd;
                  v16 = pcchRemaining - 1;
                  v17 = 0;
                  *ppszDestEnd = 58;
                  v18 = v15 + 1;
                  v19 = *(const wchar_t **)(v13 + 104);
                  if ( !wcsicmp(v19, L"Microsoft") )
                  {
                    v20 = (*a2)(a1);
                    nSize = 128;
                    v21 = (void *)v20;
                    v17 = (BYTE *)LocalAlloc(0x40u, 0x82u);
                    if ( v17 )
                    {
                      PrinterDataW = GetPrinterDataW(v21, (LPWSTR)L"V4_PDC_Manufacturer", &pType, v17, nSize, &nSize);
                      if ( PrinterDataW != 234 )
                      {
LABEL_16:
                        if ( !PrinterDataW && nSize && pType == 1 )
                        {
                          v17[nSize] = 0;
                          v19 = (const wchar_t *)v17;
                        }
                        goto LABEL_20;
                      }
                      LocalFree(v17);
                      v23 = (BYTE *)LocalAlloc(0x40u, nSize + 2LL);
                      v17 = v23;
                      if ( v23 )
                      {
                        PrinterDataW = GetPrinterDataW(v21, (LPWSTR)L"V4_PDC_Manufacturer", &pType, v23, nSize, &nSize);
                        goto LABEL_16;
                      }
                    }
                  }
LABEL_20:
                  v24 = -1;
                  if ( WideCharToMultiByte(0, 0x400u, v19, -1, v18, v16, 0, 0) )
                  {
                    v18[v16 - 1] = 0;
                    if ( a6 )
                    {
                      do
                        ++v24;
                      while ( v18[v24] );
                      if ( v24 >= v16 - 1 )
                        v18[v16 - 2] = 42;
                      else
                        v18[v24] = 42;
                    }
                  }
                  else
                  {
                    v14 = -2147467259;
                  }
                  if ( v17 )
                    LocalFree(v17);
                  return (unsigned int)v14;
                }
              }
            }
          }
        }
      }
    }
    return (unsigned int)-2147467259;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180002568  mov     [rsp-38h+arg_0], rbx
0x18000256d  mov     qword ptr [rsp-38h+nSize], r9
0x180002572  mov     [rsp-38h+ppszDestEnd], r8
0x180002577  push    rbp
0x180002578  push    rsi
0x180002579  push    rdi
0x18000257a  push    r12
0x18000257c  push    r13
0x18000257e  push    r14
0x180002580  push    r15
0x180002582  mov     rbp, rsp
0x180002585  sub     rsp, 50h
0x180002589  mov     rdi, [rbp+arg_20]
0x18000258d  xor     r14d, r14d
0x180002590  mov     [rbp+pType], r14d
0x180002594  mov     r15d, 40h ; '@'
0x18000259a  mov     [rbp+var_8], r15
0x18000259e  mov     rbx, r8
0x1800025a1  mov     [rbp+nSize], r14d
0x1800025a5  mov     rsi, rdx
0x1800025a8  mov     r12, rcx
0x1800025ab  test    rdi, rdi
0x1800025ae  jz      loc_1800027D4
0x1800025b4  test    rbx, rbx
0x1800025b7  jz      loc_1800027D4
0x1800025bd  mov     r8d, r15d; Size
0x1800025c0  xor     edx, edx; Val
0x1800025c2  mov     rcx, rbx; void *
0x1800025c5  call    memset_0
0x1800025ca  mov     rax, [rsi+18h]
0x1800025ce  mov     rcx, r12
0x1800025d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d6  test    rax, rax
0x1800025d9  jz      loc_1800027CB
0x1800025df  cmp     [rax+38h], r14d
0x1800025e3  jz      loc_1800027CB
0x1800025e9  mov     ecx, [rax+38h]
0x1800025ec  add     rax, rcx
0x1800025ef  jz      loc_1800027CB
0x1800025f5  cmp     [rdi], r14d
0x1800025f8  jz      loc_1800027CB
0x1800025fe  mov     ecx, [rdi]
0x180002600  mov     rdi, [rax+140h]
0x180002607  add     rdi, rcx
0x18000260a  jz      loc_1800027CB
0x180002610  mov     rax, [rsi+48h]
0x180002614  mov     rcx, r12
0x180002617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261c  mov     r13, rax
0x18000261f  test    rax, rax
0x180002622  jz      loc_1800027CB
0x180002628  lea     rax, [rbp+var_8]
0x18000262c  mov     r8, rdi; pszSrc
0x18000262f  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x180002633  mov     [rsp+50h+pcchRemaining], rax; pcchRemaining
0x180002638  mov     edx, r15d; cchDest
0x18000263b  mov     rcx, rbx; pszDest
0x18000263e  call    StringCchCopyExA
0x180002643  mov     ebx, eax
0x180002645  test    eax, eax
0x180002647  js      loc_1800027D0
0x18000264d  mov     ecx, [rbp+arg_28]
0x180002650  mov     r15, [rbp+var_8]
0x180002654  neg     ecx
0x180002656  sbb     rdx, rdx
0x180002659  neg     rdx
0x18000265c  add     rdx, 3
0x180002660  cmp     r15, rdx
0x180002663  jb      loc_1800027CB
0x180002669  mov     r14, [rbp+ppszDestEnd]
0x18000266d  lea     rdx, aMicrosoft; "Microsoft"
0x180002674  dec     r15
0x180002677  xor     edi, edi
0x180002679  mov     byte ptr [r14], 3Ah ; ':'
0x18000267d  inc     r14
0x180002680  mov     r13, [r13+68h]
0x180002684  mov     rcx, r13; String1
0x180002687  call    _wcsicmp
0x18000268c  test    eax, eax
0x18000268e  jnz     loc_180002758
0x180002694  mov     rax, [rsi]
0x180002697  mov     rcx, r12
0x18000269a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269f  mov     edx, 82h; uBytes
0x1800026a4  mov     [rbp+nSize], 80h
0x1800026ab  lea     ecx, [rdi+40h]; uFlags
0x1800026ae  mov     rsi, rax
0x1800026b1  call    cs:__imp_LocalAlloc
0x1800026b7  xor     r12d, r12d
0x1800026ba  mov     rdi, rax
0x1800026bd  test    rax, rax
0x1800026c0  jz      loc_18000275B
0x1800026c6  mov     ecx, [rbp+nSize]
0x1800026c9  lea     rax, [rbp+nSize]
0x1800026cd  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x1800026d2  lea     r8, [rbp+pType]; pType
0x1800026d6  mov     dword ptr [rsp+50h+pcchRemaining], ecx; nSize
0x1800026da  lea     rdx, pValueName; "V4_PDC_Manufacturer"
0x1800026e1  mov     rcx, rsi; hPrinter
0x1800026e4  mov     r9, rdi; pData
0x1800026e7  call    cs:__imp_GetPrinterDataW
0x1800026ed  cmp     eax, 0EAh
0x1800026f2  jnz     short loc_18000273E
0x1800026f4  mov     rcx, rdi; hMem
0x1800026f7  call    cs:__imp_LocalFree
0x1800026fd  mov     edx, [rbp+nSize]
0x180002700  lea     ecx, [r12+40h]; uFlags
0x180002705  add     rdx, 2; uBytes
0x180002709  call    cs:__imp_LocalAlloc
0x18000270f  mov     rdi, rax
0x180002712  test    rax, rax
0x180002715  jz      short loc_18000275B
0x180002717  lea     rax, [rbp+nSize]
0x18000271b  mov     r9, rdi; pData
0x18000271e  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180002723  lea     r8, [rbp+pType]; pType
0x180002727  mov     eax, [rbp+nSize]
0x18000272a  lea     rdx, pValueName; "V4_PDC_Manufacturer"
0x180002731  mov     rcx, rsi; hPrinter
0x180002734  mov     dword ptr [rsp+50h+pcchRemaining], eax; nSize
0x180002738  call    cs:__imp_GetPrinterDataW
0x18000273e  test    eax, eax
0x180002740  jnz     short loc_18000275B
0x180002742  mov     eax, [rbp+nSize]
0x180002745  test    eax, eax
0x180002747  jz      short loc_18000275B
0x180002749  cmp     [rbp+pType], 1
0x18000274d  jnz     short loc_18000275B
0x18000274f  mov     [rax+rdi], r12b
0x180002753  mov     r13, rdi
0x180002756  jmp     short loc_18000275B
0x180002758  xor     r12d, r12d
0x18000275b  mov     [rsp+50h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180002760  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002764  mov     [rsp+50h+lpDefaultChar], r12; lpDefaultChar
0x180002769  mov     r9d, esi; cchWideChar
0x18000276c  mov     dword ptr [rsp+50h+pcbNeeded], r15d; cbMultiByte
0x180002771  mov     r8, r13; lpWideCharStr
0x180002774  mov     edx, 400h; dwFlags
0x180002779  mov     [rsp+50h+pcchRemaining], r14; lpMultiByteStr
0x18000277e  xor     ecx, ecx; CodePage
0x180002780  call    cs:__imp_WideCharToMultiByte
0x180002786  test    eax, eax
0x180002788  jz      short loc_1800027B6
0x18000278a  mov     [r15+r14-1], r12b
0x18000278f  cmp     [rbp+arg_28], r12d
0x180002793  jz      short loc_1800027BB
0x180002795  inc     rsi
0x180002798  cmp     [r14+rsi], r12b
0x18000279c  jnz     short loc_180002795
0x18000279e  lea     rax, [r15-1]
0x1800027a2  cmp     rsi, rax
0x1800027a5  jnb     short loc_1800027AE
0x1800027a7  mov     byte ptr [rsi+r14], 2Ah ; '*'
0x1800027ac  jmp     short loc_1800027BB
0x1800027ae  mov     byte ptr [r15+r14-2], 2Ah ; '*'
0x1800027b4  jmp     short loc_1800027BB
0x1800027b6  mov     ebx, 80004005h
0x1800027bb  test    rdi, rdi
0x1800027be  jz      short loc_1800027D0
0x1800027c0  mov     rcx, rdi; hMem
0x1800027c3  call    cs:__imp_LocalFree
0x1800027c9  jmp     short loc_1800027D0
0x1800027cb  mov     ebx, 80004005h
0x1800027d0  mov     eax, ebx
0x1800027d2  jmp     short loc_1800027D9
0x1800027d4  mov     eax, 80070057h
0x1800027d9  mov     rbx, [rsp+50h+arg_0]
0x1800027e1  add     rsp, 50h
0x1800027e5  pop     r15
0x1800027e7  pop     r14
0x1800027e9  pop     r13
0x1800027eb  pop     r12
0x1800027ed  pop     rdi
0x1800027ee  pop     rsi
0x1800027ef  pop     rbp
0x1800027f0  retn
```
