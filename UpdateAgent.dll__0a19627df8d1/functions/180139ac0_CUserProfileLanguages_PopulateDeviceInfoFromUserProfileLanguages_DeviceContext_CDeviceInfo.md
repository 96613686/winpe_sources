# CUserProfileLanguages::PopulateDeviceInfoFromUserProfileLanguages(DeviceContext *,CDeviceInfo *)

- ea: `0x180139ac0`
- end: `0x18013b344`
- name: `?PopulateDeviceInfoFromUserProfileLanguages@CUserProfileLanguages@@QEAAJPEAVDeviceContext@@PEAVCDeviceInfo@@@Z`
- size: `6276`
- prototype: `__int64 __fastcall(CUserProfileLanguages *__hidden this, struct DeviceContext *, struct CDeviceInfo *)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d53c8`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x1800069e8`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000aa98`
- `0x18000b508`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x180012844`
- `0x180012d94`
- `0x180020324`
- `0x18002297c`
- `0x180023b20`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3ec`
- `0x1800a76dc`
- `0x1800be9e4`
- `0x1800bea88`
- `0x1800ce5fc`
- `0x1800ce6b0`
- `0x1800d1518`
- `0x1800d44a4`
- `0x180138388`
- `0x18013888c`
- `0x180138a14`
- `0x180138b9c`
- `0x180138d44`
- `0x180138dbc`
- `0x1801391b0`
- `0x18013957c`
- `0x180139a38`
- `0x180139ac0`
- `0x18014dba0`
- `0x180175618`
- `0x1801758a8`
- `0x18017600c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180139dbd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a052`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a0fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a1a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a248`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180139dbd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a052`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a0fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a1a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013a248`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139f0e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139f32`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139ffa`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18013a01e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139f0e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139f32`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180139ffa`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18013a01e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180139bee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180139ce8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180139bee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180139ce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139c5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139fa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139c5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139fa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a477`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013a657`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013a657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ac53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ac53`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18013a547`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18013a547`
- `api-ms-win-core-localization-obsolete-l1-2-0!LCIDToLocaleName` at `0x18013ac3f`
- `api-ms-win-core-localization-obsolete-l1-2-0!LCIDToLocaleName` at `0x18013ac3f`

## string_xrefs

