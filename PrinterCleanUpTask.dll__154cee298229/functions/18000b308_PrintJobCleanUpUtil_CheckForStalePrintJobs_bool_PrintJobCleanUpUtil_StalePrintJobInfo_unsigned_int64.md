# PrintJobCleanUpUtil::CheckForStalePrintJobs(bool,PrintJobCleanUpUtil::StalePrintJobInfo * *,unsigned __int64 *)

- ea: `0x18000b308`
- end: `0x18000ba6a`
- name: `?CheckForStalePrintJobs@PrintJobCleanUpUtil@@YAJ_NPEAPEAUStalePrintJobInfo@1@PEA_K@Z`
- size: `1890`
- prototype: `__int64 __fastcall(PrintJobCleanUpUtil *this, struct _FILETIME *, struct PrintJobCleanUpUtil::StalePrintJobInfo **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000aeb4`
- `0x18000d424`

## callees

- `0x180002020`
- `0x180007a74`
- `0x180008008`
- `0x180008074`
- `0x180008234`
- `0x1800085e8`
- `0x180008b70`
- `0x180009428`
- `0x1800094f0`
- `0x180009abc`
- `0x180009c10`
- `0x180009c6c`
- `0x18000a6e0`
- `0x18000a720`
- `0x18000b308`
- `0x18000c534`
- `0x18000d3d8`
- `0x18000eca4`
- `0x18000f0b0`
- `0x18000f0d0`
- `0x18000f118`
- `0x18000f19c`
- `0x18000f22c`
- `0x18000f26c`
- `0x18000f88c`
- `0x18000ff2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b575`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b424`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b496`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b424`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18000b496`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18000b506`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18000b506`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x18000b55f`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x18000b5dd`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x18000b55f`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x18000b5dd`
- `ext-ms-win-printer-winspool-l1-1-2!SetJobW` at `0x18000b74c`
- `ext-ms-win-printer-winspool-l1-1-2!SetJobW` at `0x18000b74c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b998`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6dd`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18000b362`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18000b3c2`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18000b362`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18000b3c2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b637`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b637`

## string_xrefs

