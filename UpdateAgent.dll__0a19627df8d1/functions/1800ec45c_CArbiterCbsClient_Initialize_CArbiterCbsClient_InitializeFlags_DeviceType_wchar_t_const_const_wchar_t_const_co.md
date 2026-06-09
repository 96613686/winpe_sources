# CArbiterCbsClient::Initialize(CArbiterCbsClient::InitializeFlags,DeviceType,wchar_t const * const,wchar_t const * const,wchar_t const * const)

- ea: `0x1800ec45c`
- end: `0x1800ed596`
- name: `?Initialize@CArbiterCbsClient@@QEAAJW4InitializeFlags@1@W4DeviceType@@QEB_W22@Z`
- size: `4410`
- prototype: `__int64 __fastcall(__int64, char, int, HMODULE, __int64, wchar_t *pszSrc)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c7604`
- `0x1800d6960`
- `0x1800dbecc`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x180012770`
- `0x1800127a4`
- `0x180023b20`
- `0x1800692fc`
- `0x18008b38c`
- `0x1800ec45c`
- `0x180148614`
- `0x180205280`
- `0x180214bd0`
- `0x180214cd0`
- `0x180214e40`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ec659`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ec672`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ec659`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ec672`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ec77c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ec8bf`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800eca17`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800eca86`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ec77c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ec8bf`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800eca17`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800eca86`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ec633`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ec633`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec5e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec964`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec985`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec5e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec964`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ec985`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ed04c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ed04c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed0da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed157`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed0da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed157`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ecf57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ecf57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eca27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eca96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eca27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eca96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed167`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ed01b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ed01b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed2db`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed32d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed381`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed2db`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed32d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800ed381`

## string_xrefs

