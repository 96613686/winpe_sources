# CArbiterCbsClient::GetEditionInfo(DeviceContext *,bool,wchar_t * *,wchar_t * *)

- ea: `0x1800eb518`
- end: `0x1800ec453`
- name: `?GetEditionInfo@CArbiterCbsClient@@QEAAJPEAVDeviceContext@@_NPEAPEA_W2@Z`
- size: `3899`
- prototype: `__int64 __fastcall(CArbiterCbsClient *__hidden this, struct DeviceContext *, bool, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d6960`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18009b6b0`
- `0x1800ea468`
- `0x1800eaa84`
- `0x1800eb518`
- `0x1800ed774`
- `0x1800f1d28`
- `0x1800f1ed0`
- `0x1801417cc`
- `0x18014a96c`
- `0x18014b0c8`
- `0x180175618`
- `0x1801758a8`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ebad2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ebad2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebb26`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebbf2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebce2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebb26`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebbf2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ebce2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ebaa8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ebaa8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ebfd8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ec15e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ebfd8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ec15e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebcd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebcd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebc9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebc9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebe60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebf6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebe60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ebf6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec3df`

## string_xrefs

- `0x1800ebaa1`: `pkeyhelper.dll`
- `0x1800ebac8`: `GetCompositionEditionForVirtualEdition`
- `0x1800eb8cf`: `Failed reading current build number`
- `0x1800eb5fe`: `Failed reading edition id`
- `0x1800eb7de`: `Failed reading current minor version`
- `0x1800eb6ee`: `Failed reading current major version`
- `0x1800eb9d3`: `Failed reading UBR`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CArbiterCbsClient::GetEditionInfo(
        CArbiterCbsClient *this,
        struct DeviceContext *a2,
        char a3,
        wchar_t **a4,
        wchar_t **a5)
{
  unsigned int v8; // edi
  int RegValue; // eax
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  HMODULE Library; // rax
  const char *v25; // r9
  HMODULE v26; // rdi
  FARPROC ProcAddress; // rax
  const char *v28; // r9
  wchar_t *v29; // rbx
  int v30; // eax
  unsigned int v31; // esi
  const struct std::nothrow_t *v32; // rdx
  wchar_t *v34; // rsi
  int v35; // eax
  unsigned int v36; // r14d
  const struct std::nothrow_t *v37; // rdx
  wchar_t *v38; // rax
  _DWORD *v39; // r14
  struct _RTL_CRITICAL_SECTION *v40; // r15
  const struct std::nothrow_t *v41; // rdx
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rdx
  LPCWCH v47; // rbx
  __int64 v48; // rdx
  void (*v49)(void); // rax
  LPCWCH v50; // rbx
  unsigned __int64 v51; // rax
  __int64 v52; // rdx
  const WCHAR *v53; // rdi
  __int64 v54; // rdx
  int v55; // eax
  unsigned int v56; // ebx
  const struct std::nothrow_t *v57; // rdx
  int v58; // eax
  const struct std::nothrow_t *v59; // rdx
  __int64 v60; // rdx
  LPCWCH *bIgnoreCase; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCasea; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCaseb; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCasec; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCased; // [rsp+28h] [rbp-B1h]
  int bIgnoreCasee; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCasef; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCaseg; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCaseh; // [rsp+28h] [rbp-B1h]
  LPCWCH lpString2; // [rsp+48h] [rbp-91h] BYREF
  wchar_t *v71; // [rsp+50h] [rbp-89h] BYREF
  wchar_t *v72[3]; // [rsp+58h] [rbp-81h] BYREF
  wchar_t *v73; // [rsp+70h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-61h] BYREF
  wchar_t *v75; // [rsp+80h] [rbp-59h] BYREF
  struct ICbsPackage *v76; // [rsp+88h] [rbp-51h] BYREF
  int v77[2]; // [rsp+90h] [rbp-49h] BYREF
  WCHAR String1[28]; // [rsp+98h] [rbp-41h] BYREF
  LPVOID v79; // [rsp+D0h] [rbp-9h]
  WCHAR v80[8]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+57h]

  v72[1] = (wchar_t *)-2LL;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v76 = 0;
  v8 = CArbiterCbsClient::OpenPackage(this, L"@Product", &v76);
  if ( (v8 & 0x80000000) == 0 )
  {
    pv = 0;
    v43 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(*(_QWORD *)v76 + 32LL))(v76, 1, &pv);
    v8 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v73) = v43;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get Edition's keyform");
        lpString2 = (LPCWCH)&v73;
        bIgnoreCase = &lpString2;
        LOBYTE(v44) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v44,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x467,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v8,
        (int)bIgnoreCase);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v76 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
      return v8;
    }
    if ( !pv || !*(_WORD *)pv )
    {
      v8 = -2147023728;
      v77[0] = -2147023728;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get Edition's keyform");
        lpString2 = (LPCWCH)v77;
        bIgnoreCase = &lpString2;
        LOBYTE(v60) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v60,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46A,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)0x80070490LL,
        (int)bIgnoreCase);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v76 )
        (*(void (__fastcall **)(struct ICbsPackage *, _QWORD))(*(_QWORD *)v76 + 16LL))(v76, *(_QWORD *)v76);
      return v8;
    }
    lpString2 = 0;
    v73 = 0;
    v71 = 0;
    v75 = 0;
    v72[0] = 0;
    v45 = ShredStringIdIntoAttributes(
            (wchar_t *)pv,
            0x7Eu,
            &lpString2,
            (const wchar_t **)&v73,
            (const wchar_t **)&v75,
            (const wchar_t **)&v71,
            (const wchar_t **)v72);
    v8 = v45;
    if ( v45 < 0 )
    {
      LODWORD(v73) = v45;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to shred keyform: {0}",
          &pv);
        lpString2 = (LPCWCH)&v73;
        bIgnoreCasef = &lpString2;
        LOBYTE(v46) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v46,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v8,
        (int)bIgnoreCasef);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v76 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
      return v8;
    }
    wcscpy(String1, L"Microsoft-Windws-");
    v47 = lpString2;
    if ( CompareStringOrdinal(String1, 18, lpString2, 18, 1) == 2 )
    {
      wcscpy(v80, L"Edition");
      v50 = v47 + 18;
      v51 = -1;
      do
        ++v51;
      while ( v50[v51] );
      if ( v51 > 7 )
      {
        v53 = &v50[v51];
        if ( CompareStringOrdinal(v80, 7, v53 - 7, 7, 1) == 2 )
        {
          *((_WORD *)v53 - 7) = 0;
          v71 = 0;
          v55 = SczAllocFromSz(&v71, v50);
          v56 = v55;
          if ( v55 >= 0 )
          {
            lpString2 = 0;
            v58 = SczAllocFromSz(&lpString2, v72[0]);
            v56 = v58;
            if ( v58 >= 0 )
            {
              *a4 = v71;
              *a5 = (wchar_t *)lpString2;
              if ( pv )
                CoTaskMemFree(pv);
              goto LABEL_178;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x49C,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
              (const char *)(unsigned int)v58,
              (int)bIgnoreCaseh);
            if ( lpString2 )
              operator delete((void *)(lpString2 - 4), v59);
            if ( v71 )
              operator delete(v71 - 4, v59);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v76 )
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x499,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
              (const char *)(unsigned int)v55,
              (int)bIgnoreCaseh);
            if ( v71 )
              operator delete(v71 - 4, v57);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v76 )
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
          }
          return v56;
        }
        v8 = -2147418113;
        LODWORD(v73) = -2147418113;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Edition's identity name is not formatted as expected");
          lpString2 = (LPCWCH)&v73;
          bIgnoreCaseh = &lpString2;
          LOBYTE(v54) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v54,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x494,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
          (const char *)0x8000FFFFLL,
          (int)bIgnoreCaseh);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( !v76 )
          return v8;
        v49 = *(void (**)(void))(*(_QWORD *)v76 + 16LL);
        goto LABEL_156;
      }
      v8 = -2147418113;
      LODWORD(v73) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Edition's identity name is not formatted as expected");
        lpString2 = (LPCWCH)&v73;
        bIgnoreCaseg = &lpString2;
        LOBYTE(v52) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v52,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x490,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)0x8000FFFFLL,
        (int)bIgnoreCaseg);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
    }
    else
    {
      v8 = -2147418113;
      LODWORD(v73) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Edition's identity name is not formatted as expected");
        lpString2 = (LPCWCH)&v73;
        bIgnoreCaseg = &lpString2;
        LOBYTE(v48) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v48,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x484,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)0x8000FFFFLL,
        (int)bIgnoreCaseg);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
    }
    if ( !v76 )
      return v8;
    v49 = *(void (**)(void))(*(_QWORD *)v76 + 16LL);
