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
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // r14d
  const struct std::nothrow_t *v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  FARPROC v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // eax
  FARPROC v22; // rax
  const struct std::nothrow_t *v23; // rdx
  __int64 v24; // rdx
  unsigned int v25; // eax
  int v26; // edi
  FARPROC v27; // rax
  int v28; // ebx
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rdx
  FARPROC v32; // rax
  __int64 v33; // rdx
  unsigned int v34; // eax
  const struct std::nothrow_t *v35; // rdx
  int MultiStringValue; // ebx
  const struct std::nothrow_t *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  int Win32RegistryPath; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  DWORD i; // edx
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  const wchar_t *v47; // rax
  __int64 v48; // rax
  DWORD v49; // ebx
  int v50; // edx
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  int v54; // eax
  unsigned int v55; // r8d
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  wchar_t *v60; // rbx
  wchar_t **v61; // rdi
  wchar_t **v62; // rsi
  unsigned int v63; // r8d
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rdx
  const struct std::nothrow_t *v68; // rdx
  const struct std::nothrow_t *v69; // rdx
  wchar_t *v70; // rbx
  const wchar_t **v71; // rdi
  const wchar_t **v72; // rsi
  int RegValue; // eax
  __int64 v74; // rdx
  __int64 v75; // rdx
  wchar_t *v76; // rbx
  LCID v77; // esi
  const struct std::nothrow_t *v78; // rdx
  signed int v79; // edi
  __int64 v80; // rdx
  unsigned int v81; // eax
  const struct std::nothrow_t *v82; // rdx
  const struct std::nothrow_t *v83; // rdx
  int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rdx
  int v87; // eax
  unsigned int v88; // r8d
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rdi
  bool v92; // r9
  _QWORD *v93; // rsi
  _QWORD *v94; // r13
  int v95; // eax
  __int64 v96; // rdx
  const struct std::nothrow_t *v97; // rdx
  __int64 v98; // rdx
  const struct std::nothrow_t *v99; // rdx
  const struct std::nothrow_t *v100; // rdx
  unsigned int v101; // eax
  int v102; // r13d
  const wchar_t *v103; // rdi
  unsigned int v104; // eax
  unsigned int v105; // edi
  const wchar_t *v106; // rdi
  const struct std::nothrow_t *v107; // rdx
  const struct std::nothrow_t *v108; // rdx
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+28h] [rbp-E0h]
  int lpClass; // [rsp+30h] [rbp-D8h]
  bool v112[8]; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE v113; // [rsp+50h] [rbp-B8h] BYREF
  HMODULE v114; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *String[2]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t *v116; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v117[2]; // [rsp+78h] [rbp-90h] BYREF
  const wchar_t *v118; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v119; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v120; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *v121; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v123; // [rsp+A8h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-58h] BYREF
  int v125[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v126[2]; // [rsp+C0h] [rbp-48h] BYREF
  DWORD cchName; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v128; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v129; // [rsp+E0h] [rbp-28h]
  PSID Sid; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v131[24]; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t *v132; // [rsp+110h] [rbp+8h]
  wchar_t **v133; // [rsp+120h] [rbp+18h]
  _BYTE v134[24]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v135; // [rsp+150h] [rbp+48h]
  _QWORD *v136; // [rsp+160h] [rbp+58h]
  WCHAR Name[88]; // [rsp+178h] [rbp+70h] BYREF
  WCHAR StringSid[256]; // [rsp+228h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+470h] [rbp+368h]

  String[1] = (wchar_t *)-2LL;
  if ( *(_BYTE *)a2 )
    return 0;
  v113 = 0;
  lpSubKey = 0;
  v121 = 0;
  hKey = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v131);
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v134);
  v112[0] = 0;
  v120 = 0;
  String[0] = 0;
  memset_0(Name, 0, 0xAAu);
  LogAdapter::TraceInfo<>("arbiter: Populate UserProfile Languages");
  v128 = 0;
  v129 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v128, L"TrimLanguagePacksAllowed", 24);
  CDeviceInfo::AddValuePair(a3, &v128, 0);
  std::wstring::~wstring(&v128);
  v128 = 0;
  v129 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v128, L"TrimLanguageFeaturesAllowed", 27);
  CDeviceInfo::AddValuePair(a3, &v128, 0);
  std::wstring::~wstring(&v128);
  Library = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0x800u);
  v114 = Library;
  if ( !Library )
  {
    LogAdapter::TraceInfo<>("Bcp47Langs.dll is not available, skipping UserProfileLanguage enumeration");
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
    return 0;
  }
  v8 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v113 = v8;
  if ( !v8 )
  {
    LogAdapter::TraceInfo<>("api-ms-win-core-winrt-string-l1-1-0.dll is not available, skipping UserProfileLanguage enumeration");
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
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
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Getting GetUserLanguagesForUser function failed");
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      else
        v13 = LastError;
      v123 = v13;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v14 = 68;
LABEL_15:
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v14,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)phkResult);
      if ( v120 )
      {
        operator delete(v120 - 4, v15);
        v120 = 0;
      }
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
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
      if ( v121 )
      {
        operator delete(v121 - 4, v17);
        v121 = 0;
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
      if ( !FreeLibrary(Library) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return v16;
    }
    goto LABEL_31;
  }
  v19 = GetProcAddress(Library, "Bcp47GetMuiForm");
  *((_QWORD *)this + 3) = v19;
  if ( !v19 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Getting Bcp47GetMuiForm function failed");
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      else
        v21 = LastError;
      v123 = v21;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v20,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v14 = 71;
      goto LABEL_15;
    }
