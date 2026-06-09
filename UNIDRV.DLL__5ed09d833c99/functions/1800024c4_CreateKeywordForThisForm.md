# CreateKeywordForThisForm

- ea: `0x1800024c4`
- end: `0x180002778`
- name: `CreateKeywordForThisForm`
- size: `692`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall **)(__int64), char *, __int64, _DWORD *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003304`
- `0x1800039d4`

## callees

- `0x1800024c4`
- `0x18003ca04`
- `0x18004a668`
- `0x18004a71c`
- `0x180077010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180002649`
- `WINSPOOL!GetPrinterDataW` at `0x1800026ac`
- `WINSPOOL!GetPrinterDataW` at `0x180002649`
- `WINSPOOL!GetPrinterDataW` at `0x1800026ac`
- `KERNEL32!WideCharToMultiByte` at `0x1800026fa`
- `KERNEL32!WideCharToMultiByte` at `0x1800026fa`
- `KERNEL32!LocalFree` at `0x18000265f`
- `KERNEL32!LocalFree` at `0x180002743`
- `KERNEL32!LocalFree` at `0x18000265f`
- `KERNEL32!LocalFree` at `0x180002743`
- `KERNEL32!LocalAlloc` at `0x18000260d`
- `KERNEL32!LocalAlloc` at `0x180002677`
- `KERNEL32!LocalAlloc` at `0x18000260d`
- `KERNEL32!LocalAlloc` at `0x180002677`

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
0x1800024c4  mov     [rsp-38h+arg_0], rbx
0x1800024c9  mov     qword ptr [rsp-38h+nSize], r9
0x1800024ce  mov     [rsp-38h+ppszDestEnd], r8
0x1800024d3  push    rbp
0x1800024d4  push    rsi
0x1800024d5  push    rdi
0x1800024d6  push    r12
0x1800024d8  push    r13
0x1800024da  push    r14
0x1800024dc  push    r15
0x1800024de  mov     rbp, rsp
0x1800024e1  sub     rsp, 50h
0x1800024e5  mov     rdi, [rbp+arg_20]
0x1800024e9  xor     r14d, r14d
0x1800024ec  mov     [rbp+pType], r14d
0x1800024f0  mov     r15d, 40h ; '@'
0x1800024f6  mov     [rbp+var_8], r15
0x1800024fa  mov     rbx, r8
0x1800024fd  mov     [rbp+nSize], r14d
0x180002501  mov     rsi, rdx
0x180002504  mov     r12, rcx
0x180002507  test    rdi, rdi
0x18000250a  jz      loc_18000275A
0x180002510  test    rbx, rbx
0x180002513  jz      loc_18000275A
0x180002519  mov     r8d, r15d; Size
0x18000251c  xor     edx, edx; Val
0x18000251e  mov     rcx, rbx; void *
0x180002521  call    memset_0
0x180002526  mov     rax, [rsi+18h]
0x18000252a  mov     rcx, r12
0x18000252d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002532  test    rax, rax
0x180002535  jz      loc_180002751
0x18000253b  cmp     [rax+38h], r14d
0x18000253f  jz      loc_180002751
0x180002545  mov     ecx, [rax+38h]
0x180002548  add     rax, rcx
0x18000254b  jz      loc_180002751
0x180002551  cmp     [rdi], r14d
0x180002554  jz      loc_180002751
0x18000255a  mov     ecx, [rdi]
0x18000255c  mov     rdi, [rax+140h]
0x180002563  add     rdi, rcx
0x180002566  jz      loc_180002751
0x18000256c  mov     rax, [rsi+48h]
0x180002570  mov     rcx, r12
0x180002573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002578  mov     r13, rax
0x18000257b  test    rax, rax
0x18000257e  jz      loc_180002751
0x180002584  lea     rax, [rbp+var_8]
0x180002588  mov     r8, rdi; pszSrc
0x18000258b  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x18000258f  mov     [rsp+50h+pcchRemaining], rax; pcchRemaining
0x180002594  mov     edx, r15d; cchDest
0x180002597  mov     rcx, rbx; pszDest
0x18000259a  call    StringCchCopyExA
0x18000259f  mov     ebx, eax
0x1800025a1  test    eax, eax
0x1800025a3  js      loc_180002756
0x1800025a9  mov     ecx, [rbp+arg_28]
0x1800025ac  mov     r15, [rbp+var_8]
0x1800025b0  neg     ecx
0x1800025b2  sbb     rdx, rdx
0x1800025b5  neg     rdx
0x1800025b8  add     rdx, 3
0x1800025bc  cmp     r15, rdx
0x1800025bf  jb      loc_180002751
0x1800025c5  mov     r14, [rbp+ppszDestEnd]
0x1800025c9  lea     rdx, aMicrosoft; "Microsoft"
0x1800025d0  dec     r15
0x1800025d3  xor     edi, edi
0x1800025d5  mov     byte ptr [r14], 3Ah ; ':'
0x1800025d9  inc     r14
0x1800025dc  mov     r13, [r13+68h]
0x1800025e0  mov     rcx, r13; String1
0x1800025e3  call    _wcsicmp
0x1800025e8  test    eax, eax
0x1800025ea  jnz     loc_1800026D2
0x1800025f0  mov     rax, [rsi]
0x1800025f3  mov     rcx, r12
0x1800025f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025fb  mov     edx, 82h; uBytes
0x180002600  mov     [rbp+nSize], 80h
0x180002607  lea     ecx, [rdi+40h]; uFlags
0x18000260a  mov     rsi, rax
0x18000260d  call    cs:__imp_LocalAlloc
0x180002614  nop     dword ptr [rax+rax+00h]
0x180002619  xor     r12d, r12d
0x18000261c  mov     rdi, rax
0x18000261f  test    rax, rax
0x180002622  jz      loc_1800026D5
0x180002628  mov     ecx, [rbp+nSize]
0x18000262b  lea     rax, [rbp+nSize]
0x18000262f  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180002634  lea     r8, [rbp+pType]; pType
0x180002638  mov     dword ptr [rsp+50h+pcchRemaining], ecx; nSize
0x18000263c  lea     rdx, pValueName; "V4_PDC_Manufacturer"
0x180002643  mov     rcx, rsi; hPrinter
0x180002646  mov     r9, rdi; pData
0x180002649  call    cs:__imp_GetPrinterDataW
0x180002650  nop     dword ptr [rax+rax+00h]
0x180002655  cmp     eax, 0EAh
0x18000265a  jnz     short loc_1800026B8
0x18000265c  mov     rcx, rdi; hMem
0x18000265f  call    cs:__imp_LocalFree
0x180002666  nop     dword ptr [rax+rax+00h]
0x18000266b  mov     edx, [rbp+nSize]
0x18000266e  lea     ecx, [r12+40h]; uFlags
0x180002673  add     rdx, 2; uBytes
0x180002677  call    cs:__imp_LocalAlloc
0x18000267e  nop     dword ptr [rax+rax+00h]
0x180002683  mov     rdi, rax
0x180002686  test    rax, rax
0x180002689  jz      short loc_1800026D5
0x18000268b  lea     rax, [rbp+nSize]
0x18000268f  mov     r9, rdi; pData
0x180002692  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180002697  lea     r8, [rbp+pType]; pType
0x18000269b  mov     eax, [rbp+nSize]
0x18000269e  lea     rdx, pValueName; "V4_PDC_Manufacturer"
0x1800026a5  mov     rcx, rsi; hPrinter
0x1800026a8  mov     dword ptr [rsp+50h+pcchRemaining], eax; nSize
0x1800026ac  call    cs:__imp_GetPrinterDataW
0x1800026b3  nop     dword ptr [rax+rax+00h]
0x1800026b8  test    eax, eax
0x1800026ba  jnz     short loc_1800026D5
0x1800026bc  mov     eax, [rbp+nSize]
0x1800026bf  test    eax, eax
0x1800026c1  jz      short loc_1800026D5
0x1800026c3  cmp     [rbp+pType], 1
0x1800026c7  jnz     short loc_1800026D5
0x1800026c9  mov     [rax+rdi], r12b
0x1800026cd  mov     r13, rdi
0x1800026d0  jmp     short loc_1800026D5
0x1800026d2  xor     r12d, r12d
0x1800026d5  mov     [rsp+50h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800026da  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800026de  mov     [rsp+50h+lpDefaultChar], r12; lpDefaultChar
0x1800026e3  mov     r9d, esi; cchWideChar
0x1800026e6  mov     dword ptr [rsp+50h+pcbNeeded], r15d; cbMultiByte
0x1800026eb  mov     r8, r13; lpWideCharStr
0x1800026ee  mov     edx, 400h; dwFlags
0x1800026f3  mov     [rsp+50h+pcchRemaining], r14; lpMultiByteStr
0x1800026f8  xor     ecx, ecx; CodePage
0x1800026fa  call    cs:__imp_WideCharToMultiByte
0x180002701  nop     dword ptr [rax+rax+00h]
0x180002706  test    eax, eax
0x180002708  jz      short loc_180002736
0x18000270a  mov     [r15+r14-1], r12b
0x18000270f  cmp     [rbp+arg_28], r12d
0x180002713  jz      short loc_18000273B
0x180002715  inc     rsi
0x180002718  cmp     [r14+rsi], r12b
0x18000271c  jnz     short loc_180002715
0x18000271e  lea     rax, [r15-1]
0x180002722  cmp     rsi, rax
0x180002725  jnb     short loc_18000272E
0x180002727  mov     byte ptr [rsi+r14], 2Ah ; '*'
0x18000272c  jmp     short loc_18000273B
0x18000272e  mov     byte ptr [r15+r14-2], 2Ah ; '*'
0x180002734  jmp     short loc_18000273B
0x180002736  mov     ebx, 80004005h
0x18000273b  test    rdi, rdi
0x18000273e  jz      short loc_180002756
0x180002740  mov     rcx, rdi; hMem
0x180002743  call    cs:__imp_LocalFree
0x18000274a  nop     dword ptr [rax+rax+00h]
0x18000274f  jmp     short loc_180002756
0x180002751  mov     ebx, 80004005h
0x180002756  mov     eax, ebx
0x180002758  jmp     short loc_18000275F
0x18000275a  mov     eax, 80070057h
0x18000275f  mov     rbx, [rsp+50h+arg_0]
0x180002767  add     rsp, 50h
0x18000276b  pop     r15
0x18000276d  pop     r14
0x18000276f  pop     r13
0x180002771  pop     r12
0x180002773  pop     rdi
0x180002774  pop     rsi
0x180002775  pop     rbp
0x180002776  retn
```
