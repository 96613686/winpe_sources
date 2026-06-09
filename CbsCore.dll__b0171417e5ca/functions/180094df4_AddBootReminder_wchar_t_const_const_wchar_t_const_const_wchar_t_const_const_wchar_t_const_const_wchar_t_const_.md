# AddBootReminder(wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,ulong,ulong,ulong,ulong)

- ea: `0x180094df4`
- end: `0x180095644`
- name: `?AddBootReminder@@YAJQEB_W0000000KKKK@Z`
- size: `2128`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b5534`

## callees

- `0x180010cc0`
- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x18003330c`
- `0x180059a00`
- `0x180093f8c`
- `0x180094db4`
- `0x180094df4`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1802af610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095099`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009550e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009554e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009558e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800955cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009550e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009554e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009558e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800955cf`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800951b0`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800951b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095306`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800953eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095306`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800953eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180094ecf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180094ecf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180094e3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180094e3d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180094fde`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180094fde`
- `USERENV!GetProfilesDirectoryW` at `0x180095085`
- `USERENV!GetProfilesDirectoryW` at `0x180095085`

## string_xrefs

- `0x180095336`: `RegCreateKeyExW failed.`
- `0x18009541b`: `RegCreateKeyExW failed.`
- `0x180094e71`: `ConvertStringSidToSid failed.`
- `0x1800950b8`: `GetProfilesDirectory failed.`
- `0x18009500d`: `LookupAccountSid failed.`
- `0x180094f02`: `IsValidSid failed.`

## pseudocode

```c
__int64 __fastcall AddBootReminder(LPCWSTR lpSubKey, const wchar_t *a2, const wchar_t *a3, const WCHAR *a4)
{
  signed int LastError; // edi
  enum _SID_NAME_USE v8; // eax
  __int64 v9; // rdx
  enum _SID_NAME_USE v10; // eax
  unsigned int v11; // ebx
  DWORD v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  LSTATUS KeyW; // edi
  int v17; // eax
  __int64 v18; // rdx
  HKEY *phkResult; // rax
  LSTATUS Key; // edi
  HKEY *InitPointer; // rax
  LSTATUS v22; // edi
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  unsigned int ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  unsigned int ReferencedDomainNameb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFile; // [rsp+50h] [rbp-B0h] BYREF
  char v36[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR *p_lpSubKeya; // [rsp+60h] [rbp-A0h]
  unsigned int v38[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKeya; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  HKEY p_peUse; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchSize; // [rsp+94h] [rbp-6Ch] BYREF
  PSID Sid; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cchName[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  WCHAR ProfileDir[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR v50[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+738h] [rbp+638h]

  lpSubKeya = a4;
  Sid = 0;
  if ( ConvertStringSidToSidW(a4, &Sid) )
  {
    if ( !IsValidSid(Sid) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"IsValidSid failed.");
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        else
          v10 = LastError;
        peUse = v10;
        p_peUse = (HKEY)&peUse;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_peUse);
      }
      if ( LastError )
      {
        v9 = 72;
        goto LABEL_17;
      }
LABEL_85:
      v11 = 0;
      goto LABEL_86;
    }
    memset_0(Name, 0, 0x208u);
    cchName[0] = 260;
    memset_0(v50, 0, 0x208u);
    cchReferencedDomainName = 260;
    peUse = 0;
    if ( !LookupAccountSidW(0, Sid, Name, cchName, v50, &cchReferencedDomainName, &peUse) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"LookupAccountSid failed.");
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
        cchSize = v12;
        p_peUse = (HKEY)&cchSize;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_peUse);
      }
      if ( LastError )
      {
        v9 = 81;
        goto LABEL_17;
      }
      goto LABEL_85;
    }
    memset_0(ProfileDir, 0, 0x208u);
    cchSize = 260;
    if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"GetProfilesDirectory failed.");
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        else
          v13 = LastError;
        *(_DWORD *)Data = v13;
        p_peUse = (HKEY)Data;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_peUse);
      }
      if ( LastError )
      {
        v9 = 87;
        goto LABEL_17;
      }
      goto LABEL_85;
    }
    lpFile = 0;
    v14 = SczAllocConcat2Sz(&lpFile, ProfileDir, L"\\");
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 91;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
        (const char *)(unsigned int)v14,
        ReferencedDomainName);
