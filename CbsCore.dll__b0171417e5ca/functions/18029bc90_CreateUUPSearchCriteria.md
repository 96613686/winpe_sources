# CreateUUPSearchCriteria

- ea: `0x18029bc90`
- end: `0x18029c6c4`
- name: `CreateUUPSearchCriteria`
- size: `2612`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18029ef9c`

## callees

- `0x18000d910`
- `0x180010cc0`
- `0x180013250`
- `0x1800150c0`
- `0x180015420`
- `0x1800261e0`
- `0x180049ec0`
- `0x18005ec58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800c0054`
- `0x1800eb920`
- `0x18029bc90`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18029bf63`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18029bf63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029be90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029be90`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18029be6b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18029be6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029be1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029bf47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c1ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c2c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029be1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029bf47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c1ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c2c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029c638`
- `OLEAUT32!__imp_SysAllocString` at `0x18029c5dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18029c5dd`

## string_xrefs

- `0x18029c0f7`: `Failed to get installed product count`
- `0x18029c085`: `Failed to enumerate installed product`
- `0x18029bd74`: `system32\ProductEnumerator.dll`
- `0x18029c005`: `Failed to create product enumerator`
- `0x18029bf5c`: `PE_CreateProductEnumerator`
- `0x18029beaf`: `Failed to load ProductEnumerator.dll.`
- `0x18029bdec`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029bf0c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029c394`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029c45b`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029c4dc`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029c56f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029bd4b`: `(Product='%s' and IsInstalled=0 and RebootRequired=1 %s)`

## pseudocode

