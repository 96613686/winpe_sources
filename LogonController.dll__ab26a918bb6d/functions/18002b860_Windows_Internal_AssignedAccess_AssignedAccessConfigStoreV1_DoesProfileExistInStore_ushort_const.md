# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesProfileExistInStore(ushort const *)

- ea: `0x18002b860`
- end: `0x18002b9f7`
- name: `?DoesProfileExistInStore@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@EEAA_NPEBG@Z`
- size: `407`
- prototype: `bool(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002b860`
- `0x18002ba00`
- `0x18002bc20`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002b8fe`
- `KERNEL32!SetLastError` at `0x18002b950`
- `KERNEL32!SetLastError` at `0x18002b8fe`
- `KERNEL32!SetLastError` at `0x18002b950`
- `KERNEL32!GetLastError` at `0x18002b8eb`
- `KERNEL32!GetLastError` at `0x18002b93d`
- `KERNEL32!GetLastError` at `0x18002b8eb`
- `KERNEL32!GetLastError` at `0x18002b93d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b8b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b8b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b926`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b926`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b8c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b8f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b987`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b8c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b8f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b987`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9e9`

## string_xrefs

- `0x18002b88b`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesProfileExistInStore(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this,
        const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  HKEY v5; // rsi
  DWORD LastError; // edi
  LPVOID pv[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              pv,
              L"%s\\%s",
              *((_QWORD *)this + 1),
              L"Configs") < 0 )
  {
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    v3 = hKey;
    if ( !hKey )
      return 0;
    goto LABEL_5;
  }
  v5 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v5);
    SetLastError(LastError);
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv[0], 0, 0x20019u, &hKey) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    v3 = hKey;
    if ( !hKey )
      return 0;
    goto LABEL_5;
  }
  phkResult = 0;
  if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult) )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    v3 = hKey;
    if ( !hKey )
      return 0;
LABEL_5:
    RegCloseKey(v3);
    return 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
  if ( hKey )
    RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18002b860  mov     [rsp-18h+arg_8], rbx
0x18002b865  mov     [rsp-18h+arg_18], rsi
0x18002b86a  push    rbp
0x18002b86b  push    rdi
0x18002b86c  push    r14
0x18002b86e  mov     rbp, rsp
0x18002b871  sub     rsp, 50h
0x18002b875  mov     rbx, rdx
0x18002b878  xor     r14d, r14d
0x18002b87b  mov     [rbp+hKey], r14
0x18002b87f  mov     [rbp+pv], r14
0x18002b883  mov     [rbp+var_18], r14
0x18002b887  mov     [rbp+var_10], r14
0x18002b88b  lea     r9, aConfigs; "Configs"
0x18002b892  mov     r8, [rcx+8]
0x18002b896  lea     rdx, aSS_0; "%s\\%s"
0x18002b89d  lea     rcx, [rbp+pv]
0x18002b8a1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002b8a6  test    eax, eax
0x18002b8a8  jns     short loc_18002B8E2
0x18002b8aa  mov     rcx, [rbp+pv]; pv
0x18002b8ae  test    rcx, rcx
0x18002b8b1  jz      short loc_18002B8BA
0x18002b8b3  call    cs:__imp_CoTaskMemFree
0x18002b8b9  nop
0x18002b8ba  mov     rcx, [rbp+hKey]; hKey
0x18002b8be  test    rcx, rcx
0x18002b8c1  jz      short loc_18002B8CA
0x18002b8c3  call    cs:__imp_RegCloseKey
0x18002b8c9  nop
0x18002b8ca  xor     al, al
0x18002b8cc  mov     rbx, [rsp+50h+arg_8]
0x18002b8d1  mov     rsi, [rsp+50h+arg_18]
0x18002b8d9  add     rsp, 50h
0x18002b8dd  pop     r14
0x18002b8df  pop     rdi
0x18002b8e0  pop     rbp
0x18002b8e1  retn
0x18002b8e2  mov     rsi, [rbp+hKey]
0x18002b8e6  test    rsi, rsi
0x18002b8e9  jz      short loc_18002B905
0x18002b8eb  call    cs:__imp_GetLastError
0x18002b8f1  mov     edi, eax
0x18002b8f3  mov     rcx, rsi; hKey
0x18002b8f6  call    cs:__imp_RegCloseKey
0x18002b8fc  mov     ecx, edi; dwErrCode
0x18002b8fe  call    cs:__imp_SetLastError
0x18002b904  nop
0x18002b905  mov     [rbp+hKey], r14
0x18002b909  lea     rax, [rbp+hKey]
0x18002b90d  mov     [rsp+50h+phkResult], rax; phkResult
0x18002b912  mov     r9d, 20019h; samDesired
0x18002b918  xor     r8d, r8d; ulOptions
0x18002b91b  mov     rdx, [rbp+pv]; lpSubKey
0x18002b91f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b926  call    cs:__imp_RegOpenKeyExW
0x18002b92c  test    eax, eax
0x18002b92e  jnz     short loc_18002B9AA
0x18002b930  mov     [rbp+arg_10], r14
0x18002b934  mov     rsi, [rbp+arg_10]
0x18002b938  test    rsi, rsi
0x18002b93b  jz      short loc_18002B957
0x18002b93d  call    cs:__imp_GetLastError
0x18002b943  mov     edi, eax
0x18002b945  mov     rcx, rsi; hKey
0x18002b948  call    cs:__imp_RegCloseKey
0x18002b94e  mov     ecx, edi; dwErrCode
0x18002b950  call    cs:__imp_SetLastError
0x18002b956  nop
0x18002b957  mov     [rbp+arg_10], r14
0x18002b95b  lea     rax, [rbp+arg_10]
0x18002b95f  mov     [rsp+50h+phkResult], rax; phkResult
0x18002b964  mov     r9d, 20019h; samDesired
0x18002b96a  xor     r8d, r8d; ulOptions
0x18002b96d  mov     rdx, rbx; lpSubKey
0x18002b970  mov     rcx, [rbp+hKey]; hKey
0x18002b974  call    cs:__imp_RegOpenKeyExW
0x18002b97a  test    eax, eax
0x18002b97c  jz      short loc_18002B9C6
0x18002b97e  mov     rcx, [rbp+arg_10]; hKey
0x18002b982  test    rcx, rcx
0x18002b985  jz      short loc_18002B98E
0x18002b987  call    cs:__imp_RegCloseKey
0x18002b98d  nop
0x18002b98e  lea     rcx, [rbp+pv]
0x18002b992  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002b997  nop
0x18002b998  mov     rcx, [rbp+hKey]
0x18002b99c  test    rcx, rcx
0x18002b99f  jz      loc_18002B8CA
0x18002b9a5  jmp     loc_18002B8C3
0x18002b9aa  lea     rcx, [rbp+pv]
0x18002b9ae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002b9b3  nop
0x18002b9b4  mov     rcx, [rbp+hKey]
0x18002b9b8  test    rcx, rcx
0x18002b9bb  jz      loc_18002B8CA
0x18002b9c1  jmp     loc_18002B8C3
0x18002b9c6  mov     rcx, [rbp+arg_10]; hKey
0x18002b9ca  test    rcx, rcx
0x18002b9cd  jz      short loc_18002B9D6
0x18002b9cf  call    cs:__imp_RegCloseKey
0x18002b9d5  nop
0x18002b9d6  lea     rcx, [rbp+pv]
0x18002b9da  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002b9df  nop
0x18002b9e0  mov     rcx, [rbp+hKey]; hKey
0x18002b9e4  test    rcx, rcx
0x18002b9e7  jz      short loc_18002B9F0
0x18002b9e9  call    cs:__imp_RegCloseKey
0x18002b9ef  nop
0x18002b9f0  mov     al, 1
0x18002b9f2  jmp     loc_18002B8CC
```