LABEL_156:
    v49();
    return v8;
  }
  if ( !a3 )
  {
    LODWORD(v73) = v8;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting edition package");
      lpString2 = (LPCWCH)&v73;
      bIgnoreCase = &lpString2;
      LOBYTE(v42) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v42,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x464,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCase);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  v72[0] = 0;
  v75 = 0;
  LODWORD(v73) = 0;
  v77[0] = 0;
  v71 = 0;
  LODWORD(pv) = 0;
  lpString2 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>>>(String1);
  bIgnoreCasea = v72;
  RegValue = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"EditionID");
  v8 = RegValue;
  if ( RegValue < 0 )
  {
    LODWORD(v73) = RegValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading edition id");
      *(_QWORD *)v77 = &v73;
      bIgnoreCasea = v77;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x440,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCasea);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v75 )
    {
      operator delete(v75 - 4, v11);
      v75 = 0;
    }
    if ( v72[0] )
      operator delete(v72[0] - 4, v11);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  bIgnoreCaseb = &v73;
  v12 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMajorVersionNumber");
  v8 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v73) = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed reading current major version");
      *(_QWORD *)v77 = &v73;
      bIgnoreCaseb = v77;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCaseb);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v75 )
    {
      operator delete(v75 - 4, v14);
      v75 = 0;
    }
    if ( v72[0] )
      operator delete(v72[0] - 4, v14);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  v15 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMinorVersionNumber");
  v8 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v73) = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed reading current minor version");
      *(_QWORD *)v77 = &v73;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v16,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)v77);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v75 )
    {
      operator delete(v75 - 4, v17);
      v75 = 0;
    }
    if ( v72[0] )
      operator delete(v72[0] - 4, v17);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  bIgnoreCasec = &v71;
  v18 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentBuildNumber");
  v8 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v73) = v18;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading current build number");
      *(_QWORD *)v77 = &v73;
      bIgnoreCasec = v77;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44C,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCasec);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v71 )
      operator delete(v71 - 4, v20);
    if ( v75 )
    {
      operator delete(v75 - 4, v20);
      v75 = 0;
    }
    if ( v72[0] )
      operator delete(v72[0] - 4, v20);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  bIgnoreCased = &pv;
  v21 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"UBR");
  v8 = v21;
  if ( v21 < 0 )
  {
    LODWORD(v73) = v21;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading UBR");
      *(_QWORD *)v77 = &v73;
      bIgnoreCased = v77;
      LOBYTE(v22) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x450,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCased);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v71 )
      operator delete(v71 - 4, v23);
    if ( v75 )
    {
      operator delete(v75 - 4, v23);
      v75 = 0;
    }
    if ( v72[0] )
      operator delete(v72[0] - 4, v23);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v8;
  }
  Library = LoadLibraryExW(L"pkeyhelper.dll", 0, 0);
  v26 = Library;
  v72[2] = (wchar_t *)Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x454,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      v25);
  ProcAddress = GetProcAddress(Library, "GetCompositionEditionForVirtualEdition");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      v28);
  *(_QWORD *)v80 = 0;
  v29 = v72[0];
  v30 = ((__int64 (__fastcall *)(wchar_t *, wchar_t **))ProcAddress)(v72[0], &v75);
  v31 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45A,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)(unsigned int)v30,
      (int)&pv);
    FreeLibrary(v26);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v71 )
      operator delete(v71 - 4, v32);
    if ( v75 )
    {
      operator delete(v75 - 4, v32);
      v75 = 0;
    }
    if ( v29 )
      operator delete(v29 - 4, v32);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v31;
  }
  v34 = v71;
  bIgnoreCasee = (int)v71;
  v35 = SczAllocFormatted(&lpString2, L"%lu.%lu.%s.%lu", (unsigned int)v73, (unsigned int)v77[0]);
  v36 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)(unsigned int)v35,
      bIgnoreCasee);
    FreeLibrary(v26);
    if ( v79 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( lpString2 )
      operator delete((void *)(lpString2 - 4), v37);
    if ( v34 )
      operator delete(v34 - 4, v37);
    if ( v75 )
    {
      operator delete(v75 - 4, v37);
      v75 = 0;
    }
    if ( v29 )
      operator delete(v29 - 4, v37);
    if ( v76 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
    return v36;
  }
  v38 = v75;
  v75 = 0;
  *a4 = v38;
  *a5 = (wchar_t *)lpString2;
  v39 = v79;
  v40 = (struct _RTL_CRITICAL_SECTION *)((char *)v79 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)v79 + 5);
  v39[18] |= 0x300u;
  if ( *((_QWORD *)v39 + 31) )
    tip2::details::shared_data<1,0,0>::complete_helper(v39 + 2, 2);
  if ( v40 )
    LeaveCriticalSection(v40);
  FreeLibrary(v26);
  if ( v79 )
    tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v79);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
  if ( v34 )
    operator delete(v34 - 4, v41);
  if ( v75 )
  {
    operator delete(v75 - 4, v41);
    v75 = 0;
  }
  if ( v29 )
    operator delete(v29 - 4, v41);
