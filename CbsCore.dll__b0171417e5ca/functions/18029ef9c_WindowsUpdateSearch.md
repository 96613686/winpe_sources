# WindowsUpdateSearch

- ea: `0x18029ef9c`
- end: `0x18029fd97`
- name: `WindowsUpdateSearch`
- size: `3579`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18029fda0`

## callees

- `0x180010cc0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800fa3ec`
- `0x1801255f4`
- `0x18029b1b0`
- `0x18029bc90`
- `0x18029c6cc`
- `0x18029d570`
- `0x18029d6cc`
- `0x18029ef9c`
- `0x1802d5010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18029f35b`
- `OLEAUT32!__imp_SysAllocString` at `0x18029f35b`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f089`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f8b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f980`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fc45`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fd12`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f089`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f8b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f980`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fc45`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fd12`
- `OLEAUT32!__imp_VariantInit` at `0x18029f343`
- `OLEAUT32!__imp_VariantInit` at `0x18029f343`
- `OLEAUT32!__imp_VariantClear` at `0x18029f39c`
- `OLEAUT32!__imp_VariantClear` at `0x18029f45f`
- `OLEAUT32!__imp_VariantClear` at `0x18029f480`
- `OLEAUT32!__imp_VariantClear` at `0x18029f39c`
- `OLEAUT32!__imp_VariantClear` at `0x18029f45f`
- `OLEAUT32!__imp_VariantClear` at `0x18029f480`

## string_xrefs

- `0x18029f10a`: `No update result specified`
- `0x18029f058`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f1bd`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f374`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f43c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f781`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f95f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fa4d`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fc0f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fcc3`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f17a`: `Failed to create searcher`
- `0x18029f01a`: `No update session specified`
- `0x18029f49b`: `Not able to show current windows update server configuration`
- `0x18029fbc8`: `DLWD: Expecting search returns 1 update, actual:{}`
- `0x18029fb48`: `Failed to get update count`

## pseudocode

```c
__int64 __fastcall WindowsUpdateSearch(char a1, __int64 a2, const OLECHAR *a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  void (*v10)(void); // rax
  int v12; // eax
  __int64 v13; // rdx
  void (*v14)(void); // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  unsigned int updated; // eax
  _QWORD *v22; // rax
  int UUPSearchCriteria; // eax
  int v24; // eax
  int v25; // eax
  int v26; // r14d
  __int64 v27; // rbx
  int v28; // eax
  int v29; // edx
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64); // rbx
  __int64 v33; // rax
  int v34; // edx
  int v35; // r8d
  int v36; // r9d
  OLECHAR *v37; // rcx
  __int64 v38; // rdx
  const char *v39; // rdx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64); // rbx
  __int64 v42; // rax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // [rsp+20h] [rbp-E0h]
  char v47[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v48[2]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v49; // [rsp+50h] [rbp-B0h] BYREF
  int *v50; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v51; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v56; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v57; // [rsp+A8h] [rbp-58h] BYREF
  int v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h] BYREF
  int v60; // [rsp+C0h] [rbp-40h] BYREF
  int v61; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h] BYREF
  int v64; // [rsp+D8h] [rbp-28h] BYREF
  int v65; // [rsp+DCh] [rbp-24h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v59 = 0;
  v54 = 0;
  v56 = 0;
  bstrString = 0;
  v53 = 0;
  v65 = 0;
  v64 = 0;
  v47[0] = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v52 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update session specified");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v9 = 552;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      v46);
LABEL_6:
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
      v56 = 0;
    }
    if ( v54 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v54)[2])(v54);
      v54 = 0;
    }
    if ( !v59 )
      return v8;
    v10 = *(void (**)(void))(*(_QWORD *)v59 + 16LL);
