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
  __int64 v13; // rdx
  void (*v14)(void); // rax
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  BSTR v19; // rax
  OLECHAR *v20; // rbx
  __int64 v21; // rdx
  void (*v22)(void); // rax
  int v23; // eax
  unsigned int v24; // edi
  __int64 v25; // rdx
  int updated; // eax
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rdx
  int started; // eax
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rdx
  OLECHAR *v42; // rbx
  OLECHAR *v43; // rdi
  int v44; // eax
  int v45; // r14d
  __int64 v46; // rdx
  __int64 v47; // rdx
  int v48; // eax
  __int64 v49; // rdx
  int v50; // eax
  __int64 v51; // rdx
  char v52; // si
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  int *ppv; // [rsp+20h] [rbp-B9h]
  int *ppva; // [rsp+20h] [rbp-B9h]
  int v64[2]; // [rsp+30h] [rbp-A9h] BYREF
  BSTR v65; // [rsp+38h] [rbp-A1h] BYREF
  BSTR v66; // [rsp+40h] [rbp-99h] BYREF
  BSTR v67; // [rsp+48h] [rbp-91h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-89h] BYREF
  int v69; // [rsp+58h] [rbp-81h] BYREF
  __int64 v70; // [rsp+60h] [rbp-79h] BYREF
  __int64 v71; // [rsp+68h] [rbp-71h] BYREF
  __int64 v72; // [rsp+70h] [rbp-69h] BYREF
  __int64 v73; // [rsp+78h] [rbp-61h] BYREF
  __int64 v74; // [rsp+80h] [rbp-59h] BYREF
  __int64 v75; // [rsp+88h] [rbp-51h] BYREF
  int v76[2]; // [rsp+90h] [rbp-49h] BYREF
  LPVOID v77; // [rsp+98h] [rbp-41h] BYREF
  int v78; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-21h] BYREF
  int v82; // [rsp+C0h] [rbp-19h] BYREF
  int v83; // [rsp+C4h] [rbp-15h] BYREF
  BSTR v84; // [rsp+C8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  psz = a5;
  v77 = 0;
  v71 = 0;
  v70 = 0;
  v75 = 0;
  v74 = 0;
  v73 = 0;
  v72 = 0;
  v82 = 0;
  if ( !a5 )
  {
    v12 = -2147467261;
    v69 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Invalid pszDownloadedSandbox");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v13) = 1;
      ppv = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      (int)ppv);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( !v77 )
      return v12;
    v14 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