- `0x18013ab11`: `InstallLanguage`
- `0x18013ab45`: `Failed reading system language`
- `0x180139be7`: `Bcp47Langs.dll`
- `0x180139ce1`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18013a1da`: `Getting WindowsCreateString function failed`
- `0x18013a19f`: `WindowsCreateString`
- `0x18013a27a`: `Getting WindowsDeleteString function failed`
- `0x18013a23e`: `WindowsDeleteString`
- `0x180139d05`: `api-ms-win-core-winrt-string-l1-1-0.dll is not available, skipping UserProfileLanguage enumeration`
- `0x180139c0b`: `Bcp47Langs.dll is not available, skipping UserProfileLanguage enumeration`
- `0x18013a3c9`: `Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x18013a3ef`: `Failed getting win32 path in software hive`
- `0x18013a6a1`: `Failed getting win32 path in software hive`
- `0x18013ae0f`: `Failed getting win32 path in system hive`
- `0x18013ae63`: `InstallLanguageFallback`
- `0x18013b16b`: `BlockCleanupOfUnusedPreinstalledLangPacks`
- `0x18013b211`: `AllowLanguageFeaturesUninstall`
- `0x18013b19f`: `Failed reading LP cleanup policy, assuming it isn't allowed`
- `0x18013b23f`: `Failed reading Language Feature cleanup policy, assuming it isn't allowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CUserProfileLanguages::PopulateDeviceInfoFromUserProfileLanguages(
        CUserProfileLanguages *this,
        struct DeviceContext *a2,
        struct CDeviceInfo *a3)
{
  HMODULE Library; // rdi
  HMODULE v8; // rbx
  FARPROC ProcAddress; // r13
  const struct std::nothrow_t *v10; // rdx
  signed int LastError; // r14d
  unsigned int v12; // eax
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // r14d
  const struct std::nothrow_t *v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  FARPROC v18; // rax
  unsigned int v19; // eax
  FARPROC v20; // rax
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // eax
  int v23; // edi
  FARPROC v24; // rax
  int v25; // ebx
  unsigned int v26; // eax
  __int64 v27; // rdx
  FARPROC v28; // rax
  unsigned int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  int MultiStringValue; // ebx
  const struct std::nothrow_t *v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  int Win32RegistryPath; // eax
  __int64 v35; // rdx
  DWORD i; // edx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  const wchar_t *v40; // rax
  __int64 v41; // rax
  DWORD v42; // ebx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  int v47; // eax
  unsigned int v48; // r8d
  wchar_t *v49; // rbx
  wchar_t **v50; // rdi
  wchar_t **v51; // rsi
  unsigned int v52; // r8d
  __int64 v53; // rdx
  const struct std::nothrow_t *v54; // rdx
  const struct std::nothrow_t *v55; // rdx
  wchar_t *v56; // rbx
  const wchar_t **v57; // rdi
  const wchar_t **v58; // rsi
  int RegValue; // eax
  wchar_t *v60; // rbx
  LCID v61; // esi
  const struct std::nothrow_t *v62; // rdx
  signed int v63; // edi
  unsigned int v64; // eax
  const struct std::nothrow_t *v65; // rdx
  const struct std::nothrow_t *v66; // rdx
  int v67; // eax
  __int64 v68; // rdx
  int v69; // eax
  unsigned int v70; // r8d
  __int64 v71; // rdi
  bool v72; // r9
  _QWORD *v73; // rsi
  _QWORD *v74; // r13
  int v75; // eax
  const struct std::nothrow_t *v76; // rdx
  const struct std::nothrow_t *v77; // rdx
  const struct std::nothrow_t *v78; // rdx
  unsigned int v79; // eax
  int v80; // r13d
  const wchar_t *v81; // rdi
  unsigned int v82; // eax
  unsigned int v83; // edi
  const wchar_t *v84; // rdi
  const struct std::nothrow_t *v85; // rdx
  const struct std::nothrow_t *v86; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  wchar_t **phkResulta; // [rsp+28h] [rbp-E0h]
  int lpClass; // [rsp+30h] [rbp-D8h]
  bool v90[8]; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE v91; // [rsp+50h] [rbp-B8h] BYREF
  HMODULE v92; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *String[2]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t *v94; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v95[2]; // [rsp+78h] [rbp-90h] BYREF
  const wchar_t *v96; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v97; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v98; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *v99; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v101; // [rsp+A8h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-58h] BYREF
  int v103[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v104[2]; // [rsp+C0h] [rbp-48h] BYREF
  DWORD cchName; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v106; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v107; // [rsp+E0h] [rbp-28h]
  PSID Sid; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v109[24]; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t *v110; // [rsp+110h] [rbp+8h]
  wchar_t **v111; // [rsp+120h] [rbp+18h]
  _BYTE v112[24]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v113; // [rsp+150h] [rbp+48h]
  _QWORD *v114; // [rsp+160h] [rbp+58h]
  WCHAR Name[88]; // [rsp+178h] [rbp+70h] BYREF
  WCHAR StringSid[256]; // [rsp+228h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+470h] [rbp+368h]

  String[1] = (wchar_t *)-2LL;
  if ( *(_BYTE *)a2 )
    return 0;
  v91 = 0;
  lpSubKey = 0;
  v99 = 0;
  hKey = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v109);
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v112);
  v90[0] = 0;
  v98 = 0;
  String[0] = 0;
  memset_0(Name, 0, 0xAAu);
  LogAdapter::TraceInfo<>("arbiter: Populate UserProfile Languages");
  v106 = 0;
  v107 = 0;
  std::wstring::_Construct<1,wchar_t const *>((__int64)&v106, L"TrimLanguagePacksAllowed", 0x18u);
  CDeviceInfo::AddValuePair(a3, &v106, 0);
  std::wstring::~wstring(&v106);
  v106 = 0;
  v107 = 0;
  std::wstring::_Construct<1,wchar_t const *>((__int64)&v106, L"TrimLanguageFeaturesAllowed", 0x1Bu);
  CDeviceInfo::AddValuePair(a3, &v106, 0);
  std::wstring::~wstring(&v106);
  Library = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0x800u);
  v92 = Library;
  if ( !Library )
  {
    LogAdapter::TraceInfo<>("Bcp47Langs.dll is not available, skipping UserProfileLanguage enumeration");
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
    return 0;
  }
  v8 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v91 = v8;
  if ( !v8 )
  {
    LogAdapter::TraceInfo<>("api-ms-win-core-winrt-string-l1-1-0.dll is not available, skipping UserProfileLanguage enumeration");
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
LABEL_44:
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "GetUserLanguagesForUser");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Getting GetUserLanguagesForUser function failed");
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      else
        v12 = LastError;
      v101 = v12;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    if ( LastError )
    {
      v13 = 68;
LABEL_15:
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v13,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)LastError,
              phkResult);
      if ( v98 )
      {
        operator delete(v98 - 4, v14);
        v98 = 0;
      }
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
      if ( hKey )
      {
        v16 = (const struct std::nothrow_t *)0xFFFFFFFF80000000LL;
        if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
        {
          GetLastError();
          __fastfail(7u);
        }
        hKey = 0;
      }
      if ( v99 )
      {
        operator delete(v99 - 4, v16);
        v99 = 0;
      }
      if ( lpSubKey )
      {
        operator delete((void *)(lpSubKey - 4), v16);
        lpSubKey = 0;
      }
      if ( !FreeLibrary(v8) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( !FreeLibrary(Library) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return v15;
    }
    goto LABEL_31;
  }
  v18 = GetProcAddress(Library, "Bcp47GetMuiForm");
  *((_QWORD *)this + 3) = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Getting Bcp47GetMuiForm function failed");
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      else
        v19 = LastError;
      v101 = v19;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    if ( LastError )
    {
      v13 = 71;
      goto LABEL_15;
    }
LABEL_31:
    if ( v98 )
    {
      operator delete(v98 - 4, v10);
      v98 = 0;
    }
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
    if ( hKey )
    {
      v17 = (const struct std::nothrow_t *)0xFFFFFFFF80000000LL;
      if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      hKey = 0;
    }
    if ( v99 )
    {
      operator delete(v99 - 4, v17);
      v99 = 0;
    }
    if ( lpSubKey )
    {
      operator delete((void *)(lpSubKey - 4), v17);
      lpSubKey = 0;
    }
    if ( !FreeLibrary(v8) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_44;
  }
  v20 = GetProcAddress(v8, "WindowsGetStringRawBuffer");
  *((_QWORD *)this + 2) = v20;
  if ( !v20 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Getting WindowsGetStringRawBuffer function failed");
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      else
        v22 = LastError;
      v101 = v22;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    if ( LastError )
    {
      v13 = 75;
      goto LABEL_15;
    }
    v23 = 0;
LABEL_86:
    if ( v98 )
    {
      operator delete(v98 - 4, v21);
      v98 = 0;
    }
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
    Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
    if ( v99 )
    {
      operator delete(v99 - 4, v33);
      v99 = 0;
    }
    if ( lpSubKey )
    {
      operator delete((void *)(lpSubKey - 4), v33);
      lpSubKey = 0;
    }
LABEL_223:
    MultiStringValue = v23;
    goto LABEL_224;
  }
  v24 = GetProcAddress(v8, "WindowsCreateString");
  *((_QWORD *)this + 1) = v24;
  v23 = 0;
  if ( !v24 )
  {
    v25 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Getting WindowsCreateString function failed");
      if ( v25 > 0 )
        v26 = (unsigned __int16)v25 | 0x80070000;
      else
        v26 = v25;
      v101 = v26;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    if ( v25 )
    {
      v27 = 78;
      goto LABEL_79;
    }
    goto LABEL_86;
  }
  v28 = GetProcAddress(v8, "WindowsDeleteString");
  *(_QWORD *)this = v28;
  if ( !v28 )
  {
    v25 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Getting WindowsDeleteString function failed");
      if ( v25 > 0 )
        v29 = (unsigned __int16)v25 | 0x80070000;
      else
        v29 = v25;
      v101 = v29;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    if ( v25 )
    {
      v27 = 81;
      goto LABEL_79;
    }
    goto LABEL_86;
  }
  Win32RegistryPath = DeviceContext::GetWin32RegistryPath(
                        a2,
                        0,
                        L"Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                        &lpSubKey);
  MultiStringValue = Win32RegistryPath;
  if ( Win32RegistryPath < 0 )
  {
    v101 = Win32RegistryPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting win32 path in software hive");
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v94);
    }
    v35 = 88;
    goto LABEL_96;
  }
  if ( hKey )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18013B343LL);
  }
  v25 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v25 < 0 )
    __fastfail(7u);
  if ( v25 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<AutoScz>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed creating key: {0}",
        &lpSubKey);
      v101 = (unsigned __int16)v25 | 0x80070000;
      v94 = (wchar_t *)&v101;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v94);
    }
    v27 = 92;
    goto LABEL_79;
  }
  v101 = 0;
  memset_0(StringSid, 0, sizeof(StringSid));
  for ( i = 0; ; i = v42 )
  {
    cchName = 256;
    v25 = RegEnumKeyExW(hKey, i, StringSid, &cchName, 0, 0, 0, 0);
    if ( v25 == 259 )
    {
      v47 = DeviceContext::GetWin32RegistryPath(a2, 1, L"CurrentControlSet\\Control\\MUI\\Settings", &v99);
      MultiStringValue = v47;
      if ( v47 >= 0 )
      {
        MultiStringValue = CbsRegQueryMultiStringValue(
                             HKEY_LOCAL_MACHINE,
                             v99,
                             v48,
                             L"PreferredUILanguages",
                             (struct CCbsStringArray *)v109);
        if ( (int)(MultiStringValue + 0x80000000) < 0 || MultiStringValue == -2147024894 )
        {
          v49 = v110;
          v94 = v110;
          LogAdapter::TraceInfo<unsigned __int64>(
            "Found {0} System preferred languages. Adding unique ones to the UserProfileLanguage list",
            &v94);
          v50 = v111;
          v51 = &v111[(_QWORD)v49];
          while ( v50 != v51 )
          {
            v94 = *v50;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v94);
            if ( MultiStringValue < 0 )
            {
              v103[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding UserProfileLanguage: {0}",
                  (__int64)&v94);
                *(_QWORD *)v104 = v103;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v104);
              }
              v53 = 177;
              goto LABEL_156;
            }
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguageFallback(this, a2, a3, v94);
            if ( MultiStringValue < 0 )
            {
              v103[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding Fallback language: {0}",
                  (__int64)&v94);
                *(_QWORD *)v104 = v103;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v104);
              }
              v53 = 180;
              goto LABEL_156;
            }
            ++v50;
          }
          CCbsStringArray::Clear((CCbsStringArray *)v109);
          MultiStringValue = CbsRegQueryMultiStringValue(
                               HKEY_CURRENT_USER,
                               L"Control Panel\\Desktop",
                               v52,
                               L"PreferredUILanguages",
                               (struct CCbsStringArray *)v109);
          if ( (int)(MultiStringValue + 0x80000000) >= 0 && MultiStringValue != -2147024894 )
          {
            v103[0] = MultiStringValue;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<wchar_t [22]>();
              *(_QWORD *)v104 = v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)v104);
            }
            v53 = 210;
LABEL_156:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v53,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)MultiStringValue,
              phkResult);
LABEL_157:
            if ( v98 )
            {
              operator delete(v98 - 4, v54);
              v98 = 0;
            }
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
            if ( v99 )
            {
              operator delete(v99 - 4, v55);
              v99 = 0;
            }
            if ( lpSubKey )
            {
              operator delete((void *)(lpSubKey - 4), v55);
              lpSubKey = 0;
            }
            goto LABEL_224;
          }
          v56 = v110;
          *(_QWORD *)v104 = v110;
          LogAdapter::TraceInfo<unsigned __int64>(
            "Found {0} User preferred languages. Adding unique ones to the UserProfileLanguage list",
            v104);
          v57 = (const wchar_t **)v111;
          v58 = (const wchar_t **)&v111[(_QWORD)v56];
          while ( v57 != v58 )
          {
            v97 = *v57;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v97);
            if ( MultiStringValue < 0 )
            {
              v103[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding UserProfileLanguage: {0}",
                  (__int64)&v97);
                *(_QWORD *)v104 = v103;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v104);
              }
              v53 = 220;
              goto LABEL_156;
            }
            ++v57;
          }
          LOBYTE(lpClass) = 1;
          phkResulta = String;
          RegValue = DeviceContext::GetRegValue(a2, 1, L"CurrentControlSet\\Control\\nls\\language", L"InstallLanguage");
          MultiStringValue = RegValue;
          if ( RegValue < 0 )
          {
            v103[0] = RegValue;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(__int64 *)&LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed reading system language");
              *(_QWORD *)v104 = v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)v104);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE9,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)MultiStringValue,
              (int)phkResulta);
            if ( String[0] )
              operator delete(String[0] - 4, v54);
            goto LABEL_157;
          }
          v60 = String[0];
          v61 = o_wcstoul_0(String[0], 0, 16);
          if ( LCIDToLocaleName(v61, Name, 85, 0) )
          {
            v67 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, Name);
            v23 = v67;
            if ( v67 >= 0 )
            {
              v69 = DeviceContext::GetWin32RegistryPath(a2, 1, L"CurrentControlSet\\Control\\nls\\language", &v98);
              v23 = v69;
              if ( v69 >= 0 )
              {
                v23 = CbsRegQueryMultiStringValue(
                        HKEY_LOCAL_MACHINE,
                        v98,
                        v70,
                        L"InstallLanguageFallback",
                        (struct CCbsStringArray *)v112);
                if ( (int)(v23 + 0x80000000) < 0 || v23 == -2147024894 )
                {
                  v71 = v113;
                  *(_QWORD *)v95 = v113;
                  LogAdapter::TraceInfo<unsigned __int64>(
                    "Found {0} System fallback languages. Adding unique ones to the UserProfileLanguage list",
                    v95);
                  v73 = v114;
                  v74 = &v114[v71];
                  while ( v73 != v74 )
                  {
                    *(_QWORD *)v95 = *v73;
                    v23 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, *(const wchar_t *const *)v95);
                    if ( v23 < 0 )
                    {
                      v104[0] = v23;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          0,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding system fallback language: {0}",
                          (__int64)v95);
                        *(_QWORD *)v103 = v104;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          1,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                          (__int64)v103);
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x10E,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                        (const char *)(unsigned int)v23,
                        (int)phkResulta);
                      if ( v60 )
                        operator delete(v60 - 4, v77);
                      if ( v98 )
                      {
                        operator delete(v98 - 4, v77);
                        v98 = 0;
                      }
                      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
                      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
                      Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
                      if ( v99 )
                      {
                        operator delete(v99 - 4, v78);
                        v99 = 0;
                      }
                      if ( lpSubKey )
                      {
                        operator delete((void *)(lpSubKey - 4), v78);
                        lpSubKey = 0;
                      }
                      goto LABEL_223;
                    }
                    ++v73;
                  }
                  CDeviceInfo::MatchNameValueSetPair(a3, L"UserProfileLanguage", L"en-GB", v72, v90);
                  if ( v90[0] )
                  {
                    v75 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, L"en-US");
                    v23 = v75;
                    if ( v75 < 0 )
                    {
                      v104[0] = v75;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogPartial<wchar_t [6]>();
                        *(_QWORD *)v103 = v104;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          1,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                          (__int64)v103);
                      }
                      v68 = 279;
                      goto LABEL_214;
                    }
                  }
                  v101 = 0;
                  v79 = DeviceContext::GetRegValue(
                          a2,
                          0,
                          L"Policies\\Microsoft\\Control Panel\\International",
                          L"BlockCleanupOfUnusedPreinstalledLangPacks");
                  if ( (int)(v79 + 0x80000000) < 0 || v79 == -805306316 )
                  {
                    v80 = v101;
                  }
                  else
                  {
                    v80 = 1;
                    LogAdapter::TraceAtLevelHr<long,>(
                      3,
                      v79,
                      "Failed reading LP cleanup policy, assuming it isn't allowed");
                  }
                  v81 = L"1";
                  if ( v80 )
                    v81 = L"0";
                  std::wstring::wstring(&v106, L"TrimLanguagePacksAllowed");
                  CDeviceInfo::AddValuePair(a3, &v106, v81);
                  std::wstring::~wstring(&v106);
                  if ( v80 )
                    goto LABEL_248;
                  v101 = 1;
                  v82 = DeviceContext::GetRegValue(
                          a2,
                          0,
                          L"Microsoft\\Windows\\CurrentVersion\\Policies\\TextInput",
                          L"AllowLanguageFeaturesUninstall");
                  if ( (int)(v82 + 0x80000000) < 0 || v82 == -805306316 )
                  {
                    v83 = v101;
                  }
                  else
                  {
                    v83 = 0;
                    LogAdapter::TraceAtLevelHr<long,>(
                      3,
                      v82,
                      "Failed reading Language Feature cleanup policy, assuming it isn't allowed");
                  }
                  if ( !v83 )
LABEL_248:
                    v84 = L"0";
                  else
                    v84 = L"1";
                  std::wstring::wstring(&v106, L"TrimLanguageFeaturesAllowed");
                  CDeviceInfo::AddValuePair(a3, &v106, v84);
                  std::wstring::~wstring(&v106);
                  *(_QWORD *)v95 = *((_QWORD *)this + 5);
                  LogAdapter::TraceInfo<unsigned __int64>("UserProfileLanguages found: {0}", v95);
                  if ( v60 )
                    operator delete(v60 - 4, v85);
                  if ( v98 )
                  {
                    operator delete(v98 - 4, v85);
                    v98 = 0;
                  }
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
                  Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
                  if ( v99 )
                  {
                    operator delete(v99 - 4, v86);
                    v99 = 0;
                  }
                  if ( lpSubKey )
                  {
                    operator delete((void *)(lpSubKey - 4), v86);
                    lpSubKey = 0;
                  }
                  CIUClient::~CIUClient((CIUClient *)&v91);
                  CIUClient::~CIUClient((CIUClient *)&v92);
                  return 0;
                }
                v104[0] = v23;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<AutoScz>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed querying key: {0}",
                    &v98);
                  *(_QWORD *)v95 = v104;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)v95);
                }
                v68 = 260;
              }
              else
              {
                v104[0] = v69;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting win32 path in system hive");
                  *(_QWORD *)v95 = v104;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)v95);
                }
                v68 = 249;
              }
            }
            else
            {
              v104[0] = v67;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t [85]>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding UserProfileLanguage: {0}",
                  Name,
                  lpClass);
                *(_QWORD *)v95 = v104;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v95);
              }
              v68 = 242;
            }
LABEL_214:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v68,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)v23,
              (int)phkResulta);
          }
          else
          {
            v63 = GetLastError();
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              v103[0] = v61;
              LogAdapter::Logger::LogNumObjects<unsigned long>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed converting language ID to locale name: {0}",
                v103);
              if ( v63 > 0 )
                v64 = (unsigned __int16)v63 | 0x80070000;
              else
                v64 = v63;
              v104[0] = v64;
              *(_QWORD *)v95 = v104;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
                (__int64)v95);
            }
            if ( !v63 )
            {
              if ( v60 )
                operator delete(v60 - 4, v62);
              if ( v98 )
              {
                operator delete(v98 - 4, v62);
                v98 = 0;
              }
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
              Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
              if ( v99 )
              {
                operator delete(v99 - 4, v66);
                v99 = 0;
              }
              if ( lpSubKey )
              {
                operator delete((void *)(lpSubKey - 4), v66);
                lpSubKey = 0;
              }
              MultiStringValue = 0;
              goto LABEL_224;
            }
            v23 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xEF,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                    (const char *)(unsigned int)v63,
                    (unsigned int)phkResulta);
          }
          if ( v60 )
            operator delete(v60 - 4, v65);
          if ( v98 )
          {
            operator delete(v98 - 4, v65);
            v98 = 0;
          }
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
          Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
          if ( v99 )
          {
            operator delete(v99 - 4, v76);
            v99 = 0;
          }
          if ( lpSubKey )
          {
            operator delete((void *)(lpSubKey - 4), v76);
            lpSubKey = 0;
          }
          goto LABEL_223;
        }
        v103[0] = MultiStringValue;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed querying key: {0}",
            &v99);
          v94 = (wchar_t *)v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v94);
        }
        v35 = 167;
      }
      else
      {
        v103[0] = v47;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting win32 path in software hive");
          v94 = (wchar_t *)v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v94);
        }
        v35 = 156;
      }
LABEL_96:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
        (const char *)(unsigned int)MultiStringValue,
        phkResult);
      goto LABEL_80;
    }
    if ( v25 < 0 )
      __fastfail(7u);
    if ( v25 )
      break;
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
    {
      *(_QWORD *)&v106 = 0;
      *((_QWORD *)&v106 + 1) = this;
      v38 = ((__int64 (__fastcall *)(PSID, _QWORD, __int128 *))ProcAddress)(Sid, 0, &v106);
      if ( v38 >= 0 )
      {
        v40 = (const wchar_t *)(*((__int64 (__fastcall **)(_QWORD, _QWORD))this + 2))(v106, 0);
        v96 = v40;
        if ( v40 )
        {
          while ( 1 )
          {
            if ( !*v40 )
              goto LABEL_119;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v40);
            if ( MultiStringValue < 0 )
              break;
            v41 = -1;
            do
              ++v41;
            while ( v96[v41] );
            v40 = &v96[v41 + 1];
            v96 = v40;
          }
          v103[0] = MultiStringValue;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding UserProfileLanguage: {0}",
              (__int64)&v96);
            v94 = (wchar_t *)v103;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&v94);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
            (const char *)(unsigned int)MultiStringValue,
            phkResult);
          if ( (_QWORD)v106 )
          {
            (**((void (***)(void))&v106 + 1))();
            *(_QWORD *)&v106 = 0;
          }
          Windows::AutoLocalPtr<void>::~AutoLocalPtr<void>(&Sid);
          goto LABEL_80;
        }
      }
      else
      {
        LogAdapter::TraceHr<long,wchar_t [256]>((unsigned int)v38, v39, StringSid);
      }
LABEL_119:
      if ( (_QWORD)v106 )
      {
        (**((void (***)(void))&v106 + 1))();
        *(_QWORD *)&v106 = 0;
      }
    }
    else
    {
      LogAdapter::TraceLastError<wchar_t [256]>(v37, StringSid);
    }
    Windows::AutoLocalPtr<void>::~AutoLocalPtr<void>(&Sid);
    v42 = ++v101;
    memset_0(StringSid, 0, sizeof(StringSid));
  }
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogPartial<wchar_t [57],unsigned long>(v44, v43, v45, v46, (__int64)&v101);
    v103[0] = (unsigned __int16)v25 | 0x80070000;
    v94 = (wchar_t *)v103;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)&v94);
  }
  v27 = 113;
LABEL_79:
  MultiStringValue = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v27,
                       (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                       (const char *)(unsigned int)v25,
                       phkResult);
LABEL_80:
  if ( v98 )
  {
    operator delete(v98 - 4, v30);
    v98 = 0;
  }
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v112);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v109);
  Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
  if ( v99 )
  {
    operator delete(v99 - 4, v32);
    v99 = 0;
  }
  if ( lpSubKey )
  {
    operator delete((void *)(lpSubKey - 4), v32);
    lpSubKey = 0;
  }
LABEL_224:
  CIUClient::~CIUClient((CIUClient *)&v91);
  CIUClient::~CIUClient((CIUClient *)&v92);
  return (unsigned int)MultiStringValue;
}

```

