# Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)

- ea: `0x18000ba64`
- end: `0x18000bbcf`
- name: `?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@PEBG@Z`
- size: `363`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ba1c`
- `0x18000c5f0`
- `0x180016478`
- `0x180027514`

## callees

- `0x180009fb8`
- `0x18000b9bc`
- `0x18000ba64`
- `0x18000cc50`
- `0x18000cc78`
- `0x180025308`
- `0x18002a030`
- `0x180031ce4`
- `0x18003caa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bb6e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bb6e`

## string_xrefs

- `0x18000bb7f`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PHKEY __fastcall Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(
        PHKEY phkResult,
        __int64 a2,
        __int64 a3)
{
  void *v5; // rax
  __int64 v6; // r8
  void *v7; // rax
  __int64 v8; // rdi
  _QWORD *SubKeyNameForProfileGeneration; // rax
  const WCHAR *v10; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-49h]
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp+Fh]
  void *v16; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int64 v17; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey((__int64 *)lpSubKey);
  v5 = (void *)std::wstring::_Append<unsigned short>(lpSubKey);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a3 + 2 * v6) );
  v7 = (void *)std::wstring::_Append<unsigned short>(v5);
  v8 = std::wstring::_Append<unsigned short>(v7);
  SubKeyNameForProfileGeneration = (_QWORD *)Windows::Internal::WiFiCloudStore::GetSubKeyNameForProfileGeneration(
                                               &v16,
                                               0x80000000LL);
  if ( SubKeyNameForProfileGeneration[3] > 7u )
    SubKeyNameForProfileGeneration = (_QWORD *)*SubKeyNameForProfileGeneration;
  std::wstring::append(v8, SubKeyNameForProfileGeneration);
  if ( v17 > 7 )
    std::_Deallocate<16>(v16, 2 * v17 + 2);
  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v10 = (const WCHAR *)lpSubKey;
  if ( v15 > 7 )
    v10 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0xFu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)Key,
      dwOptions);
  if ( v15 > 7 )
    std::_Deallocate<16>((void *)lpSubKey[0], 2 * v15 + 2);
  return phkResult;
}

```

## disassembly

```asm
0x18000ba64  mov     [rsp-8+arg_8], rbx
0x18000ba69  push    rbp
0x18000ba6a  push    rsi
0x18000ba6b  push    rdi
0x18000ba6c  lea     rbp, [rsp-47h]
0x18000ba71  sub     rsp, 0B0h
0x18000ba78  mov     rax, cs:__security_cookie
0x18000ba7f  xor     rax, rsp
0x18000ba82  mov     [rbp+57h+var_20], rax
0x18000ba86  mov     rdi, r8
0x18000ba89  mov     rbx, rcx
0x18000ba8c  mov     [rbp+57h+var_68], rcx
0x18000ba90  xor     esi, esi
0x18000ba92  mov     [rbp+57h+var_70], esi
0x18000ba95  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18000ba99  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x18000ba9e  nop
0x18000ba9f  lea     r8d, [rsi+1]
0x18000baa3  lea     rdx, asc_180043BAC; "\\"
0x18000baaa  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18000baae  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000bab3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bab7  inc     r8
0x18000baba  cmp     [rdi+r8*2], si
0x18000babf  jnz     short loc_18000BAB7
0x18000bac1  mov     rdx, rdi
0x18000bac4  mov     rcx, rax; Src
0x18000bac7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000bacc  mov     r8d, 5
0x18000bad2  lea     rdx, aNlm; "\\NLM\\"
0x18000bad9  mov     rcx, rax; Src
0x18000badc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000bae1  mov     rdi, rax
0x18000bae4  mov     edx, 80000000h
0x18000bae9  lea     rcx, [rbp+57h+var_40]
0x18000baed  call    ?GetSubKeyNameForProfileGeneration@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::GetSubKeyNameForProfileGeneration(Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000baf2  nop
0x18000baf3  cmp     qword ptr [rax+18h], 7
0x18000baf8  jbe     short loc_18000BAFD
0x18000bafa  mov     rax, [rax]
0x18000bafd  mov     rdx, rax
0x18000bb00  mov     rcx, rdi
0x18000bb03  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000bb08  nop
0x18000bb09  mov     rdx, [rbp+57h+var_28]
0x18000bb0d  cmp     rdx, 7
0x18000bb11  jbe     short loc_18000BB24
0x18000bb13  lea     rdx, ds:2[rdx*2]
0x18000bb1b  mov     rcx, [rbp+57h+var_40]
0x18000bb1f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bb24  mov     [rbx], rsi
0x18000bb27  mov     [rbp+57h+var_70], 1
0x18000bb2e  xor     edx, edx
0x18000bb30  mov     rcx, rbx
0x18000bb33  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000bb38  lea     rdx, [rbp+57h+lpSubKey]
0x18000bb3c  cmp     [rbp+57h+var_48], 7
0x18000bb41  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000bb46  mov     [rsp+0C0h+lpdwDisposition], rsi; lpdwDisposition
0x18000bb4b  mov     [rsp+0C0h+phkResult], rbx; phkResult
0x18000bb50  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000bb55  mov     [rsp+0C0h+samDesired], 0Fh; samDesired
0x18000bb5d  mov     [rsp+0C0h+dwOptions], esi; unsigned int
0x18000bb61  xor     r9d, r9d; lpClass
0x18000bb64  xor     r8d, r8d; Reserved
0x18000bb67  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bb6e  call    cs:__imp_RegCreateKeyExW
0x18000bb74  mov     rcx, [rbp+5Fh]; this
0x18000bb78  test    eax, eax
0x18000bb7a  jz      short loc_18000BB91
0x18000bb7c  mov     r9d, eax; char *
0x18000bb7f  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18000bb86  mov     edx, 0BAh; void *
0x18000bb8b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000bb91  mov     rdx, [rbp+57h+var_48]
0x18000bb95  cmp     rdx, 7
0x18000bb99  jbe     short loc_18000BBAC
0x18000bb9b  lea     rdx, ds:2[rdx*2]
0x18000bba3  mov     rcx, [rbp+57h+lpSubKey]
0x18000bba7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bbac  mov     rax, rbx
0x18000bbaf  mov     rcx, [rbp+57h+var_20]
0x18000bbb3  xor     rcx, rsp; StackCookie
0x18000bbb6  call    __security_check_cookie
0x18000bbbb  mov     rbx, [rsp+0C0h+arg_8]
0x18000bbc3  add     rsp, 0B0h
0x18000bbca  pop     rdi
0x18000bbcb  pop     rsi
0x18000bbcc  pop     rbp
0x18000bbcd  retn
```