LABEL_18:
    v14();
    return v12;
  }
  v16 = CoCreateInstance(
          &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
          0,
          1u,
          &GUID_816858a4_260d_4260_933a_2585f1abc76b,
          &v77);
  v12 = v16;
  if ( v16 < 0 )
  {
    v69 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to create UpdateSession object.");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v17) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        3,
        ": {}");
    }
    v18 = 293;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v12,
      (int)ppva);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( !v77 )
      return v12;
    v14 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
    goto LABEL_18;
  }
  v19 = SysAllocString(L"UpdateAgent");
  v20 = v19;
  if ( !v19 )
  {
    v21 = 299;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( !v77 )
      return 2147942414LL;
    v22 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
LABEL_124:
    v22();
    return 2147942414LL;
  }
  v23 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v77 + 64LL))(v77, v19);
  v24 = v23;
  if ( v23 < 0 )
  {
    v69 = v23;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v25) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v25,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v24,
      (int)ppva);
    SysFreeString(v20);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( v77 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    return v24;
  }
  SysFreeString(v20);
  updated = WindowsUpdateSearch(0, (_DWORD)v77, 0, 0, (__int64)&v71);
  v12 = updated;
  if ( updated < 0 )
  {
    v69 = updated;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to do Windows update search");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v27) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v27,
        3,
        ": {}");
    }
    v18 = 312;
    goto LABEL_24;
  }
  if ( a11 )
  {
    v28 = SetAlternateUpdateId(v71, a11, a12);
    v12 = v28;
    if ( v28 < 0 )
    {
      v69 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to set alternate Update ID");
        *(_QWORD *)v76 = &v69;
        LOBYTE(v29) = 1;
        ppva = v76;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v29,
          3,
          ": {}");
      }
      v18 = 322;
      goto LABEL_24;
    }
  }
  v30 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v77 + 104LL))(v77, &v70);
  v12 = v30;
  if ( v30 < 0 )
  {
    v69 = v30;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create downloader");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v31) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v31,
        3,
        ": {}");
    }
    v18 = 328;
    goto LABEL_24;
  }
  v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 80LL))(v70, 0xFFFFFFFFLL);
  v12 = v32;
  if ( v32 < 0 )
  {
    v69 = v32;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to set IsForced on IUpdateDownloader");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v33) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v33,
        3,
        ": {}");
    }
    v18 = 342;
    goto LABEL_24;
  }
  if ( a10 )
  {
    v34 = SetDownloadProperties(a10, v70);
    v12 = v34;
    if ( v34 < 0 )
    {
      v69 = v34;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD:Failed to set download properties");
        *(_QWORD *)v76 = &v69;
        LOBYTE(v35) = 1;
        ppva = v76;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v35,
          3,
          ": {}");
      }
      v18 = 361;
      goto LABEL_24;
    }
  }
  else
  {
    v36 = SetDefaultDownloadProperties(v70);
    v12 = v36;
    if ( v36 < 0 )
    {
      v69 = v36;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD:Failed to set default download properties");
        *(_QWORD *)v76 = &v69;
        LOBYTE(v37) = 1;
        ppva = v76;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v37,
          3,
          ": {}");
      }
      v18 = 365;
      goto LABEL_24;
    }
  }
  LODWORD(ppva) = 0;
  started = StartDownloadAndReportProgress(v70, L"{\"ModuleID\" : \"CurrentVersionScan\"}", v71, 0);
  v12 = started;
  if ( started < 0 )
  {
    v69 = started;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to download actual content");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v39) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v39,
        3,
        ": {}");
    }
    v18 = 368;
    goto LABEL_24;
  }
  if ( v73 )
    goto LABEL_221;
  v40 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v71)(
          v71,
          &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
          &v73);
  v12 = v40;
  if ( v40 < 0 )
  {
    v69 = v40;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD:Failed to query IUpdate10");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v41) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v41,
        3,
        ": {}");
    }
    v18 = 373;
    goto LABEL_24;
  }
  v84 = SysAllocString(psz);
  v42 = v84;
  if ( !v84 )
  {
    v21 = 376;
    goto LABEL_40;
  }
  v65 = SysAllocString(L"{\"ModuleID\" : \"CurrentVersionScan\"}");
  v43 = v65;
  if ( !v65 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      0);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    SysFreeString(v42);
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( !v77 )
      return 2147942414LL;
    v22 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
    goto LABEL_124;
  }
  if ( v72 )
  {
LABEL_221:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026FA1BLL);
  }
  v44 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 72LL))(v71, &v72);
  v45 = v44;
  if ( v44 < 0 )
  {
    v69 = v44;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD:Failed to get bundled updates");
      *(_QWORD *)v76 = &v69;
      LOBYTE(v46) = 1;
      ppva = v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v46,
        3,
        ": {}");
    }
    v47 = 381;
    goto LABEL_131;
  }
  v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v72 + 80LL))(v72, &v82);
  v45 = v48;
  if ( v48 < 0 )
  {
    v83 = v48;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to get bundled updates count");
      v65 = (BSTR)&v83;
      LOBYTE(v49) = 1;
      ppva = (int *)&v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v49,
        3,
        ": {}");
    }
    v47 = 383;
LABEL_131:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v45,
      (int)ppva);
