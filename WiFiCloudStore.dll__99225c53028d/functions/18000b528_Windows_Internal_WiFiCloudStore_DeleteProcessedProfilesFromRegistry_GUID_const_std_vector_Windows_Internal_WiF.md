# Windows::Internal::WiFiCloudStore::DeleteProcessedProfilesFromRegistry(_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile,std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>> const &)

- ea: `0x18000b528`
- end: `0x18000b66c`
- name: `?DeleteProcessedProfilesFromRegistry@WiFiCloudStore@Internal@Windows@@YAXAEBU_GUID@@AEBV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b508`
- `0x18001314c`

## callees

- `0x180009d18`
- `0x18000ac14`
- `0x18000b528`
- `0x18000bca8`
- `0x18001de24`
- `0x180028ed4`
- `0x18002c138`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b575`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b596`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b5c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b5c2`

## string_xrefs

- `0x18000b5dc`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x18000b65a`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall Windows::Internal::WiFiCloudStore::DeleteProcessedProfilesFromRegistry(
        GUID *rguid,
        __int64 *a2)
{
  unsigned int result; // eax
  __int64 v5; // rbx
  __int64 v6; // r15
  const WCHAR *v7; // rdx
  const char *v8; // rdi
  unsigned int v9; // ebp
  HKEY v10; // rcx
  unsigned int v11; // eax
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HLOCAL hMem; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem, a2);
  result = (unsigned int)Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(
                           &hKey,
                           rguid,
                           (__int64)hMem,
                           (__int64)L"Cost",
                           0x80000000);
  if ( hMem )
    result = (unsigned int)LocalFree(hMem);
  v5 = *a2;
  v6 = a2[1];
  while ( v5 != v6 )
  {
    Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser((PHKEY)&hMem, rguid, *(_DWORD *)(v5 + 44));
    if ( *(_DWORD *)(v5 + 40) == 1 || *(_DWORD *)(v5 + 40) == 2 )
    {
      if ( *(_QWORD *)(v5 + 24) <= 7u )
      {
        v8 = (const char *)v5;
        v7 = (const WCHAR *)v5;
      }
      else
      {
        v7 = *(const WCHAR **)v5;
        v8 = *(const char **)v5;
      }
      v9 = 153;
      v10 = (HKEY)hMem;
    }
    else
    {
      if ( *(_DWORD *)(v5 + 40) != 4 && *(_DWORD *)(v5 + 40) != 8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xA1,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
          v12);
      if ( *(_QWORD *)(v5 + 24) > 7u )
      {
        v7 = *(const WCHAR **)v5;
        v8 = *(const char **)v5;
      }
      else
      {
        v8 = (const char *)v5;
        v7 = (const WCHAR *)v5;
      }
      v9 = 158;
      v10 = hKey;
    }
    v11 = RegDeleteValueW(v10, v7);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
      (const char *)v11,
      (int)"Value name: %ws",
      v8);
    result = wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&hMem);
    v5 += 48;
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18000b528  mov     [rsp+arg_0], rbx
0x18000b52d  push    rbp
0x18000b52e  push    rsi
0x18000b52f  push    rdi
0x18000b530  push    r14
0x18000b532  push    r15
0x18000b534  sub     rsp, 30h
0x18000b538  mov     rdi, rdx
0x18000b53b  mov     r14, rcx
0x18000b53e  lea     rcx, [rsp+58h+hMem]; StringSid
0x18000b543  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18000b548  nop
0x18000b549  mov     [rsp+58h+var_38], 80000000h; int
0x18000b551  lea     r9, aCost; "Cost"
0x18000b558  mov     r8, [rsp+58h+hMem]
0x18000b55d  mov     rdx, r14; rguid
0x18000b560  lea     rcx, [rsp+58h+hKey]; phkResult
0x18000b565  call    ?OpenGenericSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG1W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(_GUID const &,ushort const *,ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000b56a  nop
0x18000b56b  mov     rcx, [rsp+58h+hMem]; hMem
0x18000b570  test    rcx, rcx
0x18000b573  jz      short loc_18000B57C
0x18000b575  call    cs:__imp_LocalFree
0x18000b57b  nop
0x18000b57c  mov     rbx, [rdi]
0x18000b57f  mov     r15, [rdi+8]
0x18000b583  cmp     rbx, r15
0x18000b586  jnz     loc_18000B62D
0x18000b58c  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b591  test    rcx, rcx
0x18000b594  jz      short loc_18000B59C
0x18000b596  call    cs:__imp_RegCloseKey
0x18000b59c  mov     rbx, [rsp+58h+arg_0]
0x18000b5a1  add     rsp, 30h
0x18000b5a5  pop     r15
0x18000b5a7  pop     r14
0x18000b5a9  pop     rdi
0x18000b5aa  pop     rsi
0x18000b5ab  pop     rbp
0x18000b5ac  retn
0x18000b5ad  mov     rdx, [rbx]; lpValueName
0x18000b5b0  mov     rdi, rdx
0x18000b5b3  mov     ebp, 9Eh
0x18000b5b8  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b5bd  mov     rsi, [rsp+58h]
0x18000b5c2  call    cs:__imp_RegDeleteValueW
0x18000b5c8  mov     [rsp+58h+var_30], rdi; char *
0x18000b5cd  lea     rcx, aValueNameWs; "Value name: %ws"
0x18000b5d4  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18000b5d9  mov     r9d, eax; char *
0x18000b5dc  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18000b5e3  mov     edx, ebp; void *
0x18000b5e5  mov     rcx, rsi; this
0x18000b5e8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b5ed  lea     rcx, [rsp+58h+hMem]
0x18000b5f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b5f7  add     rbx, 30h ; '0'
0x18000b5fb  jmp     short loc_18000B583
0x18000b5fd  cmp     qword ptr [rbx+18h], 7
0x18000b602  ja      short loc_18000B5AD
0x18000b604  mov     rdi, rbx
0x18000b607  mov     rdx, rbx
0x18000b60a  jmp     short loc_18000B5B3
0x18000b60c  cmp     qword ptr [rbx+18h], 7
0x18000b611  jbe     short loc_18000B625
0x18000b613  mov     rdx, [rbx]
0x18000b616  mov     rdi, rdx
0x18000b619  mov     ebp, 99h
0x18000b61e  mov     rcx, [rsp+58h+hMem]
0x18000b623  jmp     short loc_18000B5BD
0x18000b625  mov     rdi, rbx
0x18000b628  mov     rdx, rbx
0x18000b62b  jmp     short loc_18000B619
0x18000b62d  mov     r8d, [rbx+2Ch]; int
0x18000b631  mov     rdx, r14; rguid
0x18000b634  lea     rcx, [rsp+58h+hMem]; phkResult
0x18000b639  call    ?OpenProfileSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@QEAX@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,void * const)
0x18000b63e  mov     ecx, [rbx+28h]
0x18000b641  sub     ecx, 1
0x18000b644  jz      short loc_18000B60C
0x18000b646  sub     ecx, 1
0x18000b649  jz      short loc_18000B60C
0x18000b64b  sub     ecx, 2
0x18000b64e  jz      short loc_18000B5FD
0x18000b650  cmp     ecx, 4
0x18000b653  jz      short loc_18000B5FD
0x18000b655  mov     rcx, [rsp+58h]; this
0x18000b65a  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18000b661  mov     edx, 0A1h; void *
0x18000b666  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
