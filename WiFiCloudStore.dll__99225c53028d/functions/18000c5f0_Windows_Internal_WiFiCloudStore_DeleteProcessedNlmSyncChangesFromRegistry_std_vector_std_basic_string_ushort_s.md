# Windows::Internal::WiFiCloudStore::DeleteProcessedNlmSyncChangesFromRegistry(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18000c5f0`
- end: `0x18000c6a9`
- name: `?DeleteProcessedNlmSyncChangesFromRegistry@WiFiCloudStore@Internal@Windows@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c5d4`

## callees

- `0x18000ac14`
- `0x18000ba64`
- `0x18000c5f0`
- `0x180028ed4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c693`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c650`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c650`

## string_xrefs

- `0x18000c66f`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall Windows::Internal::WiFiCloudStore::DeleteProcessedNlmSyncChangesFromRegistry(__int64 *a1, void *a2)
{
  __int64 v3; // rdx
  LSTATUS result; // eax
  __int64 v5; // rdi
  __int64 i; // rbx
  const WCHAR *v7; // rdx
  const char *v8; // rsi
  unsigned int v9; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem, a2);
  result = (unsigned int)Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(&hKey, v3, (__int64)hMem);
  if ( hMem )
    result = (unsigned int)LocalFree(hMem);
  v5 = a1[1];
  for ( i = *a1; i != v5; i += 32 )
  {
    if ( *(_QWORD *)(i + 24) <= 7u )
    {
      v8 = (const char *)i;
      v7 = (const WCHAR *)i;
    }
    else
    {
      v7 = *(const WCHAR **)i;
      v8 = *(const char **)i;
    }
    v9 = RegDeleteValueW(hKey, v7);
    result = wil::details::in1diag3::Log_IfFailedMsg(
               retaddr,
               (void *)0xAD,
               (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
               (const char *)v9,
               (int)"Value name: %ws",
               v8);
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18000c5f0  mov     [rsp+arg_10], rbx
0x18000c5f5  mov     [rsp+arg_18], rsi
0x18000c5fa  push    rdi
0x18000c5fb  sub     rsp, 30h
0x18000c5ff  mov     rbx, rcx
0x18000c602  lea     rcx, [rsp+38h+hMem]; StringSid
0x18000c607  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18000c60c  nop
0x18000c60d  mov     r8, [rsp+38h+hMem]
0x18000c612  lea     rcx, [rsp+38h+hKey]; phkResult
0x18000c617  call    ?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18000c61c  nop
0x18000c61d  mov     rcx, [rsp+38h+hMem]; hMem
0x18000c622  test    rcx, rcx
0x18000c625  jz      short loc_18000C62D
0x18000c627  call    cs:__imp_LocalFree
0x18000c62d  mov     rdi, [rbx+8]
0x18000c631  mov     rbx, [rbx]
0x18000c634  jmp     short loc_18000C684
0x18000c636  cmp     qword ptr [rbx+18h], 7
0x18000c63b  jbe     short loc_18000C645
0x18000c63d  mov     rdx, [rbx]
0x18000c640  mov     rsi, rdx
0x18000c643  jmp     short loc_18000C64B
0x18000c645  mov     rsi, rbx
0x18000c648  mov     rdx, rbx; lpValueName
0x18000c64b  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c650  call    cs:__imp_RegDeleteValueW
0x18000c656  mov     rcx, [rsp+38h]; this
0x18000c65b  mov     [rsp+38h+var_10], rsi; char *
0x18000c660  lea     rdx, aValueNameWs; "Value name: %ws"
0x18000c667  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000c66c  mov     r9d, eax; char *
0x18000c66f  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18000c676  mov     edx, 0ADh; void *
0x18000c67b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c680  add     rbx, 20h ; ' '
0x18000c684  cmp     rbx, rdi
0x18000c687  jnz     short loc_18000C636
0x18000c689  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c68e  test    rcx, rcx
0x18000c691  jz      short loc_18000C699
0x18000c693  call    cs:__imp_RegCloseKey
0x18000c699  mov     rbx, [rsp+38h+arg_10]
0x18000c69e  mov     rsi, [rsp+38h+arg_18]
0x18000c6a3  add     rsp, 30h
0x18000c6a7  pop     rdi
0x18000c6a8  retn
```
