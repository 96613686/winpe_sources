# Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyUpperLimit(void)

- ea: `0x180034b14`
- end: `0x180034c43`
- name: `?GetExpirationPolicyUpperLimit@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ`
- size: `303`
- prototype: `unsigned int __fastcall(Windows::Internal::CapabilityAccess::Private::SQL *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800348a4`
- `0x1800349dc`
- `0x180039534`

## callees

- `0x18002392c`
- `0x1800299c4`
- `0x18002f280`
- `0x180034b14`
- `0x180037034`
- `0x18003ce34`
- `0x180058dfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034b81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034b81`

## string_xrefs

- `0x180034b73`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180034be9`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034c01`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034c19`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034c31`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyUpperLimit(
        Windows::Internal::CapabilityAccess::Private::SQL *this)
{
  unsigned int v1; // eax
  unsigned int Uint32Value; // eax
  unsigned int v3; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  bool *dwOptionsa; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int16 v9; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  if ( !Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      dwOptions);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
         0,
         0,
         0,
         0x20119u,
         0,
         &phkResult,
         0);
  if ( v1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)v1,
      (unsigned int)dwOptionsa);
  LOBYTE(v9) = 0;
  Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                  (Windows::Internal::CapabilityAccess::Private *)phkResult,
                  (HKEY)&stru_1800D7150,
                  L"ExpirationPolicyUpperLimit",
                  &v9,
                  dwOptionsa);
  v3 = Uint32Value;
  if ( !(_BYTE)v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80070002LL,
      dwOptionsb);
  if ( !Uint32Value )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x8000FFFFLL,
      dwOptionsb);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v3;
}

```

## disassembly

```asm
0x180034b14  push    rbx
0x180034b16  sub     rsp, 50h
0x180034b1a  mov     rbx, [rsp+58h]
0x180034b1f  call    ?IsDatabaseEnabledByEditionPolicy@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(void)
0x180034b24  test    al, al
0x180034b26  jz      loc_180034BFB
0x180034b2c  mov     [rsp+58h+arg_8], 0
0x180034b35  xor     edx, edx
0x180034b37  lea     rcx, [rsp+58h+arg_8]
0x180034b3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180034b41  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180034b4a  lea     rax, [rsp+58h+arg_8]
0x180034b4f  mov     [rsp+58h+phkResult], rax; phkResult
0x180034b54  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180034b5d  mov     [rsp+58h+samDesired], 20119h; samDesired
0x180034b65  mov     dword ptr [rsp+58h+dwOptions], 0; int
0x180034b6d  xor     r9d, r9d; lpClass
0x180034b70  xor     r8d, r8d; Reserved
0x180034b73  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034b7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034b81  call    cs:__imp_RegCreateKeyExW
0x180034b87  mov     rcx, [rsp+58h]; this
0x180034b8c  test    eax, eax
0x180034b8e  jnz     loc_180034C16
0x180034b94  mov     byte ptr [rsp+58h+arg_0], al
0x180034b98  lea     r9, [rsp+58h+arg_0]; unsigned __int16 *
0x180034b9d  lea     r8, aExpirationpoli; "ExpirationPolicyUpperLimit"
0x180034ba4  lea     rdx, stru_1800D7150; HKEY
0x180034bab  mov     rcx, [rsp+58h+arg_8]; this
0x180034bb0  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180034bb5  mov     ebx, eax
0x180034bb7  cmp     byte ptr [rsp+58h+arg_0], 0
0x180034bbc  setz    dl
0x180034bbf  mov     rcx, [rsp+58h]; this
0x180034bc4  test    dl, dl
0x180034bc6  jnz     short loc_180034C2B
0x180034bc8  mov     rcx, [rsp+58h]; this
0x180034bcd  test    eax, eax
0x180034bcf  jz      short loc_180034BE3
0x180034bd1  lea     rcx, [rsp+58h+arg_8]
0x180034bd6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034bdb  mov     eax, ebx
0x180034bdd  add     rsp, 50h
0x180034be1  pop     rbx
0x180034be2  retn
0x180034be3  mov     r9d, 8000FFFFh; char *
0x180034be9  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034bf0  mov     edx, 0BEh; void *
0x180034bf5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034bfb  mov     r9d, 80004001h; char *
0x180034c01  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034c08  mov     edx, 0B3h; void *
0x180034c0d  mov     rcx, rbx; this
0x180034c10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034c16  mov     r9d, eax; char *
0x180034c19  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034c20  mov     edx, 0B8h; void *
0x180034c25  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180034c2b  mov     r9d, 80070002h; char *
0x180034c31  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034c38  mov     edx, 0BDh; void *
0x180034c3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
