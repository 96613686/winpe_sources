# GetSharedPCRegistryKeyIfExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x1800227e4`
- end: `0x180022974`
- name: `?GetSharedPCRegistryKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d480`
- `0x180020cf8`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x180013dcc`
- `0x1800226e4`
- `0x1800227e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800228dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800228dd`

## string_xrefs

- `0x180022818`: `SharedPCConfiguration`
- `0x180022897`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x180022919`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HKEY GetSharedPCRegistryKeyIfExists()
{
  const WCHAR *v0; // rax
  unsigned int v1; // eax
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  unsigned __int64 v4; // r9
  HKEY v6; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-39h]
  int phkResulta; // [rsp+20h] [rbp-39h]
  HKEY v10; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v14[32]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  std::wstring::wstring((__int64)v13, (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC");
  std::wstring::wstring((__int64)v12, (__int64)L"SharedPCConfiguration");
  GetPersistedRegistryLocationTargetPath((__int64)v14, (__int64)v12, (__int64)v13);
  std::wstring::_Tidy_deallocate((__int64)v12);
  std::wstring::_Tidy_deallocate((__int64)v13);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x20019u, &hKey);
  if ( v1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v1,
      phkResult);
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v10,
    0);
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v3 = RegOpenKeyExW(hKey, v2, 0, 9u, &v10);
  v4 = (unsigned int)v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (int)(v4 + 0x80000000) >= 0 && (_DWORD)v4 != -2147024894 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x31,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v4,
      phkResulta);
  v6 = v10;
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate((__int64)v14);
  return v6;
}

```

## disassembly

```asm
0x1800227e4  mov     [rsp-8+arg_8], rbx
0x1800227e9  push    rbp
0x1800227ea  lea     rbp, [rsp-57h]
0x1800227ef  sub     rsp, 0B0h
0x1800227f6  mov     rax, cs:__security_cookie
0x1800227fd  xor     rax, rsp
0x180022800  mov     [rbp+57h+var_10], rax
0x180022804  mov     rbx, rcx
0x180022807  lea     rdx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002280e  lea     rcx, [rbp+57h+var_50]
0x180022812  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022817  nop
0x180022818  lea     rdx, aSharedpcconfig; "SharedPCConfiguration"
0x18002281f  lea     rcx, [rbp+57h+var_70]
0x180022823  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022828  nop
0x180022829  lea     r8, [rbp+57h+var_50]
0x18002282d  lea     rdx, [rbp+57h+var_70]
0x180022831  lea     rcx, [rbp+57h+var_30]
0x180022835  call    ?GetPersistedRegistryLocationTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@0@Z; GetPersistedRegistryLocationTargetPath(std::wstring const &,std::wstring const &)
0x18002283a  nop
0x18002283b  lea     rcx, [rbp+57h+var_70]
0x18002283f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022844  nop
0x180022845  lea     rcx, [rbp+57h+var_50]
0x180022849  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002284e  mov     [rbp+57h+hKey], 0
0x180022856  xor     edx, edx
0x180022858  lea     rcx, [rbp+57h+hKey]
0x18002285c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022861  lea     rcx, [rbp+57h+var_30]
0x180022865  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002286a  mov     rdx, rax; lpSubKey
0x18002286d  lea     rax, [rbp+57h+hKey]
0x180022871  mov     qword ptr [rsp+0B0h+phkResult], rax; unsigned int
0x180022876  mov     r9d, 20019h; samDesired
0x18002287c  xor     r8d, r8d; ulOptions
0x18002287f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022886  call    cs:__imp_RegOpenKeyExW
0x18002288c  mov     rcx, [rbp+5Fh]; this
0x180022890  test    eax, eax
0x180022892  jz      short loc_1800228A9
0x180022894  mov     r9d, eax; char *
0x180022897  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002289e  mov     edx, 2Dh ; '-'; void *
0x1800228a3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800228a9  mov     [rbp+57h+var_80], 0
0x1800228b1  xor     edx, edx
0x1800228b3  lea     rcx, [rbp+57h+var_80]
0x1800228b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800228bc  mov     rcx, rbx
0x1800228bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800228c4  lea     rcx, [rbp+57h+var_80]
0x1800228c8  mov     qword ptr [rsp+0B0h+phkResult], rcx; int
0x1800228cd  mov     r9d, 9; samDesired
0x1800228d3  xor     r8d, r8d; ulOptions
0x1800228d6  mov     rdx, rax; lpSubKey
0x1800228d9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800228dd  call    cs:__imp_RegOpenKeyExW
0x1800228e3  mov     r9d, eax
0x1800228e6  test    eax, eax
0x1800228e8  jle     short loc_1800228F5
0x1800228ea  movzx   r9d, ax
0x1800228ee  or      r9d, 80070000h; char *
0x1800228f5  mov     ecx, 80000000h
0x1800228fa  lea     eax, [r9+rcx]
0x1800228fe  test    ecx, eax
0x180022900  jnz     short loc_18002290F
0x180022902  cmp     r9d, 80070002h
0x180022909  jz      short loc_18002290F
0x18002290b  mov     al, 1
0x18002290d  jmp     short loc_180022911
0x18002290f  xor     al, al
0x180022911  mov     rcx, [rbp+5Fh]; this
0x180022915  test    al, al
0x180022917  jz      short loc_18002292B
0x180022919  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022920  mov     edx, 31h ; '1'; void *
0x180022925  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002292b  mov     rbx, [rbp+57h+var_80]
0x18002292f  mov     [rbp+57h+var_80], 0
0x180022937  lea     rcx, [rbp+57h+var_80]
0x18002293b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022940  nop
0x180022941  lea     rcx, [rbp+57h+hKey]
0x180022945  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002294a  nop
0x18002294b  lea     rcx, [rbp+57h+var_30]
0x18002294f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022954  mov     rax, rbx
0x180022957  mov     rcx, [rbp+57h+var_10]
0x18002295b  xor     rcx, rsp; StackCookie
0x18002295e  call    __security_check_cookie
0x180022963  mov     rbx, [rsp+0B0h+arg_8]
0x18002296b  add     rsp, 0B0h
0x180022972  pop     rbp
0x180022973  retn
```
