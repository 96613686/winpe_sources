# ShowWindowsUpdateServerConfiguration

- ea: `0x1801aed78`
- end: `0x1801af4ab`
- name: `ShowWindowsUpdateServerConfiguration`
- size: `1843`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b066c`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001ba14`
- `0x180065a7c`
- `0x1801aed78`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801aee79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801aee79`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af151`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af16a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af2bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af2d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af431`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af44a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af151`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af16a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af2bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af2d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af431`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af44a`

## string_xrefs

- `0x1801aee0c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801aeee6`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801af419`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801af3d4`: `Failed to get update service, index: {}`
- `0x1801af0b6`: `Unable to get service URL.`
- `0x1801af37d`: `Failed to query service 2`
- `0x1801aef5f`: `Failed to get services collection`
- `0x1801aeea3`: `Failed to get IUpdateServiceManager interface`
- `0x1801af138`: `WU: Update service is not default AU service, skip. URL: {}, Name: {}`
- `0x1801af2a6`: `WU: Microsoft Update service is the default, URL: {}, Name: {}`
- `0x1801af32a`: `Failed to check whether it is default service.`
- `0x1801af0e8`: `Unable to get service name.`
- `0x1801af29d`: `WU: WSUS service is the default, URL: {}, Name: {}`
- `0x1801af237`: `Failed to get whether update service is managed or not`

## pseudocode