```c
__int64 __fastcall CreateUUPSearchCriteria(char a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const wchar_t *v6; // r14
  const wchar_t *v7; // r15
  int WindowsDirectory; // eax
  unsigned __int64 v9; // r9
  HMODULE LibraryW; // rax
  signed int LastError; // ebx
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  FARPROC ProcAddress; // rbx
  __int64 InitPointer; // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64); // rbx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64); // rbx
  __int64 v26; // rax
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, const wchar_t *, __int64); // rbx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64); // rbx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64); // rbx
  __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // r9
  __int64 v39; // rdx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  __int64 v43; // r9
  __int64 v44; // rdx
  OLECHAR *v45; // rbx
  BSTR v46; // rax
  unsigned int v48; // [rsp+20h] [rbp-69h]
  __int64 v49; // [rsp+30h] [rbp-59h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-51h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-49h] BYREF
  int v52[2]; // [rsp+48h] [rbp-41h] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-39h] BYREF
  __int64 v54; // [rsp+58h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-29h] BYREF
  __int64 v56; // [rsp+68h] [rbp-21h] BYREF
  int v57; // [rsp+70h] [rbp-19h] BYREF
  LPVOID v58; // [rsp+78h] [rbp-11h] BYREF
  __int64 v59; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v60; // [rsp+88h] [rbp-1h] BYREF
  __int64 v61; // [rsp+90h] [rbp+7h] BYREF
  __int64 v62; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  hModule = 0;
  v56 = 0;
  v54 = 0;
  pv = 0;
  v49 = 0;
  psz = 0;
  v62 = 0;
  lpLibFileName = 0;
  if ( !a3 )
  {
    v4 = -2147467261;
    v60 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No search criteria result specified");
      v58 = &v60;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v5 = 1113;
LABEL_14:
    v9 = v4;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v9,
      v48);
    goto LABEL_16;
  }
  v6 = L"(Product='%s' and IsInstalled=0 and RebootRequired=1 %s)";
  if ( (a1 & 2) == 0 )
    v6 = L"(Product='%s' and CurrentVersionOnly=1 %s)";
  v7 = L"and DeploymentAction=*";
  if ( (a1 & 1) == 0 )
    v7 = &qword_1802EB518;
  if ( a2 )
  {
    v41 = SczAllocFromSz(&v49, a2);
    v4 = v41;
    if ( v41 < 0 )
    {
      v9 = (unsigned int)v41;
      v5 = 1185;
      goto LABEL_15;
    }
    v34 = 0;
LABEL_94:
    v42 = SczAllocFormatted(&psz, v6, v49, v7);
    v4 = v42;
    if ( v42 >= 0 )
    {
      v45 = psz;
      *(_QWORD *)v52 = psz;
      LogAdapter::TraceAtLevel<wchar_t const *>(1, "DWLD: Current product search criteria: {}", v52);
      v46 = SysAllocString(v45);
      Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&v62, v46);
      if ( v62 )
      {
        *a3 = v62;
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&psz);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        goto LABEL_106;
      }
      v4 = -2147024882;
      v44 = 1193;
      v43 = 2147942414LL;
    }
    else
    {
      v43 = (unsigned int)v42;
      v44 = 1188;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v43,
      v48);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&psz);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v34 )
      goto LABEL_77;
    goto LABEL_18;
  }
  v60 = 0;
  WindowsDirectory = PathGetWindowsDirectory(&lpLibFileName, L"system32\\ProductEnumerator.dll");
  v4 = WindowsDirectory;
  if ( WindowsDirectory < 0 )
  {
    v57 = WindowsDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate string");
      v58 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v5 = 1133;
    goto LABEL_14;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, LibraryW);
  if ( !hModule )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load ProductEnumerator.dll.");
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      else
        v12 = LastError;
      v57 = v12;
      v58 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&v58);
    }
    if ( LastError )
    {
      v13 = (unsigned int)LastError;
      v14 = 1136;
LABEL_30:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v14,
             (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
             (const char *)v13,
             v48);
LABEL_16:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&psz);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_18;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&psz);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
LABEL_106:
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      v56 = 0;
    }
    v4 = 0;
    goto LABEL_111;
  }
  ProcAddress = GetProcAddress(hModule, "PE_CreateProductEnumerator");
  if ( !ProcAddress )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Product enumeration not supported on this platform.");
      v58 = &v57;
      v57 = -2147024846;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&v58);
    }
    v13 = 50;
    v14 = 1141;
    goto LABEL_30;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v56);
  v17 = ((__int64 (__fastcall *)(__int64))ProcAddress)(InitPointer);
  v4 = v17;
  if ( v17 < 0 )
  {
    v57 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create product enumerator");
      v58 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v5 = 1144;
    goto LABEL_14;
  }
  v18 = v56;
  v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 24LL);
  v20 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v54);
  v21 = v19(v18, v20);
  v4 = v21;
  if ( v21 < 0 )
  {
    v57 = v21;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate installed product");
      v58 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v5 = 1146;
    goto LABEL_14;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v54 + 24LL))(v54, &v60);
  v4 = v22;
  if ( v22 < 0 )
  {
    v57 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get installed product count");
      *(_QWORD *)v52 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v52);
    }
    v5 = 1148;
    goto LABEL_14;
  }
  v23 = 0;
  if ( !v60 )
  {
LABEL_61:
    v4 = -2146498223;
    LODWORD(v62) = -2146498223;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Primary OS product not found.");
      *(_QWORD *)v52 = &v62;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v52);
    }
    v5 = 1176;
    goto LABEL_14;
  }
  while ( 1 )
  {
    v24 = v54;
    v59 = 0;
    v61 = 0;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v54 + 32LL);
    v26 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v59);
    v4 = v25(v24, v23, v26);
    if ( (v4 & 0x80000000) != 0 )
    {
      v57 = v4;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get product object");
        *(_QWORD *)v52 = &v57;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v52);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x486,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v4,
        v48);
      goto LABEL_87;
    }
    v27 = v59;
    v28 = *(int (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v59 + 40LL);
    v29 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v61);
    if ( v28(v27, L"PrimaryOSProduct", v29) >= 0 )
      break;
LABEL_56:
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    if ( ++v23 >= v60 )
      goto LABEL_61;
  }
  v30 = v61;
  v58 = 0;
  v31 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 32LL);
  v32 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v58);
  v4 = v31(v30, v32);
  if ( (v4 & 0x80000000) != 0 )
  {
    v57 = v4;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get value of PrimaryOSProduct");
      *(_QWORD *)v52 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v52);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v4,
      v48);
    if ( v58 )
    {
      CoTaskMemFree(v58);
      v58 = 0;
    }
LABEL_87:
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    goto LABEL_16;
  }
  if ( !(unsigned __int8)StringsAreEqual(v58, L"1", 0) )
  {
    if ( v58 )
    {
      CoTaskMemFree(v58);
      v58 = 0;
    }
    goto LABEL_56;
  }
  v33 = 0;
  v34 = v59;
  v59 = 0;
  if ( v58 )
  {
    CoTaskMemFree(v58);
    v33 = v59;
    v58 = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v33 = v59;
    v61 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v59 = 0;
  }
  if ( !v34 )
    goto LABEL_61;
  v35 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 24LL);
  v36 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
  v37 = v35(v34, v36);
  v4 = v37;
  if ( v37 >= 0 )
  {
    v40 = SczAllocFromSz(&v49, pv);
    v4 = v40;
    if ( v40 >= 0 )
      goto LABEL_94;
    v38 = (unsigned int)v40;
    v39 = 1181;
  }
  else
  {
    v57 = v37;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get product name.");
      *(_QWORD *)v52 = &v57;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v52);
    }
    v38 = v4;
    v39 = 1179;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v39,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)v38,
    v48);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&psz);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
LABEL_77:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_18:
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
LABEL_111:
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  return v4;
}

```

