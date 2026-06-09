# WindowsUpdateDownloadFromUUP

- ea: `0x1801b164c`
- end: `0x1801b30f5`
- name: `WindowsUpdateDownloadFromUUP`
- size: `6825`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180199fa0`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x18001ba4c`
- `0x1800364c0`
- `0x180036824`
- `0x18004797c`
- `0x180047d7c`
- `0x180065a7c`
- `0x1801acb08`
- `0x1801acb7c`
- `0x1801aec28`
- `0x1801af4b4`
- `0x1801b066c`
- `0x1801b164c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b1ac4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b1ac4`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b1bf7`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b2272`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b262e`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b2669`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b1bf7`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b2272`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b262e`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b2669`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1e23`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b26d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2833`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2842`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2b0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2c47`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2d89`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b302c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b303b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b1e23`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b26d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2833`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2842`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2b0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2c47`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b2d89`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b302c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b303b`
- `OLEAUT32!__imp_VariantInit` at `0x1801b225a`
- `OLEAUT32!__imp_VariantInit` at `0x1801b225a`
- `OLEAUT32!__imp_VariantClear` at `0x1801b22b1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b240e`
- `OLEAUT32!__imp_VariantClear` at `0x1801b24bb`
- `OLEAUT32!__imp_VariantClear` at `0x1801b22b1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b240e`
- `OLEAUT32!__imp_VariantClear` at `0x1801b24bb`

## string_xrefs

- `0x1801b172a`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b184b`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b19c0`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1b31`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1c13`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1d54`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1f2b`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b228f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b23f0`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b264a`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b268a`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b27ef`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b2bfe`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b2d71`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b2f35`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b2fe0`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801b1987`: `Failed to impersonate user`
- `0x1801b23ad`: `Failed to query internal configuration`
- `0x1801b2092`: `Failed to create downloader`
- `0x1801b2125`: `Failed to query IUpdateDownloader2`
- `0x1801b1af3`: `Failed to create UpdateSession object.`
- `0x1801b1eed`: `DWLD:Failed to do Windows update search`
- `0x1801b25e6`: `DWLD:Failed to query IUpdate10`
- `0x1801b2908`: `DWLD:Failed to get bundled updates count`
- `0x1801b27ac`: `DWLD:Failed to get bundled updates`
- `0x1801b2209`: `Failed to set IsForced on IUpdateDownloader`
- `0x1801b2acd`: `DWLD: Moved WU content to {} for update with ID {}`
- `0x1801b2dd0`: `Failed to get update ID`
- `0x1801b2d0f`: `DWLD: Failed to move WU content to {} for update with ID {}`
- `0x1801b2af4`: `DWLD: No sandbox found for update with ID: {}, continuing`
- `0x1801b299d`: `DWLD: Failed to move WU content to {}`
- `0x1801b2e2b`: `Failed to get update identity`
- `0x1801b2e92`: `DWLD: Failed to get IUpdate10 ptr for child {}`
- `0x1801b2fa3`: `DWLD: No WU content available to move to {}`

## pseudocode