## disassembly

```asm
0x180139ac0  mov     rax, rsp
0x180139ac3  push    rbp
0x180139ac4  push    rsi
0x180139ac5  push    rdi
0x180139ac6  push    r12
0x180139ac8  push    r13
0x180139aca  push    r14
0x180139acc  push    r15
0x180139ace  lea     rbp, [rax-368h]
0x180139ad5  sub     rsp, 430h
0x180139adc  mov     [rsp+460h+var_400], 0FFFFFFFFFFFFFFFEh
0x180139ae5  mov     [rax+20h], rbx
0x180139ae9  mov     rax, cs:__security_cookie
0x180139af0  xor     rax, rsp
0x180139af3  mov     [rbp+360h+var_40], rax
0x180139afa  mov     r15, r8
0x180139afd  mov     r12, rdx
0x180139b00  mov     r14, rcx
0x180139b03  xor     esi, esi
0x180139b05  cmp     [rdx], sil
0x180139b08  jnz     loc_180139CAF
0x180139b0e  mov     [rsp+460h+var_410], rsi
0x180139b13  mov     [rsp+460h+var_418], rsi
0x180139b18  mov     [rbp+360h+lpSubKey], rsi
0x180139b1c  mov     [rbp+360h+var_3D0], rsi
0x180139b20  mov     [rbp+360h+hKey], rsi
0x180139b24  lea     rcx, [rbp+360h+var_370]; this
0x180139b28  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x180139b2d  nop
0x180139b2e  lea     rcx, [rbp+360h+var_330]; this
0x180139b32  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x180139b37  nop
0x180139b38  mov     [rsp+460h+var_420], sil
0x180139b3d  mov     [rbp+360h+var_3D8], rsi
0x180139b41  mov     [rsp+460h+String], rsi
0x180139b46  xor     edx, edx; Val
0x180139b48  mov     r8d, 0AAh; Size
0x180139b4e  lea     rcx, [rbp+360h+Name]; void *
0x180139b52  call    memset_0
0x180139b57  lea     rcx, aArbiterPopulat_0; "arbiter: Populate UserProfile Languages"
0x180139b5e  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180139b63  xorps   xmm0, xmm0
0x180139b66  movups  [rbp+360h+var_398], xmm0
0x180139b6a  xorps   xmm1, xmm1
0x180139b6d  movdqu  [rbp+360h+var_388], xmm1
0x180139b72  lea     r8d, [rsi+18h]
0x180139b76  lea     rdx, aTrimlanguagepa; "TrimLanguagePacksAllowed"
0x180139b7d  lea     rcx, [rbp+360h+var_398]
0x180139b81  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180139b86  nop
0x180139b87  xor     r8d, r8d
0x180139b8a  lea     rdx, [rbp+360h+var_398]
0x180139b8e  mov     rcx, r15
0x180139b91  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x180139b96  nop
0x180139b97  lea     rcx, [rbp+360h+var_398]; void *
0x180139b9b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180139ba0  xorps   xmm0, xmm0
0x180139ba3  movups  [rbp+360h+var_398], xmm0
0x180139ba7  xorps   xmm1, xmm1
0x180139baa  movdqu  [rbp+360h+var_388], xmm1
0x180139baf  lea     r8d, [rsi+1Bh]
0x180139bb3  lea     rdx, aTrimlanguagefe; "TrimLanguageFeaturesAllowed"
0x180139bba  lea     rcx, [rbp+360h+var_398]
0x180139bbe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180139bc3  nop
0x180139bc4  xor     r8d, r8d
0x180139bc7  lea     rdx, [rbp+360h+var_398]
0x180139bcb  mov     rcx, r15
0x180139bce  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x180139bd3  nop
0x180139bd4  lea     rcx, [rbp+360h+var_398]; void *
0x180139bd8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180139bdd  mov     ebx, 800h
0x180139be2  mov     r8d, ebx; dwFlags
0x180139be5  xor     edx, edx; hFile
0x180139be7  lea     rcx, aBcp47langsDll; "Bcp47Langs.dll"
0x180139bee  call    cs:__imp_LoadLibraryExW
0x180139bf5  nop     dword ptr [rax+rax+00h]
0x180139bfa  mov     rdi, rax
0x180139bfd  mov     [rsp+460h+var_410], rax
0x180139c02  test    rax, rax
0x180139c05  jnz     loc_180139CDC
0x180139c0b  lea     rcx, aBcp47langsDllI; "Bcp47Langs.dll is not available, skippi"...
0x180139c12  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180139c17  nop
0x180139c18  mov     rcx, [rbp+360h+var_3D8]
0x180139c1c  test    rcx, rcx
0x180139c1f  jz      short loc_180139C2E
0x180139c21  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139c25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139c2a  mov     [rbp+360h+var_3D8], rsi
0x180139c2e  lea     rcx, [rbp+360h+var_330]
0x180139c32  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139c37  nop
0x180139c38  lea     rcx, [rbp+360h+var_370]
0x180139c3c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139c41  nop
0x180139c42  mov     rcx, [rbp+360h+hKey]; hKey
0x180139c46  test    rcx, rcx
0x180139c49  jz      short loc_180139C86
0x180139c4b  mov     rax, rcx
0x180139c4e  mov     rdx, 0FFFFFFFF80000000h
0x180139c55  and     rax, rdx
0x180139c58  cmp     rax, rdx
0x180139c5b  jz      short loc_180139C82
0x180139c5d  call    cs:__imp_RegCloseKey
0x180139c64  nop     dword ptr [rax+rax+00h]
0x180139c69  test    eax, eax
0x180139c6b  jz      short loc_180139C82
0x180139c6d  call    cs:__imp_GetLastError
0x180139c74  nop     dword ptr [rax+rax+00h]
0x180139c79  mov     ecx, 7
0x180139c7e  int     29h; Win8: RtlFailFast(ecx)
0x180139c80  xor     esi, esi
0x180139c82  mov     [rbp+360h+hKey], rsi
0x180139c86  mov     rcx, [rbp+360h+var_3D0]
0x180139c8a  test    rcx, rcx
0x180139c8d  jz      short loc_180139C9C
0x180139c8f  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139c93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139c98  mov     [rbp+360h+var_3D0], rsi
0x180139c9c  mov     rcx, [rbp+360h+lpSubKey]
0x180139ca0  test    rcx, rcx
0x180139ca3  jz      short loc_180139CAF
0x180139ca5  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139ca9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139cae  nop
0x180139caf  xor     eax, eax
0x180139cb1  mov     rcx, [rbp+360h+var_40]
0x180139cb8  xor     rcx, rsp; StackCookie
0x180139cbb  call    __security_check_cookie
0x180139cc0  mov     rbx, [rsp+460h+arg_18]
0x180139cc8  add     rsp, 430h
0x180139ccf  pop     r15
0x180139cd1  pop     r14
0x180139cd3  pop     r13
0x180139cd5  pop     r12
0x180139cd7  pop     rdi
0x180139cd8  pop     rsi
0x180139cd9  pop     rbp
0x180139cda  retn
0x180139cdc  mov     r8d, ebx; dwFlags
0x180139cdf  xor     edx, edx; hFile
0x180139ce1  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180139ce8  call    cs:__imp_LoadLibraryExW
0x180139cef  nop     dword ptr [rax+rax+00h]
0x180139cf4  mov     rbx, rax
0x180139cf7  mov     [rsp+460h+var_418], rax
0x180139cfc  test    rax, rax
0x180139cff  jnz     loc_180139DB3
0x180139d05  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-string-l1-1-0.dll"...
0x180139d0c  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180139d11  nop
0x180139d12  mov     rcx, [rbp+360h+var_3D8]
0x180139d16  test    rcx, rcx
0x180139d19  jz      short loc_180139D28
0x180139d1b  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139d1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139d24  mov     [rbp+360h+var_3D8], rsi
0x180139d28  lea     rcx, [rbp+360h+var_330]
0x180139d2c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139d31  nop
0x180139d32  lea     rcx, [rbp+360h+var_370]
0x180139d36  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139d3b  nop
0x180139d3c  mov     esi, 7
0x180139d41  mov     rcx, [rbp+360h+hKey]; hKey
0x180139d45  xor     ebx, ebx
0x180139d47  test    rcx, rcx
0x180139d4a  jz      short loc_180139D82
0x180139d4c  mov     rax, rcx
0x180139d4f  mov     rdx, 0FFFFFFFF80000000h; struct std::nothrow_t *
0x180139d56  and     rax, rdx
0x180139d59  cmp     rax, rdx
0x180139d5c  jz      short loc_180139D7E
0x180139d5e  call    cs:__imp_RegCloseKey
0x180139d65  nop     dword ptr [rax+rax+00h]
0x180139d6a  test    eax, eax
0x180139d6c  jz      short loc_180139D7E
0x180139d6e  call    cs:__imp_GetLastError
0x180139d75  nop     dword ptr [rax+rax+00h]
0x180139d7a  mov     ecx, esi
0x180139d7c  int     29h; Win8: RtlFailFast(ecx)
0x180139d7e  mov     [rbp+360h+hKey], rbx
0x180139d82  mov     rcx, [rbp+360h+var_3D0]
0x180139d86  test    rcx, rcx
0x180139d89  jz      short loc_180139D98
0x180139d8b  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139d8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139d94  mov     [rbp+360h+var_3D0], rbx
0x180139d98  mov     rcx, [rbp+360h+lpSubKey]
0x180139d9c  test    rcx, rcx
0x180139d9f  jz      short loc_180139DAE
0x180139da1  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139da5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139daa  mov     [rbp+360h+lpSubKey], rbx
0x180139dae  jmp     loc_18013A01B
0x180139db3  lea     rdx, aGetuserlanguag; "GetUserLanguagesForUser"
0x180139dba  mov     rcx, rdi; hModule
0x180139dbd  call    cs:__imp_GetProcAddress
0x180139dc4  nop     dword ptr [rax+rax+00h]
0x180139dc9  mov     r13, rax
0x180139dcc  test    rax, rax
0x180139dcf  jnz     loc_18013A048
0x180139dd5  call    cs:__imp_GetLastError
0x180139ddc  nop     dword ptr [rax+rax+00h]
0x180139de1  mov     r14d, eax
0x180139de4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180139deb  test    rcx, rcx
0x180139dee  jz      short loc_180139E48
0x180139df0  lea     r9, aGettingGetuser; "Getting GetUserLanguagesForUser functio"...
0x180139df7  lea     esi, [r13+3]
0x180139dfb  mov     r8d, esi
0x180139dfe  xor     edx, edx
0x180139e00  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180139e05  test    r14d, r14d
0x180139e08  jg      short loc_180139E0F
0x180139e0a  mov     eax, r14d
0x180139e0d  jmp     short loc_180139E18
0x180139e0f  movzx   eax, r14w
0x180139e13  or      eax, 80070000h
0x180139e18  mov     [rbp+360h+var_3C0], eax
0x180139e1b  lea     rax, [rbp+360h+var_3C0]
0x180139e1f  mov     [rsp+460h+var_3F8], rax
0x180139e24  lea     rax, [rsp+460h+var_3F8]
0x180139e29  mov     [rsp+460h+phkResult], rax; unsigned int
0x180139e2e  lea     r9, a0; ": {0}"
0x180139e35  mov     r8d, esi
0x180139e38  mov     dl, 1
0x180139e3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180139e41  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180139e46  xor     esi, esi
0x180139e48  test    r14d, r14d
0x180139e4b  jz      loc_180139F5B
0x180139e51  mov     edx, 44h ; 'D'; void *
0x180139e56  mov     r9d, r14d; char *
0x180139e59  lea     r8, aOnecoreBaseSer_23; "onecore\\base\\servicing\\arbiter\\cuse"...
0x180139e60  mov     rcx, [rbp+368h]; this
0x180139e67  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180139e6c  mov     r14d, eax
0x180139e6f  mov     rcx, [rbp+360h+var_3D8]
0x180139e73  test    rcx, rcx
0x180139e76  jz      short loc_180139E85
0x180139e78  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139e7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139e81  mov     [rbp+360h+var_3D8], rsi
0x180139e85  lea     rcx, [rbp+360h+var_330]
0x180139e89  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139e8e  nop
0x180139e8f  lea     rcx, [rbp+360h+var_370]
0x180139e93  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x180139e98  nop
0x180139e99  xor     r15d, r15d
0x180139e9c  mov     rcx, [rbp+360h+hKey]; hKey
0x180139ea0  lea     esi, [r15+7]
0x180139ea4  test    rcx, rcx
0x180139ea7  jz      short loc_180139EDF
0x180139ea9  mov     rdx, 0FFFFFFFF80000000h; struct std::nothrow_t *
0x180139eb0  mov     rax, rcx
0x180139eb3  and     rax, rdx
0x180139eb6  cmp     rax, rdx
0x180139eb9  jz      short loc_180139EDB
0x180139ebb  call    cs:__imp_RegCloseKey
0x180139ec2  nop     dword ptr [rax+rax+00h]
0x180139ec7  test    eax, eax
0x180139ec9  jz      short loc_180139EDB
0x180139ecb  call    cs:__imp_GetLastError
0x180139ed2  nop     dword ptr [rax+rax+00h]
0x180139ed7  mov     ecx, esi
0x180139ed9  int     29h; Win8: RtlFailFast(ecx)
0x180139edb  mov     [rbp+360h+hKey], r15
0x180139edf  mov     rcx, [rbp+360h+var_3D0]
0x180139ee3  test    rcx, rcx
0x180139ee6  jz      short loc_180139EF5
0x180139ee8  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139eec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139ef1  mov     [rbp+360h+var_3D0], r15
0x180139ef5  mov     rcx, [rbp+360h+lpSubKey]
0x180139ef9  test    rcx, rcx
0x180139efc  jz      short loc_180139F0B
0x180139efe  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180139f02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139f07  mov     [rbp+360h+lpSubKey], r15
0x180139f0b  mov     rcx, rbx; hLibModule
0x180139f0e  call    cs:__imp_FreeLibrary
0x180139f15  nop     dword ptr [rax+rax+00h]
0x180139f1a  test    eax, eax
0x180139f1c  jnz     short loc_180139F2F
0x180139f1e  call    cs:__imp_GetLastError
0x180139f25  nop     dword ptr [rax+rax+00h]
0x180139f2a  mov     rcx, rsi
0x180139f2d  int     29h; Win8: RtlFailFast(ecx)
0x180139f2f  mov     rcx, rdi; hLibModule
0x180139f32  call    cs:__imp_FreeLibrary
0x180139f39  nop     dword ptr [rax+rax+00h]
0x180139f3e  test    eax, eax
0x180139f40  jnz     short loc_180139F53
0x180139f42  call    cs:__imp_GetLastError
0x180139f49  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
