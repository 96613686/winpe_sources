# EnsureAndGetSharedPCRegistryKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x1800223cc`
- end: `0x180022557`
- name: `?EnsureAndGetSharedPCRegistryKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `395`
- prototype: `HKEY __fastcall(__int64, REGSAM)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c2c0`
- `0x18001aab0`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x180013dcc`
- `0x1800223cc`
- `0x1800226e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800224e7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800224e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022475`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022475`

## string_xrefs

- `0x180022407`: `SharedPCConfiguration`
- `0x180022486`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x1800224f8`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HKEY __fastcall EnsureAndGetSharedPCRegistryKey(__int64 a1, REGSAM a2)
{
  const WCHAR *v3; // rax
  unsigned int v4; // eax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  HKEY v7; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  HKEY v11; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v14[32]; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  std::wstring::wstring((__int64)v14, (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC");
  std::wstring::wstring((__int64)v13, (__int64)L"SharedPCConfiguration");
  GetPersistedRegistryLocationTargetPath((__int64)v15, (__int64)v13, (__int64)v14);
  std::wstring::_Tidy_deallocate((__int64)v13);
  std::wstring::_Tidy_deallocate((__int64)v14);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0xF003Fu, &hKey);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v4,
      phkResult);
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v6 = RegCreateKeyExW(hKey, v5, 0, 0, 0, a2, 0, &v11, 0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x24,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v6,
      phkResulta);
  v7 = v11;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate((__int64)v15);
  return v7;
}

```

## disassembly

```asm
0x1800223cc  mov     [rsp-8+arg_10], rbx
0x1800223d1  mov     [rsp-8+arg_18], rdi
0x1800223d6  push    rbp
0x1800223d7  lea     rbp, [rsp-57h]
0x1800223dc  sub     rsp, 0D0h
0x1800223e3  mov     rax, cs:__security_cookie
0x1800223ea  xor     rax, rsp
0x1800223ed  mov     [rbp+57h+var_10], rax
0x1800223f1  mov     edi, edx
0x1800223f3  mov     rbx, rcx
0x1800223f6  lea     rdx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800223fd  lea     rcx, [rbp+57h+var_50]
0x180022401  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022406  nop
0x180022407  lea     rdx, aSharedpcconfig; "SharedPCConfiguration"
0x18002240e  lea     rcx, [rbp+57h+var_70]
0x180022412  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022417  nop
0x180022418  lea     r8, [rbp+57h+var_50]
0x18002241c  lea     rdx, [rbp+57h+var_70]
0x180022420  lea     rcx, [rbp+57h+var_30]
0x180022424  call    ?GetPersistedRegistryLocationTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@0@Z; GetPersistedRegistryLocationTargetPath(std::wstring const &,std::wstring const &)
0x180022429  nop
0x18002242a  lea     rcx, [rbp+57h+var_70]
0x18002242e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022433  nop
0x180022434  lea     rcx, [rbp+57h+var_50]
0x180022438  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002243d  mov     [rbp+57h+hKey], 0
0x180022445  xor     edx, edx
0x180022447  lea     rcx, [rbp+57h+hKey]
0x18002244b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022450  lea     rcx, [rbp+57h+var_30]
0x180022454  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022459  mov     rdx, rax; lpSubKey
0x18002245c  lea     rax, [rbp+57h+hKey]
0x180022460  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180022465  mov     r9d, 0F003Fh; samDesired
0x18002246b  xor     r8d, r8d; ulOptions
0x18002246e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022475  call    cs:__imp_RegOpenKeyExW
0x18002247b  mov     rcx, [rbp+5Fh]; this
0x18002247f  test    eax, eax
0x180022481  jz      short loc_180022498
0x180022483  mov     r9d, eax; char *
0x180022486  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002248d  mov     edx, 21h ; '!'; void *
0x180022492  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022498  mov     [rbp+57h+var_80], 0
0x1800224a0  xor     edx, edx
0x1800224a2  lea     rcx, [rbp+57h+var_80]
0x1800224a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800224ab  mov     rcx, rbx
0x1800224ae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800224b3  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x1800224bc  lea     rcx, [rbp+57h+var_80]
0x1800224c0  mov     [rsp+0D0h+var_98], rcx; phkResult
0x1800224c5  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800224ce  mov     [rsp+0D0h+samDesired], edi; samDesired
0x1800224d2  mov     dword ptr [rsp+0D0h+phkResult], 0; unsigned int
0x1800224da  xor     r9d, r9d; lpClass
0x1800224dd  xor     r8d, r8d; Reserved
0x1800224e0  mov     rdx, rax; lpSubKey
0x1800224e3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800224e7  call    cs:__imp_RegCreateKeyExW
0x1800224ed  mov     rcx, [rbp+5Fh]; this
0x1800224f1  test    eax, eax
0x1800224f3  jz      short loc_18002250A
0x1800224f5  mov     r9d, eax; char *
0x1800224f8  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800224ff  mov     edx, 24h ; '$'; void *
0x180022504  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002250a  mov     rbx, [rbp+57h+var_80]
0x18002250e  mov     [rbp+57h+var_80], 0
0x180022516  lea     rcx, [rbp+57h+var_80]
0x18002251a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002251f  nop
0x180022520  lea     rcx, [rbp+57h+hKey]
0x180022524  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022529  nop
0x18002252a  lea     rcx, [rbp+57h+var_30]
0x18002252e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022533  mov     rax, rbx
0x180022536  mov     rcx, [rbp+57h+var_10]
0x18002253a  xor     rcx, rsp; StackCookie
0x18002253d  call    __security_check_cookie
0x180022542  lea     r11, [rsp+0D0h+var_s0]
0x18002254a  mov     rbx, [r11+20h]
0x18002254e  mov     rdi, [r11+28h]
0x180022552  mov     rsp, r11
0x180022555  pop     rbp
0x180022556  retn
```
