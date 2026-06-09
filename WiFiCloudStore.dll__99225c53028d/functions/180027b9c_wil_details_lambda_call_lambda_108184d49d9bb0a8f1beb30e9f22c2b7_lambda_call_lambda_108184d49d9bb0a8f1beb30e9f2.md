# wil::details::lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___::_lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___

- ea: `0x180027b9c`
- end: `0x180027c14`
- name: `wil::details::lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___::_lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f19f`

## callees

- `0x180015b9c`
- `0x18001de24`
- `0x180027b9c`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027be0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027be0`

## string_xrefs

- `0x180027bd4`: `WlanSvcTaskBootstrapped`
- `0x180027bf2`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___::_lambda_call__lambda_108184d49d9bb0a8f1beb30e9f22c2b7___(
        __int64 a1)
{
  unsigned int v1; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(&hKey);
    Data = 1;
    v1 = RegSetValueExW(hKey, L"WlanSvcTaskBootstrapped", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
        (const char *)v1,
        lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
}

```

## disassembly

```asm
0x180027b9c  sub     rsp, 38h
0x180027ba0  cmp     byte ptr [rcx+1], 0
0x180027ba4  jz      short loc_180027C0F
0x180027ba6  mov     byte ptr [rcx+1], 0
0x180027baa  lea     rcx, [rsp+38h+hKey]; phkResult
0x180027baf  call    ?OpenSyncBaseKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(void * const)
0x180027bb4  mov     [rsp+38h+Data], 1
0x180027bbc  mov     r9d, 4; dwType
0x180027bc2  mov     [rsp+38h+cbData], r9d; cbData
0x180027bc7  lea     rax, [rsp+38h+Data]
0x180027bcc  mov     [rsp+38h+lpData], rax; unsigned int
0x180027bd1  xor     r8d, r8d; Reserved
0x180027bd4  lea     rdx, ValueName; "WlanSvcTaskBootstrapped"
0x180027bdb  mov     rcx, [rsp+38h+hKey]; hKey
0x180027be0  call    cs:__imp_RegSetValueExW
0x180027be6  mov     rcx, [rsp+38h]; this
0x180027beb  test    eax, eax
0x180027bed  jz      short loc_180027C04
0x180027bef  mov     r9d, eax; char *
0x180027bf2  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180027bf9  mov     edx, 141h; void *
0x180027bfe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180027c04  lea     rcx, [rsp+38h+hKey]
0x180027c09  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027c0e  nop
0x180027c0f  add     rsp, 38h
0x180027c13  retn
```
