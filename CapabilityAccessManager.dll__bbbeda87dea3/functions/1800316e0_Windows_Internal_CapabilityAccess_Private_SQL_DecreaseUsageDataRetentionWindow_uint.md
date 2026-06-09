# Windows::Internal::CapabilityAccess::Private::SQL::DecreaseUsageDataRetentionWindow(uint)

- ea: `0x1800316e0`
- end: `0x18003187e`
- name: `?DecreaseUsageDataRetentionWindow@SQL@Private@CapabilityAccess@Internal@Windows@@YAXI@Z`
- size: `414`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Private::SQL *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800375f4`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800299c4`
- `0x18002f280`
- `0x1800316e0`
- `0x1800348a4`
- `0x1800349dc`
- `0x180037034`
- `0x18003ce34`
- `0x1800588a4`
- `0x180058fb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031792`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031792`

## string_xrefs

- `0x180031784`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180031821`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031839`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031854`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003186c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::CapabilityAccess::Private::SQL::DecreaseUsageDataRetentionWindow(
        Windows::Internal::CapabilityAccess::Private::SQL *this)
{
  Windows::Internal::CapabilityAccess::Private::SQL *v1; // rcx
  unsigned int ExpirationPolicyInDays; // ebx
  Windows::Internal::CapabilityAccess::Private::SQL *v3; // rcx
  unsigned int ExpirationPolicyFloorInDays; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // r9d
  DWORD dwOptions; // [rsp+20h] [rbp-78h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-78h]
  HKEY phkResult; // [rsp+50h] [rbp-48h] BYREF
  HKEY v11; // [rsp+58h] [rbp-40h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x736,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      dwOptions);
  phkResult = 0;
  ExpirationPolicyInDays = Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(v1);
  ExpirationPolicyFloorInDays = Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyFloorInDays(v3);
  v5 = ExpirationPolicyInDays - 1;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
  if ( v5 < ExpirationPolicyFloorInDays )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73E,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
         0,
         0,
         0,
         0xF013Fu,
         0,
         &phkResult,
         0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x741,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)v6,
      dwOptionsa);
  std::wstring::wstring(v12, &stru_1800D7150);
  Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(&v11);
  std::wstring::_Tidy_deallocate(v12);
  Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
    (Windows::Internal::CapabilityAccess::Private *)v11,
    (HKEY)&stru_1800D70C8,
    (const unsigned __int16 *)v5,
    v7);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x1800316e0  push    rbx
0x1800316e2  sub     rsp, 90h
0x1800316e9  mov     rax, cs:__security_cookie
0x1800316f0  xor     rax, rsp
0x1800316f3  mov     [rsp+98h+var_18], rax
0x1800316fb  mov     rbx, [rsp+98h]
0x180031703  call    ?IsDatabaseEnabledByEditionPolicy@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(void)
0x180031708  test    al, al
0x18003170a  jz      loc_180031833
0x180031710  mov     [rsp+98h+var_48], 0
0x180031719  call    ?GetExpirationPolicyInDays@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(void)
0x18003171e  mov     ebx, eax
0x180031720  call    ?GetExpirationPolicyFloorInDays@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyFloorInDays(void)
0x180031725  sub     ebx, 1
0x180031728  mov     rcx, [rsp+98h]; this
0x180031730  jz      loc_18003184E
0x180031736  mov     rcx, [rsp+98h]; this
0x18003173e  cmp     ebx, eax
0x180031740  jb      loc_180031866
0x180031746  xor     edx, edx
0x180031748  lea     rcx, [rsp+98h+var_48]
0x18003174d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031752  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x18003175b  lea     rax, [rsp+98h+var_48]
0x180031760  mov     [rsp+98h+phkResult], rax; phkResult
0x180031765  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003176e  mov     [rsp+98h+samDesired], 0F013Fh; samDesired
0x180031776  mov     [rsp+98h+dwOptions], 0; unsigned int
0x18003177e  xor     r9d, r9d; lpClass
0x180031781  xor     r8d, r8d; Reserved
0x180031784  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003178b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031792  call    cs:__imp_RegCreateKeyExW
0x180031798  mov     rcx, [rsp+98h]; this
0x1800317a0  test    eax, eax
0x1800317a2  jnz     short loc_18003181E
0x1800317a4  lea     rdx, stru_1800D7150
0x1800317ab  lea     rcx, [rsp+98h+var_38]
0x1800317b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800317b5  nop
0x1800317b6  mov     r9d, 0F013Fh
0x1800317bc  lea     r8, [rsp+98h+var_38]
0x1800317c1  lea     rdx, [rsp+98h+var_48]
0x1800317c6  lea     rcx, [rsp+98h+var_40]; phkResult
0x1800317cb  call    ?FullKeyByKeyAndSubPath@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV56@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,ulong)
0x1800317d0  nop
0x1800317d1  lea     rcx, [rsp+98h+var_38]
0x1800317d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800317db  mov     r8d, ebx; unsigned __int16 *
0x1800317de  lea     rdx, stru_1800D70C8; HKEY
0x1800317e5  mov     rcx, [rsp+98h+var_40]; this
0x1800317ea  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x1800317ef  nop
0x1800317f0  lea     rcx, [rsp+98h+var_40]
0x1800317f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800317fa  nop
0x1800317fb  lea     rcx, [rsp+98h+var_48]
0x180031800  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031805  mov     rcx, [rsp+98h+var_18]
0x18003180d  xor     rcx, rsp; StackCookie
0x180031810  call    __security_check_cookie
0x180031815  add     rsp, 90h
0x18003181c  pop     rbx
0x18003181d  retn
0x18003181e  mov     r9d, eax; char *
0x180031821  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031828  mov     edx, 741h; void *
0x18003182d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180031833  mov     r9d, 80004001h; char *
0x180031839  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031840  mov     edx, 736h; void *
0x180031845  mov     rcx, rbx; this
0x180031848  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003184e  mov     r9d, 8000FFFFh; char *
0x180031854  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003185b  mov     edx, 73Dh; void *
0x180031860  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031866  mov     r9d, 80070057h; char *
0x18003186c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031873  mov     edx, 73Eh; void *
0x180031878  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
