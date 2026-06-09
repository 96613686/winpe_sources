# Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser(_GUID const &)

- ea: `0x180029758`
- end: `0x180029864`
- name: `?StoreNlmSyncWithNetworkCategoryChangedForCurrentUser@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(GUID *rguid, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f2a9`

## callees

- `0x18000ba1c`
- `0x18001de24`
- `0x180029758`
- `0x18002986c`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800297ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800297ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800297fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800297fc`

## string_xrefs

- `0x1800297bb`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x180029811`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser(
        GUID *rguid,
        const struct _GUID *a2)
{
  unsigned int v3; // eax
  const char *v4; // r9
  __int64 result; // rax
  int lpData; // [rsp+20h] [rbp-88h]
  unsigned int lpDataa; // [rsp+20h] [rbp-88h]
  BYTE Data[8]; // [rsp+30h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(&hKey);
    memset_0(sz, 0, 0x4Eu);
    if ( !StringFromGUID2(rguid, sz, 39) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)0x8007007ALL,
        lpData);
    *(_DWORD *)Data = 2;
    v3 = RegSetValueExW(hKey, sz, 0, 3u, Data, 4u);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)v3,
        lpDataa);
    WiFiCloudStoreTelemetry::NlmStoredNeededChange<_GUID const &,enum Windows::Internal::WiFiCloudStore::NlmModificationType const &>(
      rguid,
      Data);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x113,
                           (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180029758  mov     [rsp+arg_8], rbx
0x18002975d  push    rdi
0x18002975e  sub     rsp, 0A0h
0x180029765  mov     rax, cs:__security_cookie
0x18002976c  xor     rax, rsp
0x18002976f  mov     [rsp+0A8h+var_18], rax
0x180029777  mov     rbx, rcx
0x18002977a  lea     rcx, [rsp+0A8h+hKey]
0x18002977f  call    ?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@QEAX@Z; Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,void * const)
0x180029784  nop
0x180029785  xor     edx, edx; Val
0x180029787  lea     r8d, [rdx+4Eh]; Size
0x18002978b  lea     rcx, [rsp+0A8h+sz]; void *
0x180029790  call    memset_0
0x180029795  mov     rdi, [rsp+0A8h]
0x18002979d  mov     r8d, 27h ; '''; cchMax
0x1800297a3  lea     rdx, [rsp+0A8h+sz]; lpsz
0x1800297a8  mov     rcx, rbx; rguid
0x1800297ab  call    cs:__imp_StringFromGUID2
0x1800297b1  test    eax, eax
0x1800297b3  jnz     short loc_1800297CF
0x1800297b5  mov     r9d, 8007007Ah; char *
0x1800297bb  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1800297c2  mov     edx, 10Ah; void *
0x1800297c7  mov     rcx, rdi; this
0x1800297ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800297cf  mov     dword ptr [rsp+0A8h+Data], 2
0x1800297d7  mov     [rsp+0A8h+cbData], 4; cbData
0x1800297df  lea     rax, [rsp+0A8h+Data]
0x1800297e4  mov     [rsp+0A8h+lpData], rax; unsigned int
0x1800297e9  mov     r9d, 3; dwType
0x1800297ef  xor     r8d, r8d; Reserved
0x1800297f2  lea     rdx, [rsp+0A8h+sz]; lpValueName
0x1800297f7  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800297fc  call    cs:__imp_RegSetValueExW
0x180029802  mov     rcx, [rsp+0A8h]; this
0x18002980a  test    eax, eax
0x18002980c  jz      short loc_180029822
0x18002980e  mov     r9d, eax; char *
0x180029811  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180029818  mov     edx, 10Eh; void *
0x18002981d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029822  lea     rdx, [rsp+0A8h+Data]
0x180029827  mov     rcx, rbx
0x18002982a  call    ??$NlmStoredNeededChange@AEBU_GUID@@AEBW4NlmModificationType@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAXAEBU_GUID@@AEBW4NlmModificationType@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::NlmStoredNeededChange<_GUID const &,Windows::Internal::WiFiCloudStore::NlmModificationType const &>(_GUID const &,Windows::Internal::WiFiCloudStore::NlmModificationType const &)
0x18002982f  nop
0x180029830  lea     rcx, [rsp+0A8h+hKey]
0x180029835  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002983a  xor     eax, eax
0x18002983c  jmp     short loc_180029842
0x18002983e  mov     eax, dword ptr [rsp+0A8h+Data]
0x180029842  mov     rcx, [rsp+0A8h+var_18]
0x18002984a  xor     rcx, rsp; StackCookie
0x18002984d  call    __security_check_cookie
0x180029852  mov     rbx, [rsp+0A8h+arg_8]
0x18002985a  add     rsp, 0A0h
0x180029861  pop     rdi
0x180029862  retn
```
