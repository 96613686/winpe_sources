# Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(_GUID const &)

- ea: `0x18000aebc`
- end: `0x18000afef`
- name: `?GetSyncNeededProfilesFromRegistry@WiFiCloudStore@Internal@Windows@@YA?AV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEBU_GUID@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001314c`
- `0x1800211b0`

## callees

- `0x180006afc`
- `0x180009d18`
- `0x18000ac14`
- `0x18000aebc`
- `0x18000aff8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000afa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000afa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afd4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(__int64 a1, GUID *a2)
{
  int v4; // edi
  int *v5; // rsi
  int v6; // ebx
  int v7; // edi
  __int64 v9; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+20h] [rbp-20h]
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  std::vector<bond::blob>::vector<bond::blob>(a1);
  v4 = 1;
  v5 = (int *)Windows::Internal::WiFiCloudStore::c_allProfileGenerations;
  do
  {
    v6 = *v5;
    Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem);
    Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(&hKey, a2, v6);
    v7 = v4 | 4;
    if ( hMem )
      LocalFree(hMem);
    v4 = v7 | 2;
    LODWORD(v9) = *v5;
    Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(hKey, v9);
    if ( hKey )
      RegCloseKey(hKey);
    ++v5;
  }
  while ( v5 != &dword_180043C84 );
  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem);
  Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(&phkResult, a2, 0x80000000);
  if ( hMem )
    LocalFree(hMem);
  LODWORD(v10) = 0x80000000;
  Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(phkResult, v10);
  if ( phkResult )
    RegCloseKey(phkResult);
  return a1;
}

```

## disassembly

```asm
0x18000aebc  mov     [rsp-28h+arg_8], rbx
0x18000aec1  mov     [rsp-28h+arg_0], rcx
0x18000aec6  push    rbp
0x18000aec7  push    rsi
0x18000aec8  push    rdi
0x18000aec9  push    r14
0x18000aecb  push    r15
0x18000aecd  mov     rbp, rsp
0x18000aed0  sub     rsp, 40h
0x18000aed4  mov     r15, rdx
0x18000aed7  mov     r14, rcx
0x18000aeda  mov     [rbp+var_10], 0
0x18000aee1  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18000aee6  mov     edi, 1
0x18000aeeb  mov     [rbp+var_10], edi
0x18000aeee  lea     rsi, ?c_allProfileGenerations@WiFiCloudStore@Internal@Windows@@3V?$array@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$04@std@@B; std::array<Windows::Internal::WiFiCloudStore::ProfileGeneration,5> const Windows::Internal::WiFiCloudStore::c_allProfileGenerations
0x18000aef5  mov     ebx, [rsi]
0x18000aef7  lea     rcx, [rbp+hMem]; StringSid
0x18000aefb  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18000af00  nop
0x18000af01  mov     dword ptr [rsp+40h+var_20], ebx; int
0x18000af05  lea     r9, aProfiles; "Profiles"
0x18000af0c  mov     r8, [rbp+hMem]
0x18000af10  mov     rdx, r15; rguid
0x18000af13  lea     rcx, [rbp+hKey]; phkResult
0x18000af17  call    ?OpenGenericSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG1W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(_GUID const &,ushort const *,ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000af1c  or      edi, 4
0x18000af1f  mov     rcx, [rbp+hMem]; hMem
0x18000af23  test    rcx, rcx
0x18000af26  jz      short loc_18000AF2E
0x18000af28  call    cs:__imp_LocalFree
0x18000af2e  or      edi, 2
0x18000af31  mov     [rbp+var_10], edi
0x18000af34  mov     eax, [rsi]
0x18000af36  mov     dword ptr [rsp+40h+var_20], eax; __int64
0x18000af3a  mov     r9d, 1
0x18000af40  mov     r8, r14
0x18000af43  mov     rdx, r15
0x18000af46  mov     rcx, [rbp+hKey]; hKey
0x18000af4a  call    ?AppendSyncNeededProfilesToVector@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@AEBU_GUID@@AEAV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@W4ProfileModificationType@123@W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(HKEY__ * const,_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile> &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000af4f  nop
0x18000af50  mov     rcx, [rbp+hKey]; hKey
0x18000af54  test    rcx, rcx
0x18000af57  jz      short loc_18000AF5F
0x18000af59  call    cs:__imp_RegCloseKey
0x18000af5f  add     rsi, 4
0x18000af63  lea     rax, dword_180043C84
0x18000af6a  cmp     rsi, rax
0x18000af6d  jnz     short loc_18000AEF5
0x18000af6f  lea     rcx, [rbp+hMem]; StringSid
0x18000af73  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18000af78  nop
0x18000af79  mov     ebx, 80000000h
0x18000af7e  mov     dword ptr [rsp+40h+var_20], ebx; int
0x18000af82  lea     r9, aCost; "Cost"
0x18000af89  mov     r8, [rbp+hMem]
0x18000af8d  mov     rdx, r15; rguid
0x18000af90  lea     rcx, [rbp+phkResult]; phkResult
0x18000af94  call    ?OpenGenericSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG1W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(_GUID const &,ushort const *,ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000af99  or      edi, 10h
0x18000af9c  mov     rcx, [rbp+hMem]; hMem
0x18000afa0  test    rcx, rcx
0x18000afa3  jz      short loc_18000AFAB
0x18000afa5  call    cs:__imp_LocalFree
0x18000afab  mov     r9d, 8
0x18000afb1  or      edi, r9d
0x18000afb4  mov     [rbp+var_10], edi
0x18000afb7  mov     dword ptr [rsp+40h+var_20], ebx; __int64
0x18000afbb  mov     r8, r14
0x18000afbe  mov     rdx, r15
0x18000afc1  mov     rcx, [rbp+phkResult]; hKey
0x18000afc5  call    ?AppendSyncNeededProfilesToVector@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@AEBU_GUID@@AEAV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@W4ProfileModificationType@123@W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(HKEY__ * const,_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile> &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x18000afca  nop
0x18000afcb  mov     rcx, [rbp+phkResult]; hKey
0x18000afcf  test    rcx, rcx
0x18000afd2  jz      short loc_18000AFDA
0x18000afd4  call    cs:__imp_RegCloseKey
0x18000afda  mov     rax, r14
0x18000afdd  mov     rbx, [rsp+40h+arg_8]
0x18000afe2  add     rsp, 40h
0x18000afe6  pop     r15
0x18000afe8  pop     r14
0x18000afea  pop     rdi
0x18000afeb  pop     rsi
0x18000afec  pop     rbp
0x18000afed  retn
```
