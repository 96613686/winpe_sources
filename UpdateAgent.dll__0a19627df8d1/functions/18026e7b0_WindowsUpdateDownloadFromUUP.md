# WindowsUpdateDownloadFromUUP

- ea: `0x18026e7b0`
- end: `0x18026fa1c`
- name: `WindowsUpdateDownloadFromUUP`
- size: `4716`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800335c4`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000a7fc`
- `0x18000b508`
- `0x18000b7a4`
- `0x18000c4c4`
- `0x180012770`
- `0x1800127a4`
- `0x180022d20`
- `0x1800271e8`
- `0x1800692fc`
- `0x18008b38c`
- `0x18026b318`
- `0x18026ba20`
- `0x18026bb70`
- `0x18026c8c8`
- `0x18026d9b0`
- `0x18026e7b0`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18026eaa7`
- `OLEAUT32!__imp_SysAllocString` at `0x18026f0aa`
- `OLEAUT32!__imp_SysAllocString` at `0x18026f0d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18026eaa7`
- `OLEAUT32!__imp_SysAllocString` at `0x18026f0aa`
- `OLEAUT32!__imp_SysAllocString` at `0x18026f0d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18026ec11`
- `OLEAUT32!__imp_SysFreeString` at `0x18026ecd2`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f140`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f295`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f2a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f56b`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f6ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f96a`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f979`
- `OLEAUT32!__imp_SysFreeString` at `0x18026ec11`
- `OLEAUT32!__imp_SysFreeString` at `0x18026ecd2`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f140`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f295`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f2a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f56b`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f6ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f96a`
- `OLEAUT32!__imp_SysFreeString` at `0x18026f979`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026e973`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026e973`

## string_xrefs

- `0x18026eaa0`: `UpdateAgent`
- `0x18026e876`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e9e2`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026eac8`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026ebfa`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026f0f4`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026f251`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026f6b2`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026f878`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026f921`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026ed1d`: `DWLD:Failed to do Windows update search`
- `0x18026ee0f`: `Failed to create downloader`
- `0x18026ed91`: `DWLD: Failed to set alternate Update ID`
- `0x18026e99e`: `Failed to create UpdateSession object.`
- `0x18026f060`: `DWLD:Failed to query IUpdate10`
- `0x18026ee82`: `Failed to set IsForced on IUpdateDownloader`
- `0x18026f76c`: `Failed to get update identity`
- `0x18026f7d4`: `DWLD: Failed to get IUpdate10 ptr for child {}`
- `0x18026f52e`: `DWLD: Moved WU content to {} for update with ID {}`
- `0x18026f711`: `Failed to get update ID`
- `0x18026f360`: `DWLD:Failed to get bundled updates count`
- `0x18026f20d`: `DWLD:Failed to get bundled updates`
- `0x18026f3f6`: `DWLD: Failed to move WU content to {}`
- `0x18026f64f`: `DWLD: Failed to move WU content to {} for update with ID {}`
- `0x18026f551`: `DWLD: No sandbox found for update with ID: {}, continuing`
- `0x18026f8e4`: `DWLD: No WU content available to move to {}`

## pseudocode

```c
__int64 __fastcall WindowsUpdateDownloadFromUUP(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        OLECHAR *a5,
        int a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  unsigned int v12; // ebx
  void (*v13)(void); // rax
  HRESULT v15; // eax
  __int64 v16; // rdx
  BSTR v17; // rax
  OLECHAR *v18; // rbx
  __int64 v19; // rdx
  void (*v20)(void); // rax
  int v21; // eax
  unsigned int v22; // edi
  int updated; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int started; // eax
  int v30; // eax
  OLECHAR *v31; // rbx
  OLECHAR *v32; // rdi
  int v33; // eax
  int v34; // r14d
  __int64 v35; // rdx
  int v36; // eax
  int v37; // eax
  char v38; // si
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  int ppv; // [rsp+20h] [rbp-B9h]
  int ppva; // [rsp+20h] [rbp-B9h]
  int v44[2]; // [rsp+30h] [rbp-A9h] BYREF
  BSTR v45; // [rsp+38h] [rbp-A1h] BYREF
  BSTR v46; // [rsp+40h] [rbp-99h] BYREF
  BSTR v47; // [rsp+48h] [rbp-91h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-89h] BYREF
  int v49; // [rsp+58h] [rbp-81h] BYREF
  __int64 v50; // [rsp+60h] [rbp-79h] BYREF
  __int64 v51; // [rsp+68h] [rbp-71h] BYREF
  __int64 v52; // [rsp+70h] [rbp-69h] BYREF
  __int64 v53; // [rsp+78h] [rbp-61h] BYREF
  __int64 v54; // [rsp+80h] [rbp-59h] BYREF
  __int64 v55; // [rsp+88h] [rbp-51h] BYREF
  int v56[2]; // [rsp+90h] [rbp-49h] BYREF
  LPVOID v57; // [rsp+98h] [rbp-41h] BYREF
  int v58; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-21h] BYREF
  int v62; // [rsp+C0h] [rbp-19h] BYREF
  int v63; // [rsp+C4h] [rbp-15h] BYREF
  BSTR v64; // [rsp+C8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  psz = a5;
  v57 = 0;
  v51 = 0;
  v50 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  v62 = 0;
  if ( !a5 )
  {
    v12 = -2147467261;
    v49 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid pszDownloadedSandbox");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( !v57 )
      return v12;
    v13 = *(void (**)(void))(*(_QWORD *)v57 + 16LL);
LABEL_18:
    v13();
    return v12;
  }
  v15 = CoCreateInstance(
          &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
          0,
          1u,
          &GUID_816858a4_260d_4260_933a_2585f1abc76b,
          &v57);
  v12 = v15;
  if ( v15 < 0 )
  {
    v49 = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create UpdateSession object.");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 293;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v12,
      ppva);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( !v57 )
      return v12;
    v13 = *(void (**)(void))(*(_QWORD *)v57 + 16LL);
    goto LABEL_18;
  }
  v17 = SysAllocString(L"UpdateAgent");
  v18 = v17;
  if ( !v17 )
  {
    v19 = 299;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      ppva);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( !v57 )
      return 2147942414LL;
    v20 = *(void (**)(void))(*(_QWORD *)v57 + 16LL);
