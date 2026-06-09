# WindowsUpdateSearch

- ea: `0x18026d9b0`
- end: `0x18026e7a9`
- name: `WindowsUpdateSearch`
- size: `3577`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18026e7b0`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000a7fc`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x1800692fc`
- `0x18008b38c`
- `0x180268794`
- `0x180269610`
- `0x18026a53c`
- `0x18026c18c`
- `0x18026d9b0`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18026da90`
- `OLEAUT32!__imp_SysFreeString` at `0x18026dc0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e197`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e2dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e3aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e6c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e740`
- `OLEAUT32!__imp_SysFreeString` at `0x18026da90`
- `OLEAUT32!__imp_SysFreeString` at `0x18026dc0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e197`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e2dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e3aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e6c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18026e740`

## string_xrefs

- `0x18026da5f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026dbdb`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026dd7c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e148`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e389`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e477`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e563`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026e68a`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026dd3e`: `Failed to query internal configuration`
- `0x18026de64`: `Not able to show current windows update server configuration`
- `0x18026da21`: `No update session specified`
- `0x18026db98`: `Failed to create searcher`
- `0x18026db28`: `No update result specified`
- `0x18026e617`: `DLWD: Expecting search returns 1 update, actual:{}`
- `0x18026e5a0`: `Failed to get update count`

## pseudocode