LABEL_16:
    v10();
    return v8;
  }
  if ( !a5 )
  {
    v8 = -2147467261;
    v52 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update result specified");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v9 = 553;
    goto LABEL_5;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a2 + 96LL))(
          a2,
          &v54);
  v8 = v12;
  if ( v12 < 0 )
  {
    v52 = v12;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create searcher");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 555;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      v46);
    goto LABEL_27;
  }
  v15 = v54;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v56);
  v17 = (**v15)(v15, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, InitPointer);
  v8 = v17;
  if ( v17 < 0 )
  {
    v52 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set client ID");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 560;
    goto LABEL_26;
  }
  v18 = SetDefaultSearchProperties(v54);
  v8 = v18;
  if ( v18 < 0 )
  {
    v52 = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD:Failed to set default search properties");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 562;
    goto LABEL_26;
  }
  if ( a3 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    if ( !pvarg.llVal )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)0x8007000ELL,
        v46);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_6;
    }
    v19 = *v56;
    v51 = pvarg;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v19 + 32))(v56, 1, &v51);
    v8 = v20;
    if ( v20 < 0 )
    {
      v52 = v20;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set correlation vector");
        v57 = (BSTR)&v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v57);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v8,
        v46);
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
  updated = ShowWindowsUpdateServerConfiguration(v47);
  LogAdapter::TraceAtLevelIfFailed<long,>(3, updated, "Not able to show current windows update server configuration");
  DumpWindowsInsiderSettings();
  v22 = (_QWORD *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&bstrString);
  UUPSearchCriteria = CreateUUPSearchCriteria(a1, a4, v22);
  v8 = UUPSearchCriteria;
  if ( UUPSearchCriteria < 0 )
  {
    v52 = UUPSearchCriteria;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get search criteria.");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 592;
    goto LABEL_26;
  }
  if ( v53 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18029FD96LL);
  }
  v24 = (*v54)[19](v54, (GUID *)bstrString, (__int64)&v53);
  v8 = v24;
  if ( v24 < 0 )
  {
    v52 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DLWD:WU search failed");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 594;
    goto LABEL_26;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v65);
  v8 = v25;
  if ( v25 < 0 )
  {
    v52 = v25;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get download hresult");
      v57 = (BSTR)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v13 = 596;
    goto LABEL_26;
  }
  if ( v65 == 4 )
  {
    v8 = -2146498289;
    v60 = -2146498289;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Search failed with");
      v57 = (BSTR)&v60;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v9 = 602;
    goto LABEL_5;
  }
  if ( v65 == 5 )
  {
    v8 = -2147467260;
    v60 = -2147467260;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: WU cancelled the search operation");
      v57 = (BSTR)&v60;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v57);
    }
    v9 = 606;
    goto LABEL_5;
  }
  v26 = 0;
  if ( v65 == 3 )
  {
    LogAdapter::TraceAtLevel<>(1, "DWLD: WU search succeeded with errors");
    v60 = 0;
    v62 = 0;
    v27 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 80LL))(v53, &v62);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v27, "DWLD: Unable to get WU warnings list");
    if ( (int)v27 >= 0 )
    {
      v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 72LL))(v62, &v60);
      v8 = v28;
      if ( v28 < 0 )
      {
        v52 = v28;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Unable to get WU warnings count");
          v57 = (BSTR)&v52;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v57);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v8,
          v46);
        goto LABEL_84;
      }
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v29) = 1;
        LogAdapter::Logger::LogNumObjects<long>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          1,
          (unsigned int)"DWLD: WU search warnings: {}",
          (__int64)&v60);
      }
    }
    v61 = 0;
    if ( v60 > 0 )
    {
      v30 = 0;
      while ( 1 )
      {
        v63 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 56LL))(v62, v30, &v63);
        if ( (v8 & 0x80000000) != 0 )
          break;
        v52 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v63 + 64LL))(v63, &v52);
        if ( (v8 & 0x80000000) != 0 )
        {
          v58 = v8;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"DWLD: Unable to get WU warning hr {}",
              (__int64)&v61);
            *(_QWORD *)v48 = &v58;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v48);
          }
          v38 = 630;
LABEL_114:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)v8,
            v46);
          goto LABEL_115;
        }
        v31 = v63;
        v57 = 0;
        v32 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 56LL);
        v33 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v57);
        v8 = v32(v31, v33);
        if ( (v8 & 0x80000000) != 0 )
        {
          v58 = v8;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"DWLD: Unable to get WU warning message {}",
              (__int64)&v61);
            *(_QWORD *)v48 = &v58;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v48);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)v8,
            v46);
          if ( v57 )
          {
            SysFreeString(v57);
            v57 = 0;
          }
LABEL_115:
          if ( v63 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
            v63 = 0;
          }
LABEL_84:
          if ( v62 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
            v62 = 0;
          }
