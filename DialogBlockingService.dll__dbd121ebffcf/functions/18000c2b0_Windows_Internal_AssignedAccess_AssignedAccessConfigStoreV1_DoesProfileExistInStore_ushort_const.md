# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesProfileExistInStore(ushort const *)

- ea: `0x18000c2b0`
- end: `0x18000c3f8`
- name: `?DoesProfileExistInStore@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@EEAA_NPEBG@Z`
- size: `328`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008ec8`
- `0x18000c2b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c32f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c32f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c31c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c35f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c387`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c35f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c327`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c39a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c327`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c39a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3e3`

## string_xrefs

- `0x18000c2e2`: `Configs`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesProfileExistInStore(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this,
        const unsigned __int16 *a2)
{
  WCHAR *v3; // rcx
  HKEY v4; // rdi
  DWORD LastError; // ebx
  WCHAR *v6; // rbx
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              lpSubKey,
              L"%s\\%s",
              *((_QWORD *)this + 1),
              L"Configs") < 0 )
  {
    v3 = (WCHAR *)lpSubKey[0];
    if ( lpSubKey[0] )
      goto LABEL_12;
    goto LABEL_13;
  }
  v4 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  hKey = 0;
  v6 = (WCHAR *)lpSubKey[0];
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey) )
  {
LABEL_10:
    if ( v6 )
    {
      v3 = v6;
LABEL_12:
      CoTaskMemFree(v3);
    }
LABEL_13:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  phkResult = 0;
  if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult) )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_10;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18000c2b0  mov     [rsp-18h+arg_8], rbx
0x18000c2b5  push    rbp
0x18000c2b6  push    rsi
0x18000c2b7  push    rdi
0x18000c2b8  mov     rbp, rsp
0x18000c2bb  sub     rsp, 50h
0x18000c2bf  mov     rsi, rdx
0x18000c2c2  mov     [rbp+hKey], 0
0x18000c2ca  mov     [rbp+lpSubKey], 0
0x18000c2d2  mov     [rbp+var_18], 0
0x18000c2da  mov     [rbp+var_10], 0
0x18000c2e2  lea     r9, aConfigs; "Configs"
0x18000c2e9  mov     r8, [rcx+8]
0x18000c2ed  lea     rdx, aSS; "%s\\%s"
0x18000c2f4  lea     rcx, [rbp+lpSubKey]
0x18000c2f8  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000c2fd  test    eax, eax
0x18000c2ff  jns     short loc_18000C313
0x18000c301  mov     rcx, [rbp+lpSubKey]
0x18000c305  test    rcx, rcx
0x18000c308  jz      loc_18000C3AE
0x18000c30e  jmp     loc_18000C3A8
0x18000c313  mov     rdi, [rbp+hKey]
0x18000c317  test    rdi, rdi
0x18000c31a  jz      short loc_18000C335
0x18000c31c  call    cs:__imp_GetLastError
0x18000c322  mov     ebx, eax
0x18000c324  mov     rcx, rdi; hKey
0x18000c327  call    cs:__imp_RegCloseKey
0x18000c32d  mov     ecx, ebx; dwErrCode
0x18000c32f  call    cs:__imp_SetLastError
0x18000c335  mov     [rbp+hKey], 0
0x18000c33d  lea     rax, [rbp+hKey]
0x18000c341  mov     [rsp+50h+phkResult], rax; phkResult
0x18000c346  mov     edi, 20019h
0x18000c34b  mov     r9d, edi; samDesired
0x18000c34e  xor     r8d, r8d; ulOptions
0x18000c351  mov     rbx, [rbp+lpSubKey]
0x18000c355  mov     rdx, rbx; lpSubKey
0x18000c358  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c35f  call    cs:__imp_RegOpenKeyExW
0x18000c365  test    eax, eax
0x18000c367  jnz     short loc_18000C3A0
0x18000c369  mov     [rbp+arg_10], 0
0x18000c371  lea     rax, [rbp+arg_10]
0x18000c375  mov     [rsp+50h+phkResult], rax; phkResult
0x18000c37a  mov     r9d, edi; samDesired
0x18000c37d  xor     r8d, r8d; ulOptions
0x18000c380  mov     rdx, rsi; lpSubKey
0x18000c383  mov     rcx, [rbp+hKey]; hKey
0x18000c387  call    cs:__imp_RegOpenKeyExW
0x18000c38d  mov     rcx, [rbp+arg_10]; hKey
0x18000c391  test    eax, eax
0x18000c393  jz      short loc_18000C3C1
0x18000c395  test    rcx, rcx
0x18000c398  jz      short loc_18000C3A0
0x18000c39a  call    cs:__imp_RegCloseKey
0x18000c3a0  test    rbx, rbx
0x18000c3a3  jz      short loc_18000C3AE
0x18000c3a5  mov     rcx, rbx; pv
0x18000c3a8  call    cs:__imp_CoTaskMemFree
0x18000c3ae  mov     rcx, [rbp+hKey]; hKey
0x18000c3b2  test    rcx, rcx
0x18000c3b5  jz      short loc_18000C3BD
0x18000c3b7  call    cs:__imp_RegCloseKey
0x18000c3bd  xor     al, al
0x18000c3bf  jmp     short loc_18000C3EB
0x18000c3c1  test    rcx, rcx
0x18000c3c4  jz      short loc_18000C3CC
0x18000c3c6  call    cs:__imp_RegCloseKey
0x18000c3cc  test    rbx, rbx
0x18000c3cf  jz      short loc_18000C3DA
0x18000c3d1  mov     rcx, rbx; pv
0x18000c3d4  call    cs:__imp_CoTaskMemFree
0x18000c3da  mov     rcx, [rbp+hKey]; hKey
0x18000c3de  test    rcx, rcx
0x18000c3e1  jz      short loc_18000C3E9
0x18000c3e3  call    cs:__imp_RegCloseKey
0x18000c3e9  mov     al, 1
0x18000c3eb  mov     rbx, [rsp+50h+arg_8]
0x18000c3f0  add     rsp, 50h
0x18000c3f4  pop     rdi
0x18000c3f5  pop     rsi
0x18000c3f6  pop     rbp
0x18000c3f7  retn
```