```c
__int64 __fastcall WindowsUpdateDownloadFromUUP(
        unsigned int a1,
        char a2,
        void *a3,
        OLECHAR *a4,
        OLECHAR *a5,
        OLECHAR *psz,
        OLECHAR *a7,
        __int64 a8,
        __int64 a9)
{
  char v9; // r14
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  void (*v14)(void); // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  BSTR v23; // rax
  OLECHAR *v24; // rdi
  void (*v25)(void); // rax
  int v26; // eax
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  int updated; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rdx
  int v41; // eax
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rdx
  int v49; // eax
  __int64 v50; // rdx
  OLECHAR *v51; // rdi
  int started; // eax
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdx
  OLECHAR *v56; // rbx
  OLECHAR *v57; // rdi
  int v58; // eax
  int v59; // r15d
  __int64 v60; // rdx
  __int64 v61; // rdx
  int v62; // eax
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // rdx
  char v66; // r12
  __int64 v67; // rdx
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rdx
  OLECHAR **ppv; // [rsp+20h] [rbp-E0h]
  OLECHAR **ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  int v82[2]; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v83; // [rsp+40h] [rbp-C0h] BYREF
  int v84[2]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v85[2]; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v86; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR *v87; // [rsp+80h] [rbp-80h] BYREF
  int v88; // [rsp+88h] [rbp-78h] BYREF
  __int64 v89; // [rsp+90h] [rbp-70h] BYREF
  __int64 v90; // [rsp+98h] [rbp-68h] BYREF
  int v91[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v92; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v93; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v94; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR *v95; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v96; // [rsp+C8h] [rbp-38h] BYREF
  int v97; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v98; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v99; // [rsp+E0h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+E8h] [rbp-18h] BYREF
  int v101; // [rsp+F0h] [rbp-10h] BYREF
  int v102; // [rsp+F4h] [rbp-Ch] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-8h] BYREF
  BSTR v104; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v9 = 0;
  v95 = a4;
  v87 = a5;
  v96 = 0;
  *(_QWORD *)v91 = 0;
  v89 = 0;
  v94 = 0;
  v93 = 0;
  v92 = 0;
  v90 = 0;
  v102 = 0;
  if ( !a4 )
  {
    v11 = -2147467261;
    v88 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Invalid sessionData");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v12) = 1;
      ppv = &v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      (int)ppv);
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    v13 = *(_QWORD *)v91;
    if ( !*(_QWORD *)v91 )
      goto LABEL_16;
    goto LABEL_15;
  }
  if ( !a5 )
  {
    v11 = -2147467261;
    v88 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Invalid pszDownloadedSandbox");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v15) = 1;
      ppv = &v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      (int)ppv);
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    v16 = *(_QWORD *)v91;
    if ( !*(_QWORD *)v91 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( a3 )
  {
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( *(_QWORD *)(v18 + 312) )
    {
      if ( *(void **)(v18 + 312) != a3 )
      {
        v11 = -2147483635;
        goto LABEL_41;
      }
    }
    else
    {
      v11 = ImpersonateToken(a3);
      if ( (v11 & 0x80000000) != 0 )
      {
LABEL_41:
        v88 = v11;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to impersonate user");
          v95 = (OLECHAR *)&v88;
          LOBYTE(v19) = 1;
          ppv = &v95;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v19,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x116,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v11,
          (int)ppv);
        if ( v90 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
          v90 = 0;
        }
        if ( v92 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          v92 = 0;
        }
        if ( v93 )
        {
          (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
          v93 = 0;
        }
        if ( v94 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          v94 = 0;
        }
        if ( v89 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
          v89 = 0;
        }
        v16 = *(_QWORD *)v91;
        if ( !*(_QWORD *)v91 )
          goto LABEL_33;
LABEL_32:
        (*(void (__fastcall **)(__int64))(**(_QWORD **)v91 + 16LL))(v16);
        *(_QWORD *)v91 = 0;
LABEL_33:
        if ( !v96 )
          return v11;
        v14 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
        goto LABEL_35;
      }
      v9 = 1;
    }
  }
  if ( a8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a8 + 24LL))(a8);
  v20 = CoCreateInstance(
          &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
          0,
          1u,
          &GUID_816858a4_260d_4260_933a_2585f1abc76b,
          &v96);
  v11 = v20;
  if ( v20 < 0 )
  {
    v88 = v20;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to create UpdateSession object.");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v21) = 1;
      ppva = &v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {}");
    }
    v22 = 293;
    goto LABEL_63;
  }
  if ( psz )
  {
    v23 = SysAllocString(psz);
    v24 = v23;
    if ( !v23 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)0x8007000ELL,
        (int)ppva);
      if ( v9 )
        RevertImpersonate();
LABEL_81:
      if ( !v96 )
        return 2147942414LL;
      v25 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
LABEL_212:
      v25();
      return 2147942414LL;
    }
    v26 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v96 + 64LL))(v96, v23);
    v11 = v26;
    if ( v26 < 0 )
    {
      v88 = v26;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v27) = 1;
        ppva = &v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v27,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v11,
        (int)ppva);
      SysFreeString(v24);
      if ( v90 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        v90 = 0;
      }
      if ( v92 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        v92 = 0;
      }
      if ( v9 )
        RevertImpersonate();
      if ( v93 )
      {
        (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
        v93 = 0;
      }
      if ( v94 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        v94 = 0;
      }
      if ( v89 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
      }
      v13 = *(_QWORD *)v91;
      if ( !*(_QWORD *)v91 )
        goto LABEL_16;
LABEL_15:
      (*(void (__fastcall **)(__int64))(**(_QWORD **)v91 + 16LL))(v13);
      *(_QWORD *)v91 = 0;
LABEL_16:
      if ( !v96 )
        return v11;
      v14 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
LABEL_35:
      v14();
      return v11;
    }
    SysFreeString(v24);
  }
  if ( a8 )
  {
    v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a8 + 32LL))(a8, 0);
    v11 = v28;
    if ( v28 < 0 )
    {
      v88 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to send progress");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v29) = 1;
        ppva = &v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v29,
          3,
          ": {}");
      }
      v22 = 309;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v11,
        (int)ppva);
      if ( v90 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        v90 = 0;
      }
      if ( v92 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        v92 = 0;
      }
      if ( v9 )
        RevertImpersonate();
      if ( v93 )
      {
        (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
        v93 = 0;
      }
      if ( v94 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        v94 = 0;
      }
      if ( v89 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
      }
      v13 = *(_QWORD *)v91;
      if ( !*(_QWORD *)v91 )
        goto LABEL_16;
      goto LABEL_15;
    }
  }
  ppvb = (LPVOID *)v91;
  updated = WindowsUpdateSearch(a1, v96, a7, a9);
  v11 = updated;
  if ( updated < 0 )
  {
    v88 = updated;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to do Windows update search");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v31) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v31,
        3,
        ": {}");
    }
    v32 = 312;
LABEL_110:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v11,
      (int)ppvb);
LABEL_111:
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    if ( v9 )
      RevertImpersonate();
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *(_QWORD *)v91 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
      *(_QWORD *)v91 = 0;
    }
    goto LABEL_16;
  }
  if ( a8 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a8 + 32LL))(a8, 1);
    v11 = v33;
    if ( v33 < 0 )
    {
      v88 = v33;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to send progress");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v34) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v34,
          3,
          ": {}");
      }
      v32 = 316;
      goto LABEL_110;
    }
  }
  v35 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v96 + 104LL))(v96, &v89);
  v11 = v35;
  if ( v35 < 0 )
  {
    v88 = v35;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create downloader");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v36) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v36,
        3,
        ": {}");
    }
    v32 = 328;
    goto LABEL_110;
  }
  if ( a2 )
  {
    if ( v94 )
      goto LABEL_326;
    v37 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v89)(
            v89,
            &GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d,
            &v94);
    v11 = v37;
    if ( v37 < 0 )
    {
      v88 = v37;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to query IUpdateDownloader2");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v38) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v38,
          3,
          ": {}");
      }
      v32 = 332;
      goto LABEL_110;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 144LL))(v94, 0xFFFFFFFFLL);
    v11 = v39;
    if ( v39 < 0 )
    {
      v88 = v39;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to UseCurrentNetworkCostPolicy");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v40) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v40,
          3,
          ": {}");
      }
      v32 = 334;
      goto LABEL_110;
    }
  }
  if ( (a1 & 2) == 0 )
  {
    v41 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 80LL))(v89, 0xFFFFFFFFLL);
    v11 = v41;
    if ( v41 < 0 )
    {
      v88 = v41;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to set IsForced on IUpdateDownloader");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v42) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v42,
          3,
          ": {}");
      }
      v32 = 342;
      goto LABEL_110;
    }
  }
  if ( a7 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a7);
    if ( !pvarg.llVal )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)0x8007000ELL,
        (int)v91);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_153;
    }
    if ( v93 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801B30F4LL);
    }
    v43 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v89)(
            v89,
            &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
            &v93);
    v11 = v43;
    if ( v43 < 0 )
    {
      v88 = v43;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to query internal configuration");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v44) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v44,
          3,
          ": {}");
      }
      v45 = 352;
LABEL_172:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v11,
        (int)ppvb);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_111;
    }
    v46 = *v93;
    v86 = pvarg;
    v47 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v46 + 32))(v93, 1, &v86);
    v11 = v47;
    if ( v47 < 0 )
    {
      v88 = v47;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set correlation vector");
        v95 = (OLECHAR *)&v88;
        LOBYTE(v48) = 1;
        ppvb = (LPVOID *)&v95;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v48,
          3,
          ": {}");
      }
      v45 = 356;
      goto LABEL_172;
    }
    if ( pvarg.vt )
      VariantClear(&pvarg);
  }
  v49 = SetDefaultDownloadProperties(v89);
  v11 = v49;
  if ( v49 < 0 )
  {
    v88 = v49;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to set default download properties");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v50) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v50,
        3,
        ": {}");
    }
    v32 = 365;
    goto LABEL_110;
  }
  v51 = v95;
  LODWORD(ppvb) = 0;
  started = StartDownloadAndReportProgress(v89, v95, *(_QWORD *)v91, a8);
  v11 = started;
  if ( started < 0 )
  {
    v88 = started;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to download actual content");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v53) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v53,
        3,
        ": {}");
    }
    v32 = 368;
    goto LABEL_110;
  }
  if ( v92 )
    goto LABEL_326;
  v54 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v91)(
          *(_QWORD *)v91,
          &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
          &v92);
  v11 = v54;
  if ( v54 < 0 )
  {
    v88 = v54;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD:Failed to query IUpdate10");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v55) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v55,
        3,
        ": {}");
    }
    v32 = 373;
    goto LABEL_110;
  }
  v104 = SysAllocString(v87);
  v56 = v104;
  if ( !v104 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      0);
LABEL_153:
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    if ( v9 )
      RevertImpersonate();
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *(_QWORD *)v91 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
      *(_QWORD *)v91 = 0;
    }
    goto LABEL_81;
  }
  v83 = SysAllocString(v51);
  v57 = v83;
  if ( !v83 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      0);
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    SysFreeString(v56);
    if ( v9 )
      RevertImpersonate();
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *(_QWORD *)v91 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
      *(_QWORD *)v91 = 0;
    }
    if ( !v96 )
      return 2147942414LL;
    v25 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
    goto LABEL_212;
  }
  if ( v90 )
  {
LABEL_326:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  v58 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v91 + 72LL))(*(_QWORD *)v91, &v90);
  v59 = v58;
  if ( v58 < 0 )
  {
    v88 = v58;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD:Failed to get bundled updates");
      v95 = (OLECHAR *)&v88;
      LOBYTE(v60) = 1;
      ppvb = (LPVOID *)&v95;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v60,
        3,
        ": {}");
    }
    v61 = 381;
    goto LABEL_219;
  }
  v62 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v90 + 80LL))(v90, &v102);
  v59 = v62;
  if ( v62 < 0 )
  {
    v101 = v62;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD:Failed to get bundled updates count");
      v83 = (BSTR)&v101;
      LOBYTE(v63) = 1;
      ppvb = (LPVOID *)&v83;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v63,
        3,
        ": {}");
    }
    v61 = 383;
LABEL_219:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v61,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v59,
      (int)ppvb);
LABEL_220:
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    SysFreeString(v57);
    SysFreeString(v56);
    if ( v9 )
      RevertImpersonate();
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *(_QWORD *)v91 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
      *(_QWORD *)v91 = 0;
    }
    if ( v96 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
    return (unsigned int)v59;
  }
  if ( !v102 )
  {
    v64 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v92 + 64LL))(v92, v56, v83, 0);
    v59 = v64;
    if ( v64 >= 0 )
      goto LABEL_268;
    v101 = v64;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: Failed to move WU content to {}",
        &v87);
      v83 = (BSTR)&v101;
      LOBYTE(v65) = 1;
      ppvb = (LPVOID *)&v83;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v65,
        3,
        ": {}");
    }
    v61 = 391;
    goto LABEL_219;
  }
  v88 = 0;
  if ( v102 <= 0 )
  {
LABEL_306:
    LODWORD(v104) = -2145099760;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: No WU content available to move to {}",
        &v87);
      *(_QWORD *)v82 = &v104;
      LOBYTE(v77) = 1;
      ppvb = (LPVOID *)v82;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v77,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80246010LL,
      (int)ppvb);
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    SysFreeString(v57);
    SysFreeString(v56);
    if ( v9 )
      RevertImpersonate();
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    if ( v94 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v94 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *(_QWORD *)v91 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
      *(_QWORD *)v91 = 0;
    }
    if ( v96 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
    return 2149867536LL;
  }
  v66 = 0;
  v67 = 0;
  do
  {
    v99 = 0;
    v98 = 0;
    v59 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v90 + 56LL))(v90, v67, &v99);
    if ( v59 < 0 )
    {
      v97 = v59;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get child udpate at {}",
          &v88);
        *(_QWORD *)v82 = &v97;
        LOBYTE(v76) = 1;
        ppvb = (LPVOID *)v82;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v76,
          3,
          ": {}");
      }
      v75 = 401;
      goto LABEL_301;
    }
    if ( v98 )
      goto LABEL_325;
    v59 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v99)(
            v99,
            &GUID_31c362f2_bfd1_47c3_b216_f023e61f07b9,
            &v98);
    if ( v59 < 0 )
    {
      v97 = v59;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Failed to get IUpdate10 ptr for child {}",
          &v88);
        *(_QWORD *)v82 = &v97;
        LOBYTE(v74) = 1;
        ppvb = (LPVOID *)v82;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v74,
          3,
          ": {}");
      }
      v75 = 403;
LABEL_301:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v75,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v59,
        (int)ppvb);
LABEL_302:
      if ( v98 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        v98 = 0;
      }
      if ( v99 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        v99 = 0;
      }
      goto LABEL_220;
    }
    v95 = 0;
    bstrString = 0;
    v59 = (*(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v99 + 152LL))(v99, &v95);
    if ( v59 < 0 )
    {
      v97 = v59;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update identity");
        *(_QWORD *)v82 = &v97;
        LOBYTE(v73) = 1;
        ppvb = (LPVOID *)v82;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v73,
          3,
          ": {}");
      }
      v71 = 408;
      goto LABEL_285;
    }
    if ( bstrString )
    {
LABEL_325:
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    v59 = (*(__int64 (__fastcall **)(OLECHAR *, BSTR *))(*(_QWORD *)v95 + 64LL))(v95, &bstrString);
    if ( v59 < 0 )
    {
      v97 = v59;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get update ID");
        *(_QWORD *)v82 = &v97;
        LOBYTE(v72) = 1;
        ppvb = (LPVOID *)v82;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v72,
          3,
          ": {}");
      }
      v71 = 410;
LABEL_285:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v71,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v59,
        (int)ppvb);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v95 )
      {
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v95 + 16LL))(v95);
        v95 = 0;
      }
      goto LABEL_302;
    }
    v59 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, _QWORD))(*(_QWORD *)v98 + 64LL))(v98, v56, v83, 0);
    if ( v59 < 0 )
    {
      if ( v59 != -2145099760 )
      {
        v97 = v59;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          *(_QWORD *)v84 = bstrString;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "DWLD: Failed to move WU content to {} for update with ID {}",
            &v87,
            v84);
          *(_QWORD *)v82 = &v97;
          LOBYTE(v70) = 1;
          ppvb = (LPVOID *)v82;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v70,
            3,
            ": {}");
        }
        v71 = 428;
        goto LABEL_285;
      }
      *(_QWORD *)v84 = bstrString;
      LogAdapter::TraceInfo<wchar_t const *>("DWLD: No sandbox found for update with ID: {}, continuing", v84);
    }
    else
    {
      v85[0] = bstrString;
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("DWLD: Moved WU content to {} for update with ID {}", &v87, v85);
      v66 = 1;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v95 )
    {
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v95 + 16LL))(v95);
      v95 = 0;
    }
    if ( v98 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
      v98 = 0;
    }
    if ( v99 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
      v99 = 0;
    }
    v67 = (unsigned int)(v88 + 1);
    v88 = v67;
  }
  while ( (int)v67 < v102 );
  if ( !v66 )
    goto LABEL_306;
LABEL_268:
  if ( a8 && (v68 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a8 + 32LL))(a8, 2), v11 = v68, v68 < 0) )
  {
    v101 = v68;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to send progress");
      *(_QWORD *)v84 = &v101;
      LOBYTE(v69) = 1;
      ppvb = (LPVOID *)v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v69,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v11,
      (int)ppvb);
    if ( v90 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      v90 = 0;
    }
    if ( v92 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v92 = 0;
    }
    SysFreeString(v83);
    Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v104);
    if ( v9 )
      RevertImpersonate();
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v93);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v94);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v89);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(v91);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v96);
    return v11;
  }
  else
  {
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v90);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v92);
    Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v83);
    Windows::AutoBStr::~AutoBStr((Windows::AutoBStr *)&v104);
    if ( v9 )
      RevertImpersonate();
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v93);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v94);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v89);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(v91);
    Windows::AutoComPtr<IUpdate10>::~AutoComPtr<IUpdate10>(&v96);
    return 0;
  }
}

```

