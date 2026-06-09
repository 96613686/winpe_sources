# Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)

- ea: `0x1800111a8`
- end: `0x180011209`
- name: `?OpenProfileSyncRetryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010cb4`
- `0x180011b94`
- `0x18003d4d8`

## callees

- `0x180009d18`
- `0x1800111a8`
- `0x18002c138`

## string_xrefs

- `0x1800111e9`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
HKEY *__fastcall Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(
        HKEY *a1,
        GUID *a2,
        int a3,
        const char *a4,
        __int64 a5)
{
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( (unsigned int)(a3 - 1) > 1 )
  {
    if ( ((a3 - 4) & 0xFFFFFFFB) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
        a4);
    Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(
      a1,
      a2,
      a5,
      (__int64)L"Retry\\Cost",
      (unsigned int)a4);
  }
  else
  {
    Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(
      a1,
      a2,
      a5,
      (__int64)L"Retry\\Profiles",
      (unsigned int)a4);
  }
  return a1;
}

```

## disassembly

```asm
0x1800111a8  push    rbx
0x1800111aa  sub     rsp, 40h
0x1800111ae  lea     eax, [r8-1]
0x1800111b2  mov     rbx, rcx
0x1800111b5  cmp     eax, 1
0x1800111b8  ja      short loc_1800111D9
0x1800111ba  mov     [rsp+48h+var_28], r9d; int
0x1800111bf  lea     r9, aRetryProfiles; "Retry\\Profiles"
0x1800111c6  mov     r8, [rsp+48h+arg_20]
0x1800111cb  call    ?OpenGenericSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG1W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(_GUID const &,ushort const *,ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x1800111d0  mov     rax, rbx
0x1800111d3  add     rsp, 40h
0x1800111d7  pop     rbx
0x1800111d8  retn
0x1800111d9  lea     eax, [r8-4]
0x1800111dd  test    eax, 0FFFFFFFBh
0x1800111e2  jz      short loc_1800111FB
0x1800111e4  mov     rcx, [rsp+48h]; this
0x1800111e9  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x1800111f0  mov     edx, 115h; void *
0x1800111f5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800111fb  mov     [rsp+48h+var_28], r9d
0x180011200  lea     r9, aRetryCost; "Retry\\Cost"
0x180011207  jmp     short loc_1800111C6
```
