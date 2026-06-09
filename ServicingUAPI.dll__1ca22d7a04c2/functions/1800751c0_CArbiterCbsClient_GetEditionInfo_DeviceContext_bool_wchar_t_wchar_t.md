# CArbiterCbsClient::GetEditionInfo(DeviceContext *,bool,wchar_t * *,wchar_t * *)

- ea: `0x1800751c0`
- end: `0x1800760fb`
- name: `?GetEditionInfo@CArbiterCbsClient@@QEAAJPEAVDeviceContext@@_NPEAPEA_W2@Z`
- size: `3899`
- prototype: `__int64 __fastcall(CArbiterCbsClient *__hidden this, struct DeviceContext *, bool, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008c588`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800126b8`
- `0x18003d670`
- `0x18003ddc8`
- `0x1800727f0`
- `0x180073f9c`
- `0x1800746f0`
- `0x1800751c0`
- `0x180077654`
- `0x18007bc08`
- `0x18007bdb0`
- `0x1800ebb74`
- `0x180112454`
- `0x1801126e4`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007577a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007577a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800757ce`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007589a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007598a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800757ce`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007589a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007598a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180075750`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180075750`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007597a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007597a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075947`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075947`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075c80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075e06`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075c80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076087`

## string_xrefs

- `0x180075396`: `Failed reading current major version`
- `0x1800752a6`: `Failed reading edition id`
- `0x180075577`: `Failed reading current build number`
- `0x180075486`: `Failed reading current minor version`
- `0x180075770`: `GetCompositionEditionForVirtualEdition`
- `0x180075749`: `pkeyhelper.dll`
- `0x18007567b`: `Failed reading UBR`

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
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  HMODULE Library; // rax
  const char *v20; // r9
  HMODULE v21; // rdi
  FARPROC ProcAddress; // rax
  const char *v23; // r9
  wchar_t *v24; // rbx
  int v25; // eax
  unsigned int v26; // esi
  wchar_t *v28; // rsi
  int v29; // eax
  unsigned int v30; // r14d
  wchar_t *v31; // rax
  _DWORD *v32; // r14
  struct _RTL_CRITICAL_SECTION *v33; // r15
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  LPCWCH v39; // rbx
  __int64 v40; // rdx
  void (*v41)(void); // rax
  LPCWCH v42; // rbx
  unsigned __int64 v43; // rax
  __int64 v44; // rdx
  const WCHAR *v45; // rdi
  __int64 v46; // rdx
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // eax
  __int64 v50; // rdx
  LPCWCH *bIgnoreCase; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCasea; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCaseb; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCasec; // [rsp+28h] [rbp-B1h]
  void *bIgnoreCased; // [rsp+28h] [rbp-B1h]
  int bIgnoreCasee; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCasef; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCaseg; // [rsp+28h] [rbp-B1h]
  LPCWCH *bIgnoreCaseh; // [rsp+28h] [rbp-B1h]
  wchar_t **v60; // [rsp+30h] [rbp-A9h]
  __int64 v61; // [rsp+38h] [rbp-A1h]
  LPCWCH lpString2; // [rsp+48h] [rbp-91h] BYREF
  wchar_t *v63; // [rsp+50h] [rbp-89h] BYREF
  wchar_t *v64[3]; // [rsp+58h] [rbp-81h] BYREF
  wchar_t *v65; // [rsp+70h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-61h] BYREF
  wchar_t *v67; // [rsp+80h] [rbp-59h] BYREF
  struct ICbsPackage *v68; // [rsp+88h] [rbp-51h] BYREF
  int v69[2]; // [rsp+90h] [rbp-49h] BYREF
  WCHAR String1[28]; // [rsp+98h] [rbp-41h] BYREF
  LPVOID v71; // [rsp+D0h] [rbp-9h]
  WCHAR v72[8]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+57h]

  v64[1] = (wchar_t *)-2LL;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v68 = 0;
  v8 = CArbiterCbsClient::OpenPackage(this, L"@Product", &v68);
  if ( (v8 & 0x80000000) == 0 )
  {
    pv = 0;
    v35 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(*(_QWORD *)v68 + 32LL))(v68, 1, &pv);
    v8 = v35;
    if ( v35 < 0 )
    {
      LODWORD(v65) = v35;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get Edition's keyform");
        lpString2 = (LPCWCH)&v65;
        bIgnoreCase = &lpString2;
        LOBYTE(v36) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v36,
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
      if ( v68 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
      return v8;
    }
    if ( !pv || !*(_WORD *)pv )
    {
      v8 = -2147023728;
      v69[0] = -2147023728;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get Edition's keyform");
        lpString2 = (LPCWCH)v69;
        bIgnoreCase = &lpString2;
        LOBYTE(v50) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v50,
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
      if ( v68 )
        (*(void (__fastcall **)(struct ICbsPackage *, _QWORD))(*(_QWORD *)v68 + 16LL))(v68, *(_QWORD *)v68);
      return v8;
    }
    lpString2 = 0;
    v65 = 0;
    v63 = 0;
    v67 = 0;
    v64[0] = 0;
    v37 = ShredStringIdIntoAttributes(
            (wchar_t *)pv,
            0x7Eu,
            &lpString2,
            (const wchar_t **)&v65,
            (const wchar_t **)&v67,
            (const wchar_t **)&v63,
            (const wchar_t **)v64);
    v8 = v37;
    if ( v37 < 0 )
    {
      LODWORD(v65) = v37;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to shred keyform: {0}",
          &pv,
          v60,
          v61);
        lpString2 = (LPCWCH)&v65;
        bIgnoreCasef = &lpString2;
        LOBYTE(v38) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v38,
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
      if ( v68 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
      return v8;
    }
    wcscpy(String1, L"Microsoft-Windws-");
    v39 = lpString2;
    if ( CompareStringOrdinal(String1, 18, lpString2, 18, 1) == 2 )
    {
      wcscpy(v72, L"Edition");
      v42 = v39 + 18;
      v43 = -1;
      do
        ++v43;
      while ( v42[v43] );
      if ( v43 > 7 )
      {
        v45 = &v42[v43];
        if ( CompareStringOrdinal(v72, 7, v45 - 7, 7, 1) == 2 )
        {
          *((_WORD *)v45 - 7) = 0;
          v63 = 0;
          v47 = SczAllocFromSz(&v63);
          v48 = v47;
          if ( v47 >= 0 )
          {
            lpString2 = 0;
            v49 = SczAllocFromSz(&lpString2);
            v48 = v49;
            if ( v49 >= 0 )
            {
              *a4 = v63;
              *a5 = (wchar_t *)lpString2;
              if ( pv )
                CoTaskMemFree(pv);
              goto LABEL_178;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x49C,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
              (const char *)(unsigned int)v49,
              (int)bIgnoreCaseh);
            if ( lpString2 )
              operator delete((void *)(lpString2 - 4));
            if ( v63 )
              operator delete(v63 - 4);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v68 )
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x499,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
              (const char *)(unsigned int)v47,
              (int)bIgnoreCaseh);
            if ( v63 )
              operator delete(v63 - 4);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v68 )
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
          }
          return v48;
        }
        v8 = -2147418113;
        LODWORD(v65) = -2147418113;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Edition's identity name is not formatted as expected");
          lpString2 = (LPCWCH)&v65;
          bIgnoreCaseh = &lpString2;
          LOBYTE(v46) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v46,
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
        if ( !v68 )
          return v8;
        v41 = *(void (**)(void))(*(_QWORD *)v68 + 16LL);
        goto LABEL_156;
      }
      v8 = -2147418113;
      LODWORD(v65) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Edition's identity name is not formatted as expected");
        lpString2 = (LPCWCH)&v65;
        bIgnoreCaseg = &lpString2;
        LOBYTE(v44) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v44,
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
      LODWORD(v65) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Edition's identity name is not formatted as expected");
        lpString2 = (LPCWCH)&v65;
        bIgnoreCaseg = &lpString2;
        LOBYTE(v40) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v40,
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
    if ( !v68 )
      return v8;
    v41 = *(void (**)(void))(*(_QWORD *)v68 + 16LL);
LABEL_156:
    v41();
    return v8;
  }
  if ( !a3 )
  {
    LODWORD(v65) = v8;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting edition package");
      lpString2 = (LPCWCH)&v65;
      bIgnoreCase = &lpString2;
      LOBYTE(v34) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v34,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x464,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCase);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  v64[0] = 0;
  v67 = 0;
  LODWORD(v65) = 0;
  v69[0] = 0;
  v63 = 0;
  LODWORD(pv) = 0;
  lpString2 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>>>(String1);
  bIgnoreCasea = v64;
  RegValue = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"EditionID");
  v8 = RegValue;
  if ( RegValue < 0 )
  {
    LODWORD(v65) = RegValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading edition id");
      *(_QWORD *)v69 = &v65;
      bIgnoreCasea = v69;
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
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v64[0] )
      operator delete(v64[0] - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  bIgnoreCaseb = &v65;
  v11 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMajorVersionNumber");
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v65) = v11;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed reading current major version");
      *(_QWORD *)v69 = &v65;
      bIgnoreCaseb = v69;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCaseb);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v64[0] )
      operator delete(v64[0] - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  v13 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMinorVersionNumber");
  v8 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v65) = v13;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed reading current minor version");
      *(_QWORD *)v69 = &v65;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)v69);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v64[0] )
      operator delete(v64[0] - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  bIgnoreCasec = &v63;
  v15 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentBuildNumber");
  v8 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v65) = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading current build number");
      *(_QWORD *)v69 = &v65;
      bIgnoreCasec = v69;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v16,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44C,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCasec);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v63 )
      operator delete(v63 - 4);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v64[0] )
      operator delete(v64[0] - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  bIgnoreCased = &pv;
  v17 = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"UBR");
  v8 = v17;
  if ( v17 < 0 )
  {
    LODWORD(v65) = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading UBR");
      *(_QWORD *)v69 = &v65;
      bIgnoreCased = v69;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v18,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x450,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v8,
      (int)bIgnoreCased);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v63 )
      operator delete(v63 - 4);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v64[0] )
      operator delete(v64[0] - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v8;
  }
  Library = LoadLibraryExW(L"pkeyhelper.dll", 0, 0);
  v21 = Library;
  v64[2] = (wchar_t *)Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x454,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      v20);
  ProcAddress = GetProcAddress(Library, "GetCompositionEditionForVirtualEdition");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      v23);
  *(_QWORD *)v72 = 0;
  v24 = v64[0];
  v25 = ((__int64 (__fastcall *)(wchar_t *, wchar_t **))ProcAddress)(v64[0], &v67);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45A,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)(unsigned int)v25,
      (int)&pv);
    FreeLibrary(v21);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( v63 )
      operator delete(v63 - 4);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v24 )
      operator delete(v24 - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v26;
  }
  v28 = v63;
  bIgnoreCasee = (int)v63;
  v29 = SczAllocFormatted(&lpString2, L"%lu.%lu.%s.%lu", (unsigned int)v65, (unsigned int)v69[0]);
  v30 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)(unsigned int)v29,
      bIgnoreCasee);
    FreeLibrary(v21);
    if ( v71 )
      tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
    if ( lpString2 )
      operator delete((void *)(lpString2 - 4));
    if ( v28 )
      operator delete(v28 - 4);
    if ( v67 )
    {
      operator delete(v67 - 4);
      v67 = 0;
    }
    if ( v24 )
      operator delete(v24 - 4);
    if ( v68 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
    return v30;
  }
  v31 = v67;
  v67 = 0;
  *a4 = v31;
  *a5 = (wchar_t *)lpString2;
  v32 = v71;
  v33 = (struct _RTL_CRITICAL_SECTION *)((char *)v71 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)v71 + 5);
  v32[18] |= 0x300u;
  if ( *((_QWORD *)v32 + 31) )
    tip2::details::shared_data<1,0,0>::complete_helper(v32 + 2, 2);
  if ( v33 )
    LeaveCriticalSection(v33);
  FreeLibrary(v21);
  if ( v71 )
    tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(v71);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&String1[4]);
  if ( v28 )
    operator delete(v28 - 4);
  if ( v67 )
  {
    operator delete(v67 - 4);
    v67 = 0;
  }
  if ( v24 )
    operator delete(v24 - 4);
LABEL_178:
  if ( v68 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v68 + 16LL))(v68);
  return 0;
}

```