## disassembly

```asm
0x1801b164c  mov     [rsp-8+arg_8], rbx
0x1801b1651  push    rbp
0x1801b1652  push    rsi
0x1801b1653  push    rdi
0x1801b1654  push    r12
0x1801b1656  push    r13
0x1801b1658  push    r14
0x1801b165a  push    r15
0x1801b165c  lea     rbp, [rsp-20h]
0x1801b1661  sub     rsp, 120h
0x1801b1668  mov     rax, cs:__security_cookie
0x1801b166f  xor     rax, rsp
0x1801b1672  mov     [rbp+50h+var_38], rax
0x1801b1676  mov     rax, [rbp+50h+arg_20]
0x1801b167d  xor     r14d, r14d
0x1801b1680  mov     rdi, [rbp+50h+psz]
0x1801b1687  mov     r12d, ecx
0x1801b168a  mov     r15, [rbp+50h+arg_30]
0x1801b1691  mov     rsi, [rbp+50h+arg_38]
0x1801b1698  mov     r13, [rbp+50h+arg_40]
0x1801b169f  mov     [rbp+50h+var_90], r9
0x1801b16a3  mov     [rsp+150h+var_120], dl
0x1801b16a7  mov     [rbp+50h+var_D0], rax
0x1801b16ab  mov     [rbp+50h+var_88], r14
0x1801b16af  mov     qword ptr [rbp+50h+var_B0], r14
0x1801b16b3  mov     [rbp+50h+var_C0], r14
0x1801b16b7  mov     [rbp+50h+var_98], r14
0x1801b16bb  mov     [rbp+50h+var_A0], r14
0x1801b16bf  mov     [rbp+50h+var_A8], r14
0x1801b16c3  mov     [rbp+50h+var_B8], r14
0x1801b16c7  mov     [rbp+50h+var_5C], r14d
0x1801b16cb  test    r9, r9
0x1801b16ce  jnz     loc_1801B17ED
0x1801b16d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b16db  mov     ebx, 80004003h
0x1801b16e0  mov     [rbp+50h+var_C8], ebx
0x1801b16e3  test    rcx, rcx
0x1801b16e6  jz      short loc_1801B1726
0x1801b16e8  lea     esi, [r14+3]
0x1801b16ec  xor     edx, edx
0x1801b16ee  mov     r8d, esi
0x1801b16f1  lea     r9, aInvalidSession; "Invalid sessionData"
0x1801b16f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b16fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b1704  lea     rax, [rbp+50h+var_C8]
0x1801b1708  mov     [rbp+50h+var_90], rax
0x1801b170c  lea     r9, asc_1801CAFB4; ": {}"
0x1801b1713  lea     rax, [rbp+50h+var_90]
0x1801b1717  mov     r8d, esi
0x1801b171a  mov     dl, 1
0x1801b171c  mov     [rsp+150h+ppv], rax; int
0x1801b1721  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b1726  mov     rcx, [rbp+58h]; this
0x1801b172a  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b1731  mov     r9d, ebx; char *
0x1801b1734  mov     edx, 10Ch; void *
0x1801b1739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b173e  mov     rcx, [rbp+50h+var_B8]
0x1801b1742  test    rcx, rcx
0x1801b1745  jz      short loc_1801B1757
0x1801b1747  mov     rax, [rcx]
0x1801b174a  mov     rax, [rax+10h]
0x1801b174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1753  mov     [rbp+50h+var_B8], r14
0x1801b1757  mov     rcx, [rbp+50h+var_A8]
0x1801b175b  test    rcx, rcx
0x1801b175e  jz      short loc_1801B1770
0x1801b1760  mov     rax, [rcx]
0x1801b1763  mov     rax, [rax+10h]
0x1801b1767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b176c  mov     [rbp+50h+var_A8], r14
0x1801b1770  mov     rcx, [rbp+50h+var_A0]
0x1801b1774  test    rcx, rcx
0x1801b1777  jz      short loc_1801B1789
0x1801b1779  mov     rax, [rcx]
0x1801b177c  mov     rax, [rax+10h]
0x1801b1780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1785  mov     [rbp+50h+var_A0], r14
0x1801b1789  mov     rcx, [rbp+50h+var_98]
0x1801b178d  test    rcx, rcx
0x1801b1790  jz      short loc_1801B17A2
0x1801b1792  mov     rax, [rcx]
0x1801b1795  mov     rax, [rax+10h]
0x1801b1799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b179e  mov     [rbp+50h+var_98], r14
0x1801b17a2  mov     rcx, [rbp+50h+var_C0]
0x1801b17a6  test    rcx, rcx
0x1801b17a9  jz      short loc_1801B17BB
0x1801b17ab  mov     rax, [rcx]
0x1801b17ae  mov     rax, [rax+10h]
0x1801b17b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b17b7  mov     [rbp+50h+var_C0], r14
0x1801b17bb  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1801b17bf  test    rcx, rcx
0x1801b17c2  jz      short loc_1801B17D4
0x1801b17c4  mov     rax, [rcx]
0x1801b17c7  mov     rax, [rax+10h]
0x1801b17cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b17d0  mov     qword ptr [rbp+50h+var_B0], r14
0x1801b17d4  mov     rcx, [rbp+50h+var_88]
0x1801b17d8  test    rcx, rcx
0x1801b17db  jz      loc_1801B190A
0x1801b17e1  mov     rax, [rcx]
0x1801b17e4  mov     rax, [rax+10h]
0x1801b17e8  jmp     loc_1801B1905
0x1801b17ed  test    rax, rax
0x1801b17f0  jnz     loc_1801B1934
0x1801b17f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b17fd  mov     ebx, 80004003h
0x1801b1802  mov     [rbp+50h+var_C8], ebx
0x1801b1805  test    rcx, rcx
0x1801b1808  jz      short loc_1801B1847
0x1801b180a  lea     esi, [rax+3]
0x1801b180d  xor     edx, edx
0x1801b180f  mov     r8d, esi
0x1801b1812  lea     r9, aInvalidPszdown; "Invalid pszDownloadedSandbox"
0x1801b1819  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b181e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b1825  lea     rax, [rbp+50h+var_C8]
0x1801b1829  mov     [rbp+50h+var_90], rax
0x1801b182d  lea     r9, asc_1801CAFB4; ": {}"
0x1801b1834  lea     rax, [rbp+50h+var_90]
0x1801b1838  mov     r8d, esi
0x1801b183b  mov     dl, 1
0x1801b183d  mov     [rsp+150h+ppv], rax; int
0x1801b1842  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b1847  mov     rcx, [rbp+58h]; this
0x1801b184b  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b1852  mov     r9d, ebx; char *
0x1801b1855  mov     edx, 111h; void *
0x1801b185a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b185f  mov     rcx, [rbp+50h+var_B8]
0x1801b1863  test    rcx, rcx
0x1801b1866  jz      short loc_1801B1878
0x1801b1868  mov     rax, [rcx]
0x1801b186b  mov     rax, [rax+10h]
0x1801b186f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1874  mov     [rbp+50h+var_B8], r14
0x1801b1878  mov     rcx, [rbp+50h+var_A8]
0x1801b187c  test    rcx, rcx
0x1801b187f  jz      short loc_1801B1891
0x1801b1881  mov     rax, [rcx]
0x1801b1884  mov     rax, [rax+10h]
0x1801b1888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b188d  mov     [rbp+50h+var_A8], r14
0x1801b1891  mov     rcx, [rbp+50h+var_A0]
0x1801b1895  test    rcx, rcx
0x1801b1898  jz      short loc_1801B18AA
0x1801b189a  mov     rax, [rcx]
0x1801b189d  mov     rax, [rax+10h]
0x1801b18a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b18a6  mov     [rbp+50h+var_A0], r14
0x1801b18aa  mov     rcx, [rbp+50h+var_98]
0x1801b18ae  test    rcx, rcx
0x1801b18b1  jz      short loc_1801B18C3
0x1801b18b3  mov     rax, [rcx]
0x1801b18b6  mov     rax, [rax+10h]
0x1801b18ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b18bf  mov     [rbp+50h+var_98], r14
0x1801b18c3  mov     rcx, [rbp+50h+var_C0]
0x1801b18c7  test    rcx, rcx
0x1801b18ca  jz      short loc_1801B18DC
0x1801b18cc  mov     rax, [rcx]
0x1801b18cf  mov     rax, [rax+10h]
0x1801b18d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b18d8  mov     [rbp+50h+var_C0], r14
0x1801b18dc  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1801b18e0  test    rcx, rcx
0x1801b18e3  jz      short loc_1801B18F5
0x1801b18e5  mov     rax, [rcx]
0x1801b18e8  mov     rax, [rax+10h]
0x1801b18ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b18f1  mov     qword ptr [rbp+50h+var_B0], r14
0x1801b18f5  mov     rcx, [rbp+50h+var_88]
0x1801b18f9  test    rcx, rcx
0x1801b18fc  jz      short loc_1801B190A
0x1801b18fe  mov     rdx, [rcx]
0x1801b1901  mov     rax, [rdx+10h]
0x1801b1905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b190a  mov     eax, ebx
0x1801b190c  mov     rcx, [rbp+50h+var_38]
0x1801b1910  xor     rcx, rsp; StackCookie
0x1801b1913  call    __security_check_cookie
0x1801b1918  mov     rbx, [rsp+150h+arg_8]
0x1801b1920  add     rsp, 120h
0x1801b1927  pop     r15
0x1801b1929  pop     r14
0x1801b192b  pop     r13
0x1801b192d  pop     r12
0x1801b192f  pop     rdi
0x1801b1930  pop     rsi
0x1801b1931  pop     rbp
0x1801b1932  retn
0x1801b1934  test    r8, r8
0x1801b1937  jz      loc_1801B1A88
0x1801b193d  mov     ecx, cs:_tls_index
0x1801b1943  mov     rax, gs:58h
0x1801b194c  mov     edx, 138h
0x1801b1951  mov     rax, [rax+rcx*8]
0x1801b1955  cmp     [rdx+rax], r14
0x1801b1959  jz      loc_1801B1A73
0x1801b195f  cmp     [rdx+rax], r8
0x1801b1963  jz      loc_1801B1A88
0x1801b1969  mov     ebx, 8000000Dh
0x1801b196e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b1975  xor     edi, edi
0x1801b1977  mov     [rbp+50h+var_C8], ebx
0x1801b197a  test    rcx, rcx
0x1801b197d  jz      short loc_1801B19BC
0x1801b197f  lea     esi, [rdi+3]
0x1801b1982  xor     edx, edx
0x1801b1984  mov     r8d, esi
0x1801b1987  lea     r9, aFailedToImpers; "Failed to impersonate user"
0x1801b198e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b1993  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b199a  lea     rax, [rbp+50h+var_C8]
0x1801b199e  mov     [rbp+50h+var_90], rax
0x1801b19a2  lea     r9, asc_1801CAFB4; ": {}"
0x1801b19a9  lea     rax, [rbp+50h+var_90]
0x1801b19ad  mov     r8d, esi
0x1801b19b0  mov     dl, 1
0x1801b19b2  mov     [rsp+150h+ppv], rax; int
0x1801b19b7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b19bc  mov     rcx, [rbp+58h]; this
0x1801b19c0  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801b19c7  mov     r9d, ebx; char *
0x1801b19ca  mov     edx, 116h; void *
0x1801b19cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b19d4  mov     rcx, [rbp+50h+var_B8]
0x1801b19d8  test    rcx, rcx
0x1801b19db  jz      short loc_1801B19ED
0x1801b19dd  mov     rax, [rcx]
0x1801b19e0  mov     rax, [rax+10h]
0x1801b19e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b19e9  mov     [rbp+50h+var_B8], rdi
0x1801b19ed  mov     rcx, [rbp+50h+var_A8]
0x1801b19f1  test    rcx, rcx
0x1801b19f4  jz      short loc_1801B1A06
0x1801b19f6  mov     rax, [rcx]
0x1801b19f9  mov     rax, [rax+10h]
0x1801b19fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a02  mov     [rbp+50h+var_A8], rdi
0x1801b1a06  mov     rcx, [rbp+50h+var_A0]
0x1801b1a0a  test    rcx, rcx
0x1801b1a0d  jz      short loc_1801B1A1F
0x1801b1a0f  mov     rax, [rcx]
0x1801b1a12  mov     rax, [rax+10h]
0x1801b1a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a1b  mov     [rbp+50h+var_A0], rdi
0x1801b1a1f  mov     rcx, [rbp+50h+var_98]
0x1801b1a23  test    rcx, rcx
0x1801b1a26  jz      short loc_1801B1A38
0x1801b1a28  mov     rax, [rcx]
0x1801b1a2b  mov     rax, [rax+10h]
0x1801b1a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a34  mov     [rbp+50h+var_98], rdi
0x1801b1a38  mov     rcx, [rbp+50h+var_C0]
0x1801b1a3c  test    rcx, rcx
0x1801b1a3f  jz      short loc_1801B1A51
0x1801b1a41  mov     rax, [rcx]
0x1801b1a44  mov     rax, [rax+10h]
0x1801b1a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a4d  mov     [rbp+50h+var_C0], rdi
0x1801b1a51  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1801b1a55  test    rcx, rcx
0x1801b1a58  jz      loc_1801B18F5
0x1801b1a5e  mov     rax, [rcx]
0x1801b1a61  mov     rax, [rax+10h]
0x1801b1a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a6a  mov     qword ptr [rbp+50h+var_B0], rdi
0x1801b1a6e  jmp     loc_1801B18F5
0x1801b1a73  mov     rcx, r8; Token
0x1801b1a76  call    ImpersonateToken
0x1801b1a7b  mov     ebx, eax
0x1801b1a7d  test    eax, eax
0x1801b1a7f  js      loc_1801B196E
0x1801b1a85  mov     r14b, 1
0x1801b1a88  test    rsi, rsi
0x1801b1a8b  jz      short loc_1801B1A9C
0x1801b1a8d  mov     rax, [rsi]
0x1801b1a90  mov     rcx, rsi
0x1801b1a93  mov     rax, [rax+18h]
0x1801b1a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a9c  cmp     [rbp+50h+var_88], 0
0x1801b1aa1  jnz     loc_1801B30DF
0x1801b1aa7  xor     edx, edx; pUnkOuter
0x1801b1aa9  lea     rax, [rbp+50h+var_88]
0x1801b1aad  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x1801b1ab4  mov     [rsp+150h+ppv], rax; int
0x1801b1ab9  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x1801b1ac0  lea     r8d, [rdx+1]; dwClsContext
0x1801b1ac4  call    cs:__imp_CoCreateInstance
0x1801b1acb  nop     dword ptr [rax+rax+00h]
0x1801b1ad0  mov     ebx, eax
0x1801b1ad2  test    eax, eax
0x1801b1ad4  jns     loc_1801B1BE9
0x1801b1ada  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b1ae1  xor     edi, edi
0x1801b1ae3  mov     [rbp+50h+var_C8], eax
0x1801b1ae6  test    rcx, rcx
  ... truncated ...
```