LABEL_31:
    if ( v120 )
    {
      operator delete(v120 - 4, v10);
      v120 = 0;
    }
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
    if ( hKey )
    {
      v18 = (const struct std::nothrow_t *)0xFFFFFFFF80000000LL;
      if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      hKey = 0;
    }
    if ( v121 )
    {
      operator delete(v121 - 4, v18);
      v121 = 0;
    }
    if ( lpSubKey )
    {
      operator delete((void *)(lpSubKey - 4), v18);
      lpSubKey = 0;
    }
    if ( !FreeLibrary(v8) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_44;
  }
  v22 = GetProcAddress(v8, "WindowsGetStringRawBuffer");
  *((_QWORD *)this + 2) = v22;
  if ( !v22 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Getting WindowsGetStringRawBuffer function failed");
      if ( LastError > 0 )
        v25 = (unsigned __int16)LastError | 0x80070000;
      else
        v25 = LastError;
      v123 = v25;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v24) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v24,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v14 = 75;
      goto LABEL_15;
    }
    v26 = 0;
LABEL_86:
    if ( v120 )
    {
      operator delete(v120 - 4, v23);
      v120 = 0;
    }
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
    Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
    if ( v121 )
    {
      operator delete(v121 - 4, v38);
      v121 = 0;
    }
    if ( lpSubKey )
    {
      operator delete((void *)(lpSubKey - 4), v38);
      lpSubKey = 0;
    }
