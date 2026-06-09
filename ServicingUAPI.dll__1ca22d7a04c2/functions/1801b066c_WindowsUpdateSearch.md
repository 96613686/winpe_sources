# WindowsUpdateSearch

- ea: `0x1801b066c`
- end: `0x1801b1644`
- name: `WindowsUpdateSearch`
- size: `4056`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1801b164c`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001b9e4`
- `0x180065a7c`
- `0x1801ac2a8`
- `0x1801acf20`
- `0x1801adee8`
- `0x1801aed78`
- `0x1801b066c`
- `0x1801bd010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801b0b47`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b0b47`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b075c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b08dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b0bbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1031`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b117b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1248`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b155e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b15db`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b075c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b08dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b0bbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1031`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b117b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1248`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b155e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b15db`
- `OLEAUT32!__imp_VariantInit` at `0x1801b0b2f`
- `OLEAUT32!__imp_VariantInit` at `0x1801b0b2f`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0b88`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0cc1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0ce2`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0b88`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0cc1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0ce2`

## string_xrefs

- `0x1801b072b`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b08ac`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b0a4b`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b0b64`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b0c9e`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b0fe2`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1227`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1315`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1401`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1528`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b0a0d`: `Failed to query internal configuration`
- `0x1801b06ed`: `No update session specified`
- `0x1801b0869`: `Failed to create searcher`
- `0x1801b07f9`: `No update result specified`
- `0x1801b0cfc`: `Not able to show current windows update server configuration`
- `0x1801b14b5`: `DLWD: Expecting search returns 1 update, actual:{}`
- `0x1801b143e`: `Failed to get update count`

## pseudocode

```c
__int64 __fastcall WindowsUpdateSearch(char a1, __int64 a2, const OLECHAR *a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rdx
  void (*v11)(void); // rax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  void (*v24)(void); // rax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  int updated; // eax
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  int v41; // esi
  __int64 v42; // rdx
  __int64 v43; // rdx
  int v44; // edx
  int v45; // r8d
  int v46; // r9d
  OLECHAR *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  const char *v52; // r9
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rdx
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // rdx
  int v59; // eax
  void *v60; // [rsp+20h] [rbp-E0h]
  _BYTE v61[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v62[2]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v63; // [rsp+50h] [rbp-B0h] BYREF
  int *v64; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v65; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v70; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v71; // [rsp+A8h] [rbp-58h] BYREF
  int v72; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-48h] BYREF
  int v74; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v75; // [rsp+C8h] [rbp-38h] BYREF
  int v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v78[4]; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-10h] BYREF
  int v80; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v73 = 0;
  v68 = 0;
  v70 = 0;
  bstrString = 0;
  v67 = 0;
  v80 = 0;
  v78[0] = 0;
  v61[0] = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v66 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update session specified");
      v71 = (BSTR)&v66;
      LOBYTE(v9) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v9,
        3,
        ": {}");
    }
    v10 = 552;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v8 = -2147467261;
    v66 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update result specified");
      v71 = (BSTR)&v66;
      LOBYTE(v13) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    v10 = 553;
    goto LABEL_5;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v68);
  v8 = v14;
  if ( v14 < 0 )
  {
    v66 = v14;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create searcher");
      v71 = (BSTR)&v66;
      LOBYTE(v15) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        3,
        ": {}");
    }
    v16 = 555;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      (int)v60);