LABEL_124:
    v20();
    return 2147942414LL;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v57 + 64LL))(v57, v17);
  v22 = v21;
  if ( v21 < 0 )
  {
    v49 = v21;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set client ID");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v22,
      ppva);
    SysFreeString(v18);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v57 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 16LL))(v57);
    return v22;
  }
  SysFreeString(v18);
  updated = WindowsUpdateSearch(0, (_DWORD)v57, 0, 0, (__int64)&v51);
  v12 = updated;
  if ( updated < 0 )
  {
    v49 = updated;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to do Windows update search");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 312;
    goto LABEL_24;
  }
  if ( a11 )
  {
    v24 = SetAlternateUpdateId(v51, a11, a12);
    v12 = v24;
    if ( v24 < 0 )
    {
      v49 = v24;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to set alternate Update ID");
        *(_QWORD *)v56 = &v49;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v56);
      }
      v16 = 322;
      goto LABEL_24;
    }
  }
  v25 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v57 + 104LL))(v57, &v50);
  v12 = v25;
  if ( v25 < 0 )
  {
    v49 = v25;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create downloader");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 328;
    goto LABEL_24;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 80LL))(v50, 0xFFFFFFFFLL);
  v12 = v26;
  if ( v26 < 0 )
  {
    v49 = v26;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set IsForced on IUpdateDownloader");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 342;
    goto LABEL_24;
  }
  if ( a10 )
  {
    v27 = SetDownloadProperties(a10, v50);
    v12 = v27;
    if ( v27 < 0 )
    {
      v49 = v27;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to set download properties");
        *(_QWORD *)v56 = &v49;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v56);
      }
      v16 = 361;
      goto LABEL_24;
    }
  }
  else
  {
    v28 = SetDefaultDownloadProperties(v50);
    v12 = v28;
    if ( v28 < 0 )
    {
      v49 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to set default download properties");
        *(_QWORD *)v56 = &v49;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v56);
      }
      v16 = 365;
      goto LABEL_24;
    }
  }
  ppva = 0;
  started = StartDownloadAndReportProgress(v50, L"{\"ModuleID\" : \"CurrentVersionScan\"}", v51, 0);
  v12 = started;
  if ( started < 0 )
  {
    v49 = started;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to download actual content");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 368;
    goto LABEL_24;
  }
  if ( v53 )
    goto LABEL_221;
  v30 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v51)(
          v51,
          &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
          &v53);
  v12 = v30;
  if ( v30 < 0 )
  {
    v49 = v30;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to query IUpdate10");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v16 = 373;
    goto LABEL_24;
  }
  v64 = SysAllocString(psz);
  v31 = v64;
  if ( !v64 )
  {
    v19 = 376;
    goto LABEL_40;
  }
  v45 = SysAllocString(L"{\"ModuleID\" : \"CurrentVersionScan\"}");
  v32 = v45;
  if ( !v45 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      0);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    SysFreeString(v31);
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( !v57 )
      return 2147942414LL;
    v20 = *(void (**)(void))(*(_QWORD *)v57 + 16LL);
    goto LABEL_124;
  }
  if ( v52 )
  {
LABEL_221:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026FA1BLL);
  }
  v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 72LL))(v51, &v52);
  v34 = v33;
  if ( v33 < 0 )
  {
    v49 = v33;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to get bundled updates");
      *(_QWORD *)v56 = &v49;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v56);
    }
    v35 = 381;
    goto LABEL_131;
  }
  v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 80LL))(v52, &v62);
  v34 = v36;
  if ( v36 < 0 )
  {
    v63 = v36;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to get bundled updates count");
      v45 = (BSTR)&v63;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v45);
    }
    v35 = 383;