LABEL_178:
  if ( v76 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v76 + 16LL))(v76);
  return 0;
}

```

## disassembly

```asm
0x1800eb518  mov     rax, rsp
0x1800eb51b  push    rbp
0x1800eb51c  push    rsi
0x1800eb51d  push    rdi
0x1800eb51e  push    r12
0x1800eb520  push    r13
0x1800eb522  push    r14
0x1800eb524  push    r15
0x1800eb526  lea     rbp, [rax-57h]
0x1800eb52a  sub     rsp, 0F0h
0x1800eb531  mov     [rbp+4Fh+var_C8], 0FFFFFFFFFFFFFFFEh
0x1800eb539  mov     [rax+18h], rbx
0x1800eb53d  mov     rax, cs:__security_cookie
0x1800eb544  xor     rax, rsp
0x1800eb547  mov     [rbp+4Fh+var_40], rax
0x1800eb54b  mov     r12, r9
0x1800eb54e  mov     sil, r8b
0x1800eb551  mov     rbx, rdx
0x1800eb554  mov     r15, [rbp+4Fh+arg_20]
0x1800eb558  xor     r13d, r13d
0x1800eb55b  test    r9, r9
0x1800eb55e  jz      short loc_1800EB563
0x1800eb560  mov     [r9], r13
0x1800eb563  test    r15, r15
0x1800eb566  jz      short loc_1800EB56B
0x1800eb568  mov     [r15], r13
0x1800eb56b  mov     [rbp+4Fh+var_A0], r13
0x1800eb56f  lea     r8, [rbp+4Fh+var_A0]; struct ICbsPackage **
0x1800eb573  lea     rdx, aProduct; "@Product"
0x1800eb57a  call    ?OpenPackage@CArbiterCbsClient@@QEAAJQEB_WPEAPEAUICbsPackage@@@Z; CArbiterCbsClient::OpenPackage(wchar_t const * const,ICbsPackage * *)
0x1800eb57f  mov     edi, eax
0x1800eb581  test    eax, eax
0x1800eb583  jns     loc_1800EBDC7
0x1800eb589  test    sil, sil
0x1800eb58c  jz      loc_1800EBD43
0x1800eb592  mov     [rsp+120h+var_D0], r13
0x1800eb597  mov     [rbp+4Fh+var_A8], r13
0x1800eb59b  mov     dword ptr [rbp+4Fh+var_B8], r13d
0x1800eb59f  mov     [rbp+4Fh+var_98], r13d
0x1800eb5a3  mov     [rsp+120h+var_D8], r13
0x1800eb5a8  mov     dword ptr [rbp+4Fh+pv], r13d
0x1800eb5ac  mov     [rsp+120h+lpString2], r13
0x1800eb5b1  lea     rcx, [rbp+4Fh+String1]
0x1800eb5b5  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800eb5ba  nop
0x1800eb5bb  mov     byte ptr [rsp+120h+var_F8], 1
0x1800eb5c0  lea     rax, [rsp+120h+var_D0]
0x1800eb5c5  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x1800eb5ca  lea     r9, aEditionid_0; "EditionID"
0x1800eb5d1  lea     rsi, aMicrosoftWindo_10; "Microsoft\\Windows NT\\CurrentVersion"
0x1800eb5d8  mov     r8, rsi
0x1800eb5db  xor     edx, edx
0x1800eb5dd  mov     rcx, rbx
0x1800eb5e0  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x1800eb5e5  mov     edi, eax
0x1800eb5e7  test    eax, eax
0x1800eb5e9  jns     loc_1800EB6B3
0x1800eb5ef  mov     dword ptr [rbp+4Fh+var_B8], eax
0x1800eb5f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb5f9  test    rcx, rcx
0x1800eb5fc  jz      short loc_1800EB63D
0x1800eb5fe  lea     r9, aFailedReadingE_0; "Failed reading edition id"
0x1800eb605  mov     ebx, 3
0x1800eb60a  mov     r8d, ebx
0x1800eb60d  xor     edx, edx
0x1800eb60f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800eb614  lea     rax, [rbp+4Fh+var_B8]
0x1800eb618  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800eb61c  lea     rax, [rbp+4Fh+var_98]
0x1800eb620  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800eb625  lea     r9, asc_1802C6678; ": {}"
0x1800eb62c  mov     r8d, ebx
0x1800eb62f  mov     dl, 1
0x1800eb631  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb638  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800eb63d  mov     rcx, [rbp+57h]; this
0x1800eb641  mov     r9d, edi; char *
0x1800eb644  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800eb64b  mov     edx, 440h; void *
0x1800eb650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb655  nop
0x1800eb656  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800eb65a  test    rcx, rcx
0x1800eb65d  jz      short loc_1800EB664
0x1800eb65f  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800eb664  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800eb668  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800eb66d  nop
0x1800eb66e  mov     rcx, [rbp+4Fh+var_A8]
0x1800eb672  test    rcx, rcx
0x1800eb675  jz      short loc_1800EB684
0x1800eb677  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb67b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb680  mov     [rbp+4Fh+var_A8], r13
0x1800eb684  mov     rcx, [rsp+120h+var_D0]
0x1800eb689  test    rcx, rcx
0x1800eb68c  jz      short loc_1800EB698
0x1800eb68e  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb692  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb697  nop
0x1800eb698  mov     rcx, [rbp+4Fh+var_A0]
0x1800eb69c  test    rcx, rcx
0x1800eb69f  jz      short loc_1800EB6AE
0x1800eb6a1  mov     rax, [rcx]
0x1800eb6a4  mov     rax, [rax+10h]
0x1800eb6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6ad  nop
0x1800eb6ae  jmp     loc_1800EC405
0x1800eb6b3  mov     byte ptr [rsp+120h+var_F8], 1
0x1800eb6b8  lea     rax, [rbp+4Fh+var_B8]
0x1800eb6bc  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x1800eb6c1  lea     r9, aCurrentmajorve; "CurrentMajorVersionNumber"
0x1800eb6c8  mov     r8, rsi
0x1800eb6cb  xor     edx, edx
0x1800eb6cd  mov     rcx, rbx
0x1800eb6d0  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x1800eb6d5  mov     edi, eax
0x1800eb6d7  test    eax, eax
0x1800eb6d9  jns     loc_1800EB7A3
0x1800eb6df  mov     dword ptr [rbp+4Fh+var_B8], eax
0x1800eb6e2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb6e9  test    rcx, rcx
0x1800eb6ec  jz      short loc_1800EB72D
0x1800eb6ee  lea     r9, aFailedReadingC; "Failed reading current major version"
0x1800eb6f5  mov     ebx, 3
0x1800eb6fa  mov     r8d, ebx
0x1800eb6fd  xor     edx, edx
0x1800eb6ff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800eb704  lea     rax, [rbp+4Fh+var_B8]
0x1800eb708  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800eb70c  lea     rax, [rbp+4Fh+var_98]
0x1800eb710  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800eb715  lea     r9, asc_1802C6678; ": {}"
0x1800eb71c  mov     r8d, ebx
0x1800eb71f  mov     dl, 1
0x1800eb721  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb728  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800eb72d  mov     rcx, [rbp+57h]; this
0x1800eb731  mov     r9d, edi; char *
0x1800eb734  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800eb73b  mov     edx, 444h; void *
0x1800eb740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb745  nop
0x1800eb746  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800eb74a  test    rcx, rcx
0x1800eb74d  jz      short loc_1800EB754
0x1800eb74f  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800eb754  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800eb758  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800eb75d  nop
0x1800eb75e  mov     rcx, [rbp+4Fh+var_A8]
0x1800eb762  test    rcx, rcx
0x1800eb765  jz      short loc_1800EB774
0x1800eb767  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb76b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb770  mov     [rbp+4Fh+var_A8], r13
0x1800eb774  mov     rcx, [rsp+120h+var_D0]
0x1800eb779  test    rcx, rcx
0x1800eb77c  jz      short loc_1800EB788
0x1800eb77e  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb782  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb787  nop
0x1800eb788  mov     rcx, [rbp+4Fh+var_A0]
0x1800eb78c  test    rcx, rcx
0x1800eb78f  jz      short loc_1800EB79E
0x1800eb791  mov     rax, [rcx]
0x1800eb794  mov     rax, [rax+10h]
0x1800eb798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb79d  nop
0x1800eb79e  jmp     loc_1800EC405
0x1800eb7a3  mov     byte ptr [rsp+120h+var_F8], 1
0x1800eb7a8  lea     rax, [rbp+4Fh+var_98]
0x1800eb7ac  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x1800eb7b1  lea     r9, aCurrentminorve; "CurrentMinorVersionNumber"
0x1800eb7b8  mov     r8, rsi
0x1800eb7bb  xor     edx, edx
0x1800eb7bd  mov     rcx, rbx
0x1800eb7c0  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x1800eb7c5  mov     edi, eax
0x1800eb7c7  test    eax, eax
0x1800eb7c9  jns     loc_1800EB893
0x1800eb7cf  mov     dword ptr [rbp+4Fh+var_B8], eax
0x1800eb7d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb7d9  test    rcx, rcx
0x1800eb7dc  jz      short loc_1800EB81D
0x1800eb7de  lea     r9, aFailedReadingC_1; "Failed reading current minor version"
0x1800eb7e5  mov     ebx, 3
0x1800eb7ea  mov     r8d, ebx
0x1800eb7ed  xor     edx, edx
0x1800eb7ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800eb7f4  lea     rax, [rbp+4Fh+var_B8]
0x1800eb7f8  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800eb7fc  lea     rax, [rbp+4Fh+var_98]
0x1800eb800  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800eb805  lea     r9, asc_1802C6678; ": {}"
0x1800eb80c  mov     r8d, ebx
0x1800eb80f  mov     dl, 1
0x1800eb811  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb818  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800eb81d  mov     rcx, [rbp+57h]; this
0x1800eb821  mov     r9d, edi; char *
0x1800eb824  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800eb82b  mov     edx, 448h; void *
0x1800eb830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb835  nop
0x1800eb836  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800eb83a  test    rcx, rcx
0x1800eb83d  jz      short loc_1800EB844
0x1800eb83f  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800eb844  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800eb848  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800eb84d  nop
0x1800eb84e  mov     rcx, [rbp+4Fh+var_A8]
0x1800eb852  test    rcx, rcx
0x1800eb855  jz      short loc_1800EB864
0x1800eb857  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb85b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb860  mov     [rbp+4Fh+var_A8], r13
0x1800eb864  mov     rcx, [rsp+120h+var_D0]
0x1800eb869  test    rcx, rcx
0x1800eb86c  jz      short loc_1800EB878
0x1800eb86e  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb872  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb877  nop
0x1800eb878  mov     rcx, [rbp+4Fh+var_A0]
0x1800eb87c  test    rcx, rcx
0x1800eb87f  jz      short loc_1800EB88E
0x1800eb881  mov     rax, [rcx]
0x1800eb884  mov     rax, [rax+10h]
0x1800eb888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb88d  nop
0x1800eb88e  jmp     loc_1800EC405
0x1800eb893  mov     byte ptr [rsp+120h+var_F8], 1
0x1800eb898  lea     rax, [rsp+120h+var_D8]
0x1800eb89d  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x1800eb8a2  lea     r9, aCurrentbuildnu; "CurrentBuildNumber"
0x1800eb8a9  mov     r8, rsi
0x1800eb8ac  xor     edx, edx
0x1800eb8ae  mov     rcx, rbx
0x1800eb8b1  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x1800eb8b6  mov     edi, eax
0x1800eb8b8  test    eax, eax
0x1800eb8ba  jns     loc_1800EB998
0x1800eb8c0  mov     dword ptr [rbp+4Fh+var_B8], eax
0x1800eb8c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb8ca  test    rcx, rcx
0x1800eb8cd  jz      short loc_1800EB90E
0x1800eb8cf  lea     r9, aFailedReadingC_0; "Failed reading current build number"
0x1800eb8d6  mov     ebx, 3
0x1800eb8db  mov     r8d, ebx
0x1800eb8de  xor     edx, edx
0x1800eb8e0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800eb8e5  lea     rax, [rbp+4Fh+var_B8]
0x1800eb8e9  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800eb8ed  lea     rax, [rbp+4Fh+var_98]
0x1800eb8f1  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800eb8f6  lea     r9, asc_1802C6678; ": {}"
0x1800eb8fd  mov     r8d, ebx
0x1800eb900  mov     dl, 1
0x1800eb902  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eb909  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800eb90e  mov     rcx, [rbp+57h]; this
0x1800eb912  mov     r9d, edi; char *
0x1800eb915  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800eb91c  mov     edx, 44Ch; void *
0x1800eb921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb926  nop
0x1800eb927  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800eb92b  test    rcx, rcx
0x1800eb92e  jz      short loc_1800EB935
0x1800eb930  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800eb935  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800eb939  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800eb93e  nop
0x1800eb93f  mov     rcx, [rsp+120h+var_D8]
0x1800eb944  test    rcx, rcx
0x1800eb947  jz      short loc_1800EB953
0x1800eb949  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb94d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb952  nop
0x1800eb953  mov     rcx, [rbp+4Fh+var_A8]
0x1800eb957  test    rcx, rcx
0x1800eb95a  jz      short loc_1800EB969
0x1800eb95c  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb960  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb965  mov     [rbp+4Fh+var_A8], r13
0x1800eb969  mov     rcx, [rsp+120h+var_D0]
0x1800eb96e  test    rcx, rcx
0x1800eb971  jz      short loc_1800EB97D
0x1800eb973  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800eb977  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb97c  nop
0x1800eb97d  mov     rcx, [rbp+4Fh+var_A0]
0x1800eb981  test    rcx, rcx
0x1800eb984  jz      short loc_1800EB993
0x1800eb986  mov     rax, [rcx]
0x1800eb989  mov     rax, [rax+10h]
0x1800eb98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb992  nop
0x1800eb993  jmp     loc_1800EC405
  ... truncated ...
```
