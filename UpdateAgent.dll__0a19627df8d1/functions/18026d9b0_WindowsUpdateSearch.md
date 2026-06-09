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
  void (*v7)(void); // rax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int updated; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  int v22; // esi
  __int64 v23; // rdx
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  OLECHAR *v27; // rcx
  __int64 v28; // rdx
  const char *v29; // r9
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  int v33; // eax
  unsigned int v34; // ebx
  int *v35; // [rsp+20h] [rbp-B1h]
  _BYTE v36[8]; // [rsp+40h] [rbp-91h] BYREF
  int v37[2]; // [rsp+48h] [rbp-89h] BYREF
  __int128 v38; // [rsp+50h] [rbp-81h] BYREF
  __int64 v39; // [rsp+60h] [rbp-71h]
  BSTR v40; // [rsp+70h] [rbp-61h] BYREF
  int *v41; // [rsp+78h] [rbp-59h] BYREF
  int v42; // [rsp+80h] [rbp-51h] BYREF
  __int64 v43; // [rsp+88h] [rbp-49h] BYREF
  __int64 v44; // [rsp+90h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-39h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-31h] BYREF
  BSTR v47; // [rsp+A8h] [rbp-29h] BYREF
  int v48; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-19h] BYREF
  int v50; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-9h] BYREF
  int v52; // [rsp+D0h] [rbp-1h] BYREF
  __int64 v53; // [rsp+D8h] [rbp+7h] BYREF
  int v54; // [rsp+E0h] [rbp+Fh] BYREF
  int v55; // [rsp+E4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v49 = 0;
  v44 = 0;
  v46 = 0;
  bstrString = 0;
  v43 = 0;
  v55 = 0;
  v54 = 0;
  v36[0] = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v42 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update session specified");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v6 = 552;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v5 = -2147467261;
    v42 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update result specified");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v6 = 553;
    goto LABEL_5;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v44);
  v5 = v9;
  if ( v9 < 0 )
  {
    v42 = v9;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create searcher");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 555;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v5,
      (int)v35);
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v46 = 0;
    }
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    if ( !v49 )
      return (unsigned int)v5;
    v7 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
    goto LABEL_16;
  }
  if ( v46 )
    goto LABEL_174;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v44)(
          v44,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v46);
  v5 = v11;
  if ( v11 < 0 )
  {
    v42 = v11;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set client ID");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 560;
    goto LABEL_26;
  }
  v51 = 0;
  v38 = 0;
  LOWORD(v38) = 11;
  WORD4(v38) = -1;
  v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v44)(
          v44,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v51);
  v5 = v12;
  if ( v12 < 0 )
  {
    v42 = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query internal configuration");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v5,
      (int)v35);
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    v42 = v5;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to set default search properties");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 562;
    goto LABEL_26;
  }
  v39 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v51 + 32LL))(v51, 262145, &v38);
  if ( v13 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v13, "Unable to set interactive flag for search");
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  updated = ShowWindowsUpdateServerConfiguration(v36);
  if ( updated < 0 )
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      (unsigned int)updated,
      "Not able to show current windows update server configuration");
  DumpWindowsInsiderSettings();
  if ( bstrString )
    goto LABEL_174;
  v15 = CreateUUPSearchCriteria(0, 0, &bstrString);
  v5 = v15;
  if ( v15 < 0 )
  {
    v42 = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get search criteria.");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 592;
    goto LABEL_26;
  }
  if ( v43 )
  {
LABEL_174:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026E7A8LL);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v44 + 152LL))(v44, bstrString, &v43);
  v5 = v16;
  if ( v16 < 0 )
  {
    v42 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DLWD:WU search failed");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 594;
    goto LABEL_26;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v55);
  v5 = v17;
  if ( v17 < 0 )
  {
    v42 = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get download hresult");
      v47 = (BSTR)&v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v10 = 596;
    goto LABEL_26;
  }
  if ( v55 == 4 )
  {
    v5 = -2146498289;
    v50 = -2146498289;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Search failed with");
      v47 = (BSTR)&v50;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v6 = 602;
    goto LABEL_5;
  }
  if ( v55 == 5 )
  {
    v5 = -2147467260;
    v50 = -2147467260;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: WU cancelled the search operation");
      v47 = (BSTR)&v50;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v47);
    }
    v6 = 606;
    goto LABEL_5;
  }
  v5 = 0;
  if ( v55 != 3 )
  {
    if ( v55 == 2 )
    {
      v48 = 2;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_134;
      v29 = "DWLD: WU search succeeded with WU result code {}";
    }
    else
    {
      v48 = v55;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_134;
      v29 = "DWLD: WU search failed with WU result code {}";
    }
    LOBYTE(v18) = 1;
    v35 = &v48;
    LogAdapter::Logger::LogNumObjects<long>(*(_QWORD *)&LogAdapter::g_Logger, v18, 1, v29);
LABEL_134:
    if ( !v49 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 72LL))(v43, &v49);
      v22 = v30;
      if ( v30 >= 0 )
      {
        v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 80LL))(v49, &v54);
        v22 = v32;
        if ( v32 >= 0 )
        {
          if ( v54 == 1 )
          {
            v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v49 + 56LL))(v49, 0, a5);
            v34 = v33;
            if ( v33 >= 0 )
            {
              if ( v43 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                v43 = 0;
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v46 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                v46 = 0;
              }
              if ( v44 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                v44 = 0;
              }
              if ( v49 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x297,
                (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
                (const char *)(unsigned int)v33,
                (int)v35);
              if ( v43 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                v43 = 0;
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v46 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                v46 = 0;
              }
              if ( v44 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                v44 = 0;
              }
              if ( v49 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              return v34;
            }
          }
          if ( v5 >= 0 )
            v5 = v36[0] != 0 ? -2146498220 : -2146498224;
          v42 = v5;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "DLWD: Expecting search returns 1 update, actual:{}");
            *(_QWORD *)v37 = &v42;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v37);
          }
          if ( v5 >= 0 )
            goto LABEL_6;
          v6 = 660;