LABEL_223:
    MultiStringValue = v26;
    goto LABEL_224;
  }
  v27 = GetProcAddress(v8, "WindowsCreateString");
  *((_QWORD *)this + 1) = v27;
  v26 = 0;
  if ( !v27 )
  {
    v28 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Getting WindowsCreateString function failed");
      if ( v28 > 0 )
        v30 = (unsigned __int16)v28 | 0x80070000;
      else
        v30 = v28;
      v123 = v30;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v29,
        3,
        ": {0}");
    }
    if ( v28 )
    {
      v31 = 78;
      goto LABEL_79;
    }
    goto LABEL_86;
  }
  v32 = GetProcAddress(v8, "WindowsDeleteString");
  *(_QWORD *)this = v32;
  if ( !v32 )
  {
    v28 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Getting WindowsDeleteString function failed");
      if ( v28 > 0 )
        v34 = (unsigned __int16)v28 | 0x80070000;
      else
        v34 = v28;
      v123 = v34;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v33,
        3,
        ": {0}");
    }
    if ( v28 )
    {
      v31 = 81;
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
    v123 = Win32RegistryPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed getting win32 path in software hive");
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v40) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v40,
        3,
        ": {}");
    }
    v41 = 88;
    goto LABEL_96;
  }
  if ( hKey )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18013B343LL);
  }
  v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v28 < 0 )
    __fastfail(7u);
  if ( v28 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<AutoScz>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed creating key: {0}",
        &lpSubKey);
      v123 = (unsigned __int16)v28 | 0x80070000;
      v116 = (wchar_t *)&v123;
      phkResult = (PHKEY)&v116;
      LOBYTE(v42) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v42,
        3,
        ": {0}");
    }
    v31 = 92;
    goto LABEL_79;
  }
  v123 = 0;
  memset_0(StringSid, 0, sizeof(StringSid));
  for ( i = 0; ; i = v49 )
  {
    cchName = 256;
    v28 = RegEnumKeyExW(hKey, i, StringSid, &cchName, 0, 0, 0, 0);
    if ( v28 == 259 )
    {
      v54 = DeviceContext::GetWin32RegistryPath(a2, 1, L"CurrentControlSet\\Control\\MUI\\Settings", &v121);
      MultiStringValue = v54;
      if ( v54 >= 0 )
      {
        MultiStringValue = CbsRegQueryMultiStringValue(
                             HKEY_LOCAL_MACHINE,
                             v121,
                             v55,
                             L"PreferredUILanguages",
                             (struct CCbsStringArray *)v131);
        if ( (int)(MultiStringValue + 0x80000000) < 0 || MultiStringValue == -2147024894 )
        {
          v60 = v132;
          v116 = v132;
          LogAdapter::TraceInfo<unsigned __int64>(
            "Found {0} System preferred languages. Adding unique ones to the UserProfileLanguage list",
            &v116);
          v61 = v133;
          v62 = &v133[(_QWORD)v60];
          while ( v61 != v62 )
          {
            v116 = *v61;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v116);
            if ( MultiStringValue < 0 )
            {
              v125[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding UserProfileLanguage: {0}",
                  &v116);
                *(_QWORD *)v126 = v125;
                phkResult = (PHKEY)v126;
                LOBYTE(v67) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v67,
                  3,
                  ": {}");
              }
              v65 = 177;
              goto LABEL_156;
            }
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguageFallback(this, a2, a3, v116);
            if ( MultiStringValue < 0 )
            {
              v125[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding Fallback language: {0}",
                  &v116);
                *(_QWORD *)v126 = v125;
                phkResult = (PHKEY)v126;
                LOBYTE(v66) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v66,
                  3,
                  ": {}");
              }
              v65 = 180;
              goto LABEL_156;
            }
            ++v61;
          }
          CCbsStringArray::Clear((CCbsStringArray *)v131);
          MultiStringValue = CbsRegQueryMultiStringValue(
                               HKEY_CURRENT_USER,
                               L"Control Panel\\Desktop",
                               v63,
                               L"PreferredUILanguages",
                               (struct CCbsStringArray *)v131);
          if ( (int)(MultiStringValue + 0x80000000) >= 0 && MultiStringValue != -2147024894 )
          {
            v125[0] = MultiStringValue;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<wchar_t [22]>();
              *(_QWORD *)v126 = v125;
              phkResult = (PHKEY)v126;
              LOBYTE(v64) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v64,
                3,
                ": {}");
            }
            v65 = 210;
LABEL_156:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v65,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)MultiStringValue,
              (int)phkResult);
