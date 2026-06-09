# SvcQueryConfig

- ea: `0x14001e564`
- end: `0x14001e823`
- name: `SvcQueryConfig`
- size: `703`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x14000d5c8`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x1400184fc`
- `0x140019bb8`
- `0x14001b210`
- `0x14001e564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e77d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001e68d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001e773`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001e68d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14001e773`

## string_xrefs

- `0x14001e5a8`: `No service handle specified`
- `0x14001e616`: `No service config result specified`
- `0x14001e6bd`: `Failed to query service configuration.`
- `0x14001e796`: `Failed to query service configuration.`

## pseudocode

```c
__int64 __fastcall SvcQueryConfig(SC_HANDLE hService, LPQUERY_SERVICE_CONFIGW *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  LPQUERY_SERVICE_CONFIGW v9; // rbx
  DWORD LastError; // eax
  signed int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-30h]
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbBufSize; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+44h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  if ( hService )
  {
    if ( !a2 )
    {
      v4 = -2147467261;
      v22 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No service config result specified");
        lpServiceConfig = (LPQUERY_SERVICE_CONFIGW)&v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v7,
          3,
          (__int64)": {}",
          (__int64)&lpServiceConfig);
      }
      v6 = 23;
      goto LABEL_5;
    }
    lpServiceConfig = 0;
    cbBufSize = 4096;
    if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&lpServiceConfig, 0x1000u) )
    {
      v8 = 27;
LABEL_24:
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
        (const char *)0x8007000ELL,
        v18);
      goto LABEL_35;
    }
    v9 = lpServiceConfig;
    if ( QueryServiceConfigW(hService, lpServiceConfig, cbBufSize, &cbBufSize) )
      goto LABEL_33;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 122 && LastError )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query service configuration.");
        if ( v11 > 0 )
          v13 = (unsigned __int16)v11 | 0x80070000;
        else
          v13 = v11;
        v22 = v13;
        *(_QWORD *)v20 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v12,
          3,
          (__int64)": {0}",
          (__int64)v20);
      }
      v14 = 34;
      goto LABEL_21;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&lpServiceConfig);
    if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&lpServiceConfig, cbBufSize) )
    {
      v8 = 38;
      goto LABEL_24;
    }
    v9 = lpServiceConfig;
    if ( QueryServiceConfigW(hService, lpServiceConfig, cbBufSize, &cbBufSize) )
    {
LABEL_33:
      lpServiceConfig = 0;
      *a2 = v9;
    }
    else
    {
      v11 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query service configuration.");
        if ( v11 > 0 )
          v16 = (unsigned __int16)v11 | 0x80070000;
        else
          v16 = v11;
        v22 = v16;
        *(_QWORD *)v20 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v15,
          3,
          (__int64)": {0}",
          (__int64)v20);
      }
      if ( v11 )
      {
        v14 = 46;
LABEL_21:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
               (const char *)(unsigned int)v11,
               v18);
LABEL_35:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&lpServiceConfig);
        return v4;
      }
    }
    v4 = 0;
    goto LABEL_35;
  }
  v4 = -2147024809;
  v22 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No service handle specified");
    lpServiceConfig = (LPQUERY_SERVICE_CONFIGW)&v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v5,
      3,
      (__int64)": {}",
      (__int64)&lpServiceConfig);
  }
  v6 = 22;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
    (const char *)v4,
    v18);
  return v4;
}

