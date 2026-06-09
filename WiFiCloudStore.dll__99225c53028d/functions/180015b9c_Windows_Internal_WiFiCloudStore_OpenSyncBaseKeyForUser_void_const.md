# Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(void * const)

- ea: `0x180015b9c`
- end: `0x180015ccc`
- name: `?OpenSyncBaseKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014d70`
- `0x180015aa8`
- `0x180027b9c`

## callees

- `0x180009fb8`
- `0x18000ac14`
- `0x18000cc78`
- `0x180015b9c`
- `0x180025308`
- `0x18002a030`
- `0x180031ce4`
- `0x18003caa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c85`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c59`

## string_xrefs

- `0x180015c6a`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PHKEY __fastcall Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(PHKEY phkResult)
{
  void *v2; // rdx
  void *v3; // rax
  __int64 v4; // r8
  const WCHAR *v5; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-19h]
  HLOCAL hMem[2]; // [rsp+58h] [rbp+1Fh] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned __int64 v11; // [rsp+80h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  hMem[1] = phkResult;
  Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey((__int64 *)lpSubKey);
  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)hMem, v2);
  v3 = (void *)std::wstring::_Append<unsigned short>(lpSubKey);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)hMem[0] + v4) );
  std::wstring::_Append<unsigned short>(v3);
  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v5 = (const WCHAR *)lpSubKey;
  if ( v11 > 7 )
    v5 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0xFu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)Key,
      dwOptions);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v11 > 7 )
    std::_Deallocate<16>((void *)lpSubKey[0], 2 * v11 + 2);
  return phkResult;
}

```

## disassembly

```asm
0x180015b9c  mov     [rsp-8+arg_8], rbx
0x180015ba1  mov     [rsp-8+arg_10], rdi
0x180015ba6  push    rbp
0x180015ba7  lea     rbp, [rsp-57h]
0x180015bac  sub     rsp, 90h
0x180015bb3  mov     rax, cs:__security_cookie
0x180015bba  xor     rax, rsp
0x180015bbd  mov     [rbp+57h+var_8], rax
0x180015bc1  mov     rbx, rcx
0x180015bc4  mov     [rbp+57h+var_30], rcx
0x180015bc8  xor     edi, edi
0x180015bca  mov     [rbp+57h+var_40], edi
0x180015bcd  lea     rcx, [rbp+57h+lpSubKey]; Src
0x180015bd1  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x180015bd6  nop
0x180015bd7  lea     rcx, [rbp+57h+hMem]; StringSid
0x180015bdb  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x180015be0  nop
0x180015be1  lea     r8d, [rdi+1]
0x180015be5  lea     rdx, asc_180043BAC; "\\"
0x180015bec  lea     rcx, [rbp+57h+lpSubKey]; Src
0x180015bf0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015bf5  mov     rdx, [rbp+57h+hMem]
0x180015bf9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015bfd  inc     r8
0x180015c00  cmp     [rdx+r8*2], di
0x180015c05  jnz     short loc_180015BFD
0x180015c07  mov     rcx, rax; Src
0x180015c0a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015c0f  mov     [rbx], rdi
0x180015c12  mov     [rbp+57h+var_40], 1
0x180015c19  xor     edx, edx
0x180015c1b  mov     rcx, rbx
0x180015c1e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180015c23  lea     rdx, [rbp+57h+lpSubKey]
0x180015c27  cmp     [rbp+57h+var_10], 7
0x180015c2c  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180015c31  mov     [rsp+90h+lpdwDisposition], rdi; lpdwDisposition
0x180015c36  mov     [rsp+90h+phkResult], rbx; phkResult
0x180015c3b  mov     [rsp+90h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180015c40  mov     [rsp+90h+samDesired], 0Fh; samDesired
0x180015c48  mov     [rsp+90h+dwOptions], edi; unsigned int
0x180015c4c  xor     r9d, r9d; lpClass
0x180015c4f  xor     r8d, r8d; Reserved
0x180015c52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015c59  call    cs:__imp_RegCreateKeyExW
0x180015c5f  mov     rcx, [rbp+5Fh]; this
0x180015c63  test    eax, eax
0x180015c65  jz      short loc_180015C7C
0x180015c67  mov     r9d, eax; char *
0x180015c6a  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180015c71  mov     edx, 121h; void *
0x180015c76  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180015c7c  mov     rcx, [rbp+57h+hMem]; hMem
0x180015c80  test    rcx, rcx
0x180015c83  jz      short loc_180015C8C
0x180015c85  call    cs:__imp_LocalFree
0x180015c8b  nop
0x180015c8c  mov     rdx, [rbp+57h+var_10]
0x180015c90  cmp     rdx, 7
0x180015c94  jbe     short loc_180015CA7
0x180015c96  lea     rdx, ds:2[rdx*2]
0x180015c9e  mov     rcx, [rbp+57h+lpSubKey]
0x180015ca2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015ca7  mov     rax, rbx
0x180015caa  mov     rcx, [rbp+57h+var_8]
0x180015cae  xor     rcx, rsp; StackCookie
0x180015cb1  call    __security_check_cookie
0x180015cb6  lea     r11, [rsp+90h+var_s0]
0x180015cbe  mov     rbx, [r11+18h]
0x180015cc2  mov     rdi, [r11+20h]
0x180015cc6  mov     rsp, r11
0x180015cc9  pop     rbp
0x180015cca  retn
```