LABEL_157:
            if ( v120 )
            {
              operator delete(v120 - 4, v68);
              v120 = 0;
            }
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
            if ( v121 )
            {
              operator delete(v121 - 4, v69);
              v121 = 0;
            }
            if ( lpSubKey )
            {
              operator delete((void *)(lpSubKey - 4), v69);
              lpSubKey = 0;
            }
            goto LABEL_224;
          }
          v70 = v132;
          *(_QWORD *)v126 = v132;
          LogAdapter::TraceInfo<unsigned __int64>(
            "Found {0} User preferred languages. Adding unique ones to the UserProfileLanguage list",
            v126);
          v71 = (const wchar_t **)v133;
          v72 = (const wchar_t **)&v133[(_QWORD)v70];
          while ( v71 != v72 )
          {
            v119 = *v71;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v119);
            if ( MultiStringValue < 0 )
            {
              v125[0] = MultiStringValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding UserProfileLanguage: {0}",
                  &v119);
                *(_QWORD *)v126 = v125;
                phkResult = (PHKEY)v126;
                LOBYTE(v75) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v75,
                  3,
                  ": {}");
              }
              v65 = 220;
              goto LABEL_156;
            }
            ++v71;
          }
          LOBYTE(lpClass) = 1;
          phkResulta = (PHKEY)String;
          RegValue = DeviceContext::GetRegValue(a2, 1, L"CurrentControlSet\\Control\\nls\\language", L"InstallLanguage");
          MultiStringValue = RegValue;
          if ( RegValue < 0 )
          {
            v125[0] = RegValue;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed reading system language");
              *(_QWORD *)v126 = v125;
              phkResulta = (PHKEY)v126;
              LOBYTE(v74) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v74,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE9,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)MultiStringValue,
              (int)phkResulta);
            if ( String[0] )
              operator delete(String[0] - 4, v68);
            goto LABEL_157;
          }
          v76 = String[0];
          v77 = o_wcstoul_0(String[0], 0, 16);
          if ( LCIDToLocaleName(v77, Name, 85, 0) )
          {
            v84 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, Name);
            v26 = v84;
            if ( v84 >= 0 )
            {
              v87 = DeviceContext::GetWin32RegistryPath(a2, 1, L"CurrentControlSet\\Control\\nls\\language", &v120);
              v26 = v87;
              if ( v87 >= 0 )
              {
                v26 = CbsRegQueryMultiStringValue(
                        HKEY_LOCAL_MACHINE,
                        v120,
                        v88,
                        L"InstallLanguageFallback",
                        (struct CCbsStringArray *)v134);
                if ( (int)(v26 + 0x80000000) < 0 || v26 == -2147024894 )
                {
                  v91 = v135;
                  *(_QWORD *)v117 = v135;
                  LogAdapter::TraceInfo<unsigned __int64>(
                    "Found {0} System fallback languages. Adding unique ones to the UserProfileLanguage list",
                    v117);
                  v93 = v136;
                  v94 = &v136[v91];
                  while ( v93 != v94 )
                  {
                    *(_QWORD *)v117 = *v93;
                    v26 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, *(const wchar_t *const *)v117);
                    if ( v26 < 0 )
                    {
                      v126[0] = v26;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed adding system fallback language: {0}",
                          v117);
                        *(_QWORD *)v125 = v126;
                        phkResulta = (PHKEY)v125;
                        LOBYTE(v98) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v98,
                          3,
                          ": {}");
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x10E,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                        (const char *)(unsigned int)v26,
                        (int)phkResulta);
                      if ( v76 )
                        operator delete(v76 - 4, v99);
                      if ( v120 )
                      {
                        operator delete(v120 - 4, v99);
                        v120 = 0;
                      }
                      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
                      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
                      Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
                      if ( v121 )
                      {
                        operator delete(v121 - 4, v100);
                        v121 = 0;
                      }
                      if ( lpSubKey )
                      {
                        operator delete((void *)(lpSubKey - 4), v100);
                        lpSubKey = 0;
                      }
                      goto LABEL_223;
                    }
                    ++v93;
                  }
                  CDeviceInfo::MatchNameValueSetPair(a3, L"UserProfileLanguage", L"en-GB", v92, v112);
                  if ( v112[0] )
                  {
                    v95 = CUserProfileLanguages::AddUserProfileLanguage(this, a3, L"en-US");
                    v26 = v95;
                    if ( v95 < 0 )
                    {
                      v126[0] = v95;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogPartial<wchar_t [6]>();
                        *(_QWORD *)v125 = v126;
                        phkResulta = (PHKEY)v125;
                        LOBYTE(v96) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v96,
                          3,
                          ": {}");
                      }
                      v86 = 279;
                      goto LABEL_214;
                    }
                  }
                  v123 = 0;
                  v101 = DeviceContext::GetRegValue(
                           a2,
                           0,
                           L"Policies\\Microsoft\\Control Panel\\International",
                           L"BlockCleanupOfUnusedPreinstalledLangPacks");
                  if ( (int)(v101 + 0x80000000) < 0 || v101 == -805306316 )
                  {
                    v102 = v123;
                  }
                  else
                  {
                    v102 = 1;
                    LogAdapter::TraceAtLevelHr<long,>(
                      3,
                      v101,
                      "Failed reading LP cleanup policy, assuming it isn't allowed");
                  }
                  v103 = L"1";
                  if ( v102 )
                    v103 = L"0";
                  std::wstring::wstring(&v128, L"TrimLanguagePacksAllowed");
                  CDeviceInfo::AddValuePair(a3, &v128, v103);
                  std::wstring::~wstring(&v128);
                  if ( v102 )
                    goto LABEL_248;
                  v123 = 1;
                  v104 = DeviceContext::GetRegValue(
                           a2,
                           0,
                           L"Microsoft\\Windows\\CurrentVersion\\Policies\\TextInput",
                           L"AllowLanguageFeaturesUninstall");
                  if ( (int)(v104 + 0x80000000) < 0 || v104 == -805306316 )
                  {
                    v105 = v123;
                  }
                  else
                  {
                    v105 = 0;
                    LogAdapter::TraceAtLevelHr<long,>(
                      3,
                      v104,
                      "Failed reading Language Feature cleanup policy, assuming it isn't allowed");
                  }
                  if ( !v105 )