## disassembly

```asm
0x1800751c0  mov     rax, rsp
0x1800751c3  push    rbp
0x1800751c4  push    rsi
0x1800751c5  push    rdi
0x1800751c6  push    r12
0x1800751c8  push    r13
0x1800751ca  push    r14
0x1800751cc  push    r15
0x1800751ce  lea     rbp, [rax-57h]
0x1800751d2  sub     rsp, 0F0h
0x1800751d9  mov     [rbp+4Fh+var_C8], 0FFFFFFFFFFFFFFFEh
0x1800751e1  mov     [rax+18h], rbx
0x1800751e5  mov     rax, cs:__security_cookie
0x1800751ec  xor     rax, rsp
0x1800751ef  mov     [rbp+4Fh+var_40], rax
0x1800751f3  mov     r12, r9
0x1800751f6  mov     sil, r8b
0x1800751f9  mov     rbx, rdx
0x1800751fc  mov     r15, [rbp+4Fh+arg_20]
0x180075200  xor     r13d, r13d
0x180075203  test    r9, r9
0x180075206  jz      short loc_18007520B
0x180075208  mov     [r9], r13
0x18007520b  test    r15, r15
0x18007520e  jz      short loc_180075213
0x180075210  mov     [r15], r13
0x180075213  mov     [rbp+4Fh+var_A0], r13
0x180075217  lea     r8, [rbp+4Fh+var_A0]; struct ICbsPackage **
0x18007521b  lea     rdx, aProduct; "@Product"
0x180075222  call    ?OpenPackage@CArbiterCbsClient@@QEAAJQEB_WPEAPEAUICbsPackage@@@Z; CArbiterCbsClient::OpenPackage(wchar_t const * const,ICbsPackage * *)
0x180075227  mov     edi, eax
0x180075229  test    eax, eax
0x18007522b  jns     loc_180075A6F
0x180075231  test    sil, sil
0x180075234  jz      loc_1800759EB
0x18007523a  mov     [rsp+120h+var_D0], r13
0x18007523f  mov     [rbp+4Fh+var_A8], r13
0x180075243  mov     dword ptr [rbp+4Fh+var_B8], r13d
0x180075247  mov     [rbp+4Fh+var_98], r13d
0x18007524b  mov     [rsp+120h+var_D8], r13
0x180075250  mov     dword ptr [rbp+4Fh+pv], r13d
0x180075254  mov     [rsp+120h+lpString2], r13
0x180075259  lea     rcx, [rbp+4Fh+String1]
0x18007525d  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180075262  nop
0x180075263  mov     byte ptr [rsp+120h+var_F8], 1
0x180075268  lea     rax, [rsp+120h+var_D0]
0x18007526d  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x180075272  lea     r9, aEditionid; "EditionID"
0x180075279  lea     rsi, aMicrosoftWindo_8; "Microsoft\\Windows NT\\CurrentVersion"
0x180075280  mov     r8, rsi
0x180075283  xor     edx, edx
0x180075285  mov     rcx, rbx
0x180075288  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x18007528d  mov     edi, eax
0x18007528f  test    eax, eax
0x180075291  jns     loc_18007535B
0x180075297  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18007529a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800752a1  test    rcx, rcx
0x1800752a4  jz      short loc_1800752E5
0x1800752a6  lea     r9, aFailedReadingE_0; "Failed reading edition id"
0x1800752ad  mov     ebx, 3
0x1800752b2  mov     r8d, ebx
0x1800752b5  xor     edx, edx
0x1800752b7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800752bc  lea     rax, [rbp+4Fh+var_B8]
0x1800752c0  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800752c4  lea     rax, [rbp+4Fh+var_98]
0x1800752c8  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800752cd  lea     r9, asc_1801CAFB4; ": {}"
0x1800752d4  mov     r8d, ebx
0x1800752d7  mov     dl, 1
0x1800752d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800752e0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800752e5  mov     rcx, [rbp+57h]; this
0x1800752e9  mov     r9d, edi; char *
0x1800752ec  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800752f3  mov     edx, 440h; void *
0x1800752f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800752fd  nop
0x1800752fe  mov     rcx, [rbp+4Fh+var_58]; pv
0x180075302  test    rcx, rcx
0x180075305  jz      short loc_18007530C
0x180075307  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x18007530c  lea     rcx, [rbp+4Fh+String1+8]; this
0x180075310  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180075315  nop
0x180075316  mov     rcx, [rbp+4Fh+var_A8]
0x18007531a  test    rcx, rcx
0x18007531d  jz      short loc_18007532C
0x18007531f  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180075323  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075328  mov     [rbp+4Fh+var_A8], r13
0x18007532c  mov     rcx, [rsp+120h+var_D0]
0x180075331  test    rcx, rcx
0x180075334  jz      short loc_180075340
0x180075336  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18007533a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007533f  nop
0x180075340  mov     rcx, [rbp+4Fh+var_A0]
0x180075344  test    rcx, rcx
0x180075347  jz      short loc_180075356
0x180075349  mov     rax, [rcx]
0x18007534c  mov     rax, [rax+10h]
0x180075350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075355  nop
0x180075356  jmp     loc_1800760AD
0x18007535b  mov     byte ptr [rsp+120h+var_F8], 1
0x180075360  lea     rax, [rbp+4Fh+var_B8]
0x180075364  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x180075369  lea     r9, aCurrentmajorve; "CurrentMajorVersionNumber"
0x180075370  mov     r8, rsi
0x180075373  xor     edx, edx
0x180075375  mov     rcx, rbx
0x180075378  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x18007537d  mov     edi, eax
0x18007537f  test    eax, eax
0x180075381  jns     loc_18007544B
0x180075387  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18007538a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180075391  test    rcx, rcx
0x180075394  jz      short loc_1800753D5
0x180075396  lea     r9, aFailedReadingC; "Failed reading current major version"
0x18007539d  mov     ebx, 3
0x1800753a2  mov     r8d, ebx
0x1800753a5  xor     edx, edx
0x1800753a7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800753ac  lea     rax, [rbp+4Fh+var_B8]
0x1800753b0  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800753b4  lea     rax, [rbp+4Fh+var_98]
0x1800753b8  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800753bd  lea     r9, asc_1801CAFB4; ": {}"
0x1800753c4  mov     r8d, ebx
0x1800753c7  mov     dl, 1
0x1800753c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800753d0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800753d5  mov     rcx, [rbp+57h]; this
0x1800753d9  mov     r9d, edi; char *
0x1800753dc  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800753e3  mov     edx, 444h; void *
0x1800753e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800753ed  nop
0x1800753ee  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800753f2  test    rcx, rcx
0x1800753f5  jz      short loc_1800753FC
0x1800753f7  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800753fc  lea     rcx, [rbp+4Fh+String1+8]; this
0x180075400  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180075405  nop
0x180075406  mov     rcx, [rbp+4Fh+var_A8]
0x18007540a  test    rcx, rcx
0x18007540d  jz      short loc_18007541C
0x18007540f  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180075413  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075418  mov     [rbp+4Fh+var_A8], r13
0x18007541c  mov     rcx, [rsp+120h+var_D0]
0x180075421  test    rcx, rcx
0x180075424  jz      short loc_180075430
0x180075426  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18007542a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007542f  nop
0x180075430  mov     rcx, [rbp+4Fh+var_A0]
0x180075434  test    rcx, rcx
0x180075437  jz      short loc_180075446
0x180075439  mov     rax, [rcx]
0x18007543c  mov     rax, [rax+10h]
0x180075440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075445  nop
0x180075446  jmp     loc_1800760AD
0x18007544b  mov     byte ptr [rsp+120h+var_F8], 1
0x180075450  lea     rax, [rbp+4Fh+var_98]
0x180075454  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x180075459  lea     r9, aCurrentminorve; "CurrentMinorVersionNumber"
0x180075460  mov     r8, rsi
0x180075463  xor     edx, edx
0x180075465  mov     rcx, rbx
0x180075468  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x18007546d  mov     edi, eax
0x18007546f  test    eax, eax
0x180075471  jns     loc_18007553B
0x180075477  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18007547a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180075481  test    rcx, rcx
0x180075484  jz      short loc_1800754C5
0x180075486  lea     r9, aFailedReadingC_1; "Failed reading current minor version"
0x18007548d  mov     ebx, 3
0x180075492  mov     r8d, ebx
0x180075495  xor     edx, edx
0x180075497  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007549c  lea     rax, [rbp+4Fh+var_B8]
0x1800754a0  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800754a4  lea     rax, [rbp+4Fh+var_98]
0x1800754a8  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x1800754ad  lea     r9, asc_1801CAFB4; ": {}"
0x1800754b4  mov     r8d, ebx
0x1800754b7  mov     dl, 1
0x1800754b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800754c0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800754c5  mov     rcx, [rbp+57h]; this
0x1800754c9  mov     r9d, edi; char *
0x1800754cc  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800754d3  mov     edx, 448h; void *
0x1800754d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800754dd  nop
0x1800754de  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800754e2  test    rcx, rcx
0x1800754e5  jz      short loc_1800754EC
0x1800754e7  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800754ec  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800754f0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800754f5  nop
0x1800754f6  mov     rcx, [rbp+4Fh+var_A8]
0x1800754fa  test    rcx, rcx
0x1800754fd  jz      short loc_18007550C
0x1800754ff  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180075503  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075508  mov     [rbp+4Fh+var_A8], r13
0x18007550c  mov     rcx, [rsp+120h+var_D0]
0x180075511  test    rcx, rcx
0x180075514  jz      short loc_180075520
0x180075516  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18007551a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007551f  nop
0x180075520  mov     rcx, [rbp+4Fh+var_A0]
0x180075524  test    rcx, rcx
0x180075527  jz      short loc_180075536
0x180075529  mov     rax, [rcx]
0x18007552c  mov     rax, [rax+10h]
0x180075530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075535  nop
0x180075536  jmp     loc_1800760AD
0x18007553b  mov     byte ptr [rsp+120h+var_F8], 1
0x180075540  lea     rax, [rsp+120h+var_D8]
0x180075545  mov     qword ptr [rsp+120h+bIgnoreCase], rax
0x18007554a  lea     r9, aCurrentbuildnu; "CurrentBuildNumber"
0x180075551  mov     r8, rsi
0x180075554  xor     edx, edx
0x180075556  mov     rcx, rbx
0x180075559  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x18007555e  mov     edi, eax
0x180075560  test    eax, eax
0x180075562  jns     loc_180075640
0x180075568  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18007556b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180075572  test    rcx, rcx
0x180075575  jz      short loc_1800755B6
0x180075577  lea     r9, aFailedReadingC_0; "Failed reading current build number"
0x18007557e  mov     ebx, 3
0x180075583  mov     r8d, ebx
0x180075586  xor     edx, edx
0x180075588  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007558d  lea     rax, [rbp+4Fh+var_B8]
0x180075591  mov     qword ptr [rbp+4Fh+var_98], rax
0x180075595  lea     rax, [rbp+4Fh+var_98]
0x180075599  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x18007559e  lea     r9, asc_1801CAFB4; ": {}"
0x1800755a5  mov     r8d, ebx
0x1800755a8  mov     dl, 1
0x1800755aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800755b1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800755b6  mov     rcx, [rbp+57h]; this
0x1800755ba  mov     r9d, edi; char *
0x1800755bd  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800755c4  mov     edx, 44Ch; void *
0x1800755c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800755ce  nop
0x1800755cf  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800755d3  test    rcx, rcx
0x1800755d6  jz      short loc_1800755DD
0x1800755d8  call    ?Release@?$merged_data@U_tip_ProductMonikerEnumHardening@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ProductMonikerEnumHardening,_tip_ProductMonikerEnumHardening>::Release(void)
0x1800755dd  lea     rcx, [rbp+4Fh+String1+8]; this
0x1800755e1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800755e6  nop
0x1800755e7  mov     rcx, [rsp+120h+var_D8]
0x1800755ec  test    rcx, rcx
0x1800755ef  jz      short loc_1800755FB
0x1800755f1  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800755f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800755fa  nop
0x1800755fb  mov     rcx, [rbp+4Fh+var_A8]
0x1800755ff  test    rcx, rcx
0x180075602  jz      short loc_180075611
0x180075604  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180075608  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007560d  mov     [rbp+4Fh+var_A8], r13
0x180075611  mov     rcx, [rsp+120h+var_D0]
0x180075616  test    rcx, rcx
0x180075619  jz      short loc_180075625
0x18007561b  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18007561f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075624  nop
0x180075625  mov     rcx, [rbp+4Fh+var_A0]
0x180075629  test    rcx, rcx
0x18007562c  jz      short loc_18007563B
0x18007562e  mov     rax, [rcx]
0x180075631  mov     rax, [rax+10h]
0x180075635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007563a  nop
0x18007563b  jmp     loc_1800760AD
  ... truncated ...
```