LABEL_27:
          if ( v53 )
          {
            v14 = *(void (**)(void))(*(_QWORD *)v53 + 16LL);
            goto LABEL_29;
          }
          goto LABEL_30;
        }
        v37 = v57;
        v50 = &v52;
        v49 = v57;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<long,Windows::WCP::Rtl::FormatHResultWrapper<long>,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            v35,
            v36,
            (__int64)&v61,
            (__int64)&v50,
            (__int64)&v49);
          v37 = v57;
        }
        if ( v26 >= 0 )
          v26 = v52;
        if ( v37 )
        {
          SysFreeString(v37);
          v57 = 0;
        }
        if ( v63 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        v30 = (unsigned int)(v61 + 1);
        v61 = v30;
        if ( (int)v30 >= v60 )
          goto LABEL_102;
      }
      v58 = v8;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"DWLD: Unable to get WU warning {}",
          (__int64)&v61);
        *(_QWORD *)v48 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v48);
      }
      v38 = 627;
      goto LABEL_114;
    }
LABEL_102:
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  }
  else
  {
    if ( v65 == 2 )
    {
      v58 = 2;
      v39 = "DWLD: WU search succeeded with WU result code {}";
    }
    else
    {
      v58 = v65;
      v39 = "DWLD: WU search failed with WU result code {}";
    }
    LogAdapter::TraceAtLevel<int>(1, v39, &v58);
  }
  v40 = v53;
  v41 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 72LL);
  v42 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v59);
  v43 = v41(v40, v42);
  v8 = v43;
  if ( v43 < 0 )
  {
    v58 = v43;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get search collection.");
      *(_QWORD *)v48 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v48);
    }
    v13 = 648;
    goto LABEL_26;
  }
  v44 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v59 + 80LL))(v59, &v64);
  v8 = v44;
  if ( v44 < 0 )
  {
    v58 = v44;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update count");
      *(_QWORD *)v48 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v48);
    }
    v13 = 653;
    goto LABEL_26;
  }
  if ( v64 == 1 )
  {
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v59 + 56LL))(v59, 0, a5);
    v8 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v45,
        v46);
      if ( v53 )
      {
        v14 = *(void (**)(void))(*(_QWORD *)v53 + 16LL);
LABEL_29:
        v14();
        v53 = 0;
      }