LABEL_27:
    if ( v67 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      v67 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
      v70 = 0;
    }
    if ( v68 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      v68 = 0;
    }
    if ( !v73 )
      return v8;
    v11 = *(void (**)(void))(*(_QWORD *)v73 + 16LL);
    goto LABEL_16;
  }
  if ( v70 )
    goto LABEL_195;
  v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v68)(
          v68,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v70);
  v8 = v17;
  if ( v17 < 0 )
  {
    v66 = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      v71 = (BSTR)&v66;
      LOBYTE(v18) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v18,
        3,
        ": {}");
    }
    v16 = 560;
    goto LABEL_26;
  }
  v75 = 0;
  *(_OWORD *)&pvarg.vt = 0;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v68)(
          v68,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v75);
  v8 = v19;
  if ( v19 < 0 )
  {
    v66 = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to query internal configuration");
      v71 = (BSTR)&v66;
      LOBYTE(v20) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v20,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      (int)v60);
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    v66 = v8;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to set default search properties");
      v71 = (BSTR)&v66;
      LOBYTE(v21) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {}");
    }
    v16 = 562;
    goto LABEL_26;
  }
  pvarg.pRecInfo = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v75 + 32LL))(v75, 262145, &pvarg);
  if ( v22 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v22, "Unable to set interactive flag for search");
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v75 = 0;
  }
  if ( a3 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    if ( !pvarg.llVal )
    {
      v23 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)0x8007000ELL,
        (int)v60);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v70 )
      {
        (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
        v70 = 0;
      }
      if ( v68 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
      }
      if ( !v73 )
        return v23;
      v24 = *(void (**)(void))(*(_QWORD *)v73 + 16LL);
      goto LABEL_66;
    }
    v25 = *v70;
    v65 = pvarg;
    v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v25 + 32))(v70, 1, &v65);
    v8 = v26;
    if ( v26 < 0 )
    {
      v66 = v26;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set correlation vector");
        v71 = (BSTR)&v66;
        LOBYTE(v27) = 1;
        v60 = &v71;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v27,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v8,
        (int)v60);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_27;
    }
    if ( pvarg.vt )
      VariantClear(&pvarg);
  }
  updated = ShowWindowsUpdateServerConfiguration(v61);
  if ( updated < 0 )
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      (unsigned int)updated,
      "Not able to show current windows update server configuration");
  DumpWindowsInsiderSettings();
  if ( bstrString )
    goto LABEL_195;
  v29 = CreateUUPSearchCriteria(a1, a4, &bstrString);
  v8 = v29;
  if ( v29 < 0 )
  {
    v66 = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get search criteria.");
      v71 = (BSTR)&v66;
      LOBYTE(v30) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v30,
        3,
        ": {}");
    }
    v16 = 592;
    goto LABEL_26;
  }
  if ( v67 )
  {
LABEL_195:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801B1643LL);
  }
  v31 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v68 + 152LL))(v68, bstrString, &v67);
  v8 = v31;
  if ( v31 < 0 )
  {
    v66 = v31;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DLWD:WU search failed");
      v71 = (BSTR)&v66;
      LOBYTE(v32) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v32,
        3,
        ": {}");
    }
    v16 = 594;
    goto LABEL_26;
  }
  v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 56LL))(v67, &v80);
  v8 = v33;
  if ( v33 < 0 )
  {
    v66 = v33;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get download hresult");
      v71 = (BSTR)&v66;
      LOBYTE(v35) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v35,
        3,
        ": {}");
    }
    v16 = 596;
    goto LABEL_26;
  }
  if ( v80 == 4 )
  {
    v8 = -2146498289;
    v74 = -2146498289;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Search failed with");
      v71 = (BSTR)&v74;
      LOBYTE(v36) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v36,
        3,
        ": {}");
    }
    v10 = 602;
    goto LABEL_5;
  }
  if ( v80 == 5 )
  {
    v8 = -2147467260;
    v74 = -2147467260;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: WU cancelled the search operation");
      v71 = (BSTR)&v74;
      LOBYTE(v37) = 1;
      v60 = &v71;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v37,
        3,
        ": {}");
    }
    v10 = 606;
    goto LABEL_5;
  }
  v8 = 0;
  if ( v80 != 3 )
  {
    if ( v80 == 2 )
    {
      v72 = 2;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_156;
      v52 = "DWLD: WU search succeeded with WU result code {}";
    }
    else
    {
      v72 = v80;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_156;
      v52 = "DWLD: WU search failed with WU result code {}";
    }
    LOBYTE(v34) = 1;
    LogAdapter::Logger::LogNumObjects<long>(*(_QWORD *)&LogAdapter::g_Logger, v34, 1, v52, &v72);
LABEL_156:
    if ( !v73 )
    {
      v53 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 72LL))(v67, &v73);
      v41 = v53;
      if ( v53 >= 0 )
      {
        v56 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v73 + 80LL))(v73, v78);
        v41 = v56;
        if ( v56 >= 0 )
        {
          if ( v78[0] != 1 )
          {
            if ( (v8 & 0x80000000) == 0 )
              v8 = v61[0] != 0 ? -2146498220 : -2146498224;
            v66 = v8;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<long>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "DLWD: Expecting search returns 1 update, actual:{}",
                v78);
              *(_QWORD *)v62 = &v66;
              LOBYTE(v58) = 1;
              v60 = v62;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v58,
                3,
                ": {}");
            }
            if ( (v8 & 0x80000000) == 0 )
              goto LABEL_6;
            v10 = 660;
