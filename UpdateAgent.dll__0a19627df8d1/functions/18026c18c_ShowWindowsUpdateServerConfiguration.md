# ShowWindowsUpdateServerConfiguration

- ea: `0x18026c18c`
- end: `0x18026c8bf`
- name: `ShowWindowsUpdateServerConfiguration`
- size: `1843`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18026d9b0`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000a7fc`
- `0x18000c4c4`
- `0x180012460`
- `0x1800127a4`
- `0x1800692fc`
- `0x18008b38c`
- `0x18026c18c`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18026c565`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c57e`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c6cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c845`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c85e`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c565`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c57e`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c6cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c845`
- `OLEAUT32!__imp_SysFreeString` at `0x18026c85e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026c28d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026c28d`

## string_xrefs

- `0x18026c220`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026c2fa`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026c82d`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026c373`: `Failed to get services collection`
- `0x18026c2b7`: `Failed to get IUpdateServiceManager interface`
- `0x18026c7e8`: `Failed to get update service, index: {}`
- `0x18026c6b1`: `WU: WSUS service is the default, URL: {}, Name: {}`
- `0x18026c64b`: `Failed to get whether update service is managed or not`
- `0x18026c54c`: `WU: Update service is not default AU service, skip. URL: {}, Name: {}`
- `0x18026c6ba`: `WU: Microsoft Update service is the default, URL: {}, Name: {}`
- `0x18026c4ca`: `Unable to get service URL.`
- `0x18026c791`: `Failed to query service 2`
- `0x18026c73e`: `Failed to check whether it is default service.`
- `0x18026c4fc`: `Unable to get service name.`

## pseudocode

```c
__int64 __fastcall ShowWindowsUpdateServerConfiguration(_BYTE *a1)
{
  int v2; // edi
  void (*v3)(void); // rax
  HRESULT v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  const char *v14; // rcx
  int ppv; // [rsp+20h] [rbp-29h]
  int ppva; // [rsp+20h] [rbp-29h]
  int v17[2]; // [rsp+30h] [rbp-19h] BYREF
  int v18; // [rsp+38h] [rbp-11h] BYREF
  __int64 v19; // [rsp+40h] [rbp-9h] BYREF
  int v20[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v21; // [rsp+50h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+Fh] BYREF
  BSTR v23; // [rsp+60h] [rbp+17h] BYREF
  BSTR v24; // [rsp+68h] [rbp+1Fh] BYREF
  _WORD v25[2]; // [rsp+70h] [rbp+27h] BYREF
  __int16 v26; // [rsp+74h] [rbp+2Bh] BYREF
  LPVOID v27; // [rsp+78h] [rbp+2Fh] BYREF
  int v28; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v27 = 0;
  v19 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v18 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No WSUS result specified");
      *(_QWORD *)v20 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v20);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( !v27 )
      return (unsigned int)v2;
    v3 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
LABEL_8:
    v3();
    return (unsigned int)v2;
  }
  *a1 = 0;
  v28 = 0;
  v5 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         1u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v27);
  v2 = v5;
  if ( v5 < 0 )
  {
    v18 = v5;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get IUpdateServiceManager interface");
      *(_QWORD *)v20 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v20);
    }
    v6 = 461;
    goto LABEL_14;
  }
  if ( v19 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026C8BELL);
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v19);
  v2 = v7;
  if ( v7 < 0 )
  {
    v18 = v7;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get services collection");
      *(_QWORD *)v20 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v20);
    }
    v6 = 463;
    goto LABEL_14;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 72LL))(v19, &v28);
  v2 = v8;
  if ( v8 < 0 )
  {
    v18 = v8;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get collection count.");
      *(_QWORD *)v20 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v20);
    }
    v6 = 465;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v2,
      ppva);
LABEL_15:
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( !v27 )
      return (unsigned int)v2;
    v3 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
    goto LABEL_8;
  }
  v18 = 0;
  if ( v28 > 0 )
  {
    v9 = 0;
    while ( 1 )
    {
      *(_QWORD *)v20 = 0;
      v21 = 0;
      v23 = 0;
      bstrString = 0;
      v26 = 0;
      v25[0] = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v19 + 56LL))(v19, v9, v20);
      if ( v2 < 0 )
      {
        LODWORD(v24) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<long>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to get update service, index: {}");
          *(_QWORD *)v17 = &v24;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v17);
        }
        v13 = 477;
        goto LABEL_79;
      }
      if ( v21 )
        goto LABEL_87;
      v2 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v20)(
             *(_QWORD *)v20,
             &GUID_1518b460_6518_4172_940f_c75883b24ceb,
             &v21);
      if ( v2 < 0 )
      {
        LODWORD(v24) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query service 2");
          *(_QWORD *)v17 = &v24;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v17);
        }
        v13 = 479;
        goto LABEL_79;
      }
      if ( v23 )
        goto LABEL_87;
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 144LL))(v21, &v23);
      if ( v10 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v10, "Unable to get service URL.");
      if ( bstrString )
      {
LABEL_87:
        INTERNAL_ERROR_ACTION(-1073741595);
        __debugbreak();
      }
      v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 56LL))(v21, &bstrString);
      if ( v11 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v11, "Unable to get service name.");
      v2 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v21 + 160LL))(v21, v25);
      if ( v2 < 0 )
      {
        LODWORD(v24) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to check whether it is default service.");
          *(_QWORD *)v17 = &v24;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v17);
        }
        v13 = 485;
        goto LABEL_79;
      }
      if ( v25[0] == 0xFFFF )
        break;
      v24 = bstrString;
      *(_QWORD *)v17 = v23;
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "WU: Update service is not default AU service, skip. URL: {}, Name: {}",
        v17,
        &v24);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v23 )
      {
        SysFreeString(v23);
        v23 = 0;
      }
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
      }
      if ( *(_QWORD *)v20 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 16LL))(*(_QWORD *)v20);
      v9 = (unsigned int)(v18 + 1);
      v18 = v9;
      if ( (int)v9 >= v28 )
        goto LABEL_50;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v21 + 80LL))(v21, &v26);
    v2 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v24) = v12;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get whether update service is managed or not");
        *(_QWORD *)v17 = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v17);
      }
      v13 = 489;
LABEL_79:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v2,
        ppva);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v23 )
      {
        SysFreeString(v23);
        v23 = 0;
      }
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
      }
      if ( *(_QWORD *)v20 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 16LL))(*(_QWORD *)v20);
        *(_QWORD *)v20 = 0;
      }
      goto LABEL_15;
    }
    *(_QWORD *)v17 = bstrString;
    v24 = v23;
    if ( v26 == -1 )
    {
      *a1 = 1;
      v14 = "WU: WSUS service is the default, URL: {}, Name: {}";
    }
    else
    {
      v14 = "WU: Microsoft Update service is the default, URL: {}, Name: {}";
    }
    LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(v14, &v24, v17);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v23 )
    {
      SysFreeString(v23);
      v23 = 0;
    }
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( *(_QWORD *)v20 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 16LL))(*(_QWORD *)v20);
  }
LABEL_50:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v27 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  return 0;
}

```