- `0x1800ec5dc`: `Cbscore.dll`
- `0x1800ec62c`: `ole32.dll`
- `0x1800ec668`: `CreateItemMoniker`
- `0x1800ec6e7`: `Failed to create moniker`
- `0x1800ec4f9`: `Failed to get directory`
- `0x1800ec956`: `cbs_unittests_offline.dll`
- `0x1800ec617`: `Not able to get active offline session from cbscore.dll, try Running Object Table`
- `0x1800eca71`: `Allowing nested loading of CbsCore.dll`
- `0x1800ec97c`: `servicing_unittests_offline.dll`
- `0x1800ecdc6`: `Failed to create offline session from external stack at {0}.`
- `0x1800ece96`: `Failed to create offline session.`
- `0x1800ecf49`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootInProgress`
- `0x1800ed06c`: `Failed to create session classID`
- `0x1800ed037`: `Failed to create session classID - waiting for a second and trying again`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CArbiterCbsClient::Initialize(__int64 a1, char a2, int a3, HMODULE a4, __int64 a5, wchar_t *pszSrc)
{
  wchar_t *v9; // rcx
  unsigned int v10; // r15d
  int v11; // eax
  unsigned int v12; // ebx
  HMODULE Library; // rax
  HMODULE v15; // rsi
  FARPROC ProcAddress; // r15
  FARPROC v17; // rax
  __int64 (__fastcall *v18)(_QWORD, _QWORD, _QWORD); // rdi
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r15d
  int v22; // eax
  unsigned int v23; // esi
  int v24; // eax
  int v25; // eax
  int OfflineSessionFromExternalStack; // eax
  int OfflineSessionFromStackInImage; // eax
  HRESULT v28; // eax
  IUnknown **v29; // r12
  int v30; // eax
  IUnknown **v31; // r15
  int v32; // eax
  IUnknown *v33; // rsi
  int v34; // eax
  HRESULT v35; // eax
  unsigned int v36; // r13d
  HRESULT v37; // eax
  IUnknown *v38; // rcx
  HRESULT v39; // eax
  int v40; // eax
  int v41; // eax
  int phkResult; // [rsp+28h] [rbp-79h]
  int phkResulta; // [rsp+28h] [rbp-79h]
  int phkResultb; // [rsp+28h] [rbp-79h]
  HMODULE phModule; // [rsp+60h] [rbp-41h] BYREF
  HMODULE v46; // [rsp+68h] [rbp-39h] BYREF
  wchar_t *v47; // [rsp+70h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-29h] BYREF
  __int64 v49; // [rsp+80h] [rbp-21h] BYREF
  __int64 v50; // [rsp+88h] [rbp-19h] BYREF
  _OWORD v51[2]; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+4Fh]

  v9 = pszSrc;
  v47 = pszSrc;
  v10 = 0;
  ppv = 0;
  v51[0] = 0;
  v51[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v51[0]) = 0;
  *(_DWORD *)a1 = a3;
  v49 = 0;
  if ( pszSrc )
  {
    v11 = DirectoryFromPath(pszSrc);
    v12 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v49) = v11;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get directory");
        v46 = (HMODULE)&v49;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v46);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v12,
        phkResult);
      std::wstring::~wstring(v51);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v12;
    }
    v49 = 0;
    v9 = v47;
    if ( v47 )
    {
      if ( *(_DWORD *)a1 == 1 )
      {
        if ( *(_QWORD *)(a1 + 8) )
          goto LABEL_176;
        if ( GetModuleHandleExW(0, L"Cbscore.dll", (HMODULE *)(a1 + 8)) )
        {
          if ( ppv )
            goto LABEL_176;
          if ( (int)CbsGetActiveOfflineSession(*(_QWORD *)(a1 + 8), &ppv) >= 0 )
          {
            *(_BYTE *)(a1 + 40) = 1;
          }
          else
          {
            LogAdapter::TraceInfo<>("Not able to get active offline session from cbscore.dll, try Running Object Table");
            Library = LoadLibraryExW(L"ole32.dll", 0, 0x800u);
            v15 = Library;
            if ( Library )
            {
              ProcAddress = GetProcAddress(Library, "GetRunningObjectTable");
              v17 = GetProcAddress(v15, "CreateItemMoniker");
              v18 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v17;
              if ( ProcAddress && v17 )
              {
                v46 = 0;
                v19 = ((__int64 (__fastcall *)(_QWORD, HMODULE *))ProcAddress)(0, &v46);
                v10 = 0;
                if ( v19 >= 0 )
                {
                  v50 = 0;
                  v20 = v18(0, L"CbsActiveOfflineSession", &v50);
                  v21 = v20;
                  if ( v20 < 0 )
                  {
                    LODWORD(v49) = v20;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create moniker");
                      phModule = (HMODULE)&v49;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&phModule);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x67,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                      (const char *)v21,
                      phkResult);
                    if ( v50 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                      v50 = 0;
                    }
                    if ( v46 )
                    {
                      (*(void (__fastcall **)(HMODULE))(*(_QWORD *)v46 + 16LL))(v46);
                      v46 = 0;
                    }
                    if ( !FreeLibrary(v15) )
                    {
                      GetLastError();
                      __fastfail(7u);
                    }
                    std::wstring::~wstring(v51);
                    if ( ppv )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                    return v21;
                  }
                  if ( ppv )
                    goto LABEL_178;
                  v21 = (*(__int64 (__fastcall **)(HMODULE, __int64, LPVOID *))(*(_QWORD *)v46 + 48LL))(v46, v50, &ppv);
                  if ( (int)(v21 + 0x80000000) >= 0 && v21 != -2147221021 )
                  {
                    LODWORD(v49) = v21;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get CBS session");
                      phModule = (HMODULE)&v49;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&phModule);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x6C,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                      (const char *)v21,
                      phkResult);
                    if ( v50 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                      v50 = 0;
                    }
                    if ( v46 )
                    {
                      (*(void (__fastcall **)(HMODULE))(*(_QWORD *)v46 + 16LL))(v46);
                      v46 = 0;
                    }
                    if ( !FreeLibrary(v15) )
                    {
                      GetLastError();
                      __fastfail(7u);
                    }
                    std::wstring::~wstring(v51);
                    if ( ppv )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                    return v21;
                  }
                  v10 = 0;
                  if ( v50 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                }
                if ( v46 )
                  (*(void (__fastcall **)(HMODULE))(*(_QWORD *)v46 + 16LL))(v46);
              }
              else
              {
                v10 = 0;
              }
            }
            phModule = 0;
            v46 = 0;
            if ( GetModuleHandleExW(2u, L"cbs_unittests_offline.dll", &phModule)
              || GetModuleHandleExW(2u, L"servicing_unittests_offline.dll", &v46) )
            {
              LogAdapter::TraceInfo<>("Allowing nested loading of CbsCore.dll");
            }
            else if ( !ppv )
            {
              LODWORD(v49) = -2147319767;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get CBS session");
                phModule = (HMODULE)&v49;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)&phModule);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x8A,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                (const char *)0x80028029LL,
                phkResult);
              if ( v15 && !FreeLibrary(v15) )
              {
                GetLastError();
                __fastfail(7u);
              }
              std::wstring::~wstring(v51);
              if ( ppv )
                (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
              return 2147647529LL;
            }
            if ( v15 && !FreeLibrary(v15) )
            {
              GetLastError();
              __fastfail(7u);
            }
          }
          if ( ppv )
          {
            if ( !*(_QWORD *)(a1 + 16) )
            {
              v22 = (**(__int64 (__fastcall ***)(LPVOID, GUID *))ppv)(ppv, &GUID_dc95a094_ee0e_4974_9600_027d2321c2d4);
              v23 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v49) = v22;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed querying session7");
                  phModule = (HMODULE)&v49;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)&phModule);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x95,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                  (const char *)v23,
                  phkResult);
                std::wstring::~wstring(v51);
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                return v23;
              }
              if ( !*(_QWORD *)(a1 + 24) )
              {
                v24 = (**(__int64 (__fastcall ***)(LPVOID, GUID *))ppv)(ppv, &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22);
                v23 = v24;
                if ( v24 < 0 )
                {
                  LODWORD(v49) = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed querying session9");
                    phModule = (HMODULE)&v49;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&phModule);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x96,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                    (const char *)v23,
                    phkResult);
                  std::wstring::~wstring(v51);
                  if ( ppv )
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                  return v23;
                }
                if ( !*(_QWORD *)(a1 + 32) )
                {
                  v25 = (**(__int64 (__fastcall ***)(LPVOID, GUID *))ppv)(
                          ppv,
                          &GUID_f112757a_565b_4260_bd05_9fa34417349a);
                  v23 = v25;
                  if ( v25 < 0 )
                  {
                    LODWORD(v49) = v25;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed querying session10");
                      phModule = (HMODULE)&v49;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&phModule);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x97,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                      (const char *)v23,
                      phkResult);
                    std::wstring::~wstring(v51);
                    if ( ppv )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                    return v23;
                  }
                  std::wstring::~wstring(v51);
                  if ( ppv )
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                  return 0;
                }
              }
            }
            goto LABEL_176;
          }
        }
        v9 = v47;
      }
    }
  }
  if ( (a2 & 1) == 0 && v9 )
  {
    if ( a4 )
    {
      v46 = a4;
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "Loading servicing stack: {0}, for offline Windows: {1}",
        &v46,
        &v47);
      if ( ppv )
      {
LABEL_179:
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x1800ED595LL);
      }
      OfflineSessionFromExternalStack = CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(
                                          (CbsOfflineUtil *)&vCbsOfflineUtil,
                                          (const wchar_t *)v46,
                                          (struct ICbsSession **)&ppv);
      v23 = OfflineSessionFromExternalStack;
      if ( OfflineSessionFromExternalStack < 0 )
      {
        LODWORD(v49) = OfflineSessionFromExternalStack;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create offline session from external stack at {0}.",
            (__int64)&v46);
          phModule = (HMODULE)&v49;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&phModule);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
          (const char *)v23,
          phkResult);
        std::wstring::~wstring(v51);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v23;
      }
      goto LABEL_109;
    }
    LogAdapter::TraceInfo<wchar_t const *>("Loading servicing stack from image at: {0}", &v47);
    if ( !ppv )
    {
      OfflineSessionFromStackInImage = CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(
                                         (CbsOfflineUtil *)&vCbsOfflineUtil,
                                         0,
                                         v47,
                                         (struct ICbsSession **)&ppv);
      v23 = OfflineSessionFromStackInImage;
      if ( OfflineSessionFromStackInImage < 0 )
      {
        LODWORD(v49) = OfflineSessionFromStackInImage;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create offline session.");
          phModule = (HMODULE)&v49;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&phModule);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
          (const char *)v23,
          phkResult);
        std::wstring::~wstring(v51);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v23;
      }
LABEL_109:
      SetCbsCoreCustomLogging();
LABEL_137:
      v29 = (IUnknown **)(a1 + 16);
      if ( !*(_QWORD *)(a1 + 16) )
      {
        v30 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                ppv,
                &GUID_dc95a094_ee0e_4974_9600_027d2321c2d4,
                a1 + 16);
        v23 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v49) = v30;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed querying ICbsSession7");
            phModule = (HMODULE)&v49;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&phModule);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v23,
            phkResult);
          std::wstring::~wstring(v51);
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          return v23;
        }
        v31 = (IUnknown **)(a1 + 24);
        if ( !*(_QWORD *)(a1 + 24) )
        {
          v32 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                  ppv,
                  &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
                  a1 + 24);
          if ( v32 < 0 )
            LogAdapter::TraceAtLevelHr<long,>(
              3,
              (unsigned int)v32,
              "arbiter: failed to QueryInterface for ICbsSession9");
          if ( !*(_QWORD *)(a1 + 32) )
          {
            v33 = 0;
            v34 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                    ppv,
                    &GUID_f112757a_565b_4260_bd05_9fa34417349a,
                    a1 + 32);
            if ( v34 < 0 )
              LogAdapter::TraceAtLevelHr<long,>(
                3,
                (unsigned int)v34,
                "arbiter: failed to QueryInterface for ICbsSession10");
            v35 = CoSetProxyBlanket(*v29, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
            if ( v35 < 0 )
              LogAdapter::TraceAtLevelHr<long,>(
                2,
                (unsigned int)v35,
                "Not able to set proxy blanket on ICbsSession7 object");
            v36 = (a2 & 2) << 8;
            if ( *v31 )
            {
              v37 = CoSetProxyBlanket(*v31, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
              if ( v37 < 0 )
                LogAdapter::TraceAtLevelHr<long,>(
                  2,
                  (unsigned int)v37,
                  "Not able to set proxy blanket on ICbsSession9 object");
              v33 = *v31;
            }
            v38 = *(IUnknown **)(a1 + 32);
            if ( v38 )
            {
              v39 = CoSetProxyBlanket(v38, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
              if ( v39 < 0 )
                LogAdapter::TraceAtLevelHr<long,>(
                  2,
                  (unsigned int)v39,
                  "Not able to set proxy blanket on ICbsSession10 object");
              v33 = *(IUnknown **)(a1 + 32);
            }
            if ( v33 )
            {
              phkResulta = (int)v47;
              v40 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, __int64))v33->lpVtbl[6].AddRef)(
                      v33,
                      v36,
                      L"Arbiter",
                      v49);
              v23 = v40;
              if ( v40 < 0 )
              {
                LODWORD(v49) = v40;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed initiating session");
                  phModule = (HMODULE)&v49;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)&phModule);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x133,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                  (const char *)v23,
                  phkResulta);
                std::wstring::~wstring(v51);
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                return v23;
              }
            }
            else
            {
              phkResultb = (int)v47;
              v41 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, __int64))(*v29)->lpVtbl[1].QueryInterface)(
                      *v29,
                      v36,
                      L"Arbiter",
                      v49);
              v23 = v41;
              if ( v41 < 0 )
              {
                LODWORD(v49) = v41;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed initiating session");
                  phModule = (HMODULE)&v49;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)&phModule);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x138,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
                  (const char *)v23,
                  phkResultb);
                std::wstring::~wstring(v51);
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                return v23;
              }
            }
            std::wstring::~wstring(v51);
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            return 0;
          }
        }
      }
    }
LABEL_176:
    INTERNAL_ERROR_ACTION(-1073741595);
LABEL_177:
    INTERNAL_ERROR_ACTION(-1073741595);
LABEL_178:
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_179;
  }
  LogAdapter::TraceInfo<>("Using online (TI hosted) servicing stack");
  v46 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\RebootInProgress",
          0,
          0x20019u,
          (PHKEY)&v46) )
  {
    LogAdapter::TraceInfo<>("arbiter: CBS reboot is in progress; skipping online session creation.");
    if ( v46 )
    {
      if ( ((unsigned __int64)v46 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey((HKEY)v46) )
      {
        GetLastError();
        __fastfail(7u);
      }
      v46 = 0;
    }
    std::wstring::~wstring(v51);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 2147943515LL;
  }
  while ( 1 )
  {
    if ( ppv )
      goto LABEL_177;
    v28 = CoCreateInstance(
            &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
            0,
            0x15u,
            &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
            &ppv);
    v23 = v28;
    if ( v28 >= 0 )
    {
      if ( v46 && ((unsigned __int64)v46 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey((HKEY)v46) )
      {
        GetLastError();
        __fastfail(7u);
      }
      goto LABEL_137;
    }
    if ( v10 >= 0xA )
      break;
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      (unsigned int)v28,
      "Failed to create session classID - waiting for a second and trying again");
    Sleep(0x3E8u);
    ++v10;
  }
  LODWORD(v49) = v28;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create session classID");
    phModule = (HMODULE)&v49;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)&phModule);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDC,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
    (const char *)v23,
    phkResult);
  if ( v46 )
  {
    if ( ((unsigned __int64)v46 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey((HKEY)v46) )
    {
      GetLastError();
      __fastfail(7u);
    }
    v46 = 0;
  }
  std::wstring::~wstring(v51);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v23;
}

```