LABEL_248:
                    v106 = L"0";
                  else
                    v106 = L"1";
                  std::wstring::wstring(&v128, L"TrimLanguageFeaturesAllowed");
                  CDeviceInfo::AddValuePair(a3, &v128, v106);
                  std::wstring::~wstring(&v128);
                  *(_QWORD *)v117 = *((_QWORD *)this + 5);
                  LogAdapter::TraceInfo<unsigned __int64>("UserProfileLanguages found: {0}", v117);
                  if ( v76 )
                    operator delete(v76 - 4, v107);
                  if ( v120 )
                  {
                    operator delete(v120 - 4, v107);
                    v120 = 0;
                  }
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
                  Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
                  if ( v121 )
                  {
                    operator delete(v121 - 4, v108);
                    v121 = 0;
                  }
                  if ( lpSubKey )
                  {
                    operator delete((void *)(lpSubKey - 4), v108);
                    lpSubKey = 0;
                  }
                  CIUClient::~CIUClient((CIUClient *)&v113);
                  CIUClient::~CIUClient((CIUClient *)&v114);
                  return 0;
                }
                v126[0] = v26;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<AutoScz>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed querying key: {0}",
                    &v120);
                  *(_QWORD *)v117 = v126;
                  phkResulta = (PHKEY)v117;
                  LOBYTE(v90) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v90,
                    3,
                    ": {}");
                }
                v86 = 260;
              }
              else
              {
                v126[0] = v87;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed getting win32 path in system hive");
                  *(_QWORD *)v117 = v126;
                  phkResulta = (PHKEY)v117;
                  LOBYTE(v89) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v89,
                    3,
                    ": {}");
                }
                v86 = 249;
              }
            }
            else
            {
              v126[0] = v84;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t [85]>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding UserProfileLanguage: {0}",
                  Name,
                  lpClass);
                *(_QWORD *)v117 = v126;
                phkResulta = (PHKEY)v117;
                LOBYTE(v85) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v85,
                  3,
                  ": {}");
              }
              v86 = 242;
            }
LABEL_214:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v86,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
              (const char *)(unsigned int)v26,
              (int)phkResulta);
          }
          else
          {
            v79 = GetLastError();
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              v125[0] = v77;
              LogAdapter::Logger::LogNumObjects<unsigned long>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed converting language ID to locale name: {0}",
                v125,
                lpClass);
              if ( v79 > 0 )
                v81 = (unsigned __int16)v79 | 0x80070000;
              else
                v81 = v79;
              v126[0] = v81;
              *(_QWORD *)v117 = v126;
              phkResulta = (PHKEY)v117;
              LOBYTE(v80) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v80,
                3,
                ": {0}");
            }
            if ( !v79 )
            {
              if ( v76 )
                operator delete(v76 - 4, v78);
              if ( v120 )
              {
                operator delete(v120 - 4, v78);
                v120 = 0;
              }
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
              Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
              if ( v121 )
              {
                operator delete(v121 - 4, v83);
                v121 = 0;
              }
              if ( lpSubKey )
              {
                operator delete((void *)(lpSubKey - 4), v83);
                lpSubKey = 0;
              }
              MultiStringValue = 0;
              goto LABEL_224;
            }
            v26 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xEF,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                    (const char *)(unsigned int)v79,
                    (unsigned int)phkResulta);
          }
          if ( v76 )
            operator delete(v76 - 4, v82);
          if ( v120 )
          {
            operator delete(v120 - 4, v82);
            v120 = 0;
          }
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
          Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
          if ( v121 )
          {
            operator delete(v121 - 4, v97);
            v121 = 0;
          }
          if ( lpSubKey )
          {
            operator delete((void *)(lpSubKey - 4), v97);
            lpSubKey = 0;
          }
          goto LABEL_223;
        }
        v125[0] = MultiStringValue;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed querying key: {0}",
            &v121);
          v116 = (wchar_t *)v125;
          phkResult = (PHKEY)&v116;
          LOBYTE(v59) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v59,
            3,
            ": {}");
        }
        v41 = 167;
      }
      else
      {
        v125[0] = v54;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed getting win32 path in software hive");
          v116 = (wchar_t *)v125;
          phkResult = (PHKEY)&v116;
          LOBYTE(v56) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v56,
            3,
            ": {}");
        }
        v41 = 156;
      }