## disassembly

```asm
0x18026c18c  mov     [rsp-8+arg_8], rbx
0x18026c191  mov     [rsp-8+arg_10], rsi
0x18026c196  push    rbp
0x18026c197  push    rdi
0x18026c198  push    r14
0x18026c19a  lea     rbp, [rsp-47h]
0x18026c19f  sub     rsp, 90h
0x18026c1a6  mov     rax, cs:__security_cookie
0x18026c1ad  xor     rax, rsp
0x18026c1b0  mov     [rbp+57h+var_18], rax
0x18026c1b4  xor     r14d, r14d
0x18026c1b7  mov     rsi, rcx
0x18026c1ba  mov     [rbp+57h+var_28], r14
0x18026c1be  mov     [rbp+57h+var_60], r14
0x18026c1c2  test    rcx, rcx
0x18026c1c5  jnz     loc_18026C269
0x18026c1cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c1d2  mov     edi, 80004003h
0x18026c1d7  mov     [rbp+57h+var_68], edi
0x18026c1da  test    rcx, rcx
0x18026c1dd  jz      short loc_18026C21C
0x18026c1df  lea     ebx, [rsi+3]
0x18026c1e2  xor     edx, edx
0x18026c1e4  mov     r8d, ebx
0x18026c1e7  lea     r9, aNoWsusResultSp; "No WSUS result specified"
0x18026c1ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c1f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c1fa  lea     rax, [rbp+57h+var_68]
0x18026c1fe  mov     qword ptr [rbp+57h+var_58], rax
0x18026c202  lea     r9, asc_1802C6678; ": {}"
0x18026c209  lea     rax, [rbp+57h+var_58]
0x18026c20d  mov     r8d, ebx
0x18026c210  mov     dl, 1
0x18026c212  mov     qword ptr [rsp+0A0h+ppv], rax; int
0x18026c217  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c21c  mov     rcx, [rbp+5Fh]; this
0x18026c220  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026c227  mov     r9d, edi; char *
0x18026c22a  mov     edx, 1C6h; void *
0x18026c22f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c234  mov     rcx, [rbp+57h+var_60]
0x18026c238  test    rcx, rcx
0x18026c23b  jz      short loc_18026C24D
0x18026c23d  mov     rax, [rcx]
0x18026c240  mov     rax, [rax+10h]
0x18026c244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c249  mov     [rbp+57h+var_60], r14
0x18026c24d  mov     rcx, [rbp+57h+var_28]
0x18026c251  test    rcx, rcx
0x18026c254  jz      short loc_18026C262
0x18026c256  mov     rdx, [rcx]
0x18026c259  mov     rax, [rdx+10h]
0x18026c25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c262  mov     eax, edi
0x18026c264  jmp     loc_18026C5FD
0x18026c269  xor     edx, edx; pUnkOuter
0x18026c26b  mov     [rcx], r14b
0x18026c26e  lea     rax, [rbp+57h+var_28]
0x18026c272  mov     [rbp+57h+var_20], r14d
0x18026c276  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x18026c27d  mov     qword ptr [rsp+0A0h+ppv], rax; ppv
0x18026c282  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x18026c289  lea     r8d, [rdx+1]; dwClsContext
0x18026c28d  call    cs:__imp_CoCreateInstance
0x18026c294  nop     dword ptr [rax+rax+00h]
0x18026c299  mov     edi, eax
0x18026c29b  test    eax, eax
0x18026c29d  jns     loc_18026C33B
0x18026c2a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c2aa  mov     [rbp+57h+var_68], eax
0x18026c2ad  test    rcx, rcx
0x18026c2b0  jz      short loc_18026C2F1
0x18026c2b2  mov     ebx, 3
0x18026c2b7  lea     r9, aFailedToGetIup; "Failed to get IUpdateServiceManager int"...
0x18026c2be  mov     r8d, ebx
0x18026c2c1  xor     edx, edx
0x18026c2c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c2c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c2cf  lea     rax, [rbp+57h+var_68]
0x18026c2d3  mov     qword ptr [rbp+57h+var_58], rax
0x18026c2d7  lea     r9, asc_1802C6678; ": {}"
0x18026c2de  lea     rax, [rbp+57h+var_58]
0x18026c2e2  mov     r8d, ebx
0x18026c2e5  mov     dl, 1
0x18026c2e7  mov     qword ptr [rsp+0A0h+ppv], rax; int
0x18026c2ec  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c2f1  mov     edx, 1CDh; void *
0x18026c2f6  mov     rcx, [rbp+5Fh]; this
0x18026c2fa  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026c301  mov     r9d, edi; char *
0x18026c304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c309  mov     rcx, [rbp+57h+var_60]
0x18026c30d  test    rcx, rcx
0x18026c310  jz      short loc_18026C322
0x18026c312  mov     rax, [rcx]
0x18026c315  mov     rax, [rax+10h]
0x18026c319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c31e  mov     [rbp+57h+var_60], r14
0x18026c322  mov     rcx, [rbp+57h+var_28]
0x18026c326  test    rcx, rcx
0x18026c329  jz      loc_18026C262
0x18026c32f  mov     rax, [rcx]
0x18026c332  mov     rax, [rax+10h]
0x18026c336  jmp     loc_18026C25D
0x18026c33b  cmp     [rbp+57h+var_60], r14
0x18026c33f  jnz     loc_18026C8B4
0x18026c345  mov     rcx, [rbp+57h+var_28]
0x18026c349  lea     rdx, [rbp+57h+var_60]
0x18026c34d  mov     rax, [rcx]
0x18026c350  mov     rax, [rax+38h]
0x18026c354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c359  mov     edi, eax
0x18026c35b  test    eax, eax
0x18026c35d  jns     short loc_18026C3B7
0x18026c35f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c366  mov     [rbp+57h+var_68], eax
0x18026c369  test    rcx, rcx
0x18026c36c  jz      short loc_18026C3AD
0x18026c36e  mov     ebx, 3
0x18026c373  lea     r9, aFailedToGetSer; "Failed to get services collection"
0x18026c37a  mov     r8d, ebx
0x18026c37d  xor     edx, edx
0x18026c37f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c384  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c38b  lea     rax, [rbp+57h+var_68]
0x18026c38f  mov     qword ptr [rbp+57h+var_58], rax
0x18026c393  lea     r9, asc_1802C6678; ": {}"
0x18026c39a  lea     rax, [rbp+57h+var_58]
0x18026c39e  mov     r8d, ebx
0x18026c3a1  mov     dl, 1
0x18026c3a3  mov     qword ptr [rsp+0A0h+ppv], rax
0x18026c3a8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c3ad  mov     edx, 1CFh
0x18026c3b2  jmp     loc_18026C2F6
0x18026c3b7  mov     rcx, [rbp+57h+var_60]
0x18026c3bb  lea     rdx, [rbp+57h+var_20]
0x18026c3bf  mov     rax, [rcx]
0x18026c3c2  mov     rax, [rax+48h]
0x18026c3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c3cb  mov     edi, eax
0x18026c3cd  test    eax, eax
0x18026c3cf  jns     short loc_18026C429
0x18026c3d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c3d8  mov     [rbp+57h+var_68], eax
0x18026c3db  test    rcx, rcx
0x18026c3de  jz      short loc_18026C41F
0x18026c3e0  mov     ebx, 3
0x18026c3e5  lea     r9, aFailedToGetCol; "Failed to get collection count."
0x18026c3ec  mov     r8d, ebx
0x18026c3ef  xor     edx, edx
0x18026c3f1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c3f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c3fd  lea     rax, [rbp+57h+var_68]
0x18026c401  mov     qword ptr [rbp+57h+var_58], rax
0x18026c405  lea     r9, asc_1802C6678; ": {}"
0x18026c40c  lea     rax, [rbp+57h+var_58]
0x18026c410  mov     r8d, ebx
0x18026c413  mov     dl, 1
0x18026c415  mov     qword ptr [rsp+0A0h+ppv], rax
0x18026c41a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c41f  mov     edx, 1D1h
0x18026c424  jmp     loc_18026C2F6
0x18026c429  mov     [rbp+57h+var_68], r14d
0x18026c42d  cmp     [rbp+57h+var_20], r14d
0x18026c431  jle     loc_18026C5CD
0x18026c437  mov     edx, r14d
0x18026c43a  mov     ebx, 3
0x18026c43f  mov     rcx, [rbp+57h+var_60]
0x18026c443  lea     r8, [rbp+57h+var_58]
0x18026c447  mov     qword ptr [rbp+57h+var_58], r14
0x18026c44b  mov     [rbp+57h+var_50], r14
0x18026c44f  mov     [rbp+57h+var_40], r14
0x18026c453  mov     [rbp+57h+bstrString], r14
0x18026c457  mov     [rbp+57h+var_2C], r14w
0x18026c45c  mov     [rbp+57h+var_30], r14w
0x18026c461  mov     rax, [rcx]
0x18026c464  mov     rax, [rax+38h]
0x18026c468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c46d  mov     edi, eax
0x18026c46f  test    eax, eax
0x18026c471  js      loc_18026C7D2
0x18026c477  cmp     [rbp+57h+var_50], r14
0x18026c47b  jnz     loc_18026C8A9
0x18026c481  mov     rcx, qword ptr [rbp+57h+var_58]
0x18026c485  lea     r8, [rbp+57h+var_50]
0x18026c489  lea     rdx, _GUID_1518b460_6518_4172_940f_c75883b24ceb
0x18026c490  mov     rax, [rcx]
0x18026c493  mov     rax, [rax]
0x18026c496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c49b  mov     edi, eax
0x18026c49d  test    eax, eax
0x18026c49f  js      loc_18026C782
0x18026c4a5  cmp     [rbp+57h+var_40], r14
0x18026c4a9  jnz     loc_18026C8A9
0x18026c4af  mov     rcx, [rbp+57h+var_50]
0x18026c4b3  lea     rdx, [rbp+57h+var_40]
0x18026c4b7  mov     rax, [rcx]
0x18026c4ba  mov     rax, [rax+90h]
0x18026c4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c4c6  test    eax, eax
0x18026c4c8  jns     short loc_18026C4DA
0x18026c4ca  lea     r8, aUnableToGetSer_0; "Unable to get service URL."
0x18026c4d1  mov     edx, eax
0x18026c4d3  mov     ecx, ebx
0x18026c4d5  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18026c4da  cmp     [rbp+57h+bstrString], r14
0x18026c4de  jnz     loc_18026C8A9
0x18026c4e4  mov     rcx, [rbp+57h+var_50]
0x18026c4e8  lea     rdx, [rbp+57h+bstrString]
0x18026c4ec  mov     rax, [rcx]
0x18026c4ef  mov     rax, [rax+38h]
0x18026c4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c4f8  test    eax, eax
0x18026c4fa  jns     short loc_18026C50C
0x18026c4fc  lea     r8, aUnableToGetSer; "Unable to get service name."
0x18026c503  mov     edx, eax
0x18026c505  mov     ecx, ebx
0x18026c507  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18026c50c  mov     rcx, [rbp+57h+var_50]
0x18026c510  lea     rdx, [rbp+57h+var_30]
0x18026c514  mov     rax, [rcx]
0x18026c517  mov     rax, [rax+0A0h]
0x18026c51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c523  mov     edi, eax
0x18026c525  test    eax, eax
0x18026c527  js      loc_18026C72F
0x18026c52d  cmp     [rbp+57h+var_30], 0FFFFh
0x18026c532  jz      loc_18026C622
0x18026c538  mov     rax, [rbp+57h+bstrString]
0x18026c53c  lea     r8, [rbp+57h+var_38]
0x18026c540  mov     [rbp+57h+var_38], rax
0x18026c544  lea     rdx, [rbp+57h+var_70]
0x18026c548  mov     rax, [rbp+57h+var_40]
0x18026c54c  lea     rcx, aWuUpdateServic; "WU: Update service is not default AU se"...
0x18026c553  mov     qword ptr [rbp+57h+var_70], rax
0x18026c557  call    ??$TraceInfo@PEB_WPEA_W@LogAdapter@@YAXQEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(char const * const,wchar_t const * const &,wchar_t * const &)
0x18026c55c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18026c560  test    rcx, rcx
0x18026c563  jz      short loc_18026C575
0x18026c565  call    cs:__imp_SysFreeString
0x18026c56c  nop     dword ptr [rax+rax+00h]
0x18026c571  mov     [rbp+57h+bstrString], r14
0x18026c575  mov     rcx, [rbp+57h+var_40]; bstrString
0x18026c579  test    rcx, rcx
0x18026c57c  jz      short loc_18026C58E
0x18026c57e  call    cs:__imp_SysFreeString
0x18026c585  nop     dword ptr [rax+rax+00h]
0x18026c58a  mov     [rbp+57h+var_40], r14
0x18026c58e  mov     rcx, [rbp+57h+var_50]
0x18026c592  test    rcx, rcx
0x18026c595  jz      short loc_18026C5A7
0x18026c597  mov     rax, [rcx]
0x18026c59a  mov     rax, [rax+10h]
0x18026c59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c5a3  mov     [rbp+57h+var_50], r14
0x18026c5a7  mov     rcx, qword ptr [rbp+57h+var_58]
0x18026c5ab  test    rcx, rcx
0x18026c5ae  jz      short loc_18026C5BC
0x18026c5b0  mov     rax, [rcx]
0x18026c5b3  mov     rax, [rax+10h]
0x18026c5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c5bc  mov     edx, [rbp+57h+var_68]
0x18026c5bf  inc     edx
0x18026c5c1  mov     [rbp+57h+var_68], edx
0x18026c5c4  cmp     edx, [rbp+57h+var_20]
0x18026c5c7  jl      loc_18026C43F
0x18026c5cd  mov     rcx, [rbp+57h+var_60]
0x18026c5d1  test    rcx, rcx
0x18026c5d4  jz      short loc_18026C5E6
0x18026c5d6  mov     rax, [rcx]
0x18026c5d9  mov     rax, [rax+10h]
0x18026c5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c5e2  mov     [rbp+57h+var_60], r14
0x18026c5e6  mov     rcx, [rbp+57h+var_28]
0x18026c5ea  test    rcx, rcx
0x18026c5ed  jz      short loc_18026C5FB
0x18026c5ef  mov     rax, [rcx]
0x18026c5f2  mov     rax, [rax+10h]
0x18026c5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c5fb  xor     eax, eax
0x18026c5fd  mov     rcx, [rbp+57h+var_18]
0x18026c601  xor     rcx, rsp; StackCookie
0x18026c604  call    __security_check_cookie
0x18026c609  lea     r11, [rsp+0A0h+var_10]
0x18026c611  mov     rbx, [r11+28h]
0x18026c615  mov     rsi, [r11+30h]
0x18026c619  mov     rsp, r11
0x18026c61c  pop     r14
0x18026c61e  pop     rdi
0x18026c61f  pop     rbp
0x18026c620  retn
0x18026c622  mov     rcx, [rbp+57h+var_50]
0x18026c626  lea     rdx, [rbp+57h+var_2C]
0x18026c62a  mov     rax, [rcx]
0x18026c62d  mov     rax, [rax+50h]
0x18026c631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c636  mov     edi, eax
0x18026c638  test    eax, eax
0x18026c63a  jns     short loc_18026C68F
0x18026c63c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
