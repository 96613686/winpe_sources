# AppV::Client::Common::CleanupTemporaryPersistedVfsLocks(void)

- ea: `0x140045a4c`
- end: `0x140046811`
- name: `?CleanupTemporaryPersistedVfsLocks@Common@Client@AppV@@YA_NXZ`
- size: `3525`
- prototype: `bool __fastcall(AppV::Client::Common *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011bbc`

## callees

- `0x140004280`
- `0x140004558`
- `0x140004910`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140006a94`
- `0x140008e64`
- `0x140010158`
- `0x14001f0d0`
- `0x140038eb8`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14003e4dc`
- `0x14003f204`
- `0x14004582c`
- `0x140045948`
- `0x140045a4c`
- `0x140046ad0`
- `0x1400636ac`
- `0x1400637e4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140045ac9`
- `ADVAPI32!RegOpenKeyExW` at `0x140045ac9`
- `ADVAPI32!RegCloseKey` at `0x140045af4`
- `ADVAPI32!RegCloseKey` at `0x140045bed`
- `ADVAPI32!RegCloseKey` at `0x140046536`
- `ADVAPI32!RegCloseKey` at `0x1400466d8`
- `ADVAPI32!RegCloseKey` at `0x140045af4`
- `ADVAPI32!RegCloseKey` at `0x140045bed`
- `ADVAPI32!RegCloseKey` at `0x140046536`
- `ADVAPI32!RegCloseKey` at `0x1400466d8`
- `ADVAPI32!SetThreadToken` at `0x140045c04`
- `ADVAPI32!SetThreadToken` at `0x14004654d`
- `ADVAPI32!SetThreadToken` at `0x1400466eb`
- `ADVAPI32!SetThreadToken` at `0x140045c04`
- `ADVAPI32!SetThreadToken` at `0x14004654d`
- `ADVAPI32!SetThreadToken` at `0x1400466eb`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140045c77`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140045c77`
- `ADVAPI32!RegEnumValueW` at `0x140045e36`
- `ADVAPI32!RegEnumValueW` at `0x140045e36`
- `ADVAPI32!RegDeleteValueW` at `0x140046681`
- `ADVAPI32!RegDeleteValueW` at `0x140046681`
- `KERNEL32!RaiseException` at `0x140046577`
- `KERNEL32!RaiseException` at `0x140046714`
- `KERNEL32!RaiseException` at `0x140046577`
- `KERNEL32!RaiseException` at `0x140046714`
- `KERNEL32!CloseHandle` at `0x140045c1c`
- `KERNEL32!CloseHandle` at `0x140046561`
- `KERNEL32!CloseHandle` at `0x140046582`
- `KERNEL32!CloseHandle` at `0x1400466ff`
- `KERNEL32!CloseHandle` at `0x14004671c`
- `KERNEL32!CloseHandle` at `0x1400467d2`
- `KERNEL32!CloseHandle` at `0x140045c1c`
- `KERNEL32!CloseHandle` at `0x140046561`
- `KERNEL32!CloseHandle` at `0x140046582`
- `KERNEL32!CloseHandle` at `0x1400466ff`
- `KERNEL32!CloseHandle` at `0x14004671c`
- `KERNEL32!CloseHandle` at `0x1400467d2`
- `KERNEL32!GetLastError` at `0x140045ae9`
- `KERNEL32!GetLastError` at `0x140045ae9`
- `KERNEL32!SetLastError` at `0x140045afc`
- `KERNEL32!SetLastError` at `0x140045afc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140046123`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140046123`

## string_xrefs

- `0x140045b13`: `AppV::Client::Common::CleanupTemporaryPersistedVfsLocks`
- `0x140045c89`: `AppV::Client::Common::CleanupTemporaryPersistedVfsLocks`
- `0x140045dea`: `AppV::Client::Common::CleanupTemporaryPersistedVfsLocks`
- `0x14004673f`: `AppV::Client::Common::CleanupTemporaryPersistedVfsLocks`
- `0x14004676b`: `No SID/file name values in the key.`
- `0x140045b44`: `Cannot open key %1%.`
- `0x140045cba`: `Cannot get registry limits for key %1%. Error: %2%.`
- `0x1400462b7`: `Failed to get the full path name for %1%. Error: %2%.`
- `0x140045fff`: `Found UNC path %1%.`
- `0x140045eec`: `Failed to expand environment variables for path %1%.`
- `0x140046167`: `Found temporary profile path: %1%.`
- `0x140046475`: `Failed enumerating registry values. Error: %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
bool __fastcall AppV::Client::Common::CleanupTemporaryPersistedVfsLocks(
        AppV::Client::Common *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  LSTATUS v3; // eax
  HKEY v4; // r14
  HKEY v5; // rdi
  HKEY v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  BOOL v11; // eax
  HANDLE v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  WCHAR *v17; // r13
  void *v18; // rbx
  DWORD v19; // ecx
  LSTATUS v20; // eax
  char v21; // bl
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 full_path_name; // rsi
  WCHAR *v25; // rax
  WCHAR *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rbx
  WCHAR *v29; // rcx
  WCHAR *v30; // rdx
  unsigned __int64 v31; // r8
  __int64 *v32; // rdx
  HKEY *v33; // rcx
  int v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // rbx
  unsigned __int64 v37; // r8
  LPCWSTR v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rbx
  BOOL v49; // eax
  LPCWSTR v50; // rdi
  LPCWSTR v51; // rsi
  bool v52; // zf
  __int64 v53; // rcx
  __int64 v54; // rbx
  const WCHAR *v55; // rdx
  bool v56; // bl
  LSTATUS v58; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v59[8]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Token; // [rsp+70h] [rbp-90h]
  DWORD cbMaxValueNameLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD v66; // [rsp+90h] [rbp-70h]
  DWORD cValues; // [rsp+94h] [rbp-6Ch] BYREF
  WCHAR *v68; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v70; // [rsp+B0h] [rbp-50h]
  void *Block; // [rsp+B8h] [rbp-48h]
  void *v72; // [rsp+C0h] [rbp-40h]
  WCHAR *v73; // [rsp+C8h] [rbp-38h]
  HKEY phkResult[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v75; // [rsp+E0h] [rbp-20h]
  WCHAR Src[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v77; // [rsp+100h] [rbp+0h]
  __int64 v78; // [rsp+108h] [rbp+8h]
  char *v79[4]; // [rsp+110h] [rbp+10h] BYREF
  int v80; // [rsp+130h] [rbp+30h]
  WCHAR FileName[8]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v82; // [rsp+148h] [rbp+48h]
  unsigned __int64 v83; // [rsp+150h] [rbp+50h]
  _QWORD v84[2]; // [rsp+158h] [rbp+58h] BYREF
  char *v85[5]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v86[128]; // [rsp+190h] [rbp+90h] BYREF

  AppV::ScopeTracker::ScopeTracker((AppV::ScopeTracker *)v86, a2, a3);
  softgrid::shared::revert_to_self::revert_to_self((softgrid::shared::revert_to_self *)v59);
  hKey = 0;
  phkResult[0] = (HKEY)&hKey;
  phkResult[1] = 0;
  LOBYTE(v75) = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2011Fu, &phkResult[1]);
  v58 = v3;
  if ( (_BYTE)v75 )
  {
    v4 = phkResult[1];
    v5 = phkResult[0];
    v6 = *(HKEY *)phkResult[0];
    if ( *(_QWORD *)phkResult[0] )
    {
      LastError = GetLastError();
      RegCloseKey(v6);
      SetLastError(LastError);
    }
    *(_QWORD *)v5 = v4;
    v3 = v58;
  }
  if ( v3 )
  {
    std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
    v80 = 65;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    *(_OWORD *)Src = 0;
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Cannot open key %1%.", 0x14u);
    v9 = AppV::Log::fmt(v8, v84, Src);
    v10 = AppV::LogFormatter::operator%<wchar_t const *>(v9, &lpSubKey);
    *(_OWORD *)phkResult = 0;
    v75 = 0u;
    std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v79, 8, (int)phkResult, v10);
    std::wstring::~wstring((char **)phkResult);
    v84[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v85);
    std::wstring::~wstring((char **)Src);
LABEL_7:
    std::string::~string(v79);
    if ( hKey )
      RegCloseKey(hKey);
    if ( !Token )
      goto LABEL_84;
    v11 = SetThreadToken(0, Token);
    v12 = Token;
    if ( !v11 )
    {
      if ( Token )
        CloseHandle(Token);
      goto LABEL_65;
    }
    goto LABEL_83;
  }
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v58 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v58 )
  {
    std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
    v80 = 77;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    *(_OWORD *)phkResult = 0;
    v75 = 0u;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)phkResult,
      L"Cannot get registry limits for key %1%. Error: %2%.",
      0x33u);
    v14 = AppV::Log::fmt(v13, v84, phkResult);
    v15 = AppV::LogFormatter::operator%<wchar_t const *>(v14, &lpSubKey);
    v16 = AppV::LogFormatter::operator%<unsigned long>(v15, (__int64)&v58);
    *(_OWORD *)Src = 0;
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, v16);
    std::wstring::~wstring((char **)Src);
    v84[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v85);
    std::wstring::~wstring((char **)phkResult);
    goto LABEL_7;
  }
  if ( !cValues || !cbMaxValueNameLen || !cbMaxValueLen )
  {
    std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
    v80 = 84;
    *(_OWORD *)phkResult = 0;
    v75 = 0u;
    std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, L"No SID/file name values in the key.", 0x23u);
    *(_OWORD *)Src = 0;
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, (__int64)phkResult);
    std::wstring::~wstring((char **)Src);
    std::wstring::~wstring((char **)phkResult);
    goto LABEL_7;
  }
  cbMaxValueNameLen += 2;
  cbMaxValueLen += 2;
  v72 = operator new[](0x20Au);
  v17 = (WCHAR *)operator new[](saturated_mul(cbMaxValueNameLen, 2u));
  v73 = v17;
  v18 = operator new[](cbMaxValueLen);
  Block = v18;
  v19 = 0;
  v66 = 0;
  *(_OWORD *)lpValueName = 0;
  v70 = 0;
  v58 = 0;
  do
  {
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    v20 = RegEnumValueW(hKey, v19, v17, &cchValueName, 0, 0, (LPBYTE)v18, &cbData);
    v58 = v20;
    if ( v20 )
      break;
    ++v66;
    if ( !cchValueName || !cbData )
    {
      std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
      v80 = 123;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      *(_OWORD *)phkResult = 0;
      v75 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)phkResult,
        L"Don't process this Value name = %1%, Value data = %2%.",
        0x36u);
      v43 = AppV::Log::fmt(v42, v84, phkResult);
      v44 = AppV::LogFormatter::operator%<unsigned long>(v43, (__int64)&cchValueName);
      v45 = AppV::LogFormatter::operator%<unsigned long>(v44, (__int64)&cbData);
      *(_OWORD *)Src = 0;
      v77 = 0;
      v78 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, v45);
      std::wstring::~wstring((char **)Src);
      v84[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v85);
      std::wstring::~wstring((char **)phkResult);
      std::string::~string(v79);
      goto LABEL_57;
    }
    *(_OWORD *)FileName = 0;
    v82 = 0;
    v83 = 7;
    FileName[0] = 0;
    *(_OWORD *)Src = 0;
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)Src, v18, (unsigned __int64)cbData >> 1);
    v21 = SWExpandVariables(Src);
    std::wstring::~wstring((char **)Src);
    if ( !v21 )
    {
      std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
      v80 = 131;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      *(_OWORD *)phkResult = 0;
      v75 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)phkResult,
        L"Failed to expand environment variables for path %1%.",
        0x34u);
      v23 = AppV::Log::fmt(v22, v84, phkResult);
      AppV::LogFormatter::perform_substitution<std::wstring>(v23, FileName);
      *(_OWORD *)Src = 0;
      v77 = 0;
      v78 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, v23);
      std::wstring::~wstring((char **)Src);
      v84[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v85);
      std::wstring::~wstring((char **)phkResult);
      std::string::~string(v79);
    }
    full_path_name = shared::get_full_path_name(FileName);
    if ( (full_path_name & 0x8000000000LL) != 0 )
    {
      v25 = FileName;
      if ( v83 > 7 )
        v25 = *(WCHAR **)FileName;
      if ( *v25 != 92 )
        goto LABEL_34;
      v26 = FileName;
      if ( v83 > 7 )
        v26 = *(WCHAR **)FileName;
      if ( v26[1] != 92 )
      {
LABEL_34:
        v68 = 0;
        v29 = FileName;
        if ( v83 > 7 )
          v29 = *(WCHAR **)FileName;
        if ( (unsigned __int8)paths::parse_drive_and_path(v29, v72, &v68) )
        {
          v30 = v68;
        }
        else
        {
          v30 = FileName;
          if ( v83 > 7 )
            v30 = *(WCHAR **)FileName;
        }
        *(_OWORD *)phkResult = 0;
        v75 = 0u;
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, v30, v31);
        v32 = &qword_1400B0F60;
        if ( (unsigned __int64)qword_1400B0F78 > 7 )
          v32 = (__int64 *)qword_1400B0F60;
        v33 = phkResult;
        if ( *((_QWORD *)&v75 + 1) > 7u )
          v33 = (HKEY *)phkResult[0];
        v34 = _o__wcsnicmp(v33, v32, qword_1400B0F70);
        std::wstring::~wstring((char **)phkResult);
        if ( !v34 )
        {
          std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
          v80 = 160;
          AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
          *(_OWORD *)phkResult = 0;
          v75 = 0u;
          std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, L"Found temporary profile path: %1%.", 0x22u);
          v36 = AppV::Log::fmt(v35, v84, phkResult);
          AppV::LogFormatter::perform_substitution<std::wstring>(v36, FileName);
          *(_OWORD *)Src = 0;
          v77 = 0;
          v78 = 0;
          std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
          AppV::DecoratedLog::operator()((char *)v79, 4, (int)Src, v36);
          std::wstring::~wstring((char **)Src);
          v84[0] = &AppV::LogFormatter::`vftable';
          std::wstring::~wstring(v85);
          std::wstring::~wstring((char **)phkResult);
          std::string::~string(v79);
          *(_OWORD *)phkResult = 0;
          v75 = 0u;
          v37 = -1;
          do
            ++v37;
          while ( v17[v37] );
          std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, v17, v37);
          v38 = lpValueName[1];
          if ( lpValueName[1] == v70 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(lpValueName, lpValueName[1], phkResult);
          }
          else
          {
            *(_OWORD *)lpValueName[1] = *(_OWORD *)phkResult;
            *((_OWORD *)v38 + 1) = v75;
            *(_QWORD *)&v75 = 0;
            *((_QWORD *)&v75 + 1) = 7;
            LOWORD(phkResult[0]) = 0;
            lpValueName[1] += 16;
          }
          std::wstring::~wstring((char **)phkResult);
        }
        goto LABEL_54;
      }
      std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
      v80 = 146;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      *(_OWORD *)phkResult = 0;
      v75 = 0u;
      std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, L"Found UNC path %1%.", 0x13u);
      v28 = AppV::Log::fmt(v27, v84, phkResult);
      AppV::LogFormatter::perform_substitution<std::wstring>(v28, FileName);
      *(_OWORD *)Src = 0;
      v77 = 0;
      v78 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v79, 4, (int)Src, v28);
      std::wstring::~wstring((char **)Src);
      v84[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v85);
      std::wstring::~wstring((char **)phkResult);
    }
    else
    {
      std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
      v80 = 138;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      *(_OWORD *)phkResult = 0;
      v75 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)phkResult,
        L"Failed to get the full path name for %1%. Error: %2%.",
        0x35u);
      v40 = AppV::Log::fmt(v39, v84, phkResult);
      AppV::LogFormatter::perform_substitution<std::wstring>(v40, FileName);
      v68 = (WCHAR *)full_path_name;
      v41 = AppV::LogFormatter::operator%(v40, (__int64 *)&v68);
      *(_OWORD *)Src = 0;
      v77 = 0;
      v78 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, v41);
      std::wstring::~wstring((char **)Src);
      v84[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v85);
      std::wstring::~wstring((char **)phkResult);
    }
    std::string::~string(v79);
LABEL_54:
    std::wstring::~wstring((char **)FileName);
LABEL_57:
    v20 = v58;
    v18 = Block;
    v19 = v66;
  }
  while ( !v58 );
  if ( v20 == 259 )
  {
    v50 = lpValueName[0];
    v51 = lpValueName[1];
    v52 = lpValueName[0] == lpValueName[1];
    if ( lpValueName[0] != lpValueName[1] )
    {
      do
      {
        std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
        v80 = 176;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
        *(_OWORD *)phkResult = 0;
        v75 = 0u;
        std::wstring::_Construct<1,wchar_t const *>((char **)phkResult, L"Deleting value %1%.", 0x13u);
        v54 = AppV::Log::fmt(v53, v84, phkResult);
        AppV::LogFormatter::perform_substitution<std::wstring>(v54, v50);
        *(_OWORD *)Src = 0;
        v77 = 0;
        v78 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v79, 4, (int)Src, v54);
        std::wstring::~wstring((char **)Src);
        v84[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v85);
        std::wstring::~wstring((char **)phkResult);
        std::string::~string(v79);
        if ( *((_QWORD *)v50 + 3) <= 7u )
          v55 = v50;
        else
          v55 = *(const WCHAR **)v50;
        RegDeleteValueW(hKey, v55);
        v50 += 16;
      }
      while ( v50 != v51 );
      v17 = v73;
      v52 = lpValueName[0] == lpValueName[1];
    }
    v56 = !v52;
    std::vector<std::wstring>::_Tidy(lpValueName);
    operator delete(Block);
    operator delete(v17);
    operator delete(v72);
    if ( hKey )
      RegCloseKey(hKey);
    if ( Token )
    {
      if ( SetThreadToken(0, Token) )
      {
        CloseHandle(Token);
        Token = 0;
        v59[0] = 0;
      }
      else
      {
        if ( Token )
          CloseHandle(Token);
        RaiseException(0x29Cu, 1u, 0, 0);
      }
    }
    AppV::ScopeTracker::~ScopeTracker((AppV::ScopeTracker *)v86);
    return v56;
  }
  std::string::string(v79, "AppV::Client::Common::CleanupTemporaryPersistedVfsLocks");
  v80 = 169;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
  *(_OWORD *)phkResult = 0;
  v75 = 0u;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)phkResult,
    L"Failed enumerating registry values. Error: %1%",
    0x2Eu);
  v47 = AppV::Log::fmt(v46, v84, phkResult);
  v48 = AppV::LogFormatter::operator%<unsigned long>(v47, (__int64)&v58);
  *(_OWORD *)Src = 0;
  v77 = 0;
  v78 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)Src, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v79, 8, (int)Src, v48);
  std::wstring::~wstring((char **)Src);
  v84[0] = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v85);
  std::wstring::~wstring((char **)phkResult);
  std::string::~string(v79);
  std::vector<std::wstring>::_Tidy(lpValueName);
  operator delete(Block);
  operator delete(v17);
  operator delete(v72);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !Token )
    goto LABEL_84;
  v49 = SetThreadToken(0, Token);
  v12 = Token;
  if ( v49 )
  {
LABEL_83:
    CloseHandle(v12);
    Token = 0;
    v59[0] = 0;
    goto LABEL_84;
  }
  if ( Token )
    CloseHandle(Token);
LABEL_65:
  RaiseException(0x29Cu, 1u, 0, 0);
LABEL_84:
  AppV::ScopeTracker::~ScopeTracker((AppV::ScopeTracker *)v86);
  return 0;
}

```

## disassembly

```asm
0x140045a4c  push    rbp
0x140045a4e  push    rbx
0x140045a4f  push    rsi
0x140045a50  push    rdi
0x140045a51  push    r13
0x140045a53  push    r14
0x140045a55  push    r15
0x140045a57  lea     rbp, [rsp-120h]
0x140045a5f  sub     rsp, 220h
0x140045a66  mov     rax, cs:__security_cookie
0x140045a6d  xor     rax, rsp
0x140045a70  mov     [rbp+150h+var_40], rax
0x140045a77  lea     rcx, [rbp+150h+var_C0]; this
0x140045a7e  call    ??0ScopeTracker@AppV@@QEAA@PEB_W0@Z; AppV::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140045a83  nop
0x140045a84  lea     rcx, [rsp+250h+var_1E8]; this
0x140045a89  call    ??0revert_to_self@shared@softgrid@@QEAA@XZ; softgrid::shared::revert_to_self::revert_to_self(void)
0x140045a8e  nop
0x140045a8f  xor     esi, esi
0x140045a91  mov     [rbp+150h+hKey], rsi
0x140045a95  lea     rax, [rbp+150h+hKey]
0x140045a99  mov     [rbp+150h+var_180], rax
0x140045a9d  mov     [rbp+150h+var_180+8], rsi
0x140045aa1  lea     r13d, [rsi+1]
0x140045aa5  mov     byte ptr [rbp+150h+var_170], r13b
0x140045aa9  lea     rax, [rbp+150h+var_180+8]
0x140045aad  mov     [rsp+250h+phkResult], rax; phkResult
0x140045ab2  mov     r9d, 2011Fh; samDesired
0x140045ab8  xor     r8d, r8d; ulOptions
0x140045abb  mov     rdx, cs:lpSubKey; lpSubKey
0x140045ac2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140045ac9  call    cs:__imp_RegOpenKeyExW
0x140045acf  mov     [rsp+250h+var_1F0], eax
0x140045ad3  cmp     byte ptr [rbp+150h+var_170], sil
0x140045ad7  jz      short loc_140045B0B
0x140045ad9  mov     r14, [rbp+150h+var_180+8]
0x140045add  mov     rdi, [rbp+150h+var_180]
0x140045ae1  mov     rsi, [rdi]
0x140045ae4  test    rsi, rsi
0x140045ae7  jz      short loc_140045B02
0x140045ae9  call    cs:__imp_GetLastError
0x140045aef  mov     ebx, eax
0x140045af1  mov     rcx, rsi; hKey
0x140045af4  call    cs:__imp_RegCloseKey
0x140045afa  mov     ecx, ebx; dwErrCode
0x140045afc  call    cs:__imp_SetLastError
0x140045b02  mov     [rdi], r14
0x140045b05  mov     eax, [rsp+250h+var_1F0]
0x140045b09  xor     esi, esi
0x140045b0b  test    eax, eax
0x140045b0d  jz      loc_140045C2A
0x140045b13  lea     rdx, aAppvClientComm; "AppV::Client::Common::CleanupTemporaryP"...
0x140045b1a  lea     rcx, [rbp+150h+var_140]
0x140045b1e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140045b23  mov     [rbp+150h+var_120], 41h ; 'A'
0x140045b2a  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140045b2f  xorps   xmm0, xmm0
0x140045b32  movups  xmmword ptr [rbp+150h+Src], xmm0
0x140045b36  mov     [rbp+150h+var_150], rsi
0x140045b3a  mov     [rbp+150h+var_148], rsi
0x140045b3e  mov     r8d, 14h
0x140045b44  lea     rdx, aCannotOpenKey1; "Cannot open key %1%."
0x140045b4b  lea     rcx, [rbp+150h+Src]
0x140045b4f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045b54  nop
0x140045b55  lea     r8, [rbp+150h+Src]
0x140045b59  lea     rdx, [rbp+150h+var_F8]
0x140045b5d  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140045b62  nop
0x140045b63  lea     rdx, lpSubKey
0x140045b6a  mov     rcx, rax
0x140045b6d  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x140045b72  mov     rbx, rax
0x140045b75  xorps   xmm0, xmm0
0x140045b78  movups  xmmword ptr [rbp+150h+var_180], xmm0
0x140045b7c  mov     qword ptr [rbp+150h+var_170], rsi
0x140045b80  mov     qword ptr [rbp+150h+var_170+8], rsi
0x140045b84  mov     r8d, 6
0x140045b8a  lea     rdx, aClient; "Client"
0x140045b91  lea     rcx, [rbp+150h+var_180]
0x140045b95  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045b9a  nop
0x140045b9b  mov     r9, rbx
0x140045b9e  lea     r8, [rbp+150h+var_180]
0x140045ba2  mov     edx, 8
0x140045ba7  lea     rcx, [rbp+150h+var_140]
0x140045bab  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140045bb0  nop
0x140045bb1  lea     rcx, [rbp+150h+var_180]
0x140045bb5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045bba  nop
0x140045bbb  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140045bc2  mov     [rbp+150h+var_F8], rax
0x140045bc6  lea     rcx, [rbp+150h+var_E8]
0x140045bca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045bcf  nop
0x140045bd0  lea     rcx, [rbp+150h+Src]
0x140045bd4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045bd9  nop
0x140045bda  lea     rcx, [rbp+150h+var_140]
0x140045bde  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140045be3  nop
0x140045be4  mov     rcx, [rbp+150h+hKey]; hKey
0x140045be8  test    rcx, rcx
0x140045beb  jz      short loc_140045BF4
0x140045bed  call    cs:__imp_RegCloseKey
0x140045bf3  nop
0x140045bf4  mov     rdx, [rsp+250h+Token]; Token
0x140045bf9  test    rdx, rdx
0x140045bfc  jz      loc_1400467E2
0x140045c02  xor     ecx, ecx; Thread
0x140045c04  call    cs:__imp_SetThreadToken
0x140045c0a  mov     rcx, [rsp+250h+Token]; hObject
0x140045c0f  test    eax, eax
0x140045c11  jnz     loc_1400467D2
0x140045c17  test    rcx, rcx
0x140045c1a  jz      short loc_140045C22
0x140045c1c  call    cs:__imp_CloseHandle
0x140045c22  mov     edx, r13d
0x140045c25  jmp     loc_14004656C
0x140045c2a  mov     [rsp+250h+cbMaxValueNameLen], esi
0x140045c2e  mov     [rsp+250h+cbMaxValueLen], esi
0x140045c32  mov     [rbp+150h+cValues], esi
0x140045c35  mov     [rsp+250h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x140045c3a  mov     [rsp+250h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x140045c3f  lea     rax, [rsp+250h+cbMaxValueLen]
0x140045c44  mov     [rsp+250h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140045c49  lea     rax, [rsp+250h+cbMaxValueNameLen]
0x140045c4e  mov     [rsp+250h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140045c53  lea     rax, [rbp+150h+cValues]
0x140045c57  mov     [rsp+250h+lpcValues], rax; lpcValues
0x140045c5c  mov     [rsp+250h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x140045c61  mov     [rsp+250h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x140045c66  mov     [rsp+250h+phkResult], rsi; lpcSubKeys
0x140045c6b  xor     r9d, r9d; lpReserved
0x140045c6e  xor     r8d, r8d; lpcchClass
0x140045c71  xor     edx, edx; lpClass
0x140045c73  mov     rcx, [rbp+150h+hKey]; hKey
0x140045c77  call    cs:__imp_RegQueryInfoKeyW
0x140045c7d  mov     [rsp+250h+var_1F0], eax
0x140045c81  test    eax, eax
0x140045c83  jz      loc_140045D62
0x140045c89  lea     rdx, aAppvClientComm; "AppV::Client::Common::CleanupTemporaryP"...
0x140045c90  lea     rcx, [rbp+150h+var_140]
0x140045c94  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140045c99  mov     [rbp+150h+var_120], 4Dh ; 'M'
0x140045ca0  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140045ca5  xorps   xmm0, xmm0
0x140045ca8  movups  xmmword ptr [rbp+150h+var_180], xmm0
0x140045cac  mov     qword ptr [rbp+150h+var_170], rsi
0x140045cb0  mov     qword ptr [rbp+150h+var_170+8], rsi
0x140045cb4  mov     r8d, 33h ; '3'
0x140045cba  lea     rdx, aCannotGetRegis; "Cannot get registry limits for key %1%."...
0x140045cc1  lea     rcx, [rbp+150h+var_180]
0x140045cc5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045cca  nop
0x140045ccb  lea     r8, [rbp+150h+var_180]
0x140045ccf  lea     rdx, [rbp+150h+var_F8]
0x140045cd3  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140045cd8  nop
0x140045cd9  lea     rdx, lpSubKey
0x140045ce0  mov     rcx, rax
0x140045ce3  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x140045ce8  lea     rdx, [rsp+250h+var_1F0]
0x140045ced  mov     rcx, rax
0x140045cf0  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140045cf5  mov     rbx, rax
0x140045cf8  xorps   xmm0, xmm0
0x140045cfb  movups  xmmword ptr [rbp+150h+Src], xmm0
0x140045cff  mov     [rbp+150h+var_150], rsi
0x140045d03  mov     [rbp+150h+var_148], rsi
0x140045d07  mov     r8d, 6
0x140045d0d  lea     rdx, aClient; "Client"
0x140045d14  lea     rcx, [rbp+150h+Src]
0x140045d18  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045d1d  nop
0x140045d1e  mov     r9, rbx
0x140045d21  lea     r8, [rbp+150h+Src]
0x140045d25  mov     edx, 8
0x140045d2a  lea     rcx, [rbp+150h+var_140]
0x140045d2e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140045d33  nop
0x140045d34  lea     rcx, [rbp+150h+Src]
0x140045d38  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045d3d  nop
0x140045d3e  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140045d45  mov     [rbp+150h+var_F8], rax
0x140045d49  lea     rcx, [rbp+150h+var_E8]
0x140045d4d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045d52  nop
0x140045d53  lea     rcx, [rbp+150h+var_180]
0x140045d57  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045d5c  nop
0x140045d5d  jmp     loc_140045BDA
0x140045d62  cmp     [rbp+150h+cValues], esi
0x140045d65  jz      loc_14004673F
0x140045d6b  mov     ecx, [rsp+250h+cbMaxValueNameLen]
0x140045d6f  test    ecx, ecx
0x140045d71  jz      loc_14004673F
0x140045d77  mov     edx, [rsp+250h+cbMaxValueLen]
0x140045d7b  test    edx, edx
0x140045d7d  jz      loc_14004673F
0x140045d83  add     ecx, 2
0x140045d86  mov     [rsp+250h+cbMaxValueNameLen], ecx
0x140045d8a  add     edx, 2
0x140045d8d  mov     [rsp+250h+cbMaxValueLen], edx
0x140045d91  mov     ecx, 20Ah; unsigned __int64
0x140045d96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140045d9b  mov     [rbp+150h+var_190], rax
0x140045d9f  mov     ecx, [rsp+250h+cbMaxValueNameLen]
0x140045da3  mov     eax, 2
0x140045da8  mul     rcx
0x140045dab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140045db2  cmovb   rax, rcx
0x140045db6  mov     rcx, rax; unsigned __int64
0x140045db9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140045dbe  mov     r13, rax
0x140045dc1  mov     [rbp+150h+var_188], rax
0x140045dc5  mov     ecx, [rsp+250h+cbMaxValueLen]; unsigned __int64
0x140045dc9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140045dce  mov     rbx, rax
0x140045dd1  mov     [rbp+150h+Block], rax
0x140045dd5  mov     ecx, esi
0x140045dd7  mov     [rbp+150h+var_1C0], ecx
0x140045dda  xorps   xmm0, xmm0
0x140045ddd  movdqu  xmmword ptr [rbp+150h+lpValueName], xmm0
0x140045de2  mov     [rbp+150h+var_1A0], rsi
0x140045de6  mov     [rsp+250h+var_1F0], esi
0x140045dea  lea     r14, aAppvClientComm; "AppV::Client::Common::CleanupTemporaryP"...
0x140045df1  mov     edi, 8
0x140045df6  lea     r15d, [rdi-2]
0x140045dfa  lea     rsi, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140045e01  xor     edx, edx
0x140045e03  mov     eax, [rsp+250h+cbMaxValueNameLen]
0x140045e07  mov     [rbp+150h+cchValueName], eax
0x140045e0a  mov     eax, [rsp+250h+cbMaxValueLen]
0x140045e0e  mov     [rbp+150h+cbData], eax
0x140045e11  lea     rax, [rbp+150h+cbData]
0x140045e15  mov     [rsp+250h+lpcValues], rax; lpcbData
0x140045e1a  mov     [rsp+250h+lpcbMaxClassLen], rbx; lpData
0x140045e1f  mov     [rsp+250h+lpcbMaxSubKeyLen], rdx; lpType
0x140045e24  mov     [rsp+250h+phkResult], rdx; lpReserved
0x140045e29  lea     r9, [rbp+150h+cchValueName]; lpcchValueName
0x140045e2d  mov     r8, r13; lpValueName
0x140045e30  mov     edx, ecx; dwIndex
0x140045e32  mov     rcx, [rbp+150h+hKey]; hKey
0x140045e36  call    cs:__imp_RegEnumValueW
0x140045e3c  mov     [rsp+250h+var_1F0], eax
0x140045e40  xor     edx, edx
0x140045e42  test    eax, eax
0x140045e44  jnz     loc_14004643C
0x140045e4a  inc     [rbp+150h+var_1C0]
0x140045e4d  cmp     [rbp+150h+cchValueName], edx
0x140045e50  jz      loc_14004635D
0x140045e56  mov     ecx, [rbp+150h+cbData]
0x140045e59  test    ecx, ecx
0x140045e5b  jz      loc_14004635D
0x140045e61  xorps   xmm0, xmm0
0x140045e64  movups  xmmword ptr [rbp+150h+FileName], xmm0
0x140045e68  mov     [rbp+150h+var_108], rdx
0x140045e6c  mov     [rbp+150h+var_100], 7
0x140045e74  mov     [rbp+150h+FileName], dx
0x140045e78  movups  xmmword ptr [rbp+150h+Src], xmm0
0x140045e7c  mov     [rbp+150h+var_150], rdx
0x140045e80  mov     [rbp+150h+var_148], rdx
0x140045e84  mov     r8d, ecx
0x140045e87  shr     r8, 1
0x140045e8a  mov     rdx, rbx
0x140045e8d  lea     rcx, [rbp+150h+Src]
0x140045e91  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045e96  nop
0x140045e97  lea     rdx, [rbp+150h+FileName]
0x140045e9b  lea     rcx, [rbp+150h+Src]; lpSrc
0x140045e9f  call    ?SWExpandVariables@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV12@@Z; SWExpandVariables(std::wstring const &,std::wstring &)
0x140045ea4  mov     bl, al
0x140045ea6  lea     rcx, [rbp+150h+Src]
0x140045eaa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045eaf  test    bl, bl
0x140045eb1  jnz     loc_140045F82
0x140045eb7  mov     rdx, r14
0x140045eba  lea     rcx, [rbp+150h+var_140]
0x140045ebe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140045ec3  mov     [rbp+150h+var_120], 83h
0x140045eca  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140045ecf  xorps   xmm0, xmm0
0x140045ed2  movups  xmmword ptr [rbp+150h+var_180], xmm0
0x140045ed6  mov     qword ptr [rbp+150h+var_170], 0
0x140045ede  mov     qword ptr [rbp+150h+var_170+8], 0
0x140045ee6  mov     r8d, 34h ; '4'
0x140045eec  lea     rdx, aFailedToExpand; "Failed to expand environment variables "...
0x140045ef3  lea     rcx, [rbp+150h+var_180]
0x140045ef7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140045efc  nop
0x140045efd  lea     r8, [rbp+150h+var_180]
0x140045f01  lea     rdx, [rbp+150h+var_F8]
0x140045f05  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140045f0a  mov     rbx, rax
0x140045f0d  lea     rdx, [rbp+150h+FileName]
0x140045f11  mov     rcx, rax
0x140045f14  call    ??$perform_substitution@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogFormatter@AppV@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::LogFormatter::perform_substitution<std::wstring>(std::wstring const &)
  ... truncated ...
```