LABEL_131:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v34,
      ppva);
LABEL_132:
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    SysFreeString(v32);
    SysFreeString(v31);
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v57 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 16LL))(v57);
    return (unsigned int)v34;
  }
  if ( !v62 )
  {
    v37 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v53 + 64LL))(v53, v31, v45, 0);
    v34 = v37;
    if ( v37 >= 0 )
      goto LABEL_178;
    v63 = v37;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to move WU content to {}",
        (__int64)&psz);
      v45 = (BSTR)&v63;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v45);
    }
    v35 = 391;
    goto LABEL_131;
  }
  v49 = 0;
  if ( v62 <= 0 )
  {
LABEL_203:
    LODWORD(v64) = -2145099760;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: No WU content available to move to {}",
        (__int64)&psz);
      *(_QWORD *)v44 = &v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v44);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80246010LL,
      ppva);
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    SysFreeString(v32);
    SysFreeString(v31);
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v57 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 16LL))(v57);
    return 2149867536LL;
  }
  v38 = 0;
  v39 = 0;
  do
  {
    v60 = 0;
    v59 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 56LL))(v52, v39, &v60);
    if ( v34 < 0 )
    {
      v58 = v34;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get child udpate at {}");
        *(_QWORD *)v44 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v44);
      }
      v41 = 401;
      goto LABEL_198;
    }
    if ( v59 )
      goto LABEL_220;
    v34 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v60)(
            v60,
            &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
            &v59);
    if ( v34 < 0 )
    {
      v58 = v34;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get IUpdate10 ptr for child {}");
        *(_QWORD *)v44 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v44);
      }
      v41 = 403;
LABEL_198:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v34,
        ppva);
LABEL_199:
      if ( v59 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        v59 = 0;
      }
      if ( v60 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        v60 = 0;
      }
      goto LABEL_132;
    }
    *(_QWORD *)v56 = 0;
    bstrString = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 152LL))(v60, v56);
    if ( v34 < 0 )
    {
      v58 = v34;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update identity");
        *(_QWORD *)v44 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v44);
      }
      v40 = 408;
      goto LABEL_182;
    }
    if ( bstrString )
    {
LABEL_220:
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    v34 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)v56 + 64LL))(*(_QWORD *)v56, &bstrString);
    if ( v34 < 0 )
    {
      v58 = v34;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update ID");
        *(_QWORD *)v44 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v44);
      }
      v40 = 410;