LABEL_5:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v10,
              (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
              (const char *)v8,
              (int)v60);
LABEL_6:
            if ( v67 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              v67 = 0;
            }
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v70 )
            {
              (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
              v70 = 0;
            }
            if ( v68 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
              v68 = 0;
            }
            if ( !v73 )
              return v8;
            v11 = *(void (**)(void))(*(_QWORD *)v73 + 16LL);
LABEL_16:
            v11();
            return v8;
          }
          v59 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v73 + 56LL))(v73, 0, a5);
          v23 = v59;
          if ( v59 >= 0 )
          {
            if ( v67 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              v67 = 0;
            }
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v70 )
            {
              (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
              v70 = 0;
            }
            if ( v68 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
              v68 = 0;
            }
            if ( v73 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)(unsigned int)v59,
            (int)v60);
          if ( v67 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = 0;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v70 )
          {
            (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
            v70 = 0;
          }
          if ( v68 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
            v68 = 0;
          }
          if ( !v73 )
            return v23;
          v24 = *(void (**)(void))(*(_QWORD *)v73 + 16LL);
LABEL_66:
          v24();
          return v23;
        }
        v72 = v56;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update count");
          *(_QWORD *)v62 = &v72;
          LOBYTE(v57) = 1;
          v60 = v62;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v57,
            3,
            ": {}");
        }
        v55 = 653;
      }
      else
      {
        v72 = v53;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to get search collection.");
          *(_QWORD *)v62 = &v72;
          LOBYTE(v54) = 1;
          v60 = v62;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v54,
            3,
            ": {}");
        }
        v55 = 648;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v41,
        (int)v60);
      goto LABEL_108;
    }
    goto LABEL_195;
  }
  LogAdapter::TraceInfo<>("DWLD: WU search succeeded with errors");
  v74 = 0;
  v77 = 0;
  v38 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 80LL))(v67, &v77);
  if ( v38 >= 0 )
  {
    v39 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 72LL))(v77, &v74);
    v41 = v39;
    if ( v39 < 0 )
    {
      v66 = v39;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warnings count");
        v71 = (BSTR)&v66;
        LOBYTE(v42) = 1;
        v60 = &v71;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v42,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26C,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v41,
        (int)v60);
      goto LABEL_106;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v40) = 1;
      LogAdapter::Logger::LogNumObjects<long>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v40,
        1,
        "DWLD: WU search warnings: {}",
        &v74);
    }
  }
  else
  {
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v38, "DWLD: Unable to get WU warnings list");
  }
  v76 = 0;
  if ( v74 <= 0 )
  {
LABEL_135:
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    goto LABEL_156;
  }
  v43 = 0;
  while ( 1 )
  {
    v75 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v77 + 56LL))(v77, v43, &v75);
    if ( v41 < 0 )
    {
      v72 = v41;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning {}",
          &v76);
        *(_QWORD *)v62 = &v72;
        LOBYTE(v51) = 1;
        v60 = v62;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v51,
          3,
          ": {}");
      }
      v50 = 627;
      goto LABEL_147;
    }
    v66 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v75 + 64LL))(v75, &v66);
    if ( v41 < 0 )
    {
      v72 = v41;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning hr {}",
          &v76);
        *(_QWORD *)v62 = &v72;
        LOBYTE(v49) = 1;
        v60 = v62;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v49,
          3,
          ": {}");
      }
      v50 = 630;