LABEL_132:
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    SysFreeString(v43);
    SysFreeString(v42);
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( v77 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    return (unsigned int)v45;
  }
  if ( !v82 )
  {
    v50 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v73 + 64LL))(v73, v42, v65, 0);
    v45 = v50;
    if ( v50 >= 0 )
      goto LABEL_178;
    v83 = v50;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: Failed to move WU content to {}");
      v65 = (BSTR)&v83;
      LOBYTE(v51) = 1;
      ppva = (int *)&v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v51,
        3,
        ": {}");
    }
    v47 = 391;
    goto LABEL_131;
  }
  v69 = 0;
  if ( v82 <= 0 )
  {
LABEL_203:
    LODWORD(v84) = -2145099760;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: No WU content available to move to {}");
      *(_QWORD *)v64 = &v84;
      LOBYTE(v61) = 1;
      ppva = v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v61,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80246010LL,
      (int)ppva);
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    SysFreeString(v43);
    SysFreeString(v42);
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = 0;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( v77 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    return 2149867536LL;
  }
  v52 = 0;
  v53 = 0;
  do
  {
    v80 = 0;
    v79 = 0;
    v45 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v72 + 56LL))(v72, v53, &v80);
    if ( v45 < 0 )
    {
      v78 = v45;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get child udpate at {}",
          &v69);
        *(_QWORD *)v64 = &v78;
        LOBYTE(v60) = 1;
        ppva = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v60,
          3,
          ": {}");
      }
      v59 = 401;
      goto LABEL_198;
    }
    if ( v79 )
      goto LABEL_220;
    v45 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v80)(
            v80,
            &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
            &v79);
    if ( v45 < 0 )
    {
      v78 = v45;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get IUpdate10 ptr for child {}",
          &v69);
        *(_QWORD *)v64 = &v78;
        LOBYTE(v58) = 1;
        ppva = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v58,
          3,
          ": {}");
      }
      v59 = 403;
LABEL_198:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v59,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v45,
        (int)ppva);
LABEL_199:
      if ( v79 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        v79 = 0;
      }
      if ( v80 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        v80 = 0;
      }
      goto LABEL_132;
    }
    *(_QWORD *)v76 = 0;
    bstrString = 0;
    v45 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v80 + 152LL))(v80, v76);
    if ( v45 < 0 )
    {
      v78 = v45;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update identity");
        *(_QWORD *)v64 = &v78;
        LOBYTE(v57) = 1;
        ppva = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v57,
          3,
          ": {}");
      }
      v55 = 408;
      goto LABEL_182;
    }
    if ( bstrString )
    {
LABEL_220:
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)v76 + 64LL))(*(_QWORD *)v76, &bstrString);
    if ( v45 < 0 )
    {
      v78 = v45;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update ID");
        *(_QWORD *)v64 = &v78;
        LOBYTE(v56) = 1;
        ppva = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v56,
          3,
          ": {}");
      }
      v55 = 410;
LABEL_182:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v45,
        (int)ppva);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( *(_QWORD *)v76 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v76 + 16LL))(*(_QWORD *)v76);
        *(_QWORD *)v76 = 0;
      }
      goto LABEL_199;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v79 + 64LL))(v79, v42, v65, 0);
    if ( v45 < 0 )
    {
      if ( v45 != -2145099760 )
      {
        v78 = v45;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v66 = bstrString;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "DWLD: Failed to move WU content to {} for update with ID {}",
            &psz,
            &v66);
          *(_QWORD *)v64 = &v78;
          LOBYTE(v54) = 1;
          ppva = v64;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v54,
            3,
            ": {}");
        }
        v55 = 428;
        goto LABEL_182;
      }
      v66 = bstrString;
      LogAdapter::TraceInfo<wchar_t const *>("DWLD: No sandbox found for update with ID: {}, continuing", &v66);
    }
    else
    {
      v67 = bstrString;
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("DWLD: Moved WU content to {} for update with ID {}", &psz, &v67);
      v52 = 1;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( *(_QWORD *)v76 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v76 + 16LL))(*(_QWORD *)v76);
      *(_QWORD *)v76 = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      v79 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    v53 = (unsigned int)(v69 + 1);
    v69 = v53;
  }
  while ( (int)v53 < v82 );
  if ( !v52 )
    goto LABEL_203;
LABEL_178:
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v72);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v73);
  Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v65);
  Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v84);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v74);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v75);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v70);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v71);
  Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v77);
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
