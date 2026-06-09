# AclCheckTrustedInstallerAccess

- ea: `0x1400189c8`
- end: `0x140018b48`
- name: `AclCheckTrustedInstallerAccess`
- size: `384`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000766c`

## callees

- `0x140002310`
- `0x140008d38`
- `0x140008ef4`
- `0x14000f36c`
- `0x1400189a8`
- `0x1400189c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018a94`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140018a86`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140018a86`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400189fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400189fd`

## string_xrefs

- `0x140018b04`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x140018a1d`: `Failed to convert TrustedInstaller SID`

## pseudocode

```c
__int64 AclCheckTrustedInstallerAccess()
{
  signed int LastError; // ebx
  int v1; // edx
  unsigned int v2; // eax
  __int64 v3; // rdx
  int v4; // edx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-40h]
  unsigned int v9; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v10[2]; // [rsp+38h] [rbp-28h] BYREF
  WINBOOL IsMember; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  IsMember = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464", &Sid) )
  {
    if ( CheckTokenMembership(0, Sid, &IsMember) )
    {
      if ( !IsMember )
      {
        v6 = -2147024891;
        goto LABEL_21;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to check TI membership");
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        else
          v5 = LastError;
        v9 = v5;
        *(_QWORD *)v10 = &v9;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v4,
          3,
          (unsigned int)": {0}",
          (__int64)v10);
      }
      if ( LastError )
      {
        v3 = 145;
        goto LABEL_17;
      }
    }
LABEL_20:
    v6 = 0;
    goto LABEL_21;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert TrustedInstaller SID");
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    else
      v2 = LastError;
    v9 = v2;
    *(_QWORD *)v10 = &v9;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v1,
      3,
      (unsigned int)": {0}",
      (__int64)v10);
  }
  if ( !LastError )
    goto LABEL_20;
  v3 = 141;
LABEL_17:
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
         (const char *)(unsigned int)LastError,
         v8);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  return v6;
}

```

## disassembly

```asm
0x1400189c8  mov     [rsp-8+arg_0], rbx
0x1400189cd  push    rbp
0x1400189ce  mov     rbp, rsp
0x1400189d1  sub     rsp, 60h
0x1400189d5  mov     rax, cs:__security_cookie
0x1400189dc  xor     rax, rsp
0x1400189df  mov     [rbp+var_10], rax
0x1400189e3  lea     rdx, [rbp+Sid]; Sid
0x1400189e7  mov     [rbp+IsMember], 0
0x1400189ee  lea     rcx, StringSid; "S-1-5-80-956008885-3418522649-183103804"...
0x1400189f5  mov     [rbp+Sid], 0
0x1400189fd  call    cs:__imp_ConvertStringSidToSidW
0x140018a03  test    eax, eax
0x140018a05  jnz     short loc_140018A7C
0x140018a07  call    cs:__imp_GetLastError
0x140018a0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018a14  mov     ebx, eax
0x140018a16  test    rcx, rcx
0x140018a19  jz      short loc_140018A6A
0x140018a1b  xor     edx, edx
0x140018a1d  lea     r9, aFailedToConver_0; "Failed to convert TrustedInstaller SID"
0x140018a24  lea     r8d, [rdx+3]
0x140018a28  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018a2d  test    ebx, ebx
0x140018a2f  jg      short loc_140018A35
0x140018a31  mov     eax, ebx
0x140018a33  jmp     short loc_140018A3D
0x140018a35  movzx   eax, bx
0x140018a38  or      eax, 80070000h
0x140018a3d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018a44  lea     r9, a0; ": {0}"
0x140018a4b  mov     [rbp+var_30], eax
0x140018a4e  mov     r8d, 3
0x140018a54  lea     rax, [rbp+var_30]
0x140018a58  mov     qword ptr [rbp+var_28], rax
0x140018a5c  lea     rax, [rbp+var_28]
0x140018a60  mov     qword ptr [rsp+60h+var_40], rax
0x140018a65  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018a6a  test    ebx, ebx
0x140018a6c  jz      loc_140018B24
0x140018a72  mov     edx, 8Dh
0x140018a77  jmp     loc_140018B00
0x140018a7c  mov     rdx, [rbp+Sid]; SidToCheck
0x140018a80  lea     r8, [rbp+IsMember]; IsMember
0x140018a84  xor     ecx, ecx; TokenHandle
0x140018a86  call    cs:__imp_CheckTokenMembership
0x140018a8c  test    eax, eax
0x140018a8e  jnz     loc_140018B17
0x140018a94  call    cs:__imp_GetLastError
0x140018a9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018aa1  mov     ebx, eax
0x140018aa3  test    rcx, rcx
0x140018aa6  jz      short loc_140018AF7
0x140018aa8  xor     edx, edx
0x140018aaa  lea     r9, aFailedToCheckT; "Failed to check TI membership"
0x140018ab1  lea     r8d, [rdx+3]
0x140018ab5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018aba  test    ebx, ebx
0x140018abc  jg      short loc_140018AC2
0x140018abe  mov     eax, ebx
0x140018ac0  jmp     short loc_140018ACA
0x140018ac2  movzx   eax, bx
0x140018ac5  or      eax, 80070000h
0x140018aca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018ad1  lea     r9, a0; ": {0}"
0x140018ad8  mov     [rbp+var_30], eax
0x140018adb  mov     r8d, 3
0x140018ae1  lea     rax, [rbp+var_30]
0x140018ae5  mov     qword ptr [rbp+var_28], rax
0x140018ae9  lea     rax, [rbp+var_28]
0x140018aed  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x140018af2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018af7  test    ebx, ebx
0x140018af9  jz      short loc_140018B24
0x140018afb  mov     edx, 91h; void *
0x140018b00  mov     rcx, [rbp+8]; this
0x140018b04  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x140018b0b  mov     r9d, ebx; char *
0x140018b0e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140018b13  mov     ebx, eax
0x140018b15  jmp     short loc_140018B26
0x140018b17  cmp     [rbp+IsMember], 0
0x140018b1b  jnz     short loc_140018B24
0x140018b1d  mov     ebx, 80070005h
0x140018b22  jmp     short loc_140018B26
0x140018b24  xor     ebx, ebx
0x140018b26  lea     rcx, [rbp+Sid]
0x140018b2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018b2f  mov     eax, ebx
0x140018b31  mov     rcx, [rbp+var_10]
0x140018b35  xor     rcx, rsp; StackCookie
0x140018b38  call    __security_check_cookie
0x140018b3d  mov     rbx, [rsp+60h+arg_0]
0x140018b42  add     rsp, 60h
0x140018b46  pop     rbp
0x140018b47  retn
```