```c
__int64 __fastcall WindowsUpdateSearch(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rdx
  void (*v8)(void); // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  int updated; // eax
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  OLECHAR *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  const char *v44; // r9
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rdx
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rdx
  int v51; // eax
  unsigned int v52; // ebx
  void *v53; // [rsp+20h] [rbp-B1h]
  _BYTE v54[8]; // [rsp+40h] [rbp-91h] BYREF
  int v55[2]; // [rsp+48h] [rbp-89h] BYREF
  __int128 v56; // [rsp+50h] [rbp-81h] BYREF
  __int64 v57; // [rsp+60h] [rbp-71h]
  BSTR v58; // [rsp+70h] [rbp-61h] BYREF
  int *v59; // [rsp+78h] [rbp-59h] BYREF
  int v60; // [rsp+80h] [rbp-51h] BYREF
  __int64 v61; // [rsp+88h] [rbp-49h] BYREF
  __int64 v62; // [rsp+90h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-39h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-31h] BYREF
  BSTR v65; // [rsp+A8h] [rbp-29h] BYREF
  int v66; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-19h] BYREF
  int v68; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-9h] BYREF
  int v70; // [rsp+D0h] [rbp-1h] BYREF
  __int64 v71; // [rsp+D8h] [rbp+7h] BYREF
  int v72; // [rsp+E0h] [rbp+Fh] BYREF
  int v73; // [rsp+E4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v67 = 0;
  v62 = 0;
  v64 = 0;
  bstrString = 0;
  v61 = 0;
  v73 = 0;
  v72 = 0;
  v54[0] = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v60 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update session specified");
      v65 = (BSTR)&v60;
      LOBYTE(v6) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    v7 = 552;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v5 = -2147467261;
    v60 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update result specified");
      v65 = (BSTR)&v60;
      LOBYTE(v10) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    v7 = 553;
    goto LABEL_5;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v62);
  v5 = v11;
  if ( v11 < 0 )
  {
    v60 = v11;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create searcher");
      v65 = (BSTR)&v60;
      LOBYTE(v12) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    v13 = 555;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v5,
      (int)v53);
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( !v67 )
      return (unsigned int)v5;
    v8 = *(void (**)(void))(*(_QWORD *)v67 + 16LL);
    goto LABEL_16;
  }
  if ( v64 )
    goto LABEL_174;
  v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v62)(
          v62,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v64);
  v5 = v14;
  if ( v14 < 0 )
  {
    v60 = v14;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      v65 = (BSTR)&v60;
      LOBYTE(v15) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        3,
        ": {}");
    }
    v13 = 560;
    goto LABEL_26;
  }
  v69 = 0;
  v56 = 0;
  LOWORD(v56) = 11;
  WORD4(v56) = -1;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v62)(
          v62,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v69);
  v5 = v16;
  if ( v16 < 0 )
  {
    v60 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to query internal configuration");
      v65 = (BSTR)&v60;
      LOBYTE(v17) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v5,
      (int)v53);
    if ( v69 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      v69 = 0;
    }
    v60 = v5;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to set default search properties");
      v65 = (BSTR)&v60;
      LOBYTE(v18) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v18,
        3,
        ": {}");
    }
    v13 = 562;
    goto LABEL_26;
  }
  v57 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v69 + 32LL))(v69, 262145, &v56);
  if ( v19 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v19, "Unable to set interactive flag for search");
  if ( v69 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    v69 = 0;
  }
  updated = ShowWindowsUpdateServerConfiguration(v54);
  if ( updated < 0 )
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      (unsigned int)updated,
      "Not able to show current windows update server configuration");
  DumpWindowsInsiderSettings();
  if ( bstrString )
    goto LABEL_174;
  v21 = CreateUUPSearchCriteria(0, 0, &bstrString);
  v5 = v21;
  if ( v21 < 0 )
  {
    v60 = v21;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get search criteria.");
      v65 = (BSTR)&v60;
      LOBYTE(v22) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {}");
    }
    v13 = 592;
    goto LABEL_26;
  }
  if ( v61 )
  {
LABEL_174:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026E7A8LL);
  }
  v23 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v62 + 152LL))(v62, bstrString, &v61);
  v5 = v23;
  if ( v23 < 0 )
  {
    v60 = v23;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DLWD:WU search failed");
      v65 = (BSTR)&v60;
      LOBYTE(v24) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v24,
        3,
        ": {}");
    }
    v13 = 594;
    goto LABEL_26;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 56LL))(v61, &v73);
  v5 = v25;
  if ( v25 < 0 )
  {
    v60 = v25;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get download hresult");
      v65 = (BSTR)&v60;
      LOBYTE(v27) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v27,
        3,
        ": {}");
    }
    v13 = 596;
    goto LABEL_26;
  }
  if ( v73 == 4 )
  {
    v5 = -2146498289;
    v68 = -2146498289;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Search failed with");
      v65 = (BSTR)&v68;
      LOBYTE(v28) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v28,
        3,
        ": {}");
    }
    v7 = 602;
    goto LABEL_5;
  }
  if ( v73 == 5 )
  {
    v5 = -2147467260;
    v68 = -2147467260;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: WU cancelled the search operation");
      v65 = (BSTR)&v68;
      LOBYTE(v29) = 1;
      v53 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v29,
        3,
        ": {}");
    }
    v7 = 606;
    goto LABEL_5;
  }
  v5 = 0;
  if ( v73 != 3 )
  {
    if ( v73 == 2 )
    {
      v66 = 2;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_134;
      v44 = "DWLD: WU search succeeded with WU result code {}";
    }
    else
    {
      v66 = v73;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_134;
      v44 = "DWLD: WU search failed with WU result code {}";
    }
    LOBYTE(v26) = 1;
    LogAdapter::Logger::LogNumObjects<long>(*(_QWORD *)&LogAdapter::g_Logger, v26, 1, v44, &v66);
LABEL_134:
    if ( !v67 )
    {
      v45 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 72LL))(v61, &v67);
      v33 = v45;
      if ( v45 >= 0 )
      {
        v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 80LL))(v67, &v72);
        v33 = v48;
        if ( v48 >= 0 )
        {
          if ( v72 == 1 )
          {
            v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v67 + 56LL))(v67, 0, a5);
            v52 = v51;
            if ( v51 >= 0 )
            {
              if ( v61 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                v61 = 0;
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v64 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                v64 = 0;
              }
              if ( v62 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                v62 = 0;
              }
              if ( v67 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x297,
                (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
                (const char *)(unsigned int)v51,
                (int)v53);
              if ( v61 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                v61 = 0;
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v64 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                v64 = 0;
              }
              if ( v62 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                v62 = 0;
              }
              if ( v67 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              return v52;
            }
          }
          if ( v5 >= 0 )
            v5 = v54[0] != 0 ? -2146498220 : -2146498224;
          v60 = v5;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "DLWD: Expecting search returns 1 update, actual:{}",
              &v72);
            *(_QWORD *)v55 = &v60;
            LOBYTE(v50) = 1;
            v53 = v55;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v50,
              3,
              ": {}");
          }
          if ( v5 >= 0 )
            goto LABEL_6;
          v7 = 660;
LABEL_5:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v7,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)(unsigned int)v5,
            (int)v53);
LABEL_6:
          if ( v61 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
            v61 = 0;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v64 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            v64 = 0;
          }
          if ( v62 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
            v62 = 0;
          }
          if ( !v67 )
            return (unsigned int)v5;
          v8 = *(void (**)(void))(*(_QWORD *)v67 + 16LL);
LABEL_16:
          v8();
          return (unsigned int)v5;
        }
        v66 = v48;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update count");
          *(_QWORD *)v55 = &v66;
          LOBYTE(v49) = 1;
          v53 = v55;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v49,
            3,
            ": {}");
        }
        v47 = 653;
      }
      else
      {
        v66 = v45;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to get search collection.");
          *(_QWORD *)v55 = &v66;
          LOBYTE(v46) = 1;
          v53 = v55;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v46,
            3,
            ": {}");
        }
        v47 = 648;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v33,
        (int)v53);
      goto LABEL_86;
    }
    goto LABEL_174;
  }
  LogAdapter::TraceInfo<>("DWLD: WU search succeeded with errors");
  v68 = 0;
  v71 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 80LL))(v61, &v71);
  if ( v30 >= 0 )
  {
    v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 72LL))(v71, &v68);
    v33 = v31;
    if ( v31 < 0 )
    {
      v60 = v31;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warnings count");
        v65 = (BSTR)&v60;
        LOBYTE(v34) = 1;
        v53 = &v65;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v34,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26C,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v33,
        (int)v53);
      goto LABEL_84;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<long>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v32,
        1,
        "DWLD: WU search warnings: {}",
        &v68);
    }
  }
  else
  {
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v30, "DWLD: Unable to get WU warnings list");
  }
  v70 = 0;
  if ( v68 <= 0 )
  {
LABEL_113:
    if ( v71 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    goto LABEL_134;
  }
  v35 = 0;
  while ( 1 )
  {
    v69 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v71 + 56LL))(v71, v35, &v69);
    if ( v33 < 0 )
    {
      v66 = v33;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning {}",
          &v70);
        *(_QWORD *)v55 = &v66;
        LOBYTE(v43) = 1;
        v53 = v55;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v43,
          3,
          ": {}");
      }
      v42 = 627;
      goto LABEL_125;
    }
    v60 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 64LL))(v69, &v60);
    if ( v33 < 0 )
    {
      v66 = v33;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning hr {}",
          &v70);
        *(_QWORD *)v55 = &v66;
        LOBYTE(v41) = 1;
        v53 = v55;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v41,
          3,
          ": {}");
      }
      v42 = 630;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v33,
        (int)v53);
      goto LABEL_126;
    }
    v65 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v69 + 56LL))(v69, &v65);
    if ( v33 < 0 )
      break;
    v39 = v65;
    v59 = &v60;
    v58 = v65;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<long,Windows::WCP::Rtl::FormatHResultWrapper<long>,wchar_t *>(
        LogAdapter::g_Logger,
        v36,
        v37,
        v38,
        (__int64)&v70,
        (__int64)&v59,
        (__int64)&v58);
      v39 = v65;
    }
    if ( v5 >= 0 )
      v5 = v60;
    if ( v39 )
    {
      SysFreeString(v39);
      v65 = 0;
    }
    if ( v69 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    v35 = (unsigned int)(v70 + 1);
    v70 = v35;
    if ( (int)v35 >= v68 )
      goto LABEL_113;
  }
  v66 = v33;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<long>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "DWLD: Unable to get WU warning message {}",
      &v70);
    *(_QWORD *)v55 = &v66;
    LOBYTE(v40) = 1;
    v53 = v55;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v40,
      3,
      ": {}");
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x279,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)(unsigned int)v33,
    (int)v53);
  if ( v65 )
  {
    SysFreeString(v65);
    v65 = 0;
  }
LABEL_126:
  if ( v69 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    v69 = 0;
  }
LABEL_84:
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
LABEL_86:
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18026d9b0  push    rbp
0x18026d9b2  push    rbx
0x18026d9b3  push    rsi
0x18026d9b4  push    rdi
0x18026d9b5  push    r14
0x18026d9b7  push    r15
0x18026d9b9  lea     rbp, [rsp-27h]
0x18026d9be  sub     rsp, 0F8h
0x18026d9c5  mov     rax, cs:__security_cookie
0x18026d9cc  xor     rax, rsp
0x18026d9cf  mov     [rbp+4Fh+var_38], rax
0x18026d9d3  mov     r14, [rbp+4Fh+arg_20]
0x18026d9d7  xor     r15d, r15d
0x18026d9da  mov     [rbp+4Fh+var_68], r15
0x18026d9de  mov     r8, rdx
0x18026d9e1  mov     [rbp+4Fh+var_90], r15
0x18026d9e5  mov     [rbp+4Fh+var_80], r15
0x18026d9e9  mov     [rbp+4Fh+bstrString], r15
0x18026d9ed  mov     [rbp+4Fh+var_98], r15
0x18026d9f1  mov     [rbp+4Fh+var_3C], r15d
0x18026d9f5  mov     [rbp+4Fh+var_40], r15d
0x18026d9f9  mov     [rsp+120h+var_E0], r15b
0x18026d9fe  test    rdx, rdx
0x18026da01  jnz     loc_18026DB06
0x18026da07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026da0e  mov     edi, 80070057h
0x18026da13  mov     [rbp+4Fh+var_A0], edi
0x18026da16  test    rcx, rcx
0x18026da19  jz      short loc_18026DA56
0x18026da1b  lea     ebx, [rdx+3]
0x18026da1e  mov     r8d, ebx
0x18026da21  lea     r9, aNoUpdateSessio; "No update session specified"
0x18026da28  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026da2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026da34  lea     rax, [rbp+4Fh+var_A0]
0x18026da38  mov     [rbp+4Fh+var_78], rax
0x18026da3c  lea     r9, asc_1802C6678; ": {}"
0x18026da43  lea     rax, [rbp+4Fh+var_78]
0x18026da47  mov     r8d, ebx
0x18026da4a  mov     dl, 1
0x18026da4c  mov     qword ptr [rsp+120h+var_100], rax; int
0x18026da51  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026da56  mov     edx, 228h; void *
0x18026da5b  mov     rcx, [rbp+57h]; this
0x18026da5f  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026da66  mov     r9d, edi; char *
0x18026da69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026da6e  mov     rcx, [rbp+4Fh+var_98]
0x18026da72  test    rcx, rcx
0x18026da75  jz      short loc_18026DA87
0x18026da77  mov     rax, [rcx]
0x18026da7a  mov     rax, [rax+10h]
0x18026da7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026da83  mov     [rbp+4Fh+var_98], r15
0x18026da87  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x18026da8b  test    rcx, rcx
0x18026da8e  jz      short loc_18026DAA0
0x18026da90  call    cs:__imp_SysFreeString
0x18026da97  nop     dword ptr [rax+rax+00h]
0x18026da9c  mov     [rbp+4Fh+bstrString], r15
0x18026daa0  mov     rcx, [rbp+4Fh+var_80]
0x18026daa4  test    rcx, rcx
0x18026daa7  jz      short loc_18026DAB9
0x18026daa9  mov     rax, [rcx]
0x18026daac  mov     rax, [rax+10h]
0x18026dab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dab5  mov     [rbp+4Fh+var_80], r15
0x18026dab9  mov     rcx, [rbp+4Fh+var_90]
0x18026dabd  test    rcx, rcx
0x18026dac0  jz      short loc_18026DAD2
0x18026dac2  mov     rax, [rcx]
0x18026dac5  mov     rax, [rax+10h]
0x18026dac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dace  mov     [rbp+4Fh+var_90], r15
0x18026dad2  mov     rcx, [rbp+4Fh+var_68]
0x18026dad6  test    rcx, rcx
0x18026dad9  jz      short loc_18026DAE7
0x18026dadb  mov     rdx, [rcx]
0x18026dade  mov     rax, [rdx+10h]
0x18026dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dae7  mov     eax, edi
0x18026dae9  mov     rcx, [rbp+4Fh+var_38]
0x18026daed  xor     rcx, rsp; StackCookie
0x18026daf0  call    __security_check_cookie
0x18026daf5  add     rsp, 0F8h
0x18026dafc  pop     r15
0x18026dafe  pop     r14
0x18026db00  pop     rdi
0x18026db01  pop     rsi
0x18026db02  pop     rbx
0x18026db03  pop     rbp
0x18026db04  retn
0x18026db06  test    r14, r14
0x18026db09  jnz     short loc_18026DB67
0x18026db0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026db12  mov     edi, 80004003h
0x18026db17  mov     [rbp+4Fh+var_A0], edi
0x18026db1a  test    rcx, rcx
0x18026db1d  jz      short loc_18026DB5D
0x18026db1f  lea     ebx, [r14+3]
0x18026db23  xor     edx, edx
0x18026db25  mov     r8d, ebx
0x18026db28  lea     r9, aNoUpdateResult; "No update result specified"
0x18026db2f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026db34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026db3b  lea     rax, [rbp+4Fh+var_A0]
0x18026db3f  mov     [rbp+4Fh+var_78], rax
0x18026db43  lea     r9, asc_1802C6678; ": {}"
0x18026db4a  lea     rax, [rbp+4Fh+var_78]
0x18026db4e  mov     r8d, ebx
0x18026db51  mov     dl, 1
0x18026db53  mov     qword ptr [rsp+120h+var_100], rax
0x18026db58  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026db5d  mov     edx, 229h
0x18026db62  jmp     loc_18026DA5B
0x18026db67  mov     rax, [rdx]
0x18026db6a  mov     rcx, r8
0x18026db6d  lea     rdx, [rbp+4Fh+var_90]
0x18026db71  mov     rax, [rax+60h]
0x18026db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026db7a  mov     edi, eax
0x18026db7c  test    eax, eax
0x18026db7e  jns     loc_18026DC67
0x18026db84  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026db8b  mov     [rbp+4Fh+var_A0], eax
0x18026db8e  test    rcx, rcx
0x18026db91  jz      short loc_18026DBD2
0x18026db93  mov     ebx, 3
0x18026db98  lea     r9, aFailedToCreate_46; "Failed to create searcher"
0x18026db9f  mov     r8d, ebx
0x18026dba2  xor     edx, edx
0x18026dba4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026dba9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026dbb0  lea     rax, [rbp+4Fh+var_A0]
0x18026dbb4  mov     [rbp+4Fh+var_78], rax
0x18026dbb8  lea     r9, asc_1802C6678; ": {}"
0x18026dbbf  lea     rax, [rbp+4Fh+var_78]
0x18026dbc3  mov     r8d, ebx
0x18026dbc6  mov     dl, 1
0x18026dbc8  mov     qword ptr [rsp+120h+var_100], rax; int
0x18026dbcd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026dbd2  mov     edx, 22Bh; void *
0x18026dbd7  mov     rcx, [rbp+57h]; this
0x18026dbdb  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026dbe2  mov     r9d, edi; char *
0x18026dbe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026dbea  mov     rcx, [rbp+4Fh+var_98]
0x18026dbee  test    rcx, rcx
0x18026dbf1  jz      short loc_18026DC03
0x18026dbf3  mov     rax, [rcx]
0x18026dbf6  mov     rax, [rax+10h]
0x18026dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dbff  mov     [rbp+4Fh+var_98], r15
0x18026dc03  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x18026dc07  test    rcx, rcx
0x18026dc0a  jz      short loc_18026DC1C
0x18026dc0c  call    cs:__imp_SysFreeString
0x18026dc13  nop     dword ptr [rax+rax+00h]
0x18026dc18  mov     [rbp+4Fh+bstrString], r15
0x18026dc1c  mov     rcx, [rbp+4Fh+var_80]
0x18026dc20  test    rcx, rcx
0x18026dc23  jz      short loc_18026DC35
0x18026dc25  mov     rax, [rcx]
0x18026dc28  mov     rax, [rax+10h]
0x18026dc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dc31  mov     [rbp+4Fh+var_80], r15
0x18026dc35  mov     rcx, [rbp+4Fh+var_90]
0x18026dc39  test    rcx, rcx
0x18026dc3c  jz      short loc_18026DC4E
0x18026dc3e  mov     rax, [rcx]
0x18026dc41  mov     rax, [rax+10h]
0x18026dc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dc4a  mov     [rbp+4Fh+var_90], r15
0x18026dc4e  mov     rcx, [rbp+4Fh+var_68]
0x18026dc52  test    rcx, rcx
0x18026dc55  jz      loc_18026DAE7
0x18026dc5b  mov     rax, [rcx]
0x18026dc5e  mov     rax, [rax+10h]
0x18026dc62  jmp     loc_18026DAE2
0x18026dc67  cmp     [rbp+4Fh+var_80], r15
0x18026dc6b  jnz     loc_18026E79E
0x18026dc71  mov     rcx, [rbp+4Fh+var_90]
0x18026dc75  lea     r8, [rbp+4Fh+var_80]
0x18026dc79  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18026dc80  mov     rax, [rcx]
0x18026dc83  mov     rax, [rax]
0x18026dc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dc8b  mov     edi, eax
0x18026dc8d  test    eax, eax
0x18026dc8f  jns     short loc_18026DCE9
0x18026dc91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026dc98  mov     [rbp+4Fh+var_A0], eax
0x18026dc9b  test    rcx, rcx
0x18026dc9e  jz      short loc_18026DCDF
0x18026dca0  mov     ebx, 3
0x18026dca5  lea     r9, aFailedToSetCli; "Failed to set client ID"
0x18026dcac  mov     r8d, ebx
0x18026dcaf  xor     edx, edx
0x18026dcb1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026dcb6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026dcbd  lea     rax, [rbp+4Fh+var_A0]
0x18026dcc1  mov     [rbp+4Fh+var_78], rax
0x18026dcc5  lea     r9, asc_1802C6678; ": {}"
0x18026dccc  lea     rax, [rbp+4Fh+var_78]
0x18026dcd0  mov     r8d, ebx
0x18026dcd3  mov     dl, 1
0x18026dcd5  mov     qword ptr [rsp+120h+var_100], rax
0x18026dcda  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026dcdf  mov     edx, 230h
0x18026dce4  jmp     loc_18026DBD7
0x18026dce9  mov     rcx, [rbp+4Fh+var_90]
0x18026dced  lea     r8, [rbp+4Fh+var_58]
0x18026dcf1  xorps   xmm0, xmm0
0x18026dcf4  mov     [rbp+4Fh+var_58], r15
0x18026dcf8  movups  [rsp+120h+var_D0], xmm0
0x18026dcfd  xor     ebx, ebx
0x18026dcff  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18026dd06  lea     eax, [rbx+0Bh]
0x18026dd09  mov     word ptr [rsp+120h+var_D0], ax
0x18026dd0e  or      eax, 0FFFFFFFFh
0x18026dd11  mov     word ptr [rbp+4Fh+var_D0+8], ax
0x18026dd15  mov     rax, [rcx]
0x18026dd18  mov     rax, [rax]
0x18026dd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dd20  mov     edi, eax
0x18026dd22  test    eax, eax
0x18026dd24  jns     loc_18026DDFC
0x18026dd2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026dd31  mov     ebx, 3
0x18026dd36  mov     [rbp+4Fh+var_A0], eax
0x18026dd39  test    rcx, rcx
0x18026dd3c  jz      short loc_18026DD78
0x18026dd3e  lea     r9, aFailedToQueryI_0; "Failed to query internal configuration"
0x18026dd45  mov     r8d, ebx
0x18026dd48  xor     edx, edx
0x18026dd4a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026dd4f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026dd56  lea     rax, [rbp+4Fh+var_A0]
0x18026dd5a  mov     [rbp+4Fh+var_78], rax
0x18026dd5e  lea     r9, asc_1802C6678; ": {}"
0x18026dd65  lea     rax, [rbp+4Fh+var_78]
0x18026dd69  mov     r8d, ebx
0x18026dd6c  mov     dl, 1
0x18026dd6e  mov     qword ptr [rsp+120h+var_100], rax; int
0x18026dd73  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026dd78  mov     rcx, [rbp+57h]; this
0x18026dd7c  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026dd83  mov     r9d, edi; char *
0x18026dd86  mov     edx, 20Ch; void *
0x18026dd8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026dd90  mov     rcx, [rbp+4Fh+var_58]
0x18026dd94  test    rcx, rcx
0x18026dd97  jz      short loc_18026DDA9
0x18026dd99  mov     rax, [rcx]
0x18026dd9c  mov     rax, [rax+10h]
0x18026dda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026dda5  mov     [rbp+4Fh+var_58], r15
0x18026dda9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ddb0  mov     [rbp+4Fh+var_A0], edi
0x18026ddb3  test    rcx, rcx
0x18026ddb6  jz      short loc_18026DDF2
0x18026ddb8  lea     r9, aDwldFailedToSe_2; "DWLD:Failed to set default search prope"...
0x18026ddbf  mov     r8d, ebx
0x18026ddc2  xor     edx, edx
0x18026ddc4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026ddc9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ddd0  lea     rax, [rbp+4Fh+var_A0]
0x18026ddd4  mov     [rbp+4Fh+var_78], rax
0x18026ddd8  lea     r9, asc_1802C6678; ": {}"
0x18026dddf  lea     rax, [rbp+4Fh+var_78]
0x18026dde3  mov     r8d, ebx
0x18026dde6  mov     dl, 1
0x18026dde8  mov     qword ptr [rsp+120h+var_100], rax
0x18026dded  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026ddf2  mov     edx, 232h
0x18026ddf7  jmp     loc_18026DBD7
0x18026ddfc  mov     rcx, [rbp+4Fh+var_58]
0x18026de00  lea     r8, [rsp+120h+var_D0]
0x18026de05  movups  xmm0, [rsp+120h+var_D0]
0x18026de0a  mov     edx, 40001h
0x18026de0f  mov     [rbp+4Fh+var_C0], rbx
0x18026de13  mov     rax, [rcx]
0x18026de16  movaps  [rsp+120h+var_D0], xmm0
0x18026de1b  mov     rax, [rax+20h]
0x18026de1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026de24  mov     ebx, 3
0x18026de29  test    eax, eax
0x18026de2b  jns     short loc_18026DE3D
0x18026de2d  lea     r8, aUnableToSetInt; "Unable to set interactive flag for sear"...
0x18026de34  mov     edx, eax
0x18026de36  mov     ecx, ebx
0x18026de38  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18026de3d  mov     rcx, [rbp+4Fh+var_58]
0x18026de41  test    rcx, rcx
0x18026de44  jz      short loc_18026DE56
0x18026de46  mov     rax, [rcx]
0x18026de49  mov     rax, [rax+10h]
0x18026de4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026de52  mov     [rbp+4Fh+var_58], r15
0x18026de56  lea     rcx, [rsp+120h+var_E0]
  ... truncated ...
```