```

## disassembly

```asm
0x14001e564  mov     [rsp-18h+arg_10], rbx
0x14001e569  push    rbp
0x14001e56a  push    rsi
0x14001e56b  push    rdi
0x14001e56c  mov     rbp, rsp
0x14001e56f  sub     rsp, 50h
0x14001e573  mov     rax, cs:__security_cookie
0x14001e57a  xor     rax, rsp
0x14001e57d  mov     [rbp+var_8], rax
0x14001e581  mov     rdi, rdx
0x14001e584  mov     rsi, rcx
0x14001e587  test    rcx, rcx
0x14001e58a  jnz     short loc_14001E5F8
0x14001e58c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e593  mov     ebx, 80070057h
0x14001e598  mov     [rbp+var_C], ebx
0x14001e59b  test    rcx, rcx
0x14001e59e  jz      short loc_14001E5DB
0x14001e5a0  lea     edi, [rsi+3]
0x14001e5a3  xor     edx, edx
0x14001e5a5  mov     r8d, edi
0x14001e5a8  lea     r9, aNoServiceHandl_0; "No service handle specified"
0x14001e5af  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e5b4  lea     rcx, [rbp+lpServiceConfig]
0x14001e5b8  mov     r8d, edi
0x14001e5bb  mov     qword ptr [rsp+50h+var_30], rcx; int
0x14001e5c0  lea     rax, [rbp+var_C]
0x14001e5c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e5cb  lea     r9, asc_1400353E8; ": {}"
0x14001e5d2  mov     [rbp+lpServiceConfig], rax
0x14001e5d6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e5db  mov     edx, 16h; void *
0x14001e5e0  mov     rcx, [rbp+18h]; this
0x14001e5e4  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e5eb  mov     r9d, ebx; char *
0x14001e5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e5f3  jmp     loc_14001E805
0x14001e5f8  test    rdi, rdi
0x14001e5fb  jnz     short loc_14001E655
0x14001e5fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e604  mov     ebx, 80004003h
0x14001e609  mov     [rbp+var_C], ebx
0x14001e60c  test    rcx, rcx
0x14001e60f  jz      short loc_14001E64E
0x14001e611  mov     edi, 3
0x14001e616  lea     r9, aNoServiceConfi; "No service config result specified"
0x14001e61d  mov     r8d, edi
0x14001e620  xor     edx, edx
0x14001e622  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e627  lea     rcx, [rbp+lpServiceConfig]
0x14001e62b  mov     r8d, edi
0x14001e62e  mov     qword ptr [rsp+50h+var_30], rcx
0x14001e633  lea     rax, [rbp+var_C]
0x14001e637  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e63e  lea     r9, asc_1400353E8; ": {}"
0x14001e645  mov     [rbp+lpServiceConfig], rax
0x14001e649  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e64e  mov     edx, 17h
0x14001e653  jmp     short loc_14001E5E0
0x14001e655  mov     edx, 1000h
0x14001e65a  mov     [rbp+lpServiceConfig], 0
0x14001e662  lea     rcx, [rbp+lpServiceConfig]
0x14001e666  mov     [rbp+cbBufSize], edx
0x14001e669  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x14001e66e  test    rax, rax
0x14001e671  jnz     short loc_14001E67B
0x14001e673  lea     edx, [rax+1Bh]
0x14001e676  jmp     loc_14001E744
0x14001e67b  mov     rbx, [rbp+lpServiceConfig]
0x14001e67f  lea     r9, [rbp+cbBufSize]; pcbBytesNeeded
0x14001e683  mov     r8d, [rbp+cbBufSize]; cbBufSize
0x14001e687  mov     rdx, rbx; lpServiceConfig
0x14001e68a  mov     rcx, rsi; hService
0x14001e68d  call    cs:__imp_QueryServiceConfigW
0x14001e693  test    eax, eax
0x14001e695  jnz     loc_14001E7EF
0x14001e69b  call    cs:__imp_GetLastError
0x14001e6a1  mov     ebx, eax
0x14001e6a3  cmp     eax, 7Ah ; 'z'
0x14001e6a6  jz      short loc_14001E727
0x14001e6a8  test    eax, eax
0x14001e6aa  jz      short loc_14001E727
0x14001e6ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e6b3  test    rcx, rcx
0x14001e6b6  jz      short loc_14001E708
0x14001e6b8  mov     edi, 3
0x14001e6bd  lea     r9, aFailedToQueryS; "Failed to query service configuration."
0x14001e6c4  mov     r8d, edi
0x14001e6c7  xor     edx, edx
0x14001e6c9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e6ce  test    ebx, ebx
0x14001e6d0  jg      short loc_14001E6D6
0x14001e6d2  mov     eax, ebx
0x14001e6d4  jmp     short loc_14001E6DE
0x14001e6d6  movzx   eax, bx
0x14001e6d9  or      eax, 80070000h
0x14001e6de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e6e5  lea     r9, a0; ": {0}"
0x14001e6ec  mov     [rbp+var_C], eax
0x14001e6ef  mov     r8d, edi
0x14001e6f2  lea     rax, [rbp+var_C]
0x14001e6f6  mov     qword ptr [rbp+var_18], rax
0x14001e6fa  lea     rax, [rbp+var_18]
0x14001e6fe  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x14001e703  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e708  mov     edx, 22h ; '"'; void *
0x14001e70d  mov     rcx, [rbp+18h]; this
0x14001e711  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e718  mov     r9d, ebx; char *
0x14001e71b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001e720  mov     ebx, eax
0x14001e722  jmp     loc_14001E7FC
0x14001e727  lea     rcx, [rbp+lpServiceConfig]
0x14001e72b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14001e730  mov     edx, [rbp+cbBufSize]
0x14001e733  lea     rcx, [rbp+lpServiceConfig]
0x14001e737  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x14001e73c  test    rax, rax
0x14001e73f  jnz     short loc_14001E761
0x14001e741  lea     edx, [rax+26h]; void *
0x14001e744  mov     rcx, [rbp+18h]; this
0x14001e748  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e74f  mov     ebx, 8007000Eh
0x14001e754  mov     r9d, ebx; char *
0x14001e757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e75c  jmp     loc_14001E7FC
0x14001e761  mov     rbx, [rbp+lpServiceConfig]
0x14001e765  lea     r9, [rbp+cbBufSize]; pcbBytesNeeded
0x14001e769  mov     r8d, [rbp+cbBufSize]; cbBufSize
0x14001e76d  mov     rdx, rbx; lpServiceConfig
0x14001e770  mov     rcx, rsi; hService
0x14001e773  call    cs:__imp_QueryServiceConfigW
0x14001e779  test    eax, eax
0x14001e77b  jnz     short loc_14001E7EF
0x14001e77d  call    cs:__imp_GetLastError
0x14001e783  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e78a  mov     ebx, eax
0x14001e78c  test    rcx, rcx
0x14001e78f  jz      short loc_14001E7E1
0x14001e791  mov     edi, 3
0x14001e796  lea     r9, aFailedToQueryS; "Failed to query service configuration."
0x14001e79d  mov     r8d, edi
0x14001e7a0  xor     edx, edx
0x14001e7a2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e7a7  test    ebx, ebx
0x14001e7a9  jg      short loc_14001E7AF
0x14001e7ab  mov     eax, ebx
0x14001e7ad  jmp     short loc_14001E7B7
0x14001e7af  movzx   eax, bx
0x14001e7b2  or      eax, 80070000h
0x14001e7b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e7be  lea     r9, a0; ": {0}"
0x14001e7c5  mov     [rbp+var_C], eax
0x14001e7c8  mov     r8d, edi
0x14001e7cb  lea     rax, [rbp+var_C]
0x14001e7cf  mov     qword ptr [rbp+var_18], rax
0x14001e7d3  lea     rax, [rbp+var_18]
0x14001e7d7  mov     qword ptr [rsp+50h+var_30], rax
0x14001e7dc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e7e1  test    ebx, ebx
0x14001e7e3  jz      short loc_14001E7FA
0x14001e7e5  mov     edx, 2Eh ; '.'
0x14001e7ea  jmp     loc_14001E70D
0x14001e7ef  mov     [rbp+lpServiceConfig], 0
0x14001e7f7  mov     [rdi], rbx
0x14001e7fa  xor     ebx, ebx
0x14001e7fc  lea     rcx, [rbp+lpServiceConfig]
0x14001e800  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14001e805  mov     eax, ebx
0x14001e807  mov     rcx, [rbp+var_8]
0x14001e80b  xor     rcx, rsp; StackCookie
0x14001e80e  call    __security_check_cookie
0x14001e813  mov     rbx, [rsp+50h+arg_10]
0x14001e81b  add     rsp, 50h
0x14001e81f  pop     rdi
0x14001e820  pop     rsi
0x14001e821  pop     rbp
0x14001e822  retn
```
