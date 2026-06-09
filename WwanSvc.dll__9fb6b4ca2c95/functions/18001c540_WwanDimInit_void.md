# WwanDimInit(void)

- ea: `0x18001c540`
- end: `0x18001c865`
- name: `?WwanDimInit@@YAKXZ`
- size: `805`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014fe8`

## callees

- `0x180012300`
- `0x18001bf28`
- `0x18001c540`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001c689`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001c689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c71f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c71f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c618`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c618`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c853`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c5f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c5f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c760`

## string_xrefs

- `0x18001c589`: `Error %d opening Dim registry key`
- `0x18001c62c`: `Error %d closing registry key`
- `0x18001c7e3`: `Memory allocation for dim descriptor array failed`
- `0x18001c76f`: `%d opening subkey %s`

## pseudocode

```c
__int64 WwanDimInit(void)
{
  unsigned int v0; // eax
  unsigned int v1; // edi
  DWORD LastError; // eax
  WCHAR *v3; // rsi
  __int64 v4; // rcx
  _BYTE *i; // rax
  DWORD j; // edi
  __int64 v7; // rcx
  WCHAR *v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  const unsigned __int16 *v13; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  DWORD cbMaxSubKeyLen; // [rsp+90h] [rbp+28h] BYREF
  DWORD cchName; // [rsp+98h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+38h] BYREF
  HKEY v19; // [rsp+A8h] [rbp+40h] BYREF

  cbMaxSubKeyLen = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WwanSvc\\DIM", 0, 0x20019u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    WwanLog::Error("WwanDimInit", 0, L"Error %d opening Dim registry key", v0);
LABEL_3:
    WwanLog::Error("WwanDimInit", 0, L"Dim initialization failed");
    return v1;
  }
  v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v1 )
  {
    WwanLog::Error("WwanDimInit", 0, L"Could not query no. of subkeys");
    if ( RegCloseKey(hKey) )
    {
      LastError = GetLastError();
      WwanLog::Error("WwanDimInit", 0, L"Error %d closing registry key", LastError);
    }
    goto LABEL_3;
  }
  v3 = (WCHAR *)WwanMemAlloc(2LL * (cbMaxSubKeyLen + 1));
  if ( !v3 || !cSubKeys )
  {
    v12 = GetLastError();
    v13 = L"Memory allocation for subkey name failed";
LABEL_27:
    v1 = v12;
    WwanLog::Error("WwanDimInit", 0, v13);
    if ( qword_180152970 )
      WwanMemFree(qword_180152970);
    qword_180152970 = 0;
    cSubKeys = 0;
    WwanLog::Error("WwanDimInit", 0, L"Dim initialization failed");
    if ( !v3 )
      goto LABEL_31;
    goto LABEL_30;
  }
  qword_180152970 = WwanMemAlloc(600LL * cSubKeys);
  if ( !qword_180152970 || !InitializeCriticalSectionAndSpinCount(&stru_180152828, 0) )
  {
    v12 = GetLastError();
    v13 = L"Memory allocation for dim descriptor array failed";
    goto LABEL_27;
  }
  v4 = 600LL * cSubKeys;
  for ( i = (_BYTE *)qword_180152970; v4; --v4 )
    *i++ = 0;
  EnterCriticalSection(&stru_180152828);
  for ( j = 0; j < cSubKeys; ++j )
  {
    v7 = 4;
    v19 = 0;
    cchName = 2 * cbMaxSubKeyLen + 2;
    v8 = v3;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (WCHAR *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
    v9 = RegEnumKeyExW(hKey, j, v3, &cchName, 0, 0, 0, 0);
    if ( v9 )
    {
      LODWORD(phkResult) = j;
      WwanLog::Error("WwanDimInit", 0, L"%d enumerating subkey %d", v9, phkResult);
    }
    else
    {
      v10 = RegOpenKeyExW(hKey, v3, 0, 0x20019u, &v19);
      if ( v10 )
      {
        WwanLog::Error("WwanDimInit", 0, L"%d opening subkey %s", v10, v3);
      }
      else
      {
        DimRegistration(v19, (struct _DIM_DESCRIPTOR *)(qword_180152970 + 600LL * j));
        if ( RegCloseKey(v19) )
        {
          v11 = GetLastError();
          WwanLog::Error("WwanDimInit", 0, L"%d closing subkey", v11);
        }
      }
    }
  }
  LeaveCriticalSection(&stru_180152828);
  v1 = 0;
LABEL_30:
  WwanMemFree(v3);
LABEL_31:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18001c540  push    rbp
0x18001c542  push    rsi
0x18001c543  push    rdi
0x18001c544  push    r14
0x18001c546  mov     rbp, rsp
0x18001c549  sub     rsp, 68h
0x18001c54d  xor     r14d, r14d
0x18001c550  lea     rax, [rbp+hKey]
0x18001c554  mov     r9d, 20019h; samDesired
0x18001c55a  mov     [rbp+cbMaxSubKeyLen], r14d
0x18001c55e  xor     r8d, r8d; ulOptions
0x18001c561  mov     [rbp+hKey], r14
0x18001c565  lea     rdx, SubKey; "Software\\Microsoft\\WwanSvc\\DIM"
0x18001c56c  mov     [rsp+68h+phkResult], rax; phkResult
0x18001c571  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c578  call    cs:__imp_RegOpenKeyExW
0x18001c57e  xor     edx, edx; struct _GUID *
0x18001c580  mov     edi, eax
0x18001c582  test    eax, eax
0x18001c584  jz      short loc_18001C5B6
0x18001c586  mov     r9d, eax
0x18001c589  lea     r8, aErrorDOpeningD; "Error %d opening Dim registry key"
0x18001c590  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c597  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c59c  lea     r8, aDimInitializat; "Dim initialization failed"
0x18001c5a3  xor     edx, edx; struct _GUID *
0x18001c5a5  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c5ac  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c5b1  jmp     loc_18001C859
0x18001c5b6  mov     rcx, [rbp+hKey]; hKey
0x18001c5ba  lea     rax, [rbp+cbMaxSubKeyLen]
0x18001c5be  mov     [rsp+68h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001c5c3  xor     r9d, r9d; lpReserved
0x18001c5c6  mov     [rsp+68h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18001c5cb  xor     r8d, r8d; lpcchClass
0x18001c5ce  mov     [rsp+68h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18001c5d3  mov     [rsp+68h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18001c5d8  mov     [rsp+68h+lpcValues], r14; lpcValues
0x18001c5dd  mov     [rsp+68h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001c5e2  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001c5e7  lea     rax, cSubKeys
0x18001c5ee  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x18001c5f3  call    cs:__imp_RegQueryInfoKeyW
0x18001c5f9  mov     edi, eax
0x18001c5fb  test    eax, eax
0x18001c5fd  jz      short loc_18001C63D
0x18001c5ff  lea     r8, aCouldNotQueryN; "Could not query no. of subkeys"
0x18001c606  xor     edx, edx; struct _GUID *
0x18001c608  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c60f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c614  mov     rcx, [rbp+hKey]; hKey
0x18001c618  call    cs:__imp_RegCloseKey
0x18001c61e  test    eax, eax
0x18001c620  jz      loc_18001C59C
0x18001c626  call    cs:__imp_GetLastError
0x18001c62c  lea     r8, aErrorDClosingR; "Error %d closing registry key"
0x18001c633  xor     edx, edx
0x18001c635  mov     r9d, eax
0x18001c638  jmp     loc_18001C590
0x18001c63d  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18001c640  inc     ecx
0x18001c642  add     rcx, rcx; Size
0x18001c645  call    WwanMemAlloc
0x18001c64a  mov     rsi, rax
0x18001c64d  test    rax, rax
0x18001c650  jz      loc_18001C7EC
0x18001c656  mov     eax, cs:cSubKeys
0x18001c65c  test    eax, eax
0x18001c65e  jz      loc_18001C7EC
0x18001c664  imul    rcx, rax, 258h; Size
0x18001c66b  call    WwanMemAlloc
0x18001c670  mov     cs:qword_180152970, rax
0x18001c677  test    rax, rax
0x18001c67a  jz      loc_18001C7DD
0x18001c680  xor     edx, edx; dwSpinCount
0x18001c682  lea     rcx, stru_180152828; lpCriticalSection
0x18001c689  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001c68f  test    eax, eax
0x18001c691  jz      loc_18001C7DD
0x18001c697  mov     eax, cs:cSubKeys
0x18001c69d  imul    rcx, rax, 258h
0x18001c6a4  mov     rax, cs:qword_180152970
0x18001c6ab  test    rcx, rcx
0x18001c6ae  jz      short loc_18001C6BC
0x18001c6b0  mov     [rax], r14b
0x18001c6b3  inc     rax
0x18001c6b6  sub     rcx, 1
0x18001c6ba  jnz     short loc_18001C6B0
0x18001c6bc  lea     rcx, stru_180152828; lpCriticalSection
0x18001c6c3  call    cs:__imp_EnterCriticalSection
0x18001c6c9  cmp     cs:cSubKeys, r14d
0x18001c6d0  mov     edi, r14d
0x18001c6d3  jbe     loc_18001C7CB
0x18001c6d9  mov     eax, [rbp+cbMaxSubKeyLen]
0x18001c6dc  mov     ecx, 4
0x18001c6e1  mov     [rbp+arg_18], r14
0x18001c6e5  lea     eax, ds:2[rax*2]
0x18001c6ec  mov     [rbp+cchName], eax
0x18001c6ef  mov     rax, rsi
0x18001c6f2  mov     [rax], r14b
0x18001c6f5  inc     rax
0x18001c6f8  sub     rcx, 1
0x18001c6fc  jnz     short loc_18001C6F2
0x18001c6fe  mov     rcx, [rbp+hKey]; hKey
0x18001c702  lea     r9, [rbp+cchName]; lpcchName
0x18001c706  mov     [rsp+68h+lpcValues], r14; lpftLastWriteTime
0x18001c70b  mov     r8, rsi; lpName
0x18001c70e  mov     [rsp+68h+lpcbMaxClassLen], r14; lpcchClass
0x18001c713  mov     edx, edi; dwIndex
0x18001c715  mov     [rsp+68h+lpcbMaxSubKeyLen], r14; lpClass
0x18001c71a  mov     [rsp+68h+phkResult], r14; lpReserved
0x18001c71f  call    cs:__imp_RegEnumKeyExW
0x18001c725  test    eax, eax
0x18001c727  jz      short loc_18001C747
0x18001c729  mov     dword ptr [rsp+68h+phkResult], edi
0x18001c72d  lea     r8, aDEnumeratingSu; "%d enumerating subkey %d"
0x18001c734  mov     r9d, eax
0x18001c737  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c73e  xor     edx, edx; struct _GUID *
0x18001c740  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c745  jmp     short loc_18001C7BD
0x18001c747  mov     rcx, [rbp+hKey]; hKey
0x18001c74b  lea     rax, [rbp+arg_18]
0x18001c74f  mov     r9d, 20019h; samDesired
0x18001c755  mov     [rsp+68h+phkResult], rax; phkResult
0x18001c75a  xor     r8d, r8d; ulOptions
0x18001c75d  mov     rdx, rsi; lpSubKey
0x18001c760  call    cs:__imp_RegOpenKeyExW
0x18001c766  test    eax, eax
0x18001c768  jz      short loc_18001C778
0x18001c76a  mov     [rsp+68h+phkResult], rsi
0x18001c76f  lea     r8, aDOpeningSubkey; "%d opening subkey %s"
0x18001c776  jmp     short loc_18001C734
0x18001c778  mov     rcx, [rbp+arg_18]; hKey
0x18001c77c  mov     eax, edi
0x18001c77e  imul    rdx, rax, 258h
0x18001c785  add     rdx, cs:qword_180152970; struct _DIM_DESCRIPTOR *
0x18001c78c  call    ?DimRegistration@@YAKPEAXPEAU_DIM_DESCRIPTOR@@@Z; DimRegistration(void *,_DIM_DESCRIPTOR *)
0x18001c791  mov     rcx, [rbp+arg_18]; hKey
0x18001c795  call    cs:__imp_RegCloseKey
0x18001c79b  test    eax, eax
0x18001c79d  jz      short loc_18001C7BD
0x18001c79f  call    cs:__imp_GetLastError
0x18001c7a5  lea     r8, aDClosingSubkey; "%d closing subkey"
0x18001c7ac  xor     edx, edx; struct _GUID *
0x18001c7ae  mov     r9d, eax
0x18001c7b1  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c7b8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c7bd  inc     edi
0x18001c7bf  cmp     edi, cs:cSubKeys
0x18001c7c5  jb      loc_18001C6D9
0x18001c7cb  lea     rcx, stru_180152828; lpCriticalSection
0x18001c7d2  call    cs:__imp_LeaveCriticalSection
0x18001c7d8  mov     edi, r14d
0x18001c7db  jmp     short loc_18001C842
0x18001c7dd  call    cs:__imp_GetLastError
0x18001c7e3  lea     r8, aMemoryAllocati_8; "Memory allocation for dim descriptor ar"...
0x18001c7ea  jmp     short loc_18001C7F9
0x18001c7ec  call    cs:__imp_GetLastError
0x18001c7f2  lea     r8, aMemoryAllocati_6; "Memory allocation for subkey name faile"...
0x18001c7f9  mov     edi, eax
0x18001c7fb  xor     edx, edx; struct _GUID *
0x18001c7fd  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c804  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c809  mov     rcx, cs:qword_180152970
0x18001c810  test    rcx, rcx
0x18001c813  jz      short loc_18001C81A
0x18001c815  call    WwanMemFree
0x18001c81a  lea     r8, aDimInitializat; "Dim initialization failed"
0x18001c821  mov     cs:qword_180152970, r14
0x18001c828  xor     edx, edx; struct _GUID *
0x18001c82a  mov     cs:cSubKeys, r14d
0x18001c831  lea     rcx, aWwandiminit; "WwanDimInit"
0x18001c838  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001c83d  test    rsi, rsi
0x18001c840  jz      short loc_18001C84A
0x18001c842  mov     rcx, rsi
0x18001c845  call    WwanMemFree
0x18001c84a  mov     rcx, [rbp+hKey]; hKey
0x18001c84e  test    rcx, rcx
0x18001c851  jz      short loc_18001C859
0x18001c853  call    cs:__imp_RegCloseKey
0x18001c859  mov     eax, edi
0x18001c85b  add     rsp, 68h
0x18001c85f  pop     r14
0x18001c861  pop     rdi
0x18001c862  pop     rsi
0x18001c863  pop     rbp
0x18001c864  retn
```