```c
__int64 __fastcall ShowWindowsUpdateServerConfiguration(_BYTE *a1)
{
  int v2; // edi
  __int64 v3; // rdx
  void (*v4)(void); // rax
  HRESULT v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  const char *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int *ppv; // [rsp+20h] [rbp-29h]
  int *ppva; // [rsp+20h] [rbp-29h]
  int v25[2]; // [rsp+30h] [rbp-19h] BYREF
  int v26; // [rsp+38h] [rbp-11h] BYREF
  __int64 v27; // [rsp+40h] [rbp-9h] BYREF
  int v28[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v29; // [rsp+50h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+Fh] BYREF
  BSTR v31; // [rsp+60h] [rbp+17h] BYREF
  BSTR v32; // [rsp+68h] [rbp+1Fh] BYREF
  _WORD v33[2]; // [rsp+70h] [rbp+27h] BYREF
  __int16 v34; // [rsp+74h] [rbp+2Bh] BYREF
  LPVOID v35; // [rsp+78h] [rbp+2Fh] BYREF
  int v36; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v35 = 0;
  v27 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v26 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No WSUS result specified");
      *(_QWORD *)v28 = &v26;
      LOBYTE(v3) = 1;
      ppv = v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v3,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      (int)ppv);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    if ( !v35 )
      return (unsigned int)v2;
    v4 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
LABEL_8:
    v4();
    return (unsigned int)v2;
  }
  *a1 = 0;
  v36 = 0;
  v6 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         1u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v35);
  v2 = v6;
  if ( v6 < 0 )
  {
    v26 = v6;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get IUpdateServiceManager interface");
      *(_QWORD *)v28 = &v26;
      LOBYTE(v7) = 1;
      ppva = v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    v8 = 461;
    goto LABEL_14;
  }
  if ( v27 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801AF4AALL);
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v35 + 56LL))(v35, &v27);
  v2 = v9;
  if ( v9 < 0 )
  {
    v26 = v9;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get services collection");
      *(_QWORD *)v28 = &v26;
      LOBYTE(v10) = 1;
      ppva = v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    v8 = 463;
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 72LL))(v27, &v36);
  v2 = v11;
  if ( v11 < 0 )
  {
    v26 = v11;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get collection count.");
      *(_QWORD *)v28 = &v26;
      LOBYTE(v12) = 1;
      ppva = v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    v8 = 465;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v2,
      (int)ppva);
LABEL_15:
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    if ( !v35 )
      return (unsigned int)v2;
    v4 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
    goto LABEL_8;
  }
  v26 = 0;
  if ( v36 > 0 )
  {
    v13 = 0;
    while ( 1 )
    {
      *(_QWORD *)v28 = 0;
      v29 = 0;
      v31 = 0;
      bstrString = 0;
      v34 = 0;
      v33[0] = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v27 + 56LL))(v27, v13, v28);
      if ( v2 < 0 )
      {
        LODWORD(v32) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<long>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to get update service, index: {}",
            &v26);
          *(_QWORD *)v25 = &v32;
          LOBYTE(v22) = 1;
          ppva = v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v22,
            3,
            ": {}");
        }
        v18 = 477;
        goto LABEL_79;
      }
      if ( v29 )
        goto LABEL_87;
      v2 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v28)(
             *(_QWORD *)v28,
             &GUID_1518b460_6518_4172_940f_c75883b24ceb,
             &v29);
      if ( v2 < 0 )
      {
        LODWORD(v32) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to query service 2");
          *(_QWORD *)v25 = &v32;
          LOBYTE(v21) = 1;
          ppva = v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v21,
            3,
            ": {}");
        }
        v18 = 479;
        goto LABEL_79;
      }
      if ( v31 )
        goto LABEL_87;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 144LL))(v29, &v31);
      if ( v14 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v14, "Unable to get service URL.");
      if ( bstrString )
      {
LABEL_87:
        INTERNAL_ERROR_ACTION(-1073741595);
        __debugbreak();
      }
      v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 56LL))(v29, &bstrString);
      if ( v15 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v15, "Unable to get service name.");
      v2 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v29 + 160LL))(v29, v33);
      if ( v2 < 0 )
      {
        LODWORD(v32) = v2;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to check whether it is default service.");
          *(_QWORD *)v25 = &v32;
          LOBYTE(v20) = 1;
          ppva = v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v20,
            3,
            ": {}");
        }
        v18 = 485;
        goto LABEL_79;
      }
      if ( v33[0] == 0xFFFF )
        break;
      v32 = bstrString;
      *(_QWORD *)v25 = v31;
      LogAdapter::TraceInfo<wchar_t *,wchar_t *>(
        "WU: Update service is not default AU service, skip. URL: {}, Name: {}",
        v25,
        &v32);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v31 )
      {
        SysFreeString(v31);
        v31 = 0;
      }
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v29 = 0;
      }
      if ( *(_QWORD *)v28 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
      v13 = (unsigned int)(v26 + 1);
      v26 = v13;
      if ( (int)v13 >= v36 )
        goto LABEL_50;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v29 + 80LL))(v29, &v34);
    v2 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v32) = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get whether update service is managed or not");
        *(_QWORD *)v25 = &v32;
        LOBYTE(v17) = 1;
        ppva = v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v17,
          3,
          ": {}");
      }
      v18 = 489;
LABEL_79:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v2,
        (int)ppva);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v31 )
      {
        SysFreeString(v31);
        v31 = 0;
      }
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v29 = 0;
      }
      if ( *(_QWORD *)v28 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
        *(_QWORD *)v28 = 0;
      }
      goto LABEL_15;
    }
    *(_QWORD *)v25 = bstrString;
    v32 = v31;
    if ( v34 == -1 )
    {
      *a1 = 1;
      v19 = "WU: WSUS service is the default, URL: {}, Name: {}";
    }
    else
    {
      v19 = "WU: Microsoft Update service is the default, URL: {}, Name: {}";
    }
    LogAdapter::TraceInfo<wchar_t *,wchar_t *>(v19, &v32, v25);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v31 )
    {
      SysFreeString(v31);
      v31 = 0;
    }
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = 0;
    }
    if ( *(_QWORD *)v28 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
  }
LABEL_50:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v35 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
  return 0;
}

```

## disassembly