## disassembly

```asm
0x1800ec45c  mov     rax, rsp
0x1800ec45f  push    rbp
0x1800ec460  push    rsi
0x1800ec461  push    rdi
0x1800ec462  push    r12
0x1800ec464  push    r13
0x1800ec466  push    r14
0x1800ec468  push    r15
0x1800ec46a  lea     rbp, [rax-4Fh]
0x1800ec46e  sub     rsp, 0B0h
0x1800ec475  mov     [rbp+47h+var_98], 0FFFFFFFFFFFFFFFEh
0x1800ec47d  mov     [rax+10h], rbx
0x1800ec481  mov     rax, cs:__security_cookie
0x1800ec488  xor     rax, rsp
0x1800ec48b  mov     [rbp+47h+var_38], rax
0x1800ec48f  mov     r12, r9
0x1800ec492  mov     r13d, edx
0x1800ec495  mov     r14, rcx
0x1800ec498  mov     rcx, [rbp+47h+pszSrc]; pszSrc
0x1800ec49c  mov     [rbp+47h+var_78], rcx
0x1800ec4a0  xor     r15d, r15d
0x1800ec4a3  mov     [rbp+47h+ppv], r15
0x1800ec4a7  mov     ebx, r15d
0x1800ec4aa  mov     [rbp+47h+var_A0], rbx
0x1800ec4ae  xorps   xmm0, xmm0
0x1800ec4b1  movups  [rbp+47h+var_58], xmm0
0x1800ec4b5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ec4bd  movdqu  [rbp+47h+var_48], xmm1
0x1800ec4c2  mov     word ptr [rbp+47h+var_58], r15w
0x1800ec4c7  mov     [r14], r8d
0x1800ec4ca  mov     [rbp+47h+var_68], r15
0x1800ec4ce  test    rcx, rcx
0x1800ec4d1  jz      loc_1800ECD4D
0x1800ec4d7  lea     rdx, [rbp+47h+var_A0]
0x1800ec4db  call    DirectoryFromPath
0x1800ec4e0  mov     ebx, eax
0x1800ec4e2  test    eax, eax
0x1800ec4e4  jns     loc_1800EC5AD
0x1800ec4ea  mov     dword ptr [rbp+47h+var_68], eax
0x1800ec4ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec4f4  test    rcx, rcx
0x1800ec4f7  jz      short loc_1800EC537
0x1800ec4f9  lea     r9, aFailedToGetDir_1; "Failed to get directory"
0x1800ec500  lea     edi, [r15+3]
0x1800ec504  mov     r8d, edi
0x1800ec507  xor     edx, edx
0x1800ec509  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ec50e  lea     rax, [rbp+47h+var_68]
0x1800ec512  mov     [rbp+47h+var_80], rax
0x1800ec516  lea     rax, [rbp+47h+var_80]
0x1800ec51a  mov     [rsp+0E0h+phkResult], rax; int
0x1800ec51f  lea     r9, asc_1802C6678; ": {}"
0x1800ec526  mov     r8d, edi
0x1800ec529  mov     dl, 1
0x1800ec52b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec532  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ec537  mov     rcx, [rbp+4Fh]; this
0x1800ec53b  mov     r9d, ebx; char *
0x1800ec53e  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800ec545  mov     edx, 3Ch ; '<'; void *
0x1800ec54a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec54f  nop
0x1800ec550  lea     rcx, [rbp+47h+var_58]; void *
0x1800ec554  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ec559  nop
0x1800ec55a  mov     rcx, [rbp+47h+var_A0]
0x1800ec55e  test    rcx, rcx
0x1800ec561  jz      short loc_1800EC56D
0x1800ec563  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800ec567  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ec56c  nop
0x1800ec56d  mov     rcx, [rbp+47h+ppv]
0x1800ec571  test    rcx, rcx
0x1800ec574  jz      short loc_1800EC583
0x1800ec576  mov     rax, [rcx]
0x1800ec579  mov     rax, [rax+10h]
0x1800ec57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec582  nop
0x1800ec583  mov     eax, ebx
0x1800ec585  mov     rcx, [rbp+47h+var_38]
0x1800ec589  xor     rcx, rsp; StackCookie
0x1800ec58c  call    __security_check_cookie
0x1800ec591  mov     rbx, [rsp+0E0h+arg_8]
0x1800ec599  add     rsp, 0B0h
0x1800ec5a0  pop     r15
0x1800ec5a2  pop     r14
0x1800ec5a4  pop     r13
0x1800ec5a6  pop     r12
0x1800ec5a8  pop     rdi
0x1800ec5a9  pop     rsi
0x1800ec5aa  pop     rbp
0x1800ec5ab  retn
0x1800ec5ad  mov     rbx, [rbp+47h+var_A0]
0x1800ec5b1  mov     [rbp+47h+var_68], rbx
0x1800ec5b5  mov     rcx, [rbp+47h+var_78]
0x1800ec5b9  test    rcx, rcx
0x1800ec5bc  jz      loc_1800ECD4D
0x1800ec5c2  cmp     dword ptr [r14], 1
0x1800ec5c6  jnz     loc_1800ECD4D
0x1800ec5cc  lea     rdi, [r14+8]
0x1800ec5d0  cmp     [rdi], r15
0x1800ec5d3  jnz     loc_1800ED56A
0x1800ec5d9  mov     r8, rdi; phModule
0x1800ec5dc  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x1800ec5e3  xor     ecx, ecx; dwFlags
0x1800ec5e5  call    cs:__imp_GetModuleHandleExW
0x1800ec5ec  nop     dword ptr [rax+rax+00h]
0x1800ec5f1  test    eax, eax
0x1800ec5f3  jz      loc_1800ECD49
0x1800ec5f9  cmp     [rbp+47h+ppv], r15
0x1800ec5fd  jnz     loc_1800ED56A
0x1800ec603  lea     rdx, [rbp+47h+ppv]
0x1800ec607  mov     rcx, [rdi]
0x1800ec60a  call    CbsGetActiveOfflineSession
0x1800ec60f  test    eax, eax
0x1800ec611  jns     loc_1800ECAAB
0x1800ec617  lea     rcx, aNotAbleToGetAc; "Not able to get active offline session "...
0x1800ec61e  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800ec623  nop
0x1800ec624  xor     edx, edx; hFile
0x1800ec626  mov     r8d, 800h; dwFlags
0x1800ec62c  lea     rcx, aOle32Dll; "ole32.dll"
0x1800ec633  call    cs:__imp_LoadLibraryExW
0x1800ec63a  nop     dword ptr [rax+rax+00h]
0x1800ec63f  mov     rsi, rax
0x1800ec642  mov     [rbp+47h+var_90], rax
0x1800ec646  test    rax, rax
0x1800ec649  jz      loc_1800EC94A
0x1800ec64f  lea     rdx, aGetrunningobje; "GetRunningObjectTable"
0x1800ec656  mov     rcx, rax; hModule
0x1800ec659  call    cs:__imp_GetProcAddress
0x1800ec660  nop     dword ptr [rax+rax+00h]
0x1800ec665  mov     r15, rax
0x1800ec668  lea     rdx, aCreateitemmoni; "CreateItemMoniker"
0x1800ec66f  mov     rcx, rsi; hModule
0x1800ec672  call    cs:__imp_GetProcAddress
0x1800ec679  nop     dword ptr [rax+rax+00h]
0x1800ec67e  mov     rdi, rax
0x1800ec681  test    r15, r15
0x1800ec684  jz      loc_1800EC947
0x1800ec68a  test    rax, rax
0x1800ec68d  jz      loc_1800EC947
0x1800ec693  mov     [rbp+47h+var_80], 0
0x1800ec69b  lea     rdx, [rbp+47h+var_80]
0x1800ec69f  xor     ecx, ecx
0x1800ec6a1  mov     rax, r15
0x1800ec6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec6a9  xor     r15d, r15d
0x1800ec6ac  test    eax, eax
0x1800ec6ae  js      loc_1800EC92F
0x1800ec6b4  mov     [rbp+47h+var_60], r15
0x1800ec6b8  lea     r8, [rbp+47h+var_60]
0x1800ec6bc  lea     rdx, aCbsactiveoffli; "CbsActiveOfflineSession"
0x1800ec6c3  xor     ecx, ecx
0x1800ec6c5  mov     rax, rdi
0x1800ec6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec6cd  mov     r15d, eax
0x1800ec6d0  test    eax, eax
0x1800ec6d2  jns     loc_1800EC7D6
0x1800ec6d8  mov     dword ptr [rbp+47h+var_68], eax
0x1800ec6db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec6e2  test    rcx, rcx
0x1800ec6e5  jz      short loc_1800EC726
0x1800ec6e7  lea     r9, aFailedToCreate_9; "Failed to create moniker"
0x1800ec6ee  mov     edi, 3
0x1800ec6f3  mov     r8d, edi
0x1800ec6f6  xor     edx, edx
0x1800ec6f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ec6fd  lea     rax, [rbp+47h+var_68]
0x1800ec701  mov     [rbp+47h+phModule], rax
0x1800ec705  lea     rax, [rbp+47h+phModule]
0x1800ec709  mov     [rsp+0E0h+phkResult], rax; int
0x1800ec70e  lea     r9, asc_1802C6678; ": {}"
0x1800ec715  mov     r8d, edi
0x1800ec718  mov     dl, 1
0x1800ec71a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec721  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ec726  mov     rcx, [rbp+4Fh]; this
0x1800ec72a  mov     r9d, r15d; char *
0x1800ec72d  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800ec734  mov     edx, 67h ; 'g'; void *
0x1800ec739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec73e  nop
0x1800ec73f  mov     rcx, [rbp+47h+var_60]
0x1800ec743  test    rcx, rcx
0x1800ec746  jz      short loc_1800EC75C
0x1800ec748  mov     rax, [rcx]
0x1800ec74b  mov     rax, [rax+10h]
0x1800ec74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec754  mov     [rbp+47h+var_60], 0
0x1800ec75c  mov     rcx, [rbp+47h+var_80]
0x1800ec760  test    rcx, rcx
0x1800ec763  jz      short loc_1800EC779
0x1800ec765  mov     rax, [rcx]
0x1800ec768  mov     rax, [rax+10h]
0x1800ec76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec771  mov     [rbp+47h+var_80], 0
0x1800ec779  mov     rcx, rsi; hLibModule
0x1800ec77c  call    cs:__imp_FreeLibrary
0x1800ec783  nop     dword ptr [rax+rax+00h]
0x1800ec788  test    eax, eax
0x1800ec78a  jnz     short loc_1800EC79F
0x1800ec78c  call    cs:__imp_GetLastError
0x1800ec793  nop     dword ptr [rax+rax+00h]
0x1800ec798  mov     ecx, 7
0x1800ec79d  int     29h; Win8: RtlFailFast(ecx)
0x1800ec79f  lea     rcx, [rbp+47h+var_58]; void *
0x1800ec7a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ec7a8  nop
0x1800ec7a9  test    rbx, rbx
0x1800ec7ac  jz      short loc_1800EC7B8
0x1800ec7ae  lea     rcx, [rbx-8]; void *
0x1800ec7b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ec7b7  nop
0x1800ec7b8  mov     rcx, [rbp+47h+ppv]
0x1800ec7bc  test    rcx, rcx
0x1800ec7bf  jz      short loc_1800EC7CE
0x1800ec7c1  mov     rax, [rcx]
0x1800ec7c4  mov     rax, [rax+10h]
0x1800ec7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec7cd  nop
0x1800ec7ce  mov     eax, r15d
0x1800ec7d1  jmp     loc_1800EC585
0x1800ec7d6  cmp     [rbp+47h+ppv], 0
0x1800ec7db  jnz     loc_1800ED580
0x1800ec7e1  mov     rcx, [rbp+47h+var_80]
0x1800ec7e5  mov     rax, [rcx]
0x1800ec7e8  lea     r8, [rbp+47h+ppv]
0x1800ec7ec  mov     rdx, [rbp+47h+var_60]
0x1800ec7f0  mov     rax, [rax+30h]
0x1800ec7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec7f9  mov     r15d, eax
0x1800ec7fc  mov     eax, 80000000h
0x1800ec801  lea     ecx, [r15+rax]
0x1800ec805  test    eax, ecx
0x1800ec807  jnz     loc_1800EC916
0x1800ec80d  cmp     r15d, 800401E3h
0x1800ec814  jz      loc_1800EC916
0x1800ec81a  mov     dword ptr [rbp+47h+var_68], r15d
0x1800ec81e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec825  test    rcx, rcx
0x1800ec828  jz      short loc_1800EC869
0x1800ec82a  lea     r9, aFailedToGetCbs_0; "Failed to get CBS session"
0x1800ec831  mov     edi, 3
0x1800ec836  mov     r8d, edi
0x1800ec839  xor     edx, edx
0x1800ec83b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ec840  lea     rax, [rbp+47h+var_68]
0x1800ec844  mov     [rbp+47h+phModule], rax
0x1800ec848  lea     rax, [rbp+47h+phModule]
0x1800ec84c  mov     [rsp+0E0h+phkResult], rax; int
0x1800ec851  lea     r9, asc_1802C6678; ": {}"
0x1800ec858  mov     r8d, edi
0x1800ec85b  mov     dl, 1
0x1800ec85d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ec864  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ec869  mov     rcx, [rbp+4Fh]; this
0x1800ec86d  mov     r9d, r15d; char *
0x1800ec870  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800ec877  mov     edx, 6Ch ; 'l'; void *
0x1800ec87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec881  nop
0x1800ec882  mov     rcx, [rbp+47h+var_60]
0x1800ec886  test    rcx, rcx
0x1800ec889  jz      short loc_1800EC89F
0x1800ec88b  mov     rax, [rcx]
0x1800ec88e  mov     rax, [rax+10h]
0x1800ec892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec897  mov     [rbp+47h+var_60], 0
0x1800ec89f  mov     rcx, [rbp+47h+var_80]
0x1800ec8a3  test    rcx, rcx
0x1800ec8a6  jz      short loc_1800EC8BC
0x1800ec8a8  mov     rax, [rcx]
0x1800ec8ab  mov     rax, [rax+10h]
0x1800ec8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec8b4  mov     [rbp+47h+var_80], 0
0x1800ec8bc  mov     rcx, rsi; hLibModule
0x1800ec8bf  call    cs:__imp_FreeLibrary
0x1800ec8c6  nop     dword ptr [rax+rax+00h]
0x1800ec8cb  test    eax, eax
0x1800ec8cd  jnz     short loc_1800EC8E2
0x1800ec8cf  call    cs:__imp_GetLastError
0x1800ec8d6  nop     dword ptr [rax+rax+00h]
0x1800ec8db  mov     ecx, 7
0x1800ec8e0  int     29h; Win8: RtlFailFast(ecx)
0x1800ec8e2  lea     rcx, [rbp+47h+var_58]; void *
0x1800ec8e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ec8eb  nop
0x1800ec8ec  test    rbx, rbx
0x1800ec8ef  jz      short loc_1800EC8FB
0x1800ec8f1  lea     rcx, [rbx-8]; void *
0x1800ec8f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ec8fa  nop
0x1800ec8fb  mov     rcx, [rbp+47h+ppv]
0x1800ec8ff  test    rcx, rcx
0x1800ec902  jz      short loc_1800EC911
0x1800ec904  mov     rax, [rcx]
0x1800ec907  mov     rax, [rax+10h]
0x1800ec90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec910  nop
  ... truncated ...
```