LABEL_5:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v6,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)(unsigned int)v5,
            (int)v35);
LABEL_6:
          if ( v43 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            v43 = 0;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v46 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
            v46 = 0;
          }
          if ( v44 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          if ( !v49 )
            return (unsigned int)v5;
          v7 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
LABEL_16:
          v7();
          return (unsigned int)v5;
        }
        v48 = v32;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update count");
          *(_QWORD *)v37 = &v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v37);
        }
        v31 = 653;
      }
      else
      {
        v48 = v30;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get search collection.");
          *(_QWORD *)v37 = &v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v37);
        }
        v31 = 648;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v22,
        (int)v35);
      goto LABEL_86;
    }
    goto LABEL_174;
  }
  LogAdapter::TraceInfo<>("DWLD: WU search succeeded with errors");
  v50 = 0;
  v53 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 80LL))(v43, &v53);
  if ( v19 >= 0 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 72LL))(v53, &v50);
    v22 = v20;
    if ( v20 < 0 )
    {
      v42 = v20;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Unable to get WU warnings count");
        v47 = (BSTR)&v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26C,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v22,
        (int)v35);
      goto LABEL_84;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v21) = 1;
      v35 = &v50;
      LogAdapter::Logger::LogNumObjects<long>(*(_QWORD *)&LogAdapter::g_Logger, v21, 1, "DWLD: WU search warnings: {}");
    }
  }
  else
  {
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v19, "DWLD: Unable to get WU warnings list");
  }
  v52 = 0;
  if ( v50 <= 0 )
  {
LABEL_113:
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    goto LABEL_134;
  }
  v23 = 0;
  while ( 1 )
  {
    v51 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 56LL))(v53, v23, &v51);
    if ( v22 < 0 )
    {
      v48 = v22;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning {}");
        *(_QWORD *)v37 = &v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v37);
      }
      v28 = 627;
      goto LABEL_125;
    }
    v42 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 64LL))(v51, &v42);
    if ( v22 < 0 )
    {
      v48 = v22;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Unable to get WU warning hr {}");
        *(_QWORD *)v37 = &v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v37);
      }
      v28 = 630;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v22,
        (int)v35);
      goto LABEL_126;
    }
    v47 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v51 + 56LL))(v51, &v47);
    if ( v22 < 0 )
      break;
    v27 = v47;
    v41 = &v42;
    v40 = v47;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<long,Windows::WCP::Rtl::FormatHResultWrapper<long>,wchar_t *>(
        LogAdapter::g_Logger,
        v24,
        v25,
        v26,
        (__int64)&v52,
        (__int64)&v41,
        (__int64)&v40);
      v27 = v47;
    }
    if ( v5 >= 0 )
      v5 = v42;
    if ( v27 )
    {
      SysFreeString(v27);
      v47 = 0;
    }
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v23 = (unsigned int)(v52 + 1);
    v52 = v23;
    if ( (int)v23 >= v50 )
      goto LABEL_113;
  }
  v48 = v22;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<long>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "DWLD: Unable to get WU warning message {}");
    *(_QWORD *)v37 = &v48;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)v37);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x279,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)(unsigned int)v22,
    (int)v35);
  if ( v47 )
  {
    SysFreeString(v47);
    v47 = 0;
  }
LABEL_126:
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
LABEL_84:
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
LABEL_86:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)v22;
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