```asm
0x1801aed78  mov     [rsp-8+arg_8], rbx
0x1801aed7d  mov     [rsp-8+arg_10], rsi
0x1801aed82  push    rbp
0x1801aed83  push    rdi
0x1801aed84  push    r14
0x1801aed86  lea     rbp, [rsp-47h]
0x1801aed8b  sub     rsp, 90h
0x1801aed92  mov     rax, cs:__security_cookie
0x1801aed99  xor     rax, rsp
0x1801aed9c  mov     [rbp+57h+var_18], rax
0x1801aeda0  xor     r14d, r14d
0x1801aeda3  mov     rsi, rcx
0x1801aeda6  mov     [rbp+57h+var_28], r14
0x1801aedaa  mov     [rbp+57h+var_60], r14
0x1801aedae  test    rcx, rcx
0x1801aedb1  jnz     loc_1801AEE55
0x1801aedb7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aedbe  mov     edi, 80004003h
0x1801aedc3  mov     [rbp+57h+var_68], edi
0x1801aedc6  test    rcx, rcx
0x1801aedc9  jz      short loc_1801AEE08
0x1801aedcb  lea     ebx, [rsi+3]
0x1801aedce  xor     edx, edx
0x1801aedd0  mov     r8d, ebx
0x1801aedd3  lea     r9, aNoWsusResultSp; "No WSUS result specified"
0x1801aedda  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801aeddf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aede6  lea     rax, [rbp+57h+var_68]
0x1801aedea  mov     qword ptr [rbp+57h+var_58], rax
0x1801aedee  lea     r9, asc_1801CAFB4; ": {}"
0x1801aedf5  lea     rax, [rbp+57h+var_58]
0x1801aedf9  mov     r8d, ebx
0x1801aedfc  mov     dl, 1
0x1801aedfe  mov     [rsp+0A0h+ppv], rax; int
0x1801aee03  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801aee08  mov     rcx, [rbp+5Fh]; this
0x1801aee0c  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801aee13  mov     r9d, edi; char *
0x1801aee16  mov     edx, 1C6h; void *
0x1801aee1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aee20  mov     rcx, [rbp+57h+var_60]
0x1801aee24  test    rcx, rcx
0x1801aee27  jz      short loc_1801AEE39
0x1801aee29  mov     rax, [rcx]
0x1801aee2c  mov     rax, [rax+10h]
0x1801aee30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aee35  mov     [rbp+57h+var_60], r14
0x1801aee39  mov     rcx, [rbp+57h+var_28]
0x1801aee3d  test    rcx, rcx
0x1801aee40  jz      short loc_1801AEE4E
0x1801aee42  mov     rdx, [rcx]
0x1801aee45  mov     rax, [rdx+10h]
0x1801aee49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aee4e  mov     eax, edi
0x1801aee50  jmp     loc_1801AF1E9
0x1801aee55  xor     edx, edx; pUnkOuter
0x1801aee57  mov     [rcx], r14b
0x1801aee5a  lea     rax, [rbp+57h+var_28]
0x1801aee5e  mov     [rbp+57h+var_20], r14d
0x1801aee62  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x1801aee69  mov     [rsp+0A0h+ppv], rax; ppv
0x1801aee6e  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x1801aee75  lea     r8d, [rdx+1]; dwClsContext
0x1801aee79  call    cs:__imp_CoCreateInstance
0x1801aee80  nop     dword ptr [rax+rax+00h]
0x1801aee85  mov     edi, eax
0x1801aee87  test    eax, eax
0x1801aee89  jns     loc_1801AEF27
0x1801aee8f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aee96  mov     [rbp+57h+var_68], eax
0x1801aee99  test    rcx, rcx
0x1801aee9c  jz      short loc_1801AEEDD
0x1801aee9e  mov     ebx, 3
0x1801aeea3  lea     r9, aFailedToGetIup; "Failed to get IUpdateServiceManager int"...
0x1801aeeaa  mov     r8d, ebx
0x1801aeead  xor     edx, edx
0x1801aeeaf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801aeeb4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aeebb  lea     rax, [rbp+57h+var_68]
0x1801aeebf  mov     qword ptr [rbp+57h+var_58], rax
0x1801aeec3  lea     r9, asc_1801CAFB4; ": {}"
0x1801aeeca  lea     rax, [rbp+57h+var_58]
0x1801aeece  mov     r8d, ebx
0x1801aeed1  mov     dl, 1
0x1801aeed3  mov     [rsp+0A0h+ppv], rax; int
0x1801aeed8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801aeedd  mov     edx, 1CDh; void *
0x1801aeee2  mov     rcx, [rbp+5Fh]; this
0x1801aeee6  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801aeeed  mov     r9d, edi; char *
0x1801aeef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aeef5  mov     rcx, [rbp+57h+var_60]
0x1801aeef9  test    rcx, rcx
0x1801aeefc  jz      short loc_1801AEF0E
0x1801aeefe  mov     rax, [rcx]
0x1801aef01  mov     rax, [rax+10h]
0x1801aef05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aef0a  mov     [rbp+57h+var_60], r14
0x1801aef0e  mov     rcx, [rbp+57h+var_28]
0x1801aef12  test    rcx, rcx
0x1801aef15  jz      loc_1801AEE4E
0x1801aef1b  mov     rax, [rcx]
0x1801aef1e  mov     rax, [rax+10h]
0x1801aef22  jmp     loc_1801AEE49
0x1801aef27  cmp     [rbp+57h+var_60], r14
0x1801aef2b  jnz     loc_1801AF4A0
0x1801aef31  mov     rcx, [rbp+57h+var_28]
0x1801aef35  lea     rdx, [rbp+57h+var_60]
0x1801aef39  mov     rax, [rcx]
0x1801aef3c  mov     rax, [rax+38h]
0x1801aef40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aef45  mov     edi, eax
0x1801aef47  test    eax, eax
0x1801aef49  jns     short loc_1801AEFA3
0x1801aef4b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aef52  mov     [rbp+57h+var_68], eax
0x1801aef55  test    rcx, rcx
0x1801aef58  jz      short loc_1801AEF99
0x1801aef5a  mov     ebx, 3
0x1801aef5f  lea     r9, aFailedToGetSer; "Failed to get services collection"
0x1801aef66  mov     r8d, ebx
0x1801aef69  xor     edx, edx
0x1801aef6b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801aef70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aef77  lea     rax, [rbp+57h+var_68]
0x1801aef7b  mov     qword ptr [rbp+57h+var_58], rax
0x1801aef7f  lea     r9, asc_1801CAFB4; ": {}"
0x1801aef86  lea     rax, [rbp+57h+var_58]
0x1801aef8a  mov     r8d, ebx
0x1801aef8d  mov     dl, 1
0x1801aef8f  mov     [rsp+0A0h+ppv], rax
0x1801aef94  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801aef99  mov     edx, 1CFh
0x1801aef9e  jmp     loc_1801AEEE2
0x1801aefa3  mov     rcx, [rbp+57h+var_60]
0x1801aefa7  lea     rdx, [rbp+57h+var_20]
0x1801aefab  mov     rax, [rcx]
0x1801aefae  mov     rax, [rax+48h]
0x1801aefb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aefb7  mov     edi, eax
0x1801aefb9  test    eax, eax
0x1801aefbb  jns     short loc_1801AF015
0x1801aefbd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aefc4  mov     [rbp+57h+var_68], eax
0x1801aefc7  test    rcx, rcx
0x1801aefca  jz      short loc_1801AF00B
0x1801aefcc  mov     ebx, 3
0x1801aefd1  lea     r9, aFailedToGetCol; "Failed to get collection count."
0x1801aefd8  mov     r8d, ebx
0x1801aefdb  xor     edx, edx
0x1801aefdd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801aefe2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801aefe9  lea     rax, [rbp+57h+var_68]
0x1801aefed  mov     qword ptr [rbp+57h+var_58], rax
0x1801aeff1  lea     r9, asc_1801CAFB4; ": {}"
0x1801aeff8  lea     rax, [rbp+57h+var_58]
0x1801aeffc  mov     r8d, ebx
0x1801aefff  mov     dl, 1
0x1801af001  mov     [rsp+0A0h+ppv], rax
0x1801af006  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801af00b  mov     edx, 1D1h
0x1801af010  jmp     loc_1801AEEE2
0x1801af015  mov     [rbp+57h+var_68], r14d
0x1801af019  cmp     [rbp+57h+var_20], r14d
0x1801af01d  jle     loc_1801AF1B9
0x1801af023  mov     edx, r14d
0x1801af026  mov     ebx, 3
0x1801af02b  mov     rcx, [rbp+57h+var_60]
0x1801af02f  lea     r8, [rbp+57h+var_58]
0x1801af033  mov     qword ptr [rbp+57h+var_58], r14
0x1801af037  mov     [rbp+57h+var_50], r14
0x1801af03b  mov     [rbp+57h+var_40], r14
0x1801af03f  mov     [rbp+57h+bstrString], r14
0x1801af043  mov     [rbp+57h+var_2C], r14w
0x1801af048  mov     [rbp+57h+var_30], r14w
0x1801af04d  mov     rax, [rcx]
0x1801af050  mov     rax, [rax+38h]
0x1801af054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af059  mov     edi, eax
0x1801af05b  test    eax, eax
0x1801af05d  js      loc_1801AF3BE
0x1801af063  cmp     [rbp+57h+var_50], r14
0x1801af067  jnz     loc_1801AF495
0x1801af06d  mov     rcx, qword ptr [rbp+57h+var_58]
0x1801af071  lea     r8, [rbp+57h+var_50]
0x1801af075  lea     rdx, _GUID_1518b460_6518_4172_940f_c75883b24ceb
0x1801af07c  mov     rax, [rcx]
0x1801af07f  mov     rax, [rax]
0x1801af082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af087  mov     edi, eax
0x1801af089  test    eax, eax
0x1801af08b  js      loc_1801AF36E
0x1801af091  cmp     [rbp+57h+var_40], r14
0x1801af095  jnz     loc_1801AF495
0x1801af09b  mov     rcx, [rbp+57h+var_50]
0x1801af09f  lea     rdx, [rbp+57h+var_40]
0x1801af0a3  mov     rax, [rcx]
0x1801af0a6  mov     rax, [rax+90h]
0x1801af0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af0b2  test    eax, eax
0x1801af0b4  jns     short loc_1801AF0C6
0x1801af0b6  lea     r8, aUnableToGetSer_0; "Unable to get service URL."
0x1801af0bd  mov     edx, eax
0x1801af0bf  mov     ecx, ebx
0x1801af0c1  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801af0c6  cmp     [rbp+57h+bstrString], r14
0x1801af0ca  jnz     loc_1801AF495
0x1801af0d0  mov     rcx, [rbp+57h+var_50]
0x1801af0d4  lea     rdx, [rbp+57h+bstrString]
0x1801af0d8  mov     rax, [rcx]
0x1801af0db  mov     rax, [rax+38h]
0x1801af0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af0e4  test    eax, eax
0x1801af0e6  jns     short loc_1801AF0F8
0x1801af0e8  lea     r8, aUnableToGetSer; "Unable to get service name."
0x1801af0ef  mov     edx, eax
0x1801af0f1  mov     ecx, ebx
0x1801af0f3  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801af0f8  mov     rcx, [rbp+57h+var_50]
0x1801af0fc  lea     rdx, [rbp+57h+var_30]
0x1801af100  mov     rax, [rcx]
0x1801af103  mov     rax, [rax+0A0h]
0x1801af10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af10f  mov     edi, eax
0x1801af111  test    eax, eax
0x1801af113  js      loc_1801AF31B
0x1801af119  cmp     [rbp+57h+var_30], 0FFFFh
0x1801af11e  jz      loc_1801AF20E
0x1801af124  mov     rax, [rbp+57h+bstrString]
0x1801af128  lea     r8, [rbp+57h+var_38]
0x1801af12c  mov     [rbp+57h+var_38], rax
0x1801af130  lea     rdx, [rbp+57h+var_70]
0x1801af134  mov     rax, [rbp+57h+var_40]
0x1801af138  lea     rcx, aWuUpdateServic; "WU: Update service is not default AU se"...
0x1801af13f  mov     qword ptr [rbp+57h+var_70], rax
0x1801af143  call    ??$TraceInfo@PEA_WPEA_W@LogAdapter@@YAXQEBDAEBQEA_W1@Z; LogAdapter::TraceInfo<wchar_t *,wchar_t *>(char const * const,wchar_t * const &,wchar_t * const &)
0x1801af148  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1801af14c  test    rcx, rcx
0x1801af14f  jz      short loc_1801AF161
0x1801af151  call    cs:__imp_SysFreeString
0x1801af158  nop     dword ptr [rax+rax+00h]
0x1801af15d  mov     [rbp+57h+bstrString], r14
0x1801af161  mov     rcx, [rbp+57h+var_40]; bstrString
0x1801af165  test    rcx, rcx
0x1801af168  jz      short loc_1801AF17A
0x1801af16a  call    cs:__imp_SysFreeString
0x1801af171  nop     dword ptr [rax+rax+00h]
0x1801af176  mov     [rbp+57h+var_40], r14
0x1801af17a  mov     rcx, [rbp+57h+var_50]
0x1801af17e  test    rcx, rcx
0x1801af181  jz      short loc_1801AF193
0x1801af183  mov     rax, [rcx]
0x1801af186  mov     rax, [rax+10h]
0x1801af18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af18f  mov     [rbp+57h+var_50], r14
0x1801af193  mov     rcx, qword ptr [rbp+57h+var_58]
0x1801af197  test    rcx, rcx
0x1801af19a  jz      short loc_1801AF1A8
0x1801af19c  mov     rax, [rcx]
0x1801af19f  mov     rax, [rax+10h]
0x1801af1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af1a8  mov     edx, [rbp+57h+var_68]
0x1801af1ab  inc     edx
0x1801af1ad  mov     [rbp+57h+var_68], edx
0x1801af1b0  cmp     edx, [rbp+57h+var_20]
0x1801af1b3  jl      loc_1801AF02B
0x1801af1b9  mov     rcx, [rbp+57h+var_60]
0x1801af1bd  test    rcx, rcx
0x1801af1c0  jz      short loc_1801AF1D2
0x1801af1c2  mov     rax, [rcx]
0x1801af1c5  mov     rax, [rax+10h]
0x1801af1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af1ce  mov     [rbp+57h+var_60], r14
0x1801af1d2  mov     rcx, [rbp+57h+var_28]
0x1801af1d6  test    rcx, rcx
0x1801af1d9  jz      short loc_1801AF1E7
0x1801af1db  mov     rax, [rcx]
0x1801af1de  mov     rax, [rax+10h]
0x1801af1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af1e7  xor     eax, eax
0x1801af1e9  mov     rcx, [rbp+57h+var_18]
0x1801af1ed  xor     rcx, rsp; StackCookie
0x1801af1f0  call    __security_check_cookie
0x1801af1f5  lea     r11, [rsp+0A0h+var_10]
0x1801af1fd  mov     rbx, [r11+28h]
0x1801af201  mov     rsi, [r11+30h]
0x1801af205  mov     rsp, r11
0x1801af208  pop     r14
0x1801af20a  pop     rdi
0x1801af20b  pop     rbp
0x1801af20c  retn
0x1801af20e  mov     rcx, [rbp+57h+var_50]
0x1801af212  lea     rdx, [rbp+57h+var_2C]
0x1801af216  mov     rax, [rcx]
0x1801af219  mov     rax, [rax+50h]
0x1801af21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af222  mov     edi, eax
0x1801af224  test    eax, eax
0x1801af226  jns     short loc_1801AF27B
0x1801af228  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