LABEL_37:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFile);
      goto LABEL_86;
    }
    v14 = SczAllocConcatSz(&lpFile, Name);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 92;
      goto LABEL_36;
    }
    v14 = SczAllocConcatSz(&lpFile, L"\\ntuser.dat");
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 93;
      goto LABEL_36;
    }
    KeyW = RegLoadKeyW(HKEY_USERS, lpSubKeya, lpFile);
    if ( KeyW < 0 )
      __fastfail(7u);
    if ( KeyW )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"RegLoadKey failed.");
        *(_DWORD *)Data = (unsigned __int16)KeyW | 0x80070000;
        p_peUse = (HKEY)Data;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_peUse);
      }
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x5F,
              (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
              (const char *)(unsigned int)KeyW,
              ReferencedDomainName);
      goto LABEL_37;
    }
    p_lpSubKeya = &lpSubKeya;
    v36[0] = 1;
    v17 = SczAllocFromSz(&lpFile, lpSubKeya);
    v11 = v17;
    if ( v17 < 0 )
    {
      v18 = 100;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
        (const char *)(unsigned int)v17,
        ReferencedDomainName);
LABEL_51:
      Windows::Detail::OnBlockExitImpl__AddBootReminder_::_2_::_lambda_1___::_OnBlockExitImpl__AddBootReminder_::_2_::_lambda_1___(v36);
      goto LABEL_37;
    }
    v17 = SczAllocConcat2Sz(
            &lpFile,
            L"\\",
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders");
    v11 = v17;
    if ( v17 < 0 )
    {
      v18 = 102;
      goto LABEL_50;
    }
    hKey = 0;
    phkResult = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hKey);
    Key = RegCreateKeyExW(HKEY_USERS, lpFile, 0, 0, 0, 0x20006u, 0, phkResult, 0);
    if ( Key < 0 )
      __fastfail(7u);
    if ( Key )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"RegCreateKeyExW failed.");
        *(_DWORD *)Data = (unsigned __int16)Key | 0x80070000;
        p_peUse = (HKEY)Data;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_peUse);
      }
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6B,
              (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
              (const char *)(unsigned int)Key,
              ReferencedDomainNamea);
      goto LABEL_60;
    }
    if ( lpSubKey )
    {
      p_peUse = 0;
      InitPointer = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&p_peUse);
      v22 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, InitPointer, 0);
      if ( v22 < 0 )
        __fastfail(7u);
      if ( v22 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"RegCreateKeyExW failed.");
          *(_DWORD *)Data = (unsigned __int16)v22 | 0x80070000;
          *(_QWORD *)v38 = Data;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v38);
        }
        v23 = (unsigned int)v22;
        v24 = 118;
        goto LABEL_68;
      }
      if ( a2 )
      {
        v25 = RegSetString(p_peUse, L"Title", a2);
        if ( v25 )
        {
          v23 = v25;
          v24 = 122;
LABEL_68:
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v24,
                  (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
                  (const char *)v23,
                  ReferencedDomainNameb);
          Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&p_peUse);
LABEL_60:
          Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
          goto LABEL_51;
        }
      }
      if ( a3 )
      {
        v26 = RegSetString(p_peUse, L"Text", a3);
        if ( v26 )
        {
          v23 = v26;
          v24 = 127;
          goto LABEL_68;
        }
      }
      *(_DWORD *)Data = -1;
      v27 = RegSetValueExW(p_peUse, L"ShowTime", 0, 4u, Data, 4u);
      if ( v27 )
      {
        v23 = v27;
        v24 = 150;
        goto LABEL_68;
      }
      *(_DWORD *)Data = -1;
      v28 = RegSetValueExW(p_peUse, L"RetryInterval", 0, 4u, Data, 4u);
      if ( v28 )
      {
        v23 = v28;
        v24 = 151;
        goto LABEL_68;
      }
      *(_DWORD *)Data = -1;
      v29 = RegSetValueExW(p_peUse, L"RetryCount", 0, 4u, Data, 4u);
      if ( v29 )
      {
        v23 = v29;
        v24 = 152;
        goto LABEL_68;
      }
      *(_DWORD *)Data = 0;
      v30 = RegSetValueExW(p_peUse, L"TypeFlags", 0, 4u, Data, 4u);
      if ( v30 )
      {
        v23 = v30;
        v24 = 153;
        goto LABEL_68;
      }
      Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&p_peUse);
    }
    Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
    Windows::Detail::OnBlockExitImpl__AddBootReminder_::_2_::_lambda_1___::_OnBlockExitImpl__AddBootReminder_::_2_::_lambda_1___(v36);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFile);
    goto LABEL_85;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"ConvertStringSidToSid failed.");
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    else
      v8 = LastError;
    peUse = v8;
    p_peUse = (HKEY)&peUse;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)&p_peUse);
  }
  if ( !LastError )
    goto LABEL_85;
  v9 = 70;