LABEL_147:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v41,
        (int)v60);
      goto LABEL_148;
    }
    v71 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v75 + 56LL))(v75, &v71);
    if ( v41 < 0 )
      break;
    v47 = v71;
    v64 = &v66;
    v63 = v71;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<long,Windows::WCP::Rtl::FormatHResultWrapper<long>,wchar_t *>(
        LogAdapter::g_Logger,
        v44,
        v45,
        v46,
        (__int64)&v76,
        (__int64)&v64,
        (__int64)&v63);
      v47 = v71;
    }
    if ( (v8 & 0x80000000) == 0 )
      v8 = v66;
    if ( v47 )
    {
      SysFreeString(v47);
      v71 = 0;
    }
    if ( v75 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v43 = (unsigned int)(v76 + 1);
    v76 = v43;
    if ( (int)v43 >= v74 )
      goto LABEL_135;
  }
  v72 = v41;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<long>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "DWLD: Unable to get WU warning message {}",
      &v76);
    *(_QWORD *)v62 = &v72;
    LOBYTE(v48) = 1;
    v60 = v62;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v48,
      3,
      ": {}");
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x279,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)(unsigned int)v41,
    (int)v60);
  if ( v71 )
  {
    SysFreeString(v71);
    v71 = 0;
  }
LABEL_148:
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v75 = 0;
  }
LABEL_106:
  if ( v77 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    v77 = 0;
  }
