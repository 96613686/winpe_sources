# Windows::Internal::WiFiCloudStore::DeleteProcessedNlmSyncChangesFromRegistry(std::vector<Windows::Internal::WiFiCloudStore::NlmSyncStruct,std::allocator<Windows::Internal::WiFiCloudStore::NlmSyncStruct>> const &)

- ea: `0x180027514`
- end: `0x18002763f`
- name: `?DeleteProcessedNlmSyncChangesFromRegistry@WiFiCloudStore@Internal@Windows@@YAXAEBV?$vector@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@V?$allocator@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@@std@@@std@@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800144c0`

## callees

- `0x18000ac14`
- `0x18000ba64`
- `0x180027514`
- `0x180028ed4`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027596`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027596`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800275f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800275f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800275ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800275ae`

## string_xrefs

- `0x1800275d5`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x18002762a`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall Windows::Internal::WiFiCloudStore::DeleteProcessedNlmSyncChangesFromRegistry(
        const GUID **a1,
        void *a2)
{
  LSTATUS result; // eax
  const GUID *v4; // rbx
  const GUID *v5; // rdi
  unsigned int v6; // eax
  int v7; // [rsp+20h] [rbp-88h]
  HLOCAL hMem; // [rsp+30h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem, a2);
  result = Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(&hKey);
  if ( hMem )
    result = (unsigned int)LocalFree(hMem);
  v4 = *a1;
  v5 = a1[1];
  while ( v4 != v5 )
  {
    memset_0(sz, 0, 0x4Eu);
    if ( !StringFromGUID2(v4, sz, 39) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)0x8007007ALL,
        v7);
    v6 = RegDeleteValueW(hKey, sz);
    result = wil::details::in1diag3::Log_IfFailedMsg(
               retaddr,
               (void *)0x100,
               (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
               (const char *)v6,
               (int)"Value name: %ws",
               (const char *)sz);
    v4 = (const GUID *)((char *)v4 + 20);
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180027514  mov     [rsp+arg_8], rbx
0x180027519  mov     [rsp+arg_10], rsi
0x18002751e  push    rdi
0x18002751f  sub     rsp, 0A0h
0x180027526  mov     rax, cs:__security_cookie
0x18002752d  xor     rax, rsp
0x180027530  mov     [rsp+0A8h+var_18], rax
0x180027538  mov     rdi, rcx
0x18002753b  lea     rcx, [rsp+0A8h+hMem]; StringSid
0x180027540  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x180027545  nop
0x180027546  mov     r8, [rsp+0A8h+hMem]
0x18002754b  lea     rcx, [rsp+0A8h+hKey]; phkResult
0x180027550  call    ?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x180027555  nop
0x180027556  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18002755b  test    rcx, rcx
0x18002755e  jz      short loc_180027567
0x180027560  call    cs:__imp_LocalFree
0x180027566  nop
0x180027567  mov     rbx, [rdi]
0x18002756a  mov     rdi, [rdi+8]
0x18002756e  jmp     short loc_1800275EA
0x180027570  xor     edx, edx; Val
0x180027572  lea     r8d, [rdx+4Eh]; Size
0x180027576  lea     rcx, [rsp+0A8h+sz]; void *
0x18002757b  call    memset_0
0x180027580  mov     rsi, [rsp+0A8h]
0x180027588  mov     r8d, 27h ; '''; cchMax
0x18002758e  lea     rdx, [rsp+0A8h+sz]; lpsz
0x180027593  mov     rcx, rbx; rguid
0x180027596  call    cs:__imp_StringFromGUID2
0x18002759c  test    eax, eax
0x18002759e  jz      loc_180027624
0x1800275a4  lea     rdx, [rsp+0A8h+sz]; lpValueName
0x1800275a9  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800275ae  call    cs:__imp_RegDeleteValueW
0x1800275b4  mov     rcx, [rsp+0A8h]; this
0x1800275bc  lea     rdx, [rsp+0A8h+sz]
0x1800275c1  mov     [rsp+0A8h+var_80], rdx; char *
0x1800275c6  lea     rdx, aValueNameWs; "Value name: %ws"
0x1800275cd  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x1800275d2  mov     r9d, eax; char *
0x1800275d5  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1800275dc  mov     edx, 100h; void *
0x1800275e1  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800275e6  add     rbx, 14h
0x1800275ea  cmp     rbx, rdi
0x1800275ed  jnz     short loc_180027570
0x1800275ef  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800275f4  test    rcx, rcx
0x1800275f7  jz      short loc_1800275FF
0x1800275f9  call    cs:__imp_RegCloseKey
0x1800275ff  mov     rcx, [rsp+0A8h+var_18]
0x180027607  xor     rcx, rsp; StackCookie
0x18002760a  call    __security_check_cookie
0x18002760f  lea     r11, [rsp+0A8h+var_8]
0x180027617  mov     rbx, [r11+18h]
0x18002761b  mov     rsi, [r11+20h]
0x18002761f  mov     rsp, r11
0x180027622  pop     rdi
0x180027623  retn
0x180027624  mov     r9d, 8007007Ah; char *
0x18002762a  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180027631  mov     edx, 0FDh; void *
0x180027636  mov     rcx, rsi; this
0x180027639  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