LABEL_96:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
        (const char *)(unsigned int)MultiStringValue,
        (int)phkResult);
      goto LABEL_80;
    }
    if ( v28 < 0 )
      __fastfail(7u);
    if ( v28 )
      break;
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
    {
      *(_QWORD *)&v128 = 0;
      *((_QWORD *)&v128 + 1) = this;
      v45 = ((__int64 (__fastcall *)(PSID, _QWORD, __int128 *))ProcAddress)(Sid, 0, &v128);
      if ( v45 >= 0 )
      {
        v47 = (const wchar_t *)(*((__int64 (__fastcall **)(_QWORD, _QWORD))this + 2))(v128, 0);
        v118 = v47;
        if ( v47 )
        {
          while ( 1 )
          {
            if ( !*v47 )
              goto LABEL_119;
            MultiStringValue = CUserProfileLanguages::AddUserProfileLanguage(this, a3, v47);
            if ( MultiStringValue < 0 )
              break;
            v48 = -1;
            do
              ++v48;
            while ( v118[v48] );
            v47 = &v118[v48 + 1];
            v118 = v47;
          }
          v125[0] = MultiStringValue;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed adding UserProfileLanguage: {0}",
              &v118);
            v116 = (wchar_t *)v125;
            phkResult = (PHKEY)&v116;
            LOBYTE(v57) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v57,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
            (const char *)(unsigned int)MultiStringValue,
            (int)phkResult);
          if ( (_QWORD)v128 )
          {
            (**((void (***)(void))&v128 + 1))();
            *(_QWORD *)&v128 = 0;
          }
          Windows::AutoLocalPtr<void>::~AutoLocalPtr<void>(&Sid);
          goto LABEL_80;
        }
      }
      else
      {
        LogAdapter::TraceHr<long,wchar_t [256]>((unsigned int)v45, v46, StringSid);
      }
LABEL_119:
      if ( (_QWORD)v128 )
      {
        (**((void (***)(void))&v128 + 1))();
        *(_QWORD *)&v128 = 0;
      }
    }
    else
    {
      LogAdapter::TraceLastError<wchar_t [256]>(v44, StringSid);
    }
    Windows::AutoLocalPtr<void>::~AutoLocalPtr<void>(&Sid);
    v49 = ++v123;
    memset_0(StringSid, 0, sizeof(StringSid));
  }
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogPartial<wchar_t [57],unsigned long>(v51, v50, v52, v53, (__int64)&v123);
    v125[0] = (unsigned __int16)v28 | 0x80070000;
    v116 = (wchar_t *)v125;
    phkResult = (PHKEY)&v116;
    LOBYTE(v58) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v58,
      3,
      ": {0}");
  }
  v31 = 113;
LABEL_79:
  MultiStringValue = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v31,
                       (unsigned int)"onecore\\base\\servicing\\arbiter\\cuserprofilelanguages.cpp",
                       (const char *)(unsigned int)v28,
                       (unsigned int)phkResult);
LABEL_80:
  if ( v120 )
  {
    operator delete(v120 - 4, v35);
    v120 = 0;
  }
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v134);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v131);
  Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&hKey);
  if ( v121 )
  {
    operator delete(v121 - 4, v37);
    v121 = 0;
  }
  if ( lpSubKey )
  {
    operator delete((void *)(lpSubKey - 4), v37);
    lpSubKey = 0;
  }
LABEL_224:
  CIUClient::~CIUClient((CIUClient *)&v113);
  CIUClient::~CIUClient((CIUClient *)&v114);
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