LABEL_182:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v34,
        ppva);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( *(_QWORD *)v56 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
        *(_QWORD *)v56 = 0;
      }
      goto LABEL_199;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v59 + 64LL))(v59, v31, v45, 0);
    if ( v34 < 0 )
    {
      if ( v34 != -2145099760 )
      {
        v58 = v34;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v46 = bstrString;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "DWLD: Failed to move WU content to {} for update with ID {}",
            &psz,
            &v46);
          *(_QWORD *)v44 = &v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v44);
        }
        v40 = 428;
        goto LABEL_182;
      }
      v46 = bstrString;
      LogAdapter::TraceInfo<wchar_t const *>("DWLD: No sandbox found for update with ID: {}, continuing", &v46);
    }
    else
    {
      v47 = bstrString;
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("DWLD: Moved WU content to {} for update with ID {}", &psz, &v47);
      v38 = 1;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( *(_QWORD *)v56 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
      *(_QWORD *)v56 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    v39 = (unsigned int)(v49 + 1);
    v49 = v39;
  }
  while ( (int)v39 < v62 );
  if ( !v38 )
    goto LABEL_203;
LABEL_178:
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v52);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v53);
  Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v45);
  Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v64);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v54);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v55);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v50);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v51);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v57);
  return 0;
}

```

## disassembly

```asm
0x18026e7b0  push    rbp
0x18026e7b2  push    rbx
0x18026e7b3  push    rsi
0x18026e7b4  push    rdi
0x18026e7b5  push    r12
0x18026e7b7  push    r14
0x18026e7b9  push    r15
0x18026e7bb  lea     rbp, [rsp-7]
0x18026e7c0  sub     rsp, 0E0h
0x18026e7c7  mov     rax, cs:__security_cookie
0x18026e7ce  xor     rax, rsp
0x18026e7d1  mov     [rbp+37h+var_40], rax
0x18026e7d5  mov     rax, [rbp+37h+arg_20]
0x18026e7d9  xor     r12d, r12d
0x18026e7dc  mov     r14, [rbp+37h+arg_48]
0x18026e7e3  mov     rsi, [rbp+37h+arg_50]
0x18026e7ea  mov     r15, [rbp+37h+arg_58]
0x18026e7f1  mov     [rsp+110h+psz], rax
0x18026e7f6  mov     [rbp+37h+var_78], r12
0x18026e7fa  mov     [rbp+37h+var_A8], r12
0x18026e7fe  mov     [rbp+37h+var_B0], r12
0x18026e802  mov     [rbp+37h+var_88], r12
0x18026e806  mov     [rbp+37h+var_90], r12
0x18026e80a  mov     [rbp+37h+var_98], r12
0x18026e80e  mov     [rbp+37h+var_A0], r12
0x18026e812  mov     [rbp+37h+var_50], r12d
0x18026e816  test    rax, rax
0x18026e819  jnz     loc_18026E956
0x18026e81f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026e826  mov     ebx, 80004003h
0x18026e82b  mov     [rsp+110h+var_B8], ebx
0x18026e82f  test    rcx, rcx
0x18026e832  jz      short loc_18026E872
0x18026e834  lea     esi, [rax+3]
0x18026e837  xor     edx, edx
0x18026e839  mov     r8d, esi
0x18026e83c  lea     r9, aInvalidPszdown; "Invalid pszDownloadedSandbox"
0x18026e843  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026e848  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026e84f  lea     rax, [rsp+110h+var_B8]
0x18026e854  mov     qword ptr [rbp+37h+var_80], rax
0x18026e858  lea     r9, asc_1802C6678; ": {}"
0x18026e85f  lea     rax, [rbp+37h+var_80]
0x18026e863  mov     r8d, esi
0x18026e866  mov     dl, 1
0x18026e868  mov     [rsp+110h+ppv], rax; int
0x18026e86d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026e872  mov     rcx, [rbp+3Fh]; this
0x18026e876  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026e87d  mov     r9d, ebx; char *
0x18026e880  mov     edx, 111h; void *
0x18026e885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e88a  mov     rcx, [rbp+37h+var_A0]
0x18026e88e  test    rcx, rcx
0x18026e891  jz      short loc_18026E8A3
0x18026e893  mov     rax, [rcx]
0x18026e896  mov     rax, [rax+10h]
0x18026e89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e89f  mov     [rbp+37h+var_A0], r12
0x18026e8a3  mov     rcx, [rbp+37h+var_98]
0x18026e8a7  test    rcx, rcx
0x18026e8aa  jz      short loc_18026E8BC
0x18026e8ac  mov     rax, [rcx]
0x18026e8af  mov     rax, [rax+10h]
0x18026e8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e8b8  mov     [rbp+37h+var_98], r12
0x18026e8bc  mov     rcx, [rbp+37h+var_90]
0x18026e8c0  test    rcx, rcx
0x18026e8c3  jz      short loc_18026E8D5
0x18026e8c5  mov     rax, [rcx]
0x18026e8c8  mov     rax, [rax+10h]
0x18026e8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e8d1  mov     [rbp+37h+var_90], r12
0x18026e8d5  mov     rcx, [rbp+37h+var_88]
0x18026e8d9  test    rcx, rcx
0x18026e8dc  jz      short loc_18026E8EE
0x18026e8de  mov     rax, [rcx]
0x18026e8e1  mov     rax, [rax+10h]
0x18026e8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e8ea  mov     [rbp+37h+var_88], r12
0x18026e8ee  mov     rcx, [rbp+37h+var_B0]
0x18026e8f2  test    rcx, rcx
0x18026e8f5  jz      short loc_18026E907
0x18026e8f7  mov     rax, [rcx]
0x18026e8fa  mov     rax, [rax+10h]
0x18026e8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e903  mov     [rbp+37h+var_B0], r12
0x18026e907  mov     rcx, [rbp+37h+var_A8]
0x18026e90b  test    rcx, rcx
0x18026e90e  jz      short loc_18026E920
0x18026e910  mov     rax, [rcx]
0x18026e913  mov     rax, [rax+10h]
0x18026e917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e91c  mov     [rbp+37h+var_A8], r12
0x18026e920  mov     rcx, [rbp+37h+var_78]
0x18026e924  test    rcx, rcx
0x18026e927  jz      short loc_18026E935
0x18026e929  mov     rdx, [rcx]
0x18026e92c  mov     rax, [rdx+10h]
0x18026e930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026e935  mov     eax, ebx
0x18026e937  mov     rcx, [rbp+37h+var_40]
0x18026e93b  xor     rcx, rsp; StackCookie
0x18026e93e  call    __security_check_cookie
0x18026e943  add     rsp, 0E0h
0x18026e94a  pop     r15
0x18026e94c  pop     r14
0x18026e94e  pop     r12
0x18026e950  pop     rdi
0x18026e951  pop     rsi
0x18026e952  pop     rbx
0x18026e953  pop     rbp
0x18026e954  retn
0x18026e956  xor     edx, edx; pUnkOuter
0x18026e958  lea     rax, [rbp+37h+var_78]
0x18026e95c  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x18026e963  mov     [rsp+110h+ppv], rax; int
0x18026e968  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x18026e96f  lea     r8d, [rdx+1]; dwClsContext
0x18026e973  call    cs:__imp_CoCreateInstance
0x18026e97a  nop     dword ptr [rax+rax+00h]
0x18026e97f  mov     ebx, eax
0x18026e981  test    eax, eax
0x18026e983  jns     loc_18026EAA0
0x18026e989  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026e990  mov     [rsp+110h+var_B8], eax
0x18026e994  test    rcx, rcx
0x18026e997  jz      short loc_18026E9D9
0x18026e999  mov     esi, 3
0x18026e99e  lea     r9, aFailedToCreate_43; "Failed to create UpdateSession object."
0x18026e9a5  mov     r8d, esi
0x18026e9a8  xor     edx, edx
0x18026e9aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026e9af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026e9b6  lea     rax, [rsp+110h+var_B8]
0x18026e9bb  mov     qword ptr [rbp+37h+var_80], rax
0x18026e9bf  lea     r9, asc_1802C6678; ": {}"
0x18026e9c6  lea     rax, [rbp+37h+var_80]
0x18026e9ca  mov     r8d, esi
0x18026e9cd  mov     dl, 1
0x18026e9cf  mov     [rsp+110h+ppv], rax; int
0x18026e9d4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026e9d9  mov     edx, 125h; void *
0x18026e9de  mov     rcx, [rbp+3Fh]; this
0x18026e9e2  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026e9e9  mov     r9d, ebx; char *
0x18026e9ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e9f1  mov     rcx, [rbp+37h+var_A0]
0x18026e9f5  test    rcx, rcx
0x18026e9f8  jz      short loc_18026EA0A
0x18026e9fa  mov     rax, [rcx]
0x18026e9fd  mov     rax, [rax+10h]
0x18026ea01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea06  mov     [rbp+37h+var_A0], r12
0x18026ea0a  mov     rcx, [rbp+37h+var_98]
0x18026ea0e  test    rcx, rcx
0x18026ea11  jz      short loc_18026EA23
0x18026ea13  mov     rax, [rcx]
0x18026ea16  mov     rax, [rax+10h]
0x18026ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea1f  mov     [rbp+37h+var_98], r12
0x18026ea23  mov     rcx, [rbp+37h+var_90]
0x18026ea27  test    rcx, rcx
0x18026ea2a  jz      short loc_18026EA3C
0x18026ea2c  mov     rax, [rcx]
0x18026ea2f  mov     rax, [rax+10h]
0x18026ea33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea38  mov     [rbp+37h+var_90], r12
0x18026ea3c  mov     rcx, [rbp+37h+var_88]
0x18026ea40  test    rcx, rcx
0x18026ea43  jz      short loc_18026EA55
0x18026ea45  mov     rax, [rcx]
0x18026ea48  mov     rax, [rax+10h]
0x18026ea4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea51  mov     [rbp+37h+var_88], r12
0x18026ea55  mov     rcx, [rbp+37h+var_B0]
0x18026ea59  test    rcx, rcx
0x18026ea5c  jz      short loc_18026EA6E
0x18026ea5e  mov     rax, [rcx]
0x18026ea61  mov     rax, [rax+10h]
0x18026ea65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea6a  mov     [rbp+37h+var_B0], r12
0x18026ea6e  mov     rcx, [rbp+37h+var_A8]
0x18026ea72  test    rcx, rcx
0x18026ea75  jz      short loc_18026EA87
0x18026ea77  mov     rax, [rcx]
0x18026ea7a  mov     rax, [rax+10h]
0x18026ea7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ea83  mov     [rbp+37h+var_A8], r12
0x18026ea87  mov     rcx, [rbp+37h+var_78]
0x18026ea8b  test    rcx, rcx
0x18026ea8e  jz      loc_18026E935
0x18026ea94  mov     rax, [rcx]
0x18026ea97  mov     rax, [rax+10h]
0x18026ea9b  jmp     loc_18026E930
0x18026eaa0  lea     rcx, aUpdateagent; "UpdateAgent"
0x18026eaa7  call    cs:__imp_SysAllocString
0x18026eaae  nop     dword ptr [rax+rax+00h]
0x18026eab3  mov     rbx, rax
0x18026eab6  test    rax, rax
0x18026eab9  jnz     loc_18026EB89
0x18026eabf  mov     edx, 12Bh; void *
0x18026eac4  mov     rcx, [rbp+3Fh]; this
0x18026eac8  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026eacf  mov     r9d, 8007000Eh; char *
0x18026ead5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026eada  mov     rcx, [rbp+37h+var_A0]
0x18026eade  test    rcx, rcx
0x18026eae1  jz      short loc_18026EAF3
0x18026eae3  mov     rax, [rcx]
0x18026eae6  mov     rax, [rax+10h]
0x18026eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eaef  mov     [rbp+37h+var_A0], r12
0x18026eaf3  mov     rcx, [rbp+37h+var_98]
0x18026eaf7  test    rcx, rcx
0x18026eafa  jz      short loc_18026EB0C
0x18026eafc  mov     rax, [rcx]
0x18026eaff  mov     rax, [rax+10h]
0x18026eb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb08  mov     [rbp+37h+var_98], r12
0x18026eb0c  mov     rcx, [rbp+37h+var_90]
0x18026eb10  test    rcx, rcx
0x18026eb13  jz      short loc_18026EB25
0x18026eb15  mov     rax, [rcx]
0x18026eb18  mov     rax, [rax+10h]
0x18026eb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb21  mov     [rbp+37h+var_90], r12
0x18026eb25  mov     rcx, [rbp+37h+var_88]
0x18026eb29  test    rcx, rcx
0x18026eb2c  jz      short loc_18026EB3E
0x18026eb2e  mov     rax, [rcx]
0x18026eb31  mov     rax, [rax+10h]
0x18026eb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb3a  mov     [rbp+37h+var_88], r12
0x18026eb3e  mov     rcx, [rbp+37h+var_B0]
0x18026eb42  test    rcx, rcx
0x18026eb45  jz      short loc_18026EB57
0x18026eb47  mov     rax, [rcx]
0x18026eb4a  mov     rax, [rax+10h]
0x18026eb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb53  mov     [rbp+37h+var_B0], r12
0x18026eb57  mov     rcx, [rbp+37h+var_A8]
0x18026eb5b  test    rcx, rcx
0x18026eb5e  jz      short loc_18026EB70
0x18026eb60  mov     rax, [rcx]
0x18026eb63  mov     rax, [rax+10h]
0x18026eb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb6c  mov     [rbp+37h+var_A8], r12
0x18026eb70  mov     rcx, [rbp+37h+var_78]
0x18026eb74  test    rcx, rcx
0x18026eb77  jz      loc_18026F1C5
0x18026eb7d  mov     rax, [rcx]
0x18026eb80  mov     rax, [rax+10h]
0x18026eb84  jmp     loc_18026F1C0
0x18026eb89  mov     rcx, [rbp+37h+var_78]
0x18026eb8d  mov     rdx, rbx
0x18026eb90  mov     rax, [rcx]
0x18026eb93  mov     rax, [rax+40h]
0x18026eb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026eb9c  mov     edi, eax
0x18026eb9e  test    eax, eax
0x18026eba0  jns     loc_18026ECCF
0x18026eba6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ebad  mov     [rsp+110h+var_B8], eax
0x18026ebb1  test    rcx, rcx
0x18026ebb4  jz      short loc_18026EBF6
0x18026ebb6  mov     esi, 3
0x18026ebbb  lea     r9, aFailedToSetCli; "Failed to set client ID"
0x18026ebc2  mov     r8d, esi
0x18026ebc5  xor     edx, edx
0x18026ebc7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026ebcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ebd3  lea     rax, [rsp+110h+var_B8]
0x18026ebd8  mov     qword ptr [rbp+37h+var_80], rax
0x18026ebdc  lea     r9, asc_1802C6678; ": {}"
0x18026ebe3  lea     rax, [rbp+37h+var_80]
0x18026ebe7  mov     r8d, esi
0x18026ebea  mov     dl, 1
0x18026ebec  mov     [rsp+110h+ppv], rax; int
0x18026ebf1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026ebf6  mov     rcx, [rbp+3Fh]; this
0x18026ebfa  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026ec01  mov     r9d, edi; char *
0x18026ec04  mov     edx, 12Dh; void *
0x18026ec09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ec0e  mov     rcx, rbx; bstrString
0x18026ec11  call    cs:__imp_SysFreeString
0x18026ec18  nop     dword ptr [rax+rax+00h]
0x18026ec1d  mov     rcx, [rbp+37h+var_A0]
0x18026ec21  test    rcx, rcx
0x18026ec24  jz      short loc_18026EC36
0x18026ec26  mov     rax, [rcx]
0x18026ec29  mov     rax, [rax+10h]
0x18026ec2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ec32  mov     [rbp+37h+var_A0], r12
0x18026ec36  mov     rcx, [rbp+37h+var_98]
0x18026ec3a  test    rcx, rcx
0x18026ec3d  jz      short loc_18026EC4F
0x18026ec3f  mov     rax, [rcx]
0x18026ec42  mov     rax, [rax+10h]
  ... truncated ...
```