LABEL_30:
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v56 )
      {
        (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
        v56 = 0;
      }
      if ( v54 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v54)[2])(v54);
        v54 = 0;
      }
      if ( !v59 )
        return v8;
      v10 = *(void (**)(void))(*(_QWORD *)v59 + 16LL);
      goto LABEL_16;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
      v56 = 0;
    }
    if ( v54 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v54)[2])(v54);
      v54 = 0;
    }
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    return 0;
  }
  else
  {
    if ( v26 >= 0 )
      v26 = v47[0] != 0 ? -2146498220 : -2146498224;
    v52 = v26;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<long>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"DLWD: Expecting search returns 1 update, actual:{}",
        (__int64)&v64);
      *(_QWORD *)v48 = &v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v48);
    }
    if ( v26 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x294,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v26,
        v46);
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
      v56 = 0;
    }
    if ( v54 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v54)[2])(v54);
      v54 = 0;
    }
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x18029ef9c  push    rbp
0x18029ef9e  push    rbx
0x18029ef9f  push    rsi
0x18029efa0  push    rdi
0x18029efa1  push    r12
0x18029efa3  push    r13
0x18029efa5  push    r14
0x18029efa7  push    r15
0x18029efa9  lea     rbp, [rsp-8]
0x18029efae  sub     rsp, 108h
0x18029efb5  mov     rax, cs:__security_cookie
0x18029efbc  xor     rax, rsp
0x18029efbf  mov     [rbp+40h+var_48], rax
0x18029efc3  mov     r12, [rbp+40h+arg_20]
0x18029efc7  xor     r13d, r13d
0x18029efca  mov     [rbp+40h+var_88], r13
0x18029efce  mov     rdi, r8
0x18029efd1  mov     [rbp+40h+var_B0], r13
0x18029efd5  mov     r15, r9
0x18029efd8  mov     [rbp+40h+var_A0], r13
0x18029efdc  mov     r8, rdx
0x18029efdf  mov     [rbp+40h+bstrString], r13
0x18029efe3  mov     r14d, ecx
0x18029efe6  mov     [rbp+40h+var_B8], r13
0x18029efea  mov     [rbp+40h+var_64], r13d
0x18029efee  mov     [rbp+40h+var_68], r13d
0x18029eff2  mov     [rsp+140h+var_100], r13b
0x18029eff7  test    rdx, rdx
0x18029effa  jnz     loc_18029F0E7
0x18029f000  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f007  mov     ebx, 80070057h
0x18029f00c  mov     [rbp+40h+var_C0], ebx
0x18029f00f  test    rcx, rcx
0x18029f012  jz      short loc_18029F04F
0x18029f014  lea     esi, [rdx+3]
0x18029f017  mov     r8d, esi
0x18029f01a  lea     r9, aNoUpdateSessio; "No update session specified"
0x18029f021  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f026  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f02d  lea     rax, [rbp+40h+var_C0]
0x18029f031  mov     [rbp+40h+var_98], rax
0x18029f035  lea     r9, asc_1802EE7AC; ": {}"
0x18029f03c  lea     rax, [rbp+40h+var_98]
0x18029f040  mov     r8d, esi
0x18029f043  mov     dl, 1
0x18029f045  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f04a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f04f  mov     edx, 228h; void *
0x18029f054  mov     rcx, [rbp+48h]; this
0x18029f058  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f05f  mov     r9d, ebx; char *
0x18029f062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f067  mov     rcx, [rbp+40h+var_B8]
0x18029f06b  test    rcx, rcx
0x18029f06e  jz      short loc_18029F080
0x18029f070  mov     rax, [rcx]
0x18029f073  mov     rax, [rax+10h]
0x18029f077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f07c  mov     [rbp+40h+var_B8], r13
0x18029f080  mov     rcx, [rbp+40h+bstrString]; bstrString
0x18029f084  test    rcx, rcx
0x18029f087  jz      short loc_18029F099
0x18029f089  call    cs:__imp_SysFreeString
0x18029f090  nop     dword ptr [rax+rax+00h]
0x18029f095  mov     [rbp+40h+bstrString], r13
0x18029f099  mov     rcx, [rbp+40h+var_A0]
0x18029f09d  test    rcx, rcx
0x18029f0a0  jz      short loc_18029F0B2
0x18029f0a2  mov     rax, [rcx]
0x18029f0a5  mov     rax, [rax+10h]
0x18029f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0ae  mov     [rbp+40h+var_A0], r13
0x18029f0b2  mov     rcx, [rbp+40h+var_B0]
0x18029f0b6  test    rcx, rcx
0x18029f0b9  jz      short loc_18029F0CB
0x18029f0bb  mov     rax, [rcx]
0x18029f0be  mov     rax, [rax+10h]
0x18029f0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0c7  mov     [rbp+40h+var_B0], r13
0x18029f0cb  mov     rcx, [rbp+40h+var_88]
0x18029f0cf  test    rcx, rcx
0x18029f0d2  jz      short loc_18029F0E0
0x18029f0d4  mov     rdx, [rcx]
0x18029f0d7  mov     rax, [rdx+10h]
0x18029f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0e0  mov     eax, ebx
0x18029f0e2  jmp     loc_18029FD6B
0x18029f0e7  test    r12, r12
0x18029f0ea  jnz     short loc_18029F149
0x18029f0ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f0f3  mov     ebx, 80004003h
0x18029f0f8  mov     [rbp+40h+var_C0], ebx
0x18029f0fb  test    rcx, rcx
0x18029f0fe  jz      short loc_18029F13F
0x18029f100  lea     esi, [r12+3]
0x18029f105  xor     edx, edx
0x18029f107  mov     r8d, esi
0x18029f10a  lea     r9, aNoUpdateResult; "No update result specified"
0x18029f111  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f116  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f11d  lea     rax, [rbp+40h+var_C0]
0x18029f121  mov     [rbp+40h+var_98], rax
0x18029f125  lea     r9, asc_1802EE7AC; ": {}"
0x18029f12c  lea     rax, [rbp+40h+var_98]
0x18029f130  mov     r8d, esi
0x18029f133  mov     dl, 1
0x18029f135  mov     qword ptr [rsp+140h+var_120], rax
0x18029f13a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f13f  mov     edx, 229h
0x18029f144  jmp     loc_18029F054
0x18029f149  mov     rax, [rdx]
0x18029f14c  mov     rcx, r8
0x18029f14f  lea     rdx, [rbp+40h+var_B0]
0x18029f153  mov     rax, [rax+60h]
0x18029f157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f15c  mov     ebx, eax
0x18029f15e  test    eax, eax
0x18029f160  jns     loc_18029F249
0x18029f166  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f16d  mov     [rbp+40h+var_C0], eax
0x18029f170  test    rcx, rcx
0x18029f173  jz      short loc_18029F1B4
0x18029f175  mov     esi, 3
0x18029f17a  lea     r9, aFailedToCreate_83; "Failed to create searcher"
0x18029f181  mov     r8d, esi
0x18029f184  xor     edx, edx
0x18029f186  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f18b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f192  lea     rax, [rbp+40h+var_C0]
0x18029f196  mov     [rbp+40h+var_98], rax
0x18029f19a  lea     r9, asc_1802EE7AC; ": {}"
0x18029f1a1  lea     rax, [rbp+40h+var_98]
0x18029f1a5  mov     r8d, esi
0x18029f1a8  mov     dl, 1
0x18029f1aa  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f1af  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f1b4  mov     edx, 22Bh; void *
0x18029f1b9  mov     rcx, [rbp+48h]; this
0x18029f1bd  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f1c4  mov     r9d, ebx; char *
0x18029f1c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f1cc  mov     rcx, [rbp+40h+var_B8]
0x18029f1d0  test    rcx, rcx
0x18029f1d3  jz      short loc_18029F1E5
0x18029f1d5  mov     rax, [rcx]
0x18029f1d8  mov     rax, [rax+10h]
0x18029f1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f1e1  mov     [rbp+40h+var_B8], r13
0x18029f1e5  mov     rcx, [rbp+40h+bstrString]; bstrString
0x18029f1e9  test    rcx, rcx
0x18029f1ec  jz      short loc_18029F1FE
0x18029f1ee  call    cs:__imp_SysFreeString
0x18029f1f5  nop     dword ptr [rax+rax+00h]
0x18029f1fa  mov     [rbp+40h+bstrString], r13
0x18029f1fe  mov     rcx, [rbp+40h+var_A0]
0x18029f202  test    rcx, rcx
0x18029f205  jz      short loc_18029F217
0x18029f207  mov     rax, [rcx]
0x18029f20a  mov     rax, [rax+10h]
0x18029f20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f213  mov     [rbp+40h+var_A0], r13
0x18029f217  mov     rcx, [rbp+40h+var_B0]
0x18029f21b  test    rcx, rcx
0x18029f21e  jz      short loc_18029F230
0x18029f220  mov     rax, [rcx]
0x18029f223  mov     rax, [rax+10h]
0x18029f227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f22c  mov     [rbp+40h+var_B0], r13
0x18029f230  mov     rcx, [rbp+40h+var_88]
0x18029f234  test    rcx, rcx
0x18029f237  jz      loc_18029F0E0
0x18029f23d  mov     rax, [rcx]
0x18029f240  mov     rax, [rax+10h]
0x18029f244  jmp     loc_18029F0DB
0x18029f249  mov     rbx, [rbp+40h+var_B0]
0x18029f24d  lea     rcx, [rbp+40h+var_A0]
0x18029f251  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029f256  mov     rcx, [rbx]
0x18029f259  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18029f260  mov     r8, rax
0x18029f263  mov     r9, [rcx]
0x18029f266  mov     rcx, rbx
0x18029f269  mov     rax, r9
0x18029f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f271  mov     ebx, eax
0x18029f273  test    eax, eax
0x18029f275  jns     short loc_18029F2CF
0x18029f277  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f27e  mov     [rbp+40h+var_C0], eax
0x18029f281  test    rcx, rcx
0x18029f284  jz      short loc_18029F2C5
0x18029f286  mov     esi, 3
0x18029f28b  lea     r9, aFailedToSetCli; "Failed to set client ID"
0x18029f292  mov     r8d, esi
0x18029f295  xor     edx, edx
0x18029f297  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f29c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f2a3  lea     rax, [rbp+40h+var_C0]
0x18029f2a7  mov     [rbp+40h+var_98], rax
0x18029f2ab  lea     r9, asc_1802EE7AC; ": {}"
0x18029f2b2  lea     rax, [rbp+40h+var_98]
0x18029f2b6  mov     r8d, esi
0x18029f2b9  mov     dl, 1
0x18029f2bb  mov     qword ptr [rsp+140h+var_120], rax
0x18029f2c0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f2c5  mov     edx, 230h
0x18029f2ca  jmp     loc_18029F1B9
0x18029f2cf  mov     rcx, [rbp+40h+var_B0]
0x18029f2d3  call    SetDefaultSearchProperties
0x18029f2d8  mov     ebx, eax
0x18029f2da  test    eax, eax
0x18029f2dc  jns     short loc_18029F336
0x18029f2de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f2e5  mov     [rbp+40h+var_C0], eax
0x18029f2e8  test    rcx, rcx
0x18029f2eb  jz      short loc_18029F32C
0x18029f2ed  mov     esi, 3
0x18029f2f2  lea     r9, aDwldFailedToSe_1; "DWLD:Failed to set default search prope"...
0x18029f2f9  mov     r8d, esi
0x18029f2fc  xor     edx, edx
0x18029f2fe  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f303  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f30a  lea     rax, [rbp+40h+var_C0]
0x18029f30e  mov     [rbp+40h+var_98], rax
0x18029f312  lea     r9, asc_1802EE7AC; ": {}"
0x18029f319  lea     rax, [rbp+40h+var_98]
0x18029f31d  mov     r8d, esi
0x18029f320  mov     dl, 1
0x18029f322  mov     qword ptr [rsp+140h+var_120], rax
0x18029f327  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f32c  mov     edx, 232h
0x18029f331  jmp     loc_18029F1B9
0x18029f336  test    rdi, rdi
0x18029f339  jz      loc_18029F48C
0x18029f33f  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f343  call    cs:__imp_VariantInit
0x18029f34a  nop     dword ptr [rax+rax+00h]
0x18029f34f  mov     eax, 8
0x18029f354  mov     rcx, rdi; psz
0x18029f357  mov     word ptr [rbp+40h+pvarg], ax
0x18029f35b  call    cs:__imp_SysAllocString
0x18029f362  nop     dword ptr [rax+rax+00h]
0x18029f367  mov     qword ptr [rbp+40h+pvarg+8], rax
0x18029f36b  test    rax, rax
0x18029f36e  jnz     short loc_18029F3B2
0x18029f370  mov     rcx, [rbp+48h]; this
0x18029f374  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f37b  mov     ebx, 8007000Eh
0x18029f380  mov     edx, 239h; void *
0x18029f385  mov     r9d, ebx; char *
0x18029f388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f38d  cmp     word ptr [rbp+40h+pvarg], r13w
0x18029f392  jz      loc_18029F067
0x18029f398  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f39c  call    cs:__imp_VariantClear
0x18029f3a3  nop     dword ptr [rax+rax+00h]
0x18029f3a8  mov     word ptr [rbp+40h+pvarg], r13w
0x18029f3ad  jmp     loc_18029F067
0x18029f3b2  mov     rcx, [rbp+40h+var_A0]
0x18029f3b6  lea     r8, [rsp+140h+var_E0]
0x18029f3bb  movups  xmm0, xmmword ptr [rbp+40h+pvarg]
0x18029f3bf  mov     edx, 1
0x18029f3c4  movsd   xmm1, qword ptr [rbp+40h+pvarg+10h]
0x18029f3c9  mov     rax, [rcx]
0x18029f3cc  movaps  [rsp+140h+var_E0], xmm0
0x18029f3d1  movsd   [rsp+140h+var_D0], xmm1
0x18029f3d7  mov     rax, [rax+20h]
0x18029f3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f3e0  mov     ebx, eax
0x18029f3e2  test    eax, eax
0x18029f3e4  jns     loc_18029F475
0x18029f3ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f3f1  mov     [rbp+40h+var_C0], eax
0x18029f3f4  test    rcx, rcx
0x18029f3f7  jz      short loc_18029F438
0x18029f3f9  mov     esi, 3
0x18029f3fe  lea     r9, aFailedToSetCor; "Failed to set correlation vector"
0x18029f405  mov     r8d, esi
0x18029f408  xor     edx, edx
0x18029f40a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f40f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f416  lea     rax, [rbp+40h+var_C0]
0x18029f41a  mov     [rbp+40h+var_98], rax
0x18029f41e  lea     r9, asc_1802EE7AC; ": {}"
0x18029f425  lea     rax, [rbp+40h+var_98]
0x18029f429  mov     r8d, esi
0x18029f42c  mov     dl, 1
0x18029f42e  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f433  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f438  mov     rcx, [rbp+48h]; this
0x18029f43c  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f443  mov     r9d, ebx; char *
0x18029f446  mov     edx, 23Dh; void *
0x18029f44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f450  cmp     word ptr [rbp+40h+pvarg], r13w
0x18029f455  jz      loc_18029F1CC
0x18029f45b  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f45f  call    cs:__imp_VariantClear
0x18029f466  nop     dword ptr [rax+rax+00h]
0x18029f46b  mov     word ptr [rbp+40h+pvarg], r13w
  ... truncated ...
```
