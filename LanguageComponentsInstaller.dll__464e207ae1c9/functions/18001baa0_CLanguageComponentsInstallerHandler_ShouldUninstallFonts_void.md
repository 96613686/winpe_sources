# CLanguageComponentsInstallerHandler::ShouldUninstallFonts(void)

- ea: `0x18001baa0`
- end: `0x18001bb74`
- name: `?ShouldUninstallFonts@CLanguageComponentsInstallerHandler@@AEBA_NXZ`
- size: `212`
- prototype: `bool __fastcall(CLanguageComponentsInstallerHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180003520`
- `0x180006380`
- `0x180018234`
- `0x18001baa0`
- `0x180021494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bb1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bb1e`

## string_xrefs

- `0x18001bae6`: `ShouldUninstallFonts`
- `0x18001bb5f`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
bool __fastcall CLanguageComponentsInstallerHandler::ShouldUninstallFonts(CLanguageComponentsInstallerHandler *this)
{
  __int64 RegistryKeyPath; // rax
  const WCHAR *v3; // rdx
  __int64 v4; // rcx
  unsigned int ValueW; // ebx
  unsigned int pdwType; // [rsp+20h] [rbp-58h]
  _BYTE v8[32]; // [rsp+40h] [rbp-38h] BYREF
  int pvData; // [rsp+60h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  pvData = 0;
  pcbData = 4;
  RegistryKeyPath = CLanguageComponentsInstallerHandler::GetRegistryKeyPath((__int64)this, (__int64)v8);
  v3 = (const WCHAR *)RegistryKeyPath;
  if ( *(_QWORD *)(RegistryKeyPath + 24) > 7u )
    v3 = *(const WCHAR **)RegistryKeyPath;
  v4 = -2147483646;
  if ( *((_QWORD *)this + 35) )
    v4 = *((_QWORD *)this + 35);
  ValueW = RegGetValueW((HKEY)v4, v3, L"ShouldUninstallFonts", 0x18u, 0, &pvData, &pcbData);
  std::wstring::~wstring(v8);
  if ( ValueW - 2 <= 1 )
    return 1;
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)ValueW,
      pdwType);
  return pvData != 0;
}

```

## disassembly

```asm
0x18001baa0  push    rbx
0x18001baa2  sub     rsp, 70h
0x18001baa6  mov     rax, cs:__security_cookie
0x18001baad  xor     rax, rsp
0x18001bab0  mov     [rsp+78h+var_10], rax
0x18001bab5  lea     rdx, [rsp+78h+var_38]
0x18001baba  mov     [rsp+78h+var_18], 0
0x18001bac2  mov     rbx, rcx
0x18001bac5  mov     [rsp+78h+var_14], 4
0x18001bacd  call    ?GetRegistryKeyPath@CLanguageComponentsInstallerHandler@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CLanguageComponentsInstallerHandler::GetRegistryKeyPath(void)
0x18001bad2  mov     rdx, rax
0x18001bad5  cmp     qword ptr [rax+18h], 7
0x18001bada  jbe     short loc_18001BADF
0x18001badc  mov     rdx, [rax]; lpSubKey
0x18001badf  mov     rax, [rbx+118h]
0x18001bae6  lea     r8, ValueName; "ShouldUninstallFonts"
0x18001baed  test    rax, rax
0x18001baf0  mov     rcx, 0FFFFFFFF80000002h
0x18001baf7  mov     r9d, 18h; dwFlags
0x18001bafd  cmovnz  rcx, rax; hkey
0x18001bb01  lea     rax, [rsp+78h+var_14]
0x18001bb06  mov     [rsp+78h+pcbData], rax; pcbData
0x18001bb0b  lea     rax, [rsp+78h+var_18]
0x18001bb10  mov     [rsp+78h+pvData], rax; pvData
0x18001bb15  mov     [rsp+78h+pdwType], 0; unsigned int
0x18001bb1e  call    cs:__imp_RegGetValueW
0x18001bb24  lea     rcx, [rsp+78h+var_38]; void *
0x18001bb29  mov     ebx, eax
0x18001bb2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bb30  lea     ecx, [rbx-2]
0x18001bb33  cmp     ecx, 1
0x18001bb36  jbe     short loc_18001BB45
0x18001bb38  test    ebx, ebx
0x18001bb3a  jnz     short loc_18001BB5A
0x18001bb3c  cmp     [rsp+78h+var_18], ebx
0x18001bb40  setnz   al
0x18001bb43  jmp     short loc_18001BB47
0x18001bb45  mov     al, 1
0x18001bb47  mov     rcx, [rsp+78h+var_10]
0x18001bb4c  xor     rcx, rsp; StackCookie
0x18001bb4f  call    __security_check_cookie
0x18001bb54  add     rsp, 70h
0x18001bb58  pop     rbx
0x18001bb59  retn
0x18001bb5a  mov     rcx, [rsp+78h]; this
0x18001bb5f  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001bb66  mov     r9d, ebx; char *
0x18001bb69  mov     edx, 133h; void *
0x18001bb6e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