## disassembly

```asm
0x18029bc90  mov     [rsp-8+arg_0], rbx
0x18029bc95  push    rbp
0x18029bc96  push    rsi
0x18029bc97  push    rdi
0x18029bc98  push    r12
0x18029bc9a  push    r13
0x18029bc9c  push    r14
0x18029bc9e  push    r15
0x18029bca0  lea     rbp, [rsp-27h]
0x18029bca5  sub     rsp, 0B0h
0x18029bcac  mov     rax, cs:__security_cookie
0x18029bcb3  xor     rax, rsp
0x18029bcb6  mov     [rbp+57h+var_40], rax
0x18029bcba  xor     r13d, r13d
0x18029bcbd  mov     r12, r8
0x18029bcc0  mov     [rbp+57h+hModule], r13
0x18029bcc4  mov     [rbp+57h+var_78], r13
0x18029bcc8  mov     [rbp+57h+var_88], r13
0x18029bccc  mov     [rbp+57h+pv], r13
0x18029bcd0  mov     [rbp+57h+var_B0], r13
0x18029bcd4  mov     [rbp+57h+psz], r13
0x18029bcd8  mov     [rbp+57h+var_48], r13
0x18029bcdc  mov     [rbp+57h+lpLibFileName], r13
0x18029bce0  test    r8, r8
0x18029bce3  jnz     short loc_18029BD41
0x18029bce5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bcec  mov     ebx, 80004003h
0x18029bcf1  mov     [rbp+57h+var_58], ebx
0x18029bcf4  test    rcx, rcx
0x18029bcf7  jz      short loc_18029BD37
0x18029bcf9  lea     esi, [r8+3]
0x18029bcfd  xor     edx, edx
0x18029bcff  mov     r8d, esi
0x18029bd02  lea     r9, aNoSearchCriter; "No search criteria result specified"
0x18029bd09  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029bd0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bd15  lea     rax, [rbp+57h+var_58]
0x18029bd19  mov     [rbp+57h+var_68], rax
0x18029bd1d  lea     r9, asc_1802EE7AC; ": {}"
0x18029bd24  lea     rax, [rbp+57h+var_68]
0x18029bd28  mov     r8d, esi
0x18029bd2b  mov     dl, 1
0x18029bd2d  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029bd32  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029bd37  mov     edx, 459h
0x18029bd3c  jmp     loc_18029BDE5
0x18029bd41  test    cl, 2
0x18029bd44  lea     rax, aProductSAndCur; "(Product='%s' and CurrentVersionOnly=1 "...
0x18029bd4b  lea     r14, aProductSAndIsi; "(Product='%s' and IsInstalled=0 and Reb"...
0x18029bd52  cmovz   r14, rax
0x18029bd56  lea     r15, aAndDeploymenta; "and DeploymentAction=*"
0x18029bd5d  test    cl, 1
0x18029bd60  lea     rax, qword_1802EB518
0x18029bd67  cmovz   r15, rax
0x18029bd6b  test    rdx, rdx
0x18029bd6e  jnz     loc_18029C52B
0x18029bd74  lea     rdx, aSystem32Produc; "system32\\ProductEnumerator.dll"
0x18029bd7b  mov     [rbp+57h+var_58], r13d
0x18029bd7f  lea     rcx, [rbp+57h+lpLibFileName]
0x18029bd83  call    PathGetWindowsDirectory
0x18029bd88  mov     ebx, eax
0x18029bd8a  test    eax, eax
0x18029bd8c  jns     loc_18029BE67
0x18029bd92  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bd99  mov     [rbp+57h+var_70], eax
0x18029bd9c  test    rcx, rcx
0x18029bd9f  jz      short loc_18029BDE0
0x18029bda1  mov     esi, 3
0x18029bda6  lea     r9, aFailedToAlloca_10; "Failed to allocate string"
0x18029bdad  mov     r8d, esi
0x18029bdb0  xor     edx, edx
0x18029bdb2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029bdb7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bdbe  lea     rax, [rbp+57h+var_70]
0x18029bdc2  mov     [rbp+57h+var_68], rax
0x18029bdc6  lea     r9, asc_1802EE7AC; ": {}"
0x18029bdcd  lea     rax, [rbp+57h+var_68]
0x18029bdd1  mov     r8d, esi
0x18029bdd4  mov     dl, 1
0x18029bdd6  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18029bddb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029bde0  mov     edx, 46Dh; void *
0x18029bde5  mov     r9d, ebx; char *
0x18029bde8  mov     rcx, [rbp+5Fh]; this
0x18029bdec  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029bdf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029bdf8  lea     rcx, [rbp+57h+lpLibFileName]
0x18029bdfc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029be01  lea     rcx, [rbp+57h+psz]
0x18029be05  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029be0a  lea     rcx, [rbp+57h+var_B0]
0x18029be0e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029be13  mov     rcx, [rbp+57h+pv]; pv
0x18029be17  test    rcx, rcx
0x18029be1a  jz      short loc_18029BE2C
0x18029be1c  call    cs:__imp_CoTaskMemFree
0x18029be23  nop     dword ptr [rax+rax+00h]
0x18029be28  mov     [rbp+57h+pv], r13
0x18029be2c  mov     rcx, [rbp+57h+var_88]
0x18029be30  test    rcx, rcx
0x18029be33  jz      short loc_18029BE45
0x18029be35  mov     rax, [rcx]
0x18029be38  mov     rax, [rax+10h]
0x18029be3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029be41  mov     [rbp+57h+var_88], r13
0x18029be45  mov     rcx, [rbp+57h+var_78]
0x18029be49  test    rcx, rcx
0x18029be4c  jz      loc_18029C691
0x18029be52  mov     rax, [rcx]
0x18029be55  mov     rax, [rax+10h]
0x18029be59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029be5e  mov     [rbp+57h+var_78], r13
0x18029be62  jmp     loc_18029C691
0x18029be67  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x18029be6b  call    cs:__imp_LoadLibraryW
0x18029be72  nop     dword ptr [rax+rax+00h]
0x18029be77  mov     rdx, rax
0x18029be7a  lea     rcx, [rbp+57h+hModule]
0x18029be7e  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x18029be83  mov     rcx, [rbp+57h+hModule]; hModule
0x18029be87  test    rcx, rcx
0x18029be8a  jnz     loc_18029BF5C
0x18029be90  call    cs:__imp_GetLastError
0x18029be97  nop     dword ptr [rax+rax+00h]
0x18029be9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bea3  mov     ebx, eax
0x18029bea5  test    rcx, rcx
0x18029bea8  jz      short loc_18029BEFC
0x18029beaa  mov     esi, 3
0x18029beaf  lea     r9, aFailedToLoadPr; "Failed to load ProductEnumerator.dll."
0x18029beb6  mov     r8d, esi
0x18029beb9  xor     edx, edx
0x18029bebb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029bec0  test    ebx, ebx
0x18029bec2  jg      short loc_18029BEC8
0x18029bec4  mov     eax, ebx
0x18029bec6  jmp     short loc_18029BED0
0x18029bec8  movzx   eax, bx
0x18029becb  or      eax, 80070000h
0x18029bed0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bed7  lea     r9, a0; ": {0}"
0x18029bede  mov     [rbp+57h+var_70], eax
0x18029bee1  mov     r8d, esi
0x18029bee4  lea     rax, [rbp+57h+var_70]
0x18029bee8  mov     dl, 1
0x18029beea  mov     [rbp+57h+var_68], rax
0x18029beee  lea     rax, [rbp+57h+var_68]
0x18029bef2  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x18029bef7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029befc  test    ebx, ebx
0x18029befe  jz      short loc_18029BF1F
0x18029bf00  mov     r9d, ebx; char *
0x18029bf03  mov     edx, 470h; void *
0x18029bf08  mov     rcx, [rbp+5Fh]; this
0x18029bf0c  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029bf13  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18029bf18  mov     ebx, eax
0x18029bf1a  jmp     loc_18029BDF8
0x18029bf1f  lea     rcx, [rbp+57h+lpLibFileName]
0x18029bf23  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029bf28  lea     rcx, [rbp+57h+psz]
0x18029bf2c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029bf31  lea     rcx, [rbp+57h+var_B0]
0x18029bf35  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18029bf3a  mov     rcx, [rbp+57h+pv]; pv
0x18029bf3e  test    rcx, rcx
0x18029bf41  jz      loc_18029C65C
0x18029bf47  call    cs:__imp_CoTaskMemFree
0x18029bf4e  nop     dword ptr [rax+rax+00h]
0x18029bf53  mov     [rbp+57h+pv], r13
0x18029bf57  jmp     loc_18029C65C
0x18029bf5c  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x18029bf63  call    cs:__imp_GetProcAddress
0x18029bf6a  nop     dword ptr [rax+rax+00h]
0x18029bf6f  mov     rbx, rax
0x18029bf72  test    rax, rax
0x18029bf75  jnz     short loc_18029BFD7
0x18029bf77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bf7e  test    rcx, rcx
0x18029bf81  jz      short loc_18029BFC7
0x18029bf83  lea     esi, [rax+3]
0x18029bf86  xor     edx, edx
0x18029bf88  mov     r8d, esi
0x18029bf8b  lea     r9, aProductEnumera; "Product enumeration not supported on th"...
0x18029bf92  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029bf97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bf9e  lea     rax, [rbp+57h+var_70]
0x18029bfa2  mov     [rbp+57h+var_68], rax
0x18029bfa6  lea     r9, a0; ": {0}"
0x18029bfad  lea     rax, [rbp+57h+var_68]
0x18029bfb1  mov     [rbp+57h+var_70], 80070032h
0x18029bfb8  mov     r8d, esi
0x18029bfbb  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029bfc0  mov     dl, 1
0x18029bfc2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029bfc7  mov     r9d, 32h ; '2'
0x18029bfcd  mov     edx, 475h
0x18029bfd2  jmp     loc_18029BF08
0x18029bfd7  lea     rcx, [rbp+57h+var_78]
0x18029bfdb  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029bfe0  mov     rcx, rax
0x18029bfe3  mov     rax, rbx
0x18029bfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029bfeb  mov     ebx, eax
0x18029bfed  test    eax, eax
0x18029bfef  jns     short loc_18029C049
0x18029bff1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029bff8  mov     [rbp+57h+var_70], eax
0x18029bffb  test    rcx, rcx
0x18029bffe  jz      short loc_18029C03F
0x18029c000  mov     esi, 3
0x18029c005  lea     r9, aFailedToCreate_113; "Failed to create product enumerator"
0x18029c00c  mov     r8d, esi
0x18029c00f  xor     edx, edx
0x18029c011  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029c016  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029c01d  lea     rax, [rbp+57h+var_70]
0x18029c021  mov     [rbp+57h+var_68], rax
0x18029c025  lea     r9, asc_1802EE7AC; ": {}"
0x18029c02c  lea     rax, [rbp+57h+var_68]
0x18029c030  mov     r8d, esi
0x18029c033  mov     dl, 1
0x18029c035  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029c03a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029c03f  mov     edx, 478h
0x18029c044  jmp     loc_18029BDE5
0x18029c049  mov     rdi, [rbp+57h+var_78]
0x18029c04d  lea     rcx, [rbp+57h+var_88]
0x18029c051  mov     rax, [rdi]
0x18029c054  mov     rbx, [rax+18h]
0x18029c058  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029c05d  mov     rdx, rax
0x18029c060  mov     rcx, rdi
0x18029c063  mov     rax, rbx
0x18029c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029c06b  mov     ebx, eax
0x18029c06d  test    eax, eax
0x18029c06f  jns     short loc_18029C0C9
0x18029c071  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029c078  mov     [rbp+57h+var_70], eax
0x18029c07b  test    rcx, rcx
0x18029c07e  jz      short loc_18029C0BF
0x18029c080  mov     esi, 3
0x18029c085  lea     r9, aFailedToEnumer_11; "Failed to enumerate installed product"
0x18029c08c  mov     r8d, esi
0x18029c08f  xor     edx, edx
0x18029c091  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029c096  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029c09d  lea     rax, [rbp+57h+var_70]
0x18029c0a1  mov     [rbp+57h+var_68], rax
0x18029c0a5  lea     r9, asc_1802EE7AC; ": {}"
0x18029c0ac  lea     rax, [rbp+57h+var_68]
0x18029c0b0  mov     r8d, esi
0x18029c0b3  mov     dl, 1
0x18029c0b5  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029c0ba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029c0bf  mov     edx, 47Ah
0x18029c0c4  jmp     loc_18029BDE5
0x18029c0c9  mov     rcx, [rbp+57h+var_88]
0x18029c0cd  lea     rdx, [rbp+57h+var_58]
0x18029c0d1  mov     rax, [rcx]
0x18029c0d4  mov     rax, [rax+18h]
0x18029c0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029c0dd  mov     ebx, eax
0x18029c0df  test    eax, eax
0x18029c0e1  jns     short loc_18029C13B
0x18029c0e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029c0ea  mov     [rbp+57h+var_70], eax
0x18029c0ed  test    rcx, rcx
0x18029c0f0  jz      short loc_18029C131
0x18029c0f2  mov     esi, 3
0x18029c0f7  lea     r9, aFailedToGetIns_0; "Failed to get installed product count"
0x18029c0fe  mov     r8d, esi
0x18029c101  xor     edx, edx
0x18029c103  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029c108  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029c10f  lea     rax, [rbp+57h+var_70]
0x18029c113  mov     qword ptr [rbp+57h+var_98], rax
0x18029c117  lea     r9, asc_1802EE7AC; ": {}"
0x18029c11e  lea     rax, [rbp+57h+var_98]
0x18029c122  mov     r8d, esi
0x18029c125  mov     dl, 1
0x18029c127  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029c12c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029c131  mov     edx, 47Ch
0x18029c136  jmp     loc_18029BDE5
0x18029c13b  mov     esi, r13d
0x18029c13e  cmp     [rbp+57h+var_58], r13d
0x18029c142  jbe     loc_18029C24C
0x18029c148  mov     rdi, [rbp+57h+var_88]
0x18029c14c  lea     rcx, [rbp+57h+var_60]
0x18029c150  mov     [rbp+57h+var_60], r13
0x18029c154  mov     [rbp+57h+var_50], r13
0x18029c158  mov     rax, [rdi]
0x18029c15b  mov     rbx, [rax+20h]
0x18029c15f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029c164  mov     r8, rax
0x18029c167  mov     edx, esi
0x18029c169  mov     rax, rbx
0x18029c16c  mov     rcx, rdi
  ... truncated ...
```
