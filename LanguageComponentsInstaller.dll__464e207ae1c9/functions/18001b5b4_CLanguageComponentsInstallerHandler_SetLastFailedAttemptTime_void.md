# CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime(void)

- ea: `0x18001b5b4`
- end: `0x18001b720`
- name: `?SetLastFailedAttemptTime@CLanguageComponentsInstallerHandler@@AEBAXXZ`
- size: `364`
- prototype: `void __fastcall(CLanguageComponentsInstallerHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d0f0`

## callees

- `0x180003520`
- `0x180006380`
- `0x180018234`
- `0x180018ac4`
- `0x18001b5b4`
- `0x180021494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b656`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b656`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b6cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b6cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b6b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b6b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b684`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b684`

## string_xrefs

- `0x18001b6a5`: `LastFailedAttemptTime`
- `0x18001b6f8`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x18001b70d`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
void __fastcall CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime(
        CLanguageComponentsInstallerHandler *this)
{
  __int64 v2; // rbx
  __int64 RegistryKeyPath; // rax
  unsigned int v4; // eax
  unsigned int v5; // eax
  const char *v6; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-78h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-78h]
  _BYTE v9[32]; // [rsp+50h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( IsRunningAsLocalSystem() )
  {
    v2 = -2147483646;
    if ( *((_QWORD *)this + 35) )
      v2 = *((_QWORD *)this + 35);
  }
  else
  {
    v2 = -2147483647;
  }
  try
  {
    hKey = 0;
    RegistryKeyPath = CLanguageComponentsInstallerHandler::GetRegistryKeyPath((__int64)this, (__int64)v9);
    if ( *(_QWORD *)(RegistryKeyPath + 24) > 7u )
      RegistryKeyPath = *(_QWORD *)RegistryKeyPath;
    v4 = RegCreateKeyExW((HKEY)v2, (LPCWSTR)RegistryKeyPath, 0, 0, 0, 0x102u, 0, &hKey, 0);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)v4,
        dwOptions);
    std::wstring::~wstring(v9);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v5 = RegSetValueExW(hKey, L"LastFailedAttemptTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)v5,
        dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18001b5b4  mov     [rsp+arg_8], rbx
0x18001b5b9  push    rdi
0x18001b5ba  sub     rsp, 90h
0x18001b5c1  mov     rax, cs:__security_cookie
0x18001b5c8  xor     rax, rsp
0x18001b5cb  mov     [rsp+98h+var_18], rax
0x18001b5d3  mov     rdi, rcx
0x18001b5d6  call    ?IsRunningAsLocalSystem@@YA_NXZ; IsRunningAsLocalSystem(void)
0x18001b5db  test    al, al
0x18001b5dd  jz      short loc_18001B5F6
0x18001b5df  mov     rax, [rdi+118h]
0x18001b5e6  mov     rbx, 0FFFFFFFF80000002h
0x18001b5ed  test    rax, rax
0x18001b5f0  cmovnz  rbx, rax
0x18001b5f4  jmp     short loc_18001B5FD
0x18001b5f6  mov     rbx, 0FFFFFFFF80000001h
0x18001b5fd  mov     [rsp+98h+hKey], 0
0x18001b606  lea     rdx, [rsp+98h+var_48]
0x18001b60b  mov     rcx, rdi
0x18001b60e  call    ?GetRegistryKeyPath@CLanguageComponentsInstallerHandler@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CLanguageComponentsInstallerHandler::GetRegistryKeyPath(void)
0x18001b613  nop
0x18001b614  cmp     qword ptr [rax+18h], 7
0x18001b619  jbe     short loc_18001B61E
0x18001b61b  mov     rax, [rax]
0x18001b61e  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x18001b627  lea     rcx, [rsp+98h+hKey]
0x18001b62c  mov     [rsp+98h+phkResult], rcx; phkResult
0x18001b631  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001b63a  mov     [rsp+98h+samDesired], 102h; samDesired
0x18001b642  mov     [rsp+98h+dwOptions], 0; unsigned int
0x18001b64a  xor     r9d, r9d; lpClass
0x18001b64d  xor     r8d, r8d; Reserved
0x18001b650  mov     rdx, rax; lpSubKey
0x18001b653  mov     rcx, rbx; hKey
0x18001b656  call    cs:__imp_RegCreateKeyExW
0x18001b65c  mov     rcx, [rsp+98h]; this
0x18001b664  test    eax, eax
0x18001b666  jnz     loc_18001B6F5
0x18001b66c  lea     rcx, [rsp+98h+var_48]; void *
0x18001b671  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b676  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001b67f  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001b684  call    cs:__imp_GetSystemTimeAsFileTime
0x18001b68a  mov     [rsp+98h+samDesired], 8; cbData
0x18001b692  lea     rax, [rsp+98h+SystemTimeAsFileTime]
0x18001b697  mov     qword ptr [rsp+98h+dwOptions], rax; unsigned int
0x18001b69c  mov     r9d, 0Bh; dwType
0x18001b6a2  xor     r8d, r8d; Reserved
0x18001b6a5  lea     rdx, aLastfailedatte; "LastFailedAttemptTime"
0x18001b6ac  mov     rcx, [rsp+98h+hKey]; hKey
0x18001b6b1  call    cs:__imp_RegSetValueExW
0x18001b6b7  mov     rcx, [rsp+98h]; this
0x18001b6bf  test    eax, eax
0x18001b6c1  jnz     short loc_18001B70A
0x18001b6c3  mov     rcx, [rsp+98h+hKey]; hKey
0x18001b6c8  test    rcx, rcx
0x18001b6cb  jz      short loc_18001B6D4
0x18001b6cd  call    cs:__imp_RegCloseKey
0x18001b6d3  nop
0x18001b6d4  mov     rcx, [rsp+98h+var_18]
0x18001b6dc  xor     rcx, rsp; StackCookie
0x18001b6df  call    __security_check_cookie
0x18001b6e4  mov     rbx, [rsp+98h+arg_8]
0x18001b6ec  add     rsp, 90h
0x18001b6f3  pop     rdi
0x18001b6f4  retn
0x18001b6f5  mov     r9d, eax; char *
0x18001b6f8  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001b6ff  mov     edx, 1A4h; void *
0x18001b704  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001b70a  mov     r9d, eax; char *
0x18001b70d  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001b714  mov     edx, 1AFh; void *
0x18001b719  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
