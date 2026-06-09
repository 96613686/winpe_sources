# AreAllPrintQueueEmpty(void)

- ea: `0x18000b11c`
- end: `0x18000b2a0`
- name: `?AreAllPrintQueueEmpty@@YA_NXZ`
- size: `388`
- prototype: `char(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000aeb4`
- `0x18000eee4`

## callees

- `0x180008008`
- `0x180008074`
- `0x180009c10`
- `0x180009c6c`
- `0x18000b11c`
- `0x18000eca4`
- `0x18000f118`
- `0x18000f19c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16e`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b15c`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b1c0`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b15c`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b1c0`

## string_xrefs

- `0x18000b179`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b1ce`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
char AreAllPrintQueueEmpty(void)
{
  unsigned int v0; // r8d
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rdx
  unsigned __int64 i; // rcx
  PrintJobCleanUpUtil *v5; // rbx
  PrintJobCleanUpUtil *v7; // rbx
  DWORD cbBuf; // [rsp+20h] [rbp-50h]
  PrintJobCleanUpUtil *v9; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+50h] [rbp-20h]
  LPBYTE pPrinterEnum[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  DWORD pcbNeeded; // [rsp+80h] [rbp+10h] BYREF
  DWORD pcReturned; // [rsp+88h] [rbp+18h] BYREF

  pcbNeeded = 0;
  pcReturned = 0;
  if ( EnumPrintersW(2u, 0, 2u, 0, 0, &pcbNeeded, &pcReturned) )
  {
    if ( pcbNeeded )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x70, v0, (const char *)0x8000FFFFLL, cbBuf);
  }
  else
  {
    if ( GetLastError() != 122 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
        v1);
    std::vector<unsigned char>::vector<unsigned char>(pPrinterEnum, pcbNeeded);
    if ( !EnumPrintersW(2u, 0, 2u, pPrinterEnum[0], pcbNeeded, &pcbNeeded, &pcReturned) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x75,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
        v2);
    std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>(&v9);
    for ( i = 0; i < pcReturned; ++i )
    {
      if ( *(_DWORD *)(136 * i + v3 + 128) )
      {
        v5 = v9;
        if ( v9 )
        {
          std::_Destroy_range<std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>>(v9);
          std::_Deallocate<16>(v5, (v10 - (_QWORD)v5) & 0xFFFFFFFFFFFFFFF0uLL);
        }
        std::vector<unsigned char>::_Tidy(pPrinterEnum);
        return 0;
      }
    }
    v7 = v9;
    if ( v9 )
    {
      std::_Destroy_range<std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>>(v9);
      std::_Deallocate<16>(v7, (v10 - (_QWORD)v7) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    std::vector<unsigned char>::_Tidy(pPrinterEnum);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b11c  mov     [rsp-8+arg_10], rbx
0x18000b121  push    rbp
0x18000b122  mov     rbp, rsp
0x18000b125  sub     rsp, 70h
0x18000b129  mov     [rbp+arg_0], 0
0x18000b130  mov     [rbp+arg_8], 0
0x18000b137  lea     rax, [rbp+arg_8]
0x18000b13b  mov     [rsp+70h+pcReturned], rax; pcReturned
0x18000b140  lea     rax, [rbp+arg_0]
0x18000b144  mov     [rsp+70h+pcbNeeded], rax; pcbNeeded
0x18000b149  mov     [rsp+70h+cbBuf], 0; int
0x18000b151  xor     r9d, r9d; pPrinterEnum
0x18000b154  xor     edx, edx; Name
0x18000b156  lea     ecx, [rdx+2]; Flags
0x18000b159  mov     r8d, ecx; Level
0x18000b15c  call    cs:__imp_EnumPrintersW
0x18000b162  test    eax, eax
0x18000b164  jnz     loc_18000B281
0x18000b16a  mov     rbx, [rbp+8]
0x18000b16e  call    cs:__imp_GetLastError
0x18000b174  cmp     eax, 7Ah ; 'z'
0x18000b177  jz      short loc_18000B18E
0x18000b179  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b180  mov     edx, 66h ; 'f'; void *
0x18000b185  mov     rcx, rbx; this
0x18000b188  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b18e  mov     edx, [rbp+arg_0]
0x18000b191  lea     rcx, [rbp+pPrinterEnum]
0x18000b195  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000b19a  nop
0x18000b19b  mov     eax, [rbp+arg_0]
0x18000b19e  lea     rdx, [rbp+arg_8]
0x18000b1a2  mov     [rsp+70h+pcReturned], rdx; pcReturned
0x18000b1a7  lea     rdx, [rbp+arg_0]
0x18000b1ab  mov     [rsp+70h+pcbNeeded], rdx; pcbNeeded
0x18000b1b0  mov     [rsp+70h+cbBuf], eax; cbBuf
0x18000b1b4  mov     r9, [rbp+pPrinterEnum]; pPrinterEnum
0x18000b1b8  xor     edx, edx; Name
0x18000b1ba  lea     ecx, [rdx+2]; Flags
0x18000b1bd  mov     r8d, ecx; Level
0x18000b1c0  call    cs:__imp_EnumPrintersW
0x18000b1c6  mov     rcx, [rbp+8]; this
0x18000b1ca  test    eax, eax
0x18000b1cc  jnz     short loc_18000B1DE
0x18000b1ce  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b1d5  lea     edx, [rax+75h]; void *
0x18000b1d8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b1de  mov     rdx, [rbp+pPrinterEnum]
0x18000b1e2  lea     rcx, [rbp+var_30]
0x18000b1e6  call    ??0?$vector@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>(void)
0x18000b1eb  xor     ecx, ecx
0x18000b1ed  mov     eax, [rbp+arg_8]
0x18000b1f0  cmp     rcx, rax
0x18000b1f3  jnb     short loc_18000B24D
0x18000b1f5  imul    rax, rcx, 88h
0x18000b1fc  cmp     dword ptr [rax+rdx+80h], 0
0x18000b204  ja      short loc_18000B20B
0x18000b206  inc     rcx
0x18000b209  jmp     short loc_18000B1ED
0x18000b20b  mov     rbx, [rbp+var_30]
0x18000b20f  test    rbx, rbx
0x18000b212  jz      short loc_18000B234
0x18000b214  mov     rdx, [rbp+var_28]
0x18000b218  mov     rcx, rbx; this
0x18000b21b  call    ??$_Destroy_range@V?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@std@@@std@@YAXPEAV?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@QEAV12@AEAV?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>>(wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0> *,wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0> * const,std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>> &)
0x18000b220  mov     rdx, [rbp+var_20]
0x18000b224  sub     rdx, rbx
0x18000b227  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000b22b  mov     rcx, rbx
0x18000b22e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b233  nop
0x18000b234  lea     rcx, [rbp+pPrinterEnum]
0x18000b238  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b23d  xor     al, al
0x18000b23f  mov     rbx, [rsp+70h+arg_10]
0x18000b247  add     rsp, 70h
0x18000b24b  pop     rbp
0x18000b24c  retn
0x18000b24d  mov     rbx, [rbp+var_30]
0x18000b251  test    rbx, rbx
0x18000b254  jz      short loc_18000B276
0x18000b256  mov     rdx, [rbp+var_28]
0x18000b25a  mov     rcx, rbx; this
0x18000b25d  call    ??$_Destroy_range@V?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@std@@@std@@YAXPEAV?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@QEAV12@AEAV?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>>(wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0> *,wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0> * const,std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>> &)
0x18000b262  mov     rdx, [rbp+var_20]
0x18000b266  sub     rdx, rbx
0x18000b269  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000b26d  mov     rcx, rbx
0x18000b270  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b275  nop
0x18000b276  lea     rcx, [rbp+pPrinterEnum]
0x18000b27a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b27f  jmp     short loc_18000B287
0x18000b281  cmp     [rbp+arg_0], 0
0x18000b285  jnz     short loc_18000B28B
0x18000b287  mov     al, 1
0x18000b289  jmp     short loc_18000B23F
0x18000b28b  mov     rcx, [rbp+8]; this
0x18000b28f  mov     edx, 70h ; 'p'; void *
0x18000b294  mov     r9d, 8000FFFFh; char *
0x18000b29a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