LABEL_108:
  if ( v67 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v70 )
  {
    (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
    v70 = 0;
  }
  if ( v68 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    v68 = 0;
  }
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x1801b066c  push    rbp
0x1801b066e  push    rbx
0x1801b066f  push    rsi
0x1801b0670  push    rdi
0x1801b0671  push    r12
0x1801b0673  push    r13
0x1801b0675  push    r14
0x1801b0677  push    r15
0x1801b0679  lea     rbp, [rsp-28h]
0x1801b067e  sub     rsp, 128h
0x1801b0685  mov     rax, cs:__security_cookie
0x1801b068c  xor     rax, rsp
0x1801b068f  mov     [rbp+60h+var_48], rax
0x1801b0693  mov     r12, [rbp+60h+arg_20]
0x1801b069a  xor     r13d, r13d
0x1801b069d  mov     [rbp+60h+var_A8], r13
0x1801b06a1  mov     rsi, r8
0x1801b06a4  mov     [rbp+60h+var_D0], r13
0x1801b06a8  mov     r15, r9
0x1801b06ab  mov     [rbp+60h+var_C0], r13
0x1801b06af  mov     r8, rdx
0x1801b06b2  mov     [rbp+60h+bstrString], r13
0x1801b06b6  mov     r14d, ecx
0x1801b06b9  mov     [rbp+60h+var_D8], r13
0x1801b06bd  mov     [rbp+60h+var_50], r13d
0x1801b06c1  mov     [rbp+60h+var_80], r13d
0x1801b06c5  mov     [rsp+160h+var_120], r13b
0x1801b06ca  test    rdx, rdx
0x1801b06cd  jnz     loc_1801B07D6
0x1801b06d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b06da  mov     edi, 80070057h
0x1801b06df  mov     [rbp+60h+var_E0], edi
0x1801b06e2  test    rcx, rcx
0x1801b06e5  jz      short loc_1801B0722
0x1801b06e7  lea     ebx, [rdx+3]
0x1801b06ea  mov     r8d, ebx
0x1801b06ed  lea     r9, aNoUpdateSessio; "No update session specified"
0x1801b06f4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b06f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0700  lea     rax, [rbp+60h+var_E0]
0x1801b0704  mov     [rbp+60h+var_B8], rax
0x1801b0708  lea     r9, asc_1801CAFB4; ": {}"
0x1801b070f  lea     rax, [rbp+60h+var_B8]
0x1801b0713  mov     r8d, ebx
0x1801b0716  mov     dl, 1
0x1801b0718  mov     qword ptr [rsp+160h+var_140], rax; int
0x1801b071d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b0722  mov     edx, 228h; void *
0x1801b0727  mov     rcx, [rbp+68h]; this
0x1801b072b  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b0732  mov     r9d, edi; char *
0x1801b0735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b073a  mov     rcx, [rbp+60h+var_D8]
0x1801b073e  test    rcx, rcx
0x1801b0741  jz      short loc_1801B0753
0x1801b0743  mov     rax, [rcx]
0x1801b0746  mov     rax, [rax+10h]
0x1801b074a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b074f  mov     [rbp+60h+var_D8], r13
0x1801b0753  mov     rcx, [rbp+60h+bstrString]; bstrString
0x1801b0757  test    rcx, rcx
0x1801b075a  jz      short loc_1801B076C
0x1801b075c  call    cs:__imp_SysFreeString
0x1801b0763  nop     dword ptr [rax+rax+00h]
0x1801b0768  mov     [rbp+60h+bstrString], r13
0x1801b076c  mov     rcx, [rbp+60h+var_C0]
0x1801b0770  test    rcx, rcx
0x1801b0773  jz      short loc_1801B0785
0x1801b0775  mov     rax, [rcx]
0x1801b0778  mov     rax, [rax+10h]
0x1801b077c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0781  mov     [rbp+60h+var_C0], r13
0x1801b0785  mov     rcx, [rbp+60h+var_D0]
0x1801b0789  test    rcx, rcx
0x1801b078c  jz      short loc_1801B079E
0x1801b078e  mov     rax, [rcx]
0x1801b0791  mov     rax, [rax+10h]
0x1801b0795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b079a  mov     [rbp+60h+var_D0], r13
0x1801b079e  mov     rcx, [rbp+60h+var_A8]
0x1801b07a2  test    rcx, rcx
0x1801b07a5  jz      short loc_1801B07B3
0x1801b07a7  mov     rdx, [rcx]
0x1801b07aa  mov     rax, [rdx+10h]
0x1801b07ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b07b3  mov     eax, edi
0x1801b07b5  mov     rcx, [rbp+60h+var_48]
0x1801b07b9  xor     rcx, rsp; StackCookie
0x1801b07bc  call    __security_check_cookie
0x1801b07c1  add     rsp, 128h
0x1801b07c8  pop     r15
0x1801b07ca  pop     r14
0x1801b07cc  pop     r13
0x1801b07ce  pop     r12
0x1801b07d0  pop     rdi
0x1801b07d1  pop     rsi
0x1801b07d2  pop     rbx
0x1801b07d3  pop     rbp
0x1801b07d4  retn
0x1801b07d6  test    r12, r12
0x1801b07d9  jnz     short loc_1801B0838
0x1801b07db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b07e2  mov     edi, 80004003h
0x1801b07e7  mov     [rbp+60h+var_E0], edi
0x1801b07ea  test    rcx, rcx
0x1801b07ed  jz      short loc_1801B082E
0x1801b07ef  lea     ebx, [r12+3]
0x1801b07f4  xor     edx, edx
0x1801b07f6  mov     r8d, ebx
0x1801b07f9  lea     r9, aNoUpdateResult; "No update result specified"
0x1801b0800  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b0805  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b080c  lea     rax, [rbp+60h+var_E0]
0x1801b0810  mov     [rbp+60h+var_B8], rax
0x1801b0814  lea     r9, asc_1801CAFB4; ": {}"
0x1801b081b  lea     rax, [rbp+60h+var_B8]
0x1801b081f  mov     r8d, ebx
0x1801b0822  mov     dl, 1
0x1801b0824  mov     qword ptr [rsp+160h+var_140], rax
0x1801b0829  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b082e  mov     edx, 229h
0x1801b0833  jmp     loc_1801B0727
0x1801b0838  mov     rax, [rdx]
0x1801b083b  mov     rcx, r8
0x1801b083e  lea     rdx, [rbp+60h+var_D0]
0x1801b0842  mov     rax, [rax+60h]
0x1801b0846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b084b  mov     edi, eax
0x1801b084d  test    eax, eax
0x1801b084f  jns     loc_1801B0938
0x1801b0855  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b085c  mov     [rbp+60h+var_E0], eax
0x1801b085f  test    rcx, rcx
0x1801b0862  jz      short loc_1801B08A3
0x1801b0864  mov     ebx, 3
0x1801b0869  lea     r9, aFailedToCreate_20; "Failed to create searcher"
0x1801b0870  mov     r8d, ebx
0x1801b0873  xor     edx, edx
0x1801b0875  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b087a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0881  lea     rax, [rbp+60h+var_E0]
0x1801b0885  mov     [rbp+60h+var_B8], rax
0x1801b0889  lea     r9, asc_1801CAFB4; ": {}"
0x1801b0890  lea     rax, [rbp+60h+var_B8]
0x1801b0894  mov     r8d, ebx
0x1801b0897  mov     dl, 1
0x1801b0899  mov     qword ptr [rsp+160h+var_140], rax; int
0x1801b089e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b08a3  mov     edx, 22Bh; void *
0x1801b08a8  mov     rcx, [rbp+68h]; this
0x1801b08ac  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b08b3  mov     r9d, edi; char *
0x1801b08b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b08bb  mov     rcx, [rbp+60h+var_D8]
0x1801b08bf  test    rcx, rcx
0x1801b08c2  jz      short loc_1801B08D4
0x1801b08c4  mov     rax, [rcx]
0x1801b08c7  mov     rax, [rax+10h]
0x1801b08cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b08d0  mov     [rbp+60h+var_D8], r13
0x1801b08d4  mov     rcx, [rbp+60h+bstrString]; bstrString
0x1801b08d8  test    rcx, rcx
0x1801b08db  jz      short loc_1801B08ED
0x1801b08dd  call    cs:__imp_SysFreeString
0x1801b08e4  nop     dword ptr [rax+rax+00h]
0x1801b08e9  mov     [rbp+60h+bstrString], r13
0x1801b08ed  mov     rcx, [rbp+60h+var_C0]
0x1801b08f1  test    rcx, rcx
0x1801b08f4  jz      short loc_1801B0906
0x1801b08f6  mov     rax, [rcx]
0x1801b08f9  mov     rax, [rax+10h]
0x1801b08fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0902  mov     [rbp+60h+var_C0], r13
0x1801b0906  mov     rcx, [rbp+60h+var_D0]
0x1801b090a  test    rcx, rcx
0x1801b090d  jz      short loc_1801B091F
0x1801b090f  mov     rax, [rcx]
0x1801b0912  mov     rax, [rax+10h]
0x1801b0916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b091b  mov     [rbp+60h+var_D0], r13
0x1801b091f  mov     rcx, [rbp+60h+var_A8]
0x1801b0923  test    rcx, rcx
0x1801b0926  jz      loc_1801B07B3
0x1801b092c  mov     rax, [rcx]
0x1801b092f  mov     rax, [rax+10h]
0x1801b0933  jmp     loc_1801B07AE
0x1801b0938  cmp     [rbp+60h+var_C0], r13
0x1801b093c  jnz     loc_1801B1639
0x1801b0942  mov     rcx, [rbp+60h+var_D0]
0x1801b0946  lea     r8, [rbp+60h+var_C0]
0x1801b094a  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x1801b0951  mov     rax, [rcx]
0x1801b0954  mov     rax, [rax]
0x1801b0957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b095c  mov     edi, eax
0x1801b095e  test    eax, eax
0x1801b0960  jns     short loc_1801B09BA
0x1801b0962  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0969  mov     [rbp+60h+var_E0], eax
0x1801b096c  test    rcx, rcx
0x1801b096f  jz      short loc_1801B09B0
0x1801b0971  mov     ebx, 3
0x1801b0976  lea     r9, aFailedToSetCli; "Failed to set client ID"
0x1801b097d  mov     r8d, ebx
0x1801b0980  xor     edx, edx
0x1801b0982  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b0987  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b098e  lea     rax, [rbp+60h+var_E0]
0x1801b0992  mov     [rbp+60h+var_B8], rax
0x1801b0996  lea     r9, asc_1801CAFB4; ": {}"
0x1801b099d  lea     rax, [rbp+60h+var_B8]
0x1801b09a1  mov     r8d, ebx
0x1801b09a4  mov     dl, 1
0x1801b09a6  mov     qword ptr [rsp+160h+var_140], rax
0x1801b09ab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b09b0  mov     edx, 230h
0x1801b09b5  jmp     loc_1801B08A8
0x1801b09ba  mov     rcx, [rbp+60h+var_D0]
0x1801b09be  lea     r8, [rbp+60h+var_98]
0x1801b09c2  xorps   xmm0, xmm0
0x1801b09c5  mov     [rbp+60h+var_98], r13
0x1801b09c9  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x1801b09cd  xor     ebx, ebx
0x1801b09cf  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x1801b09d6  lea     eax, [rbx+0Bh]
0x1801b09d9  mov     word ptr [rbp+60h+pvarg], ax
0x1801b09dd  or      eax, 0FFFFFFFFh
0x1801b09e0  mov     word ptr [rbp+60h+pvarg+8], ax
0x1801b09e4  mov     rax, [rcx]
0x1801b09e7  mov     rax, [rax]
0x1801b09ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b09ef  mov     edi, eax
0x1801b09f1  test    eax, eax
0x1801b09f3  jns     loc_1801B0ACB
0x1801b09f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0a00  mov     ebx, 3
0x1801b0a05  mov     [rbp+60h+var_E0], eax
0x1801b0a08  test    rcx, rcx
0x1801b0a0b  jz      short loc_1801B0A47
0x1801b0a0d  lea     r9, aFailedToQueryI; "Failed to query internal configuration"
0x1801b0a14  mov     r8d, ebx
0x1801b0a17  xor     edx, edx
0x1801b0a19  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b0a1e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0a25  lea     rax, [rbp+60h+var_E0]
0x1801b0a29  mov     [rbp+60h+var_B8], rax
0x1801b0a2d  lea     r9, asc_1801CAFB4; ": {}"
0x1801b0a34  lea     rax, [rbp+60h+var_B8]
0x1801b0a38  mov     r8d, ebx
0x1801b0a3b  mov     dl, 1
0x1801b0a3d  mov     qword ptr [rsp+160h+var_140], rax; int
0x1801b0a42  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b0a47  mov     rcx, [rbp+68h]; this
0x1801b0a4b  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b0a52  mov     r9d, edi; char *
0x1801b0a55  mov     edx, 20Ch; void *
0x1801b0a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0a5f  mov     rcx, [rbp+60h+var_98]
0x1801b0a63  test    rcx, rcx
0x1801b0a66  jz      short loc_1801B0A78
0x1801b0a68  mov     rax, [rcx]
0x1801b0a6b  mov     rax, [rax+10h]
0x1801b0a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a74  mov     [rbp+60h+var_98], r13
0x1801b0a78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0a7f  mov     [rbp+60h+var_E0], edi
0x1801b0a82  test    rcx, rcx
0x1801b0a85  jz      short loc_1801B0AC1
0x1801b0a87  lea     r9, aDwldFailedToSe_1; "DWLD:Failed to set default search prope"...
0x1801b0a8e  mov     r8d, ebx
0x1801b0a91  xor     edx, edx
0x1801b0a93  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b0a98  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b0a9f  lea     rax, [rbp+60h+var_E0]
0x1801b0aa3  mov     [rbp+60h+var_B8], rax
0x1801b0aa7  lea     r9, asc_1801CAFB4; ": {}"
0x1801b0aae  lea     rax, [rbp+60h+var_B8]
0x1801b0ab2  mov     r8d, ebx
0x1801b0ab5  mov     dl, 1
0x1801b0ab7  mov     qword ptr [rsp+160h+var_140], rax
0x1801b0abc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b0ac1  mov     edx, 232h
0x1801b0ac6  jmp     loc_1801B08A8
0x1801b0acb  mov     rcx, [rbp+60h+var_98]
0x1801b0acf  lea     r8, [rbp+60h+pvarg]
0x1801b0ad3  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x1801b0ad7  mov     edx, 40001h
0x1801b0adc  mov     qword ptr [rbp+60h+pvarg+10h], rbx
0x1801b0ae0  mov     rax, [rcx]
0x1801b0ae3  movaps  xmmword ptr [rbp+60h+pvarg], xmm0
0x1801b0ae7  mov     rax, [rax+20h]
0x1801b0aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0af0  mov     ebx, 3
0x1801b0af5  test    eax, eax
0x1801b0af7  jns     short loc_1801B0B09
0x1801b0af9  lea     r8, aUnableToSetInt; "Unable to set interactive flag for sear"...
0x1801b0b00  mov     edx, eax
0x1801b0b02  mov     ecx, ebx
0x1801b0b04  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801b0b09  mov     rcx, [rbp+60h+var_98]
  ... truncated ...
```