- `0x18000b6cf`: `SYSTEM\CurrentControlSet\Control\Print\PrintJobCleanupTask\`
- `0x18000b37f`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b3cc`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b445`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b4a8`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b518`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b580`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b5ef`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b649`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000b7c1`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::CheckForStalePrintJobs(
        PrintJobCleanUpUtil *this,
        struct _FILETIME *a2,
        struct PrintJobCleanUpUtil::StalePrintJobInfo **a3,
        unsigned __int64 *a4)
{
  const char *v5; // r9
  WCHAR *v6; // rax
  const char *v7; // r9
  unsigned int v8; // r8d
  const char *v9; // r9
  const char *v10; // r9
  LPBYTE v11; // r12
  unsigned __int64 i; // rsi
  __int64 v13; // r15
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  const char *v17; // r9
  LPBYTE v18; // r13
  unsigned __int64 j; // rdi
  __int64 v20; // rbx
  const char *v21; // r9
  __int64 v22; // rax
  LSTATUS ValueW; // eax
  int v24; // edx
  BOOL v25; // ebx
  char v26; // al
  _QWORD *v27; // rcx
  const char *v28; // r9
  _OWORD *v29; // rax
  PrintJobCleanUpUtil *v30; // rcx
  __int64 v31; // r8
  struct _FILETIME v32; // rcx
  _OWORD *v33; // rax
  _OWORD *k; // rcx
  PrintJobCleanUpUtil *v35; // rax
  void *v36; // rdx
  int cbBuf; // [rsp+20h] [rbp-148h]
  int cbBufa; // [rsp+20h] [rbp-148h]
  char v40; // [rsp+40h] [rbp-128h]
  DWORD v41; // [rsp+44h] [rbp-124h] BYREF
  DWORD pcbNeeded; // [rsp+48h] [rbp-120h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-11Ch] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-118h] BYREF
  DWORD pcbBuffer; // [rsp+58h] [rbp-110h] BYREF
  DWORD pcReturned; // [rsp+5Ch] [rbp-10Ch] BYREF
  DWORD v47; // [rsp+60h] [rbp-108h] BYREF
  HANDLE phPrinter; // [rsp+68h] [rbp-100h] BYREF
  int v49; // [rsp+70h] [rbp-F8h]
  _OWORD *v50; // [rsp+78h] [rbp-F0h] BYREF
  PrintJobCleanUpUtil *v51[2]; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v52; // [rsp+90h] [rbp-D8h]
  _QWORD *pvData; // [rsp+98h] [rbp-D0h] BYREF
  unsigned __int64 v54; // [rsp+A0h] [rbp-C8h] BYREF
  struct PrintJobCleanUpUtil::StalePrintJobInfo **v55; // [rsp+A8h] [rbp-C0h]
  _QWORD v56[2]; // [rsp+B0h] [rbp-B8h] BYREF
  LPBYTE pJob[3]; // [rsp+C0h] [rbp-A8h] BYREF
  LPBYTE pPrinterEnum[3]; // [rsp+D8h] [rbp-90h] BYREF
  _BYTE v59[16]; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v60; // [rsp+100h] [rbp-68h]
  _QWORD v61[4]; // [rsp+110h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v55 = a3;
  v40 = (char)this;
  v49 = 0;
  if ( a2 )
    *a2 = 0;
  *a3 = 0;
  pcbBuffer = 0;
  if ( !GetUserNameW(0, &pcbBuffer) && GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB1,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      v5);
  std::wstring::wstring(v59, pcbBuffer);
  v6 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  if ( !GetUserNameW(v6, &pcbBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB4,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      v7);
  std::wstring::resize(v59, pcbBuffer - 1);
  pcbNeeded = 0;
  pcReturned = 0;
  if ( EnumPrintersW(2u, 0, 2u, 0, 0, &pcbNeeded, &pcReturned) )
  {
    if ( pcbNeeded )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xC8, v8, (const char *)0x8000FFFFLL, cbBuf);
    std::wstring::_Tidy_deallocate(v59);
    return 0;
  }
  else
  {
    if ( GetLastError() != 122 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBE,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
        v9);
    std::vector<unsigned char>::vector<unsigned char>(pPrinterEnum, pcbNeeded);
    if ( !EnumPrintersW(2u, 0, 2u, pPrinterEnum[0], pcbNeeded, &pcbNeeded, &pcReturned) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xCD,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
        v10);
    v11 = pPrinterEnum[0];
    std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>(v51);
    for ( i = 0; i < pcReturned; ++i )
    {
      v13 = 136 * i;
      if ( *(_DWORD *)&v11[136 * i + 128] )
      {
        phPrinter = 0;
        if ( !OpenPrinterW(*(LPWSTR *)&v11[v13 + 8], &phPrinter, 0) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xD6,
            (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
            v14);
        v41 = 0;
        v47 = 0;
        if ( EnumJobsW(phPrinter, 0, 0xFFFFFFFF, 2u, 0, 0, &v41, &v47) )
        {
          if ( v41 )
            wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xE8, v15, (const char *)0x8000FFFFLL, cbBufa);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
        }
        else
        {
          if ( GetLastError() != 122 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xDD,
              (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
              v16);
          std::vector<unsigned char>::vector<unsigned char>(pJob, v41);
          if ( !EnumJobsW(phPrinter, 0, 0xFFFFFFFF, 2u, pJob[0], v41, &v41, &v47) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xED,
              (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
              v17);
          v18 = pJob[0];
          for ( j = 0; j < v47; ++j )
          {
            FileTime = 0;
            v20 = 160 * j;
            if ( !SystemTimeToFileTime((const SYSTEMTIME *)&v18[160 * j + 132], &FileTime) )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0xF3,
                (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                v21);
            std::_WChar_traits<unsigned short>::length(*(_QWORD *)&v18[v20 + 24]);
            v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v22, v60) )
            {
              LODWORD(pvData) = 0;
              pcbData = 4;
              ValueW = RegGetValueW(
                         HKEY_LOCAL_MACHINE,
                         L"SYSTEM\\CurrentControlSet\\Control\\Print\\PrintJobCleanupTask\\",
                         L"StalePrintJobDaysCondition",
                         0x20000018u,
                         0,
                         &pvData,
                         &pcbData);
              v24 = 3;
              if ( !ValueW )
                v24 = (int)pvData;
              v54 = (unsigned __int64)FileTime;
              if ( IsStale(*(_QWORD *)&FileTime, 10000000LL * (unsigned int)(86400 * v24)) )
              {
                if ( v40 )
                {
                  v25 = SetJobW(phPrinter, *(_DWORD *)&v18[v20], 0, 0, 5u);
                  pcbData = v25;
                  GetManufacturerString(v61, *(_QWORD *)&v11[v13 + 8]);
                  v26 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v61);
                  v27 = v61;
                  if ( v26 )
                    v27 = (_QWORD *)v61[0];
                  pvData = v27;
                  PrinterCleanUpTelemetry::StalePrintJobDelete<char const *,unsigned short * &,unsigned short * &,int &>(
                    &pvData,
                    &v11[v13 + 24],
                    &v11[v13 + 32],
                    &pcbData);
                  if ( !v25 )
                    wil::details::in1diag3::_Throw_GetLastError(
                      retaddr,
                      (void *)0xFD,
                      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                      v28);
                  std::string::_Tidy_deallocate(v61);
                }
                else
                {
                  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &v50,
                    *(_QWORD *)&v18[v20 + 32]);
                  v49 |= 1u;
                  v29 = v50;
                  v50 = 0;
                  v56[0] = v29;
                  v56[1] = FileTime;
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
                  std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::emplace_back<PrintJobCleanUpUtil::StalePrintJobInfo>(
                    v51,
                    v56);
                }
              }
            }
          }
          std::vector<unsigned char>::_Tidy(pJob);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
        }
      }
    }
    v30 = v51[0];
    if ( v51[0] != v51[1] )
    {
      wil::make_unique_cotaskmem<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(&FileTime, (v51[1] - v51[0]) >> 4);
      v30 = v51[0];
      v54 = (unsigned __int64)v51[0];
      if ( (v51[1] - v51[0]) >> 4 )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          &v50,
          &v54);
        v32 = FileTime;
        v33 = v50;
        *(_OWORD *)*(_QWORD *)&FileTime = *v50;
        for ( k = (_OWORD *)(*(_QWORD *)&v32 + 16LL); --v31; ++k )
          *k = *++v33;
        v30 = v51[0];
      }
      v35 = v51[1];
      if ( v30 != v51[1] )
      {
        do
        {
          *(_OWORD *)v30 = 0;
          v30 = (PrintJobCleanUpUtil *)((char *)v30 + 16);
        }
        while ( v30 != v35 );
        v30 = v51[0];
      }
      *v55 = (struct PrintJobCleanUpUtil::StalePrintJobInfo *)((v51[1] - v30) >> 4);
      if ( a2 )
      {
        v36 = 0;
        *a2 = FileTime;
      }
      else
      {
        v36 = (void *)FileTime;
      }
      FileTime = 0;
      if ( v36 )
      {
        CoTaskMemFree(v36);
        v30 = v51[0];
      }
    }
    if ( v30 )
    {
      std::_Destroy_range<std::allocator<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>>(v30);
      std::_Deallocate<16>(v51[0], (v52 - (unsigned __int64)v51[0]) & 0xFFFFFFFFFFFFFFF0uLL);
      *(_OWORD *)v51 = 0;
      v52 = 0;
    }
    std::vector<unsigned char>::_Tidy(pPrinterEnum);
    std::wstring::_Tidy_deallocate(v59);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b308  mov     [rsp+arg_0], rbx
0x18000b30d  mov     [rsp+arg_18], rsi
0x18000b312  push    rdi
0x18000b313  push    r12
0x18000b315  push    r13
0x18000b317  push    r14
0x18000b319  push    r15
0x18000b31b  sub     rsp, 140h
0x18000b322  mov     rax, cs:__security_cookie
0x18000b329  xor     rax, rsp
0x18000b32c  mov     [rsp+168h+var_38], rax
0x18000b334  mov     [rsp+168h+var_C0], r8
0x18000b33c  mov     r14, rdx
0x18000b33f  mov     [rsp+168h+var_128], cl
0x18000b343  xor     r13d, r13d
0x18000b346  mov     [rsp+168h+var_F8], r13d
0x18000b34b  test    rdx, rdx
0x18000b34e  jz      short loc_18000B353
0x18000b350  mov     [rdx], r13
0x18000b353  mov     [r8], r13
0x18000b356  mov     [rsp+168h+pcbBuffer], r13d
0x18000b35b  lea     rdx, [rsp+168h+pcbBuffer]; pcbBuffer
0x18000b360  xor     ecx, ecx; lpBuffer
0x18000b362  call    cs:__imp_GetUserNameW
0x18000b368  test    eax, eax
0x18000b36a  jnz     short loc_18000B393
0x18000b36c  mov     rbx, [rsp+168h]
0x18000b374  call    cs:__imp_GetLastError
0x18000b37a  cmp     eax, 7Ah ; 'z'
0x18000b37d  jz      short loc_18000B393
0x18000b37f  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b386  mov     edx, 0B1h; void *
0x18000b38b  mov     rcx, rbx; this
0x18000b38e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b393  mov     edx, [rsp+168h+pcbBuffer]
0x18000b397  lea     rcx, [rsp+168h+var_78]
0x18000b39f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18000b3a4  nop
0x18000b3a5  mov     rbx, [rsp+168h]
0x18000b3ad  lea     rcx, [rsp+168h+var_78]
0x18000b3b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b3ba  mov     rcx, rax; lpBuffer
0x18000b3bd  lea     rdx, [rsp+168h+pcbBuffer]; pcbBuffer
0x18000b3c2  call    cs:__imp_GetUserNameW
0x18000b3c8  test    eax, eax
0x18000b3ca  jnz     short loc_18000B3E0
0x18000b3cc  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b3d3  mov     edx, 0B4h; void *
0x18000b3d8  mov     rcx, rbx; this
0x18000b3db  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b3e0  mov     edx, [rsp+168h+pcbBuffer]
0x18000b3e4  dec     edx
0x18000b3e6  lea     rcx, [rsp+168h+var_78]
0x18000b3ee  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000b3f3  mov     [rsp+168h+var_120], r13d
0x18000b3f8  mov     [rsp+168h+var_10C], r13d
0x18000b3fd  lea     rax, [rsp+168h+var_10C]
0x18000b402  mov     [rsp+168h+pcReturned], rax; pcReturned
0x18000b407  lea     rax, [rsp+168h+var_120]
0x18000b40c  mov     [rsp+168h+pcbNeeded], rax; pcbNeeded
0x18000b411  mov     [rsp+168h+cbBuf], r13d; int
0x18000b416  xor     r9d, r9d; pPrinterEnum
0x18000b419  lea     edi, [r9+2]
0x18000b41d  mov     r8d, edi; Level
0x18000b420  xor     edx, edx; Name
0x18000b422  mov     ecx, edi; Flags
0x18000b424  call    cs:__imp_EnumPrintersW
0x18000b42a  test    eax, eax
0x18000b42c  jnz     loc_18000BA07
0x18000b432  mov     rbx, [rsp+168h]
0x18000b43a  call    cs:__imp_GetLastError
0x18000b440  cmp     eax, 7Ah ; 'z'
0x18000b443  jz      short loc_18000B459
0x18000b445  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b44c  mov     edx, 0BEh; void *
0x18000b451  mov     rcx, rbx; this
0x18000b454  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b459  mov     edx, [rsp+168h+var_120]
0x18000b45d  lea     rcx, [rsp+168h+pPrinterEnum]
0x18000b465  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000b46a  nop
0x18000b46b  mov     eax, [rsp+168h+var_120]
0x18000b46f  lea     rcx, [rsp+168h+var_10C]
0x18000b474  mov     [rsp+168h+pcReturned], rcx; pcReturned
0x18000b479  lea     rcx, [rsp+168h+var_120]
0x18000b47e  mov     [rsp+168h+pcbNeeded], rcx; pcbNeeded
0x18000b483  mov     [rsp+168h+cbBuf], eax; cbBuf
0x18000b487  mov     r9, [rsp+168h+pPrinterEnum]; pPrinterEnum
0x18000b48f  mov     r8d, edi; Level
0x18000b492  xor     edx, edx; Name
0x18000b494  mov     ecx, edi; Flags
0x18000b496  call    cs:__imp_EnumPrintersW
0x18000b49c  mov     rcx, [rsp+168h]; this
0x18000b4a4  test    eax, eax
0x18000b4a6  jnz     short loc_18000B4B9
0x18000b4a8  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b4af  mov     edx, 0CDh; void *
0x18000b4b4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b4b9  mov     r12, [rsp+168h+pPrinterEnum]
0x18000b4c1  lea     rcx, [rsp+168h+var_E8]
0x18000b4c9  call    ??0?$vector@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>(void)
0x18000b4ce  nop
0x18000b4cf  mov     rsi, r13
0x18000b4d2  mov     eax, [rsp+168h+var_10C]
0x18000b4d6  cmp     rsi, rax
0x18000b4d9  jnb     loc_18000B8A2
0x18000b4df  imul    r15, rsi, 88h
0x18000b4e6  cmp     [r15+r12+80h], r13d
0x18000b4ee  jbe     loc_18000B86E
0x18000b4f4  mov     [rsp+168h+phPrinter], r13
0x18000b4f9  xor     r8d, r8d; pDefault
0x18000b4fc  lea     rdx, [rsp+168h+phPrinter]; phPrinter
0x18000b501  mov     rcx, [r15+r12+8]; pPrinterName
0x18000b506  call    cs:__imp_OpenPrinterW
0x18000b50c  mov     rcx, [rsp+168h]; this
0x18000b514  test    eax, eax
0x18000b516  jnz     short loc_18000B529
0x18000b518  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b51f  mov     edx, 0D6h; void *
0x18000b524  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b529  mov     [rsp+168h+var_124], r13d
0x18000b52e  mov     [rsp+168h+var_108], r13d
0x18000b533  lea     rax, [rsp+168h+var_108]
0x18000b538  mov     [rsp+168h+var_130], rax; pcReturned
0x18000b53d  lea     rax, [rsp+168h+var_124]
0x18000b542  mov     [rsp+168h+pcReturned], rax; pcbNeeded
0x18000b547  mov     dword ptr [rsp+168h+pcbNeeded], r13d; cbBuf
0x18000b54c  mov     qword ptr [rsp+168h+cbBuf], r13; int
0x18000b551  mov     r9d, edi; Level
0x18000b554  or      r8d, 0FFFFFFFFh; NoJobs
0x18000b558  xor     edx, edx; FirstJob
0x18000b55a  mov     rcx, [rsp+168h+phPrinter]; hPrinter
0x18000b55f  call    cs:__imp_EnumJobsW
0x18000b565  test    eax, eax
0x18000b567  jnz     loc_18000B876
0x18000b56d  mov     rbx, [rsp+168h]
0x18000b575  call    cs:__imp_GetLastError
0x18000b57b  cmp     eax, 7Ah ; 'z'
0x18000b57e  jz      short loc_18000B594
0x18000b580  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b587  mov     edx, 0DDh; void *
0x18000b58c  mov     rcx, rbx; this
0x18000b58f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b594  mov     edx, [rsp+168h+var_124]
0x18000b598  lea     rcx, [rsp+168h+pJob]
0x18000b5a0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000b5a5  nop
0x18000b5a6  mov     eax, [rsp+168h+var_124]
0x18000b5aa  mov     rdx, [rsp+168h+pJob]
0x18000b5b2  lea     rcx, [rsp+168h+var_108]
0x18000b5b7  mov     [rsp+168h+var_130], rcx; pcReturned
0x18000b5bc  lea     rcx, [rsp+168h+var_124]
0x18000b5c1  mov     [rsp+168h+pcReturned], rcx; pcbNeeded
0x18000b5c6  mov     dword ptr [rsp+168h+pcbNeeded], eax; cbBuf
0x18000b5ca  mov     qword ptr [rsp+168h+cbBuf], rdx; pJob
0x18000b5cf  mov     r9d, edi; Level
0x18000b5d2  or      r8d, 0FFFFFFFFh; NoJobs
0x18000b5d6  xor     edx, edx; FirstJob
0x18000b5d8  mov     rcx, [rsp+168h+phPrinter]; hPrinter
0x18000b5dd  call    cs:__imp_EnumJobsW
0x18000b5e3  mov     rcx, [rsp+168h]; this
0x18000b5eb  test    eax, eax
0x18000b5ed  jnz     short loc_18000B600
0x18000b5ef  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b5f6  mov     edx, 0EDh; void *
0x18000b5fb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b600  mov     r13, [rsp+168h+pJob]
0x18000b608  xor     edi, edi
0x18000b60a  mov     eax, [rsp+168h+var_108]
0x18000b60e  cmp     rdi, rax
0x18000b611  jnb     loc_18000B84F
0x18000b617  mov     qword ptr [rsp+168h+FileTime.dwLowDateTime], 0
0x18000b620  lea     rbx, [rdi+rdi*4]
0x18000b624  shl     rbx, 5
0x18000b628  lea     rcx, [r13+84h]
0x18000b62f  add     rcx, rbx; lpSystemTime
0x18000b632  lea     rdx, [rsp+168h+FileTime]; lpFileTime
0x18000b637  call    cs:__imp_SystemTimeToFileTime
0x18000b63d  mov     rcx, [rsp+168h]; this
0x18000b645  test    eax, eax
0x18000b647  jnz     short loc_18000B65A
0x18000b649  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b650  mov     edx, 0F3h; void *
0x18000b655  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b65a  mov     r8, [rbx+r13+18h]
0x18000b65f  mov     rcx, r8
0x18000b662  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b667  mov     r9, rax
0x18000b66a  lea     rcx, [rsp+168h+var_78]
0x18000b672  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b677  mov     rcx, rax
0x18000b67a  mov     rdx, [rsp+168h+var_68]
0x18000b682  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000b687  test    al, al
0x18000b689  jz      loc_18000B847
0x18000b68f  mov     dword ptr [rsp+168h+pvData], 0
0x18000b69a  mov     [rsp+168h+pcbData], 4
0x18000b6a2  lea     rax, [rsp+168h+pcbData]
0x18000b6a7  mov     [rsp+168h+pcReturned], rax; pcbData
0x18000b6ac  lea     rax, [rsp+168h+pvData]
0x18000b6b4  mov     [rsp+168h+pcbNeeded], rax; pvData
0x18000b6b9  mov     qword ptr [rsp+168h+cbBuf], 0; pdwType
0x18000b6c2  mov     r9d, 20000018h; dwFlags
0x18000b6c8  lea     r8, Value; "StalePrintJobDaysCondition"
0x18000b6cf  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x18000b6d6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b6dd  call    cs:__imp_RegGetValueW
0x18000b6e3  mov     edx, 3
0x18000b6e8  test    eax, eax
0x18000b6ea  cmovz   edx, dword ptr [rsp+168h+pvData]
0x18000b6f2  mov     eax, [rsp+168h+FileTime.dwLowDateTime]
0x18000b6f6  mov     ecx, [rsp+168h+FileTime.dwHighDateTime]
0x18000b6fa  mov     dword ptr [rsp+168h+var_C8], eax
0x18000b701  mov     dword ptr [rsp+168h+var_C8+4], ecx
0x18000b708  imul    ecx, edx, 15180h
0x18000b70e  imul    rdx, rcx, 989680h; unsigned __int64
0x18000b715  mov     rcx, [rsp+168h+var_C8]; unsigned __int64
0x18000b71d  call    ?IsStale@@YA_N_K0@Z; IsStale(unsigned __int64,unsigned __int64)
0x18000b722  test    al, al
0x18000b724  jz      loc_18000B847
0x18000b72a  cmp     [rsp+168h+var_128], 0
0x18000b72f  jz      loc_18000B7E2
0x18000b735  mov     [rsp+168h+cbBuf], 5; Command
0x18000b73d  xor     r9d, r9d; pJob
0x18000b740  xor     r8d, r8d; Level
0x18000b743  mov     edx, [rbx+r13]; JobId
0x18000b747  mov     rcx, [rsp+168h+phPrinter]; hPrinter
0x18000b74c  call    cs:__imp_SetJobW
0x18000b752  mov     ebx, eax
0x18000b754  mov     [rsp+168h+pcbData], eax
0x18000b758  mov     rdx, [r15+r12+8]
0x18000b75d  lea     rcx, [rsp+168h+var_58]
0x18000b765  call    ?GetManufacturerString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAG@Z; GetManufacturerString(ushort *)
0x18000b76a  nop
0x18000b76b  lea     rcx, [rsp+168h+var_58]
0x18000b773  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x18000b778  lea     rcx, [rsp+168h+var_58]
0x18000b780  test    al, al
0x18000b782  cmovnz  rcx, [rsp+168h+var_58]
0x18000b78b  mov     [rsp+168h+pvData], rcx
0x18000b793  lea     r8, [r12+20h]
0x18000b798  add     r8, r15
0x18000b79b  lea     rdx, [r12+18h]
0x18000b7a0  add     rdx, r15
0x18000b7a3  lea     r9, [rsp+168h+pcbData]
0x18000b7a8  lea     rcx, [rsp+168h+pvData]
0x18000b7b0  call    ??$StalePrintJobDelete@PEBDAEAPEAGAEAPEAGAEAH@PrinterCleanUpTelemetry@@SAX$$QEAPEBDAEAPEAG1AEAH@Z; PrinterCleanUpTelemetry::StalePrintJobDelete<char const *,ushort * &,ushort * &,int &>(char const * &&,ushort * &,ushort * &,int &)
0x18000b7b5  mov     rcx, [rsp+168h]; this
0x18000b7bd  test    ebx, ebx
0x18000b7bf  jnz     short loc_18000B7D3
0x18000b7c1  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000b7c8  mov     edx, 0FDh; void *
0x18000b7cd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b7d3  lea     rcx, [rsp+168h+var_58]
0x18000b7db  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000b7e0  jmp     short loc_18000B847
0x18000b7e2  mov     rdx, [rbx+r13+20h]
0x18000b7e7  lea     rcx, [rsp+168h+var_F0]
0x18000b7ec  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000b7f1  mov     eax, [rsp+168h+var_F8]
0x18000b7f5  or      eax, 1
0x18000b7f8  mov     [rsp+168h+var_F8], eax
0x18000b7fc  mov     rax, [rsp+168h+var_F0]
0x18000b801  mov     [rsp+168h+var_F0], 0
0x18000b80a  mov     [rsp+168h+var_B8], rax
0x18000b812  mov     eax, [rsp+168h+FileTime.dwLowDateTime]
0x18000b816  mov     [rsp+168h+var_B0], eax
0x18000b81d  mov     eax, [rsp+168h+FileTime.dwHighDateTime]
0x18000b821  mov     [rsp+168h+var_AC], eax
0x18000b828  lea     rcx, [rsp+168h+var_F0]
0x18000b82d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000b832  lea     rdx, [rsp+168h+var_B8]
0x18000b83a  lea     rcx, [rsp+168h+var_E8]
0x18000b842  call    ??$emplace_back@UStalePrintJobInfo@PrintJobCleanUpUtil@@@?$vector@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@@std@@@std@@QEAAAEAV?$unique_struct@UStalePrintJobInfo@PrintJobCleanUpUtil@@P6AXPEAU12@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z$$T$0A@@wil@@$$QEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z; std::vector<wil::unique_struct<PrintJobCleanUpUtil::StalePrintJobInfo,void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *),std::nullptr_t,0>>::emplace_back<PrintJobCleanUpUtil::StalePrintJobInfo>(PrintJobCleanUpUtil::StalePrintJobInfo &&)
0x18000b847  inc     rdi
0x18000b84a  jmp     loc_18000B60A
0x18000b84f  lea     rcx, [rsp+168h+pJob]
0x18000b857  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b85c  nop
0x18000b85d  lea     rcx, [rsp+168h+phPrinter]
0x18000b862  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b867  xor     r13d, r13d
0x18000b86a  lea     edi, [r13+2]
0x18000b86e  inc     rsi
0x18000b871  jmp     loc_18000B4D2
0x18000b876  cmp     [rsp+168h+var_124], r13d
0x18000b87b  jnz     short loc_18000B889
0x18000b87d  lea     rcx, [rsp+168h+phPrinter]
0x18000b882  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b887  jmp     short loc_18000B86E
0x18000b889  mov     rcx, [rsp+168h]; this
0x18000b891  mov     edx, 0E8h; void *
0x18000b896  mov     r9d, 8000FFFFh; char *
0x18000b89c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b8a2  mov     rdx, [rsp+168h+var_E8+8]
0x18000b8aa  mov     rcx, [rsp+168h+var_E8]
0x18000b8b2  cmp     rcx, rdx
0x18000b8b5  jz      loc_18000B9A6
0x18000b8bb  sub     rdx, rcx
0x18000b8be  sar     rdx, 4
  ... truncated ...
```
