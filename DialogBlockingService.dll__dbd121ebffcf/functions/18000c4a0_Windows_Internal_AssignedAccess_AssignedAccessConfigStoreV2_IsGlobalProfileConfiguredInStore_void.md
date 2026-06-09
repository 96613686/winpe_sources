# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::IsGlobalProfileConfiguredInStore(void)

- ea: `0x18000c4a0`
- end: `0x18000c5cc`
- name: `?IsGlobalProfileConfiguredInStore@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@EEAA_NXZ`
- size: `300`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008ec8`
- `0x18000c4a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c58c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c58c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c505`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c546`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c546`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c59b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c59b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c57a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c57a`

## string_xrefs

- `0x18000c4cb`: `Configs`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::IsGlobalProfileConfiguredInStore(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *this)
{
  WCHAR *v1; // rcx
  HKEY v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rbx
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              (__int64)lpSubKey,
              L"%s\\%s",
              *((_QWORD *)this + 1),
              L"Configs") < 0 )
  {
    v1 = (WCHAR *)lpSubKey[0];
    if ( lpSubKey[0] )
      goto LABEL_10;
    goto LABEL_11;
  }
  v2 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v2);
    SetLastError(LastError);
  }
  hKey = 0;
  v4 = (WCHAR *)lpSubKey[0];
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey)
    || (Type = 0, cbData = 0, RegQueryValueExW(hKey, L"GlobalProfileId", 0, &Type, 0, &cbData)) )
  {
    if ( v4 )
    {
      v1 = v4;
LABEL_10:
      CoTaskMemFree(v1);
    }
LABEL_11:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18000c4a0  push    rbp
0x18000c4a2  push    rbx
0x18000c4a3  push    rdi
0x18000c4a4  mov     rbp, rsp
0x18000c4a7  sub     rsp, 50h
0x18000c4ab  mov     [rbp+hKey], 0
0x18000c4b3  mov     [rbp+lpSubKey], 0
0x18000c4bb  mov     [rbp+var_18], 0
0x18000c4c3  mov     [rbp+var_10], 0
0x18000c4cb  lea     r9, aConfigs; "Configs"
0x18000c4d2  mov     r8, [rcx+8]
0x18000c4d6  lea     rdx, aSS; "%s\\%s"
0x18000c4dd  lea     rcx, [rbp+lpSubKey]
0x18000c4e1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000c4e6  test    eax, eax
0x18000c4e8  jns     short loc_18000C4FC
0x18000c4ea  mov     rcx, [rbp+lpSubKey]
0x18000c4ee  test    rcx, rcx
0x18000c4f1  jz      loc_18000C592
0x18000c4f7  jmp     loc_18000C58C
0x18000c4fc  mov     rdi, [rbp+hKey]
0x18000c500  test    rdi, rdi
0x18000c503  jz      short loc_18000C51E
0x18000c505  call    cs:__imp_GetLastError
0x18000c50b  mov     ebx, eax
0x18000c50d  mov     rcx, rdi; hKey
0x18000c510  call    cs:__imp_RegCloseKey
0x18000c516  mov     ecx, ebx; dwErrCode
0x18000c518  call    cs:__imp_SetLastError
0x18000c51e  mov     [rbp+hKey], 0
0x18000c526  lea     rax, [rbp+hKey]
0x18000c52a  mov     [rsp+50h+phkResult], rax; phkResult
0x18000c52f  mov     r9d, 20019h; samDesired
0x18000c535  xor     r8d, r8d; ulOptions
0x18000c538  mov     rbx, [rbp+lpSubKey]
0x18000c53c  mov     rdx, rbx; lpSubKey
0x18000c53f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c546  call    cs:__imp_RegOpenKeyExW
0x18000c54c  test    eax, eax
0x18000c54e  jnz     short loc_18000C584
0x18000c550  mov     [rbp+Type], eax
0x18000c553  mov     [rbp+cbData], eax
0x18000c556  lea     rax, [rbp+cbData]
0x18000c55a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000c55f  mov     [rsp+50h+phkResult], 0; lpData
0x18000c568  lea     r9, [rbp+Type]; lpType
0x18000c56c  xor     r8d, r8d; lpReserved
0x18000c56f  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x18000c576  mov     rcx, [rbp+hKey]; hKey
0x18000c57a  call    cs:__imp_RegQueryValueExW
0x18000c580  test    eax, eax
0x18000c582  jz      short loc_18000C5A5
0x18000c584  test    rbx, rbx
0x18000c587  jz      short loc_18000C592
0x18000c589  mov     rcx, rbx; pv
0x18000c58c  call    cs:__imp_CoTaskMemFree
0x18000c592  mov     rcx, [rbp+hKey]; hKey
0x18000c596  test    rcx, rcx
0x18000c599  jz      short loc_18000C5A1
0x18000c59b  call    cs:__imp_RegCloseKey
0x18000c5a1  xor     al, al
0x18000c5a3  jmp     short loc_18000C5C4
0x18000c5a5  test    rbx, rbx
0x18000c5a8  jz      short loc_18000C5B3
0x18000c5aa  mov     rcx, rbx; pv
0x18000c5ad  call    cs:__imp_CoTaskMemFree
0x18000c5b3  mov     rcx, [rbp+hKey]; hKey
0x18000c5b7  test    rcx, rcx
0x18000c5ba  jz      short loc_18000C5C2
0x18000c5bc  call    cs:__imp_RegCloseKey
0x18000c5c2  mov     al, 1
0x18000c5c4  add     rsp, 50h
0x18000c5c8  pop     rdi
0x18000c5c9  pop     rbx
0x18000c5ca  pop     rbp
0x18000c5cb  retn
```