LABEL_17:
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\base\\cbs\\core\\bootreminder.cpp",
          (const char *)(unsigned int)LastError,
          ReferencedDomainName);
LABEL_86:
  Windows::Auto<_ACL>::Close(&Sid);
  return v11;
}

```

## disassembly

```asm
0x180094df4  push    rbp
0x180094df6  push    rbx
0x180094df7  push    rsi
0x180094df8  push    rdi
0x180094df9  push    r12
0x180094dfb  push    r13
0x180094dfd  push    r14
0x180094dff  push    r15
0x180094e01  lea     rbp, [rsp-5F8h]
0x180094e09  sub     rsp, 6F8h
0x180094e10  mov     rax, cs:__security_cookie
0x180094e17  xor     rax, rsp
0x180094e1a  mov     [rbp+630h+var_50], rax
0x180094e21  mov     r14, rdx
0x180094e24  mov     [rsp+730h+lpSubKey], r9
0x180094e29  mov     r15, rcx
0x180094e2c  lea     rdx, [rbp+630h+Sid]; Sid
0x180094e30  xor     r12d, r12d
0x180094e33  mov     rcx, r9; StringSid
0x180094e36  mov     [rbp+630h+Sid], r12
0x180094e3a  mov     rsi, r8
0x180094e3d  call    cs:__imp_ConvertStringSidToSidW
0x180094e44  nop     dword ptr [rax+rax+00h]
0x180094e49  test    eax, eax
0x180094e4b  jnz     short loc_180094ECB
0x180094e4d  call    cs:__imp_GetLastError
0x180094e54  nop     dword ptr [rax+rax+00h]
0x180094e59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094e60  mov     edi, eax
0x180094e62  test    rcx, rcx
0x180094e65  jz      short loc_180094EB9
0x180094e67  lea     ebx, [r12+3]
0x180094e6c  xor     edx, edx
0x180094e6e  mov     r8d, ebx
0x180094e71  lea     r9, aConvertstrings; "ConvertStringSidToSid failed."
0x180094e78  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094e7d  test    edi, edi
0x180094e7f  jg      short loc_180094E85
0x180094e81  mov     eax, edi
0x180094e83  jmp     short loc_180094E8D
0x180094e85  movzx   eax, di
0x180094e88  or      eax, 80070000h
0x180094e8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094e94  lea     r9, a0; ": {0}"
0x180094e9b  mov     [rbp+630h+var_6A0], eax
0x180094e9e  mov     r8d, ebx
0x180094ea1  lea     rax, [rbp+630h+var_6A0]
0x180094ea5  mov     dl, 1
0x180094ea7  mov     [rbp+630h+var_6B0], rax
0x180094eab  lea     rax, [rbp+630h+var_6B0]
0x180094eaf  mov     [rsp+730h+ReferencedDomainName], rax
0x180094eb4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094eb9  test    edi, edi
0x180094ebb  jz      loc_180095612
0x180094ec1  mov     edx, 46h ; 'F'
0x180094ec6  jmp     loc_180094F5C
0x180094ecb  mov     rcx, [rbp+630h+Sid]; pSid
0x180094ecf  call    cs:__imp_IsValidSid
0x180094ed6  nop     dword ptr [rax+rax+00h]
0x180094edb  test    eax, eax
0x180094edd  jnz     loc_180094F79
0x180094ee3  call    cs:__imp_GetLastError
0x180094eea  nop     dword ptr [rax+rax+00h]
0x180094eef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094ef6  mov     edi, eax
0x180094ef8  test    rcx, rcx
0x180094efb  jz      short loc_180094F4F
0x180094efd  mov     ebx, 3
0x180094f02  lea     r9, aIsvalidsidFail; "IsValidSid failed."
0x180094f09  mov     r8d, ebx
0x180094f0c  xor     edx, edx
0x180094f0e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094f13  test    edi, edi
0x180094f15  jg      short loc_180094F1B
0x180094f17  mov     eax, edi
0x180094f19  jmp     short loc_180094F23
0x180094f1b  movzx   eax, di
0x180094f1e  or      eax, 80070000h
0x180094f23  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094f2a  lea     r9, a0; ": {0}"
0x180094f31  mov     [rbp+630h+var_6A0], eax
0x180094f34  mov     r8d, ebx
0x180094f37  lea     rax, [rbp+630h+var_6A0]
0x180094f3b  mov     dl, 1
0x180094f3d  mov     [rbp+630h+var_6B0], rax
0x180094f41  lea     rax, [rbp+630h+var_6B0]
0x180094f45  mov     [rsp+730h+ReferencedDomainName], rax; unsigned int
0x180094f4a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094f4f  test    edi, edi
0x180094f51  jz      loc_180095612
0x180094f57  mov     edx, 48h ; 'H'; void *
0x180094f5c  mov     rcx, [rbp+638h]; this
0x180094f63  lea     r8, aOnecoreBaseCbs_149; "onecore\\base\\cbs\\core\\bootreminder."...
0x180094f6a  mov     r9d, edi; char *
0x180094f6d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180094f72  mov     ebx, eax
0x180094f74  jmp     loc_180095615
0x180094f79  mov     ebx, 208h
0x180094f7e  lea     rcx, [rbp+630h+Name]; void *
0x180094f85  mov     r8d, ebx; Size
0x180094f88  xor     edx, edx; Val
0x180094f8a  call    memset_0
0x180094f8f  mov     edi, 104h
0x180094f94  lea     rcx, [rbp+630h+var_260]; void *
0x180094f9b  mov     r8d, ebx; Size
0x180094f9e  mov     [rbp+630h+cchName], edi
0x180094fa1  xor     edx, edx; Val
0x180094fa3  call    memset_0
0x180094fa8  mov     rdx, [rbp+630h+Sid]; Sid
0x180094fac  lea     rax, [rbp+630h+var_6A0]
0x180094fb0  mov     [rsp+730h+peUse], rax; peUse
0x180094fb5  lea     r9, [rbp+630h+cchName]; cchName
0x180094fb9  lea     rax, [rbp+630h+var_690]
0x180094fbd  mov     [rbp+630h+var_690], edi
0x180094fc0  mov     [rsp+730h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180094fc5  lea     r8, [rbp+630h+Name]; Name
0x180094fcc  lea     rax, [rbp+630h+var_260]
0x180094fd3  mov     [rbp+630h+var_6A0], r12d
0x180094fd7  xor     ecx, ecx; lpSystemName
0x180094fd9  mov     [rsp+730h+ReferencedDomainName], rax; int
0x180094fde  call    cs:__imp_LookupAccountSidW
0x180094fe5  nop     dword ptr [rax+rax+00h]
0x180094fea  test    eax, eax
0x180094fec  jnz     short loc_18009506C
0x180094fee  call    cs:__imp_GetLastError
0x180094ff5  nop     dword ptr [rax+rax+00h]
0x180094ffa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095001  mov     edi, eax
0x180095003  test    rcx, rcx
0x180095006  jz      short loc_18009505A
0x180095008  mov     ebx, 3
0x18009500d  lea     r9, aLookupaccounts; "LookupAccountSid failed."
0x180095014  mov     r8d, ebx
0x180095017  xor     edx, edx
0x180095019  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009501e  test    edi, edi
0x180095020  jg      short loc_180095026
0x180095022  mov     eax, edi
0x180095024  jmp     short loc_18009502E
0x180095026  movzx   eax, di
0x180095029  or      eax, 80070000h
0x18009502e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095035  lea     r9, a0; ": {0}"
0x18009503c  mov     [rbp+630h+cchSize], eax
0x18009503f  mov     r8d, ebx
0x180095042  lea     rax, [rbp+630h+cchSize]
0x180095046  mov     dl, 1
0x180095048  mov     [rbp+630h+var_6B0], rax
0x18009504c  lea     rax, [rbp+630h+var_6B0]
0x180095050  mov     [rsp+730h+ReferencedDomainName], rax
0x180095055  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009505a  test    edi, edi
0x18009505c  jz      loc_180095612
0x180095062  mov     edx, 51h ; 'Q'
0x180095067  jmp     loc_180094F5C
0x18009506c  mov     r8, rbx; Size
0x18009506f  lea     rcx, [rbp+630h+ProfileDir]; void *
0x180095073  xor     edx, edx; Val
0x180095075  call    memset_0
0x18009507a  lea     rdx, [rbp+630h+cchSize]; lpcchSize
0x18009507e  mov     [rbp+630h+cchSize], edi
0x180095081  lea     rcx, [rbp+630h+ProfileDir]; lpProfileDir
0x180095085  call    cs:__imp_GetProfilesDirectoryW
0x18009508c  nop     dword ptr [rax+rax+00h]
0x180095091  test    eax, eax
0x180095093  jnz     loc_180095119
0x180095099  call    cs:__imp_GetLastError
0x1800950a0  nop     dword ptr [rax+rax+00h]
0x1800950a5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800950ac  mov     edi, eax
0x1800950ae  test    rcx, rcx
0x1800950b1  jz      short loc_180095107
0x1800950b3  mov     ebx, 3
0x1800950b8  lea     r9, aGetprofilesdir; "GetProfilesDirectory failed."
0x1800950bf  mov     r8d, ebx
0x1800950c2  xor     edx, edx
0x1800950c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800950c9  test    edi, edi
0x1800950cb  jg      short loc_1800950D1
0x1800950cd  mov     eax, edi
0x1800950cf  jmp     short loc_1800950D9
0x1800950d1  movzx   eax, di
0x1800950d4  or      eax, 80070000h
0x1800950d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800950e0  lea     r9, a0; ": {0}"
0x1800950e7  mov     dword ptr [rsp+730h+Data], eax
0x1800950eb  mov     r8d, ebx
0x1800950ee  lea     rax, [rsp+730h+Data]
0x1800950f3  mov     dl, 1
0x1800950f5  mov     [rbp+630h+var_6B0], rax
0x1800950f9  lea     rax, [rbp+630h+var_6B0]
0x1800950fd  mov     [rsp+730h+ReferencedDomainName], rax
0x180095102  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180095107  test    edi, edi
0x180095109  jz      loc_180095612
0x18009510f  mov     edx, 57h ; 'W'
0x180095114  jmp     loc_180094F5C
0x180095119  lea     r8, SubBlock; "\\"
0x180095120  mov     [rsp+730h+lpFile], r12
0x180095125  lea     rdx, [rbp+630h+ProfileDir]
0x180095129  lea     rcx, [rsp+730h+lpFile]
0x18009512e  call    SczAllocConcat2Sz
0x180095133  mov     ebx, eax
0x180095135  test    eax, eax
0x180095137  jns     short loc_180095163
0x180095139  mov     edx, 5Bh ; '['; void *
0x18009513e  mov     rcx, [rbp+638h]; this
0x180095145  lea     r8, aOnecoreBaseCbs_149; "onecore\\base\\cbs\\core\\bootreminder."...
0x18009514c  mov     r9d, eax; char *
0x18009514f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095154  lea     rcx, [rsp+730h+lpFile]
0x180095159  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009515e  jmp     loc_180095615
0x180095163  lea     rdx, [rbp+630h+Name]
0x18009516a  lea     rcx, [rsp+730h+lpFile]
0x18009516f  call    SczAllocConcatSz
0x180095174  mov     ebx, eax
0x180095176  test    eax, eax
0x180095178  jns     short loc_180095181
0x18009517a  mov     edx, 5Ch ; '\'
0x18009517f  jmp     short loc_18009513E
0x180095181  lea     rdx, aNtuserDat; "\\ntuser.dat"
0x180095188  lea     rcx, [rsp+730h+lpFile]
0x18009518d  call    SczAllocConcatSz
0x180095192  mov     ebx, eax
0x180095194  test    eax, eax
0x180095196  jns     short loc_18009519F
0x180095198  mov     edx, 5Dh ; ']'
0x18009519d  jmp     short loc_18009513E
0x18009519f  mov     r8, [rsp+730h+lpFile]; lpFile
0x1800951a4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800951ab  mov     rdx, [rsp+730h+lpSubKey]; lpSubKey
0x1800951b0  call    cs:__imp_RegLoadKeyW
0x1800951b7  nop     dword ptr [rax+rax+00h]
0x1800951bc  mov     edi, eax
0x1800951be  mov     r13d, 7
0x1800951c4  test    eax, eax
0x1800951c6  jns     short loc_1800951CD
0x1800951c8  mov     ecx, r13d
0x1800951cb  int     29h; Win8: RtlFailFast(ecx)
0x1800951cd  test    edi, edi
0x1800951cf  jz      loc_180095257
0x1800951d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800951dc  test    rcx, rcx
0x1800951df  jz      short loc_180095235
0x1800951e1  mov     ebx, 3
0x1800951e6  lea     r9, aRegloadkeyFail; "RegLoadKey failed."
0x1800951ed  mov     r8d, ebx
0x1800951f0  xor     edx, edx
0x1800951f2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800951f7  test    edi, edi
0x1800951f9  jg      short loc_1800951FF
0x1800951fb  mov     eax, edi
0x1800951fd  jmp     short loc_180095207
0x1800951ff  movzx   eax, di
0x180095202  or      eax, 80070000h
0x180095207  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009520e  lea     r9, a0; ": {0}"
0x180095215  mov     dword ptr [rsp+730h+Data], eax
0x180095219  mov     r8d, ebx
0x18009521c  lea     rax, [rsp+730h+Data]
0x180095221  mov     dl, 1
0x180095223  mov     [rbp+630h+var_6B0], rax
0x180095227  lea     rax, [rbp+630h+var_6B0]
0x18009522b  mov     [rsp+730h+ReferencedDomainName], rax; unsigned int
0x180095230  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180095235  mov     rcx, [rbp+638h]; this
0x18009523c  lea     r8, aOnecoreBaseCbs_149; "onecore\\base\\cbs\\core\\bootreminder."...
0x180095243  mov     r9d, edi; char *
0x180095246  mov     edx, 5Fh ; '_'; void *
0x18009524b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180095250  mov     ebx, eax
0x180095252  jmp     loc_180095154
0x180095257  mov     rdx, [rsp+730h+lpSubKey]
0x18009525c  lea     rax, [rsp+730h+lpSubKey]
0x180095261  lea     rcx, [rsp+730h+lpFile]
0x180095266  mov     [rsp+730h+var_6D0], rax
0x18009526b  mov     [rsp+730h+var_6D8], 1
0x180095270  call    SczAllocFromSz
0x180095275  mov     ebx, eax
0x180095277  test    eax, eax
0x180095279  jns     short loc_1800952A5
0x18009527b  mov     edx, 64h ; 'd'; void *
0x180095280  mov     rcx, [rbp+638h]; this
0x180095287  lea     r8, aOnecoreBaseCbs_149; "onecore\\base\\cbs\\core\\bootreminder."...
0x18009528e  mov     r9d, eax; char *
0x180095291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095296  lea     rcx, [rsp+730h+var_6D8]
0x18009529b  call    Windows__Detail__OnBlockExitImpl__AddBootReminder____2____lambda_1______OnBlockExitImpl__AddBootReminder____2____lambda_1___
0x1800952a0  jmp     loc_180095154
0x1800952a5  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800952ac  lea     rdx, SubBlock; "\\"
0x1800952b3  lea     rcx, [rsp+730h+lpFile]
0x1800952b8  call    SczAllocConcat2Sz
0x1800952bd  mov     ebx, eax
0x1800952bf  test    eax, eax
0x1800952c1  jns     short loc_1800952CA
0x1800952c3  mov     edx, 66h ; 'f'
0x1800952c8  jmp     short loc_180095280
0x1800952ca  lea     rcx, [rbp+630h+hKey]
  ... truncated ...
```
