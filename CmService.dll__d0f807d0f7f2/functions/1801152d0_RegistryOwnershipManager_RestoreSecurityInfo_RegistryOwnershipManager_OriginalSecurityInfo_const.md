# RegistryOwnershipManager::RestoreSecurityInfo(RegistryOwnershipManager::OriginalSecurityInfo const &)

- ea: `0x1801152d0`
- end: `0x1801154cd`
- name: `?RestoreSecurityInfo@RegistryOwnershipManager@@AEAAJAEBUOriginalSecurityInfo@1@@Z`
- size: `509`
- prototype: `int(RegistryOwnershipManager *__hidden this, const struct RegistryOwnershipManager::OriginalSecurityInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180114720`

## callees

- `0x18000da88`
- `0x18000dad8`
- `0x1801152d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801153f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801153f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115416`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011536e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801154b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011536e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801154b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011533b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011544c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011533b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011544c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801153a8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18011548e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801153a8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18011548e`

## string_xrefs

- `0x1801152f4`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180115354`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x1801153d0`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
__int64 __fastcall RegistryOwnershipManager::RestoreSecurityInfo(
        HKEY *this,
        const struct RegistryOwnershipManager::OriginalSecurityInfo *a2)
{
  const struct RegistryOwnershipManager::OriginalSecurityInfo *v2; // rdi
  unsigned int v4; // ebx
  bool v6; // cc
  DWORD v7; // eax
  __int64 v8; // rdx
  PACL *v9; // rsi
  HKEY v10; // r14
  DWORD LastError; // ebx
  int phkResult; // [rsp+20h] [rbp-28h]
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  v2 = a2;
  if ( *((_QWORD *)a2 + 4) == *((_QWORD *)a2 + 5) )
  {
    v4 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
      (const char *)0x8000FFFFLL,
      phkResult);
    return v4;
  }
  v6 = *((_QWORD *)a2 + 3) <= 7u;
  hKey = 0;
  if ( !v6 )
    a2 = *(const struct RegistryOwnershipManager::OriginalSecurityInfo **)a2;
  v7 = RegOpenKeyExW(*this, (LPCWSTR)a2, 0, 0x80000u, &hKey);
  if ( v7 )
  {
    v8 = 256;
LABEL_8:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
           (const char *)v7,
           phkResulta);
    goto LABEL_9;
  }
  v7 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 1u, *((PSID *)v2 + 4), 0, 0, 0);
  if ( v7 )
  {
    v8 = 259;
    goto LABEL_8;
  }
  v9 = (PACL *)((char *)v2 + 56);
  if ( *((_QWORD *)v2 + 7) == *((_QWORD *)v2 + 8) )
  {
    v4 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
      (const char *)0x8000FFFFLL,
      phkResulta);
LABEL_9:
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v10 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v10);
    SetLastError(LastError);
  }
  v6 = *((_QWORD *)v2 + 3) <= 7u;
  hKey = 0;
  if ( !v6 )
    v2 = *(const struct RegistryOwnershipManager::OriginalSecurityInfo **)v2;
  v7 = RegOpenKeyExW(*this, (LPCWSTR)v2, 0, 0x40000u, &hKey);
  if ( v7 )
  {
    v8 = 264;
    goto LABEL_8;
  }
  v7 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 4u, 0, 0, *v9, 0);
  if ( v7 )
  {
    v8 = 267;
    goto LABEL_8;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1801152d0  push    rbp
0x1801152d2  push    rbx
0x1801152d3  push    rsi
0x1801152d4  push    rdi
0x1801152d5  push    r14
0x1801152d7  push    r15
0x1801152d9  mov     rbp, rsp
0x1801152dc  sub     rsp, 48h
0x1801152e0  mov     rax, [rdx+28h]
0x1801152e4  mov     rdi, rdx
0x1801152e7  mov     r15, rcx
0x1801152ea  cmp     [rdx+20h], rax
0x1801152ee  jnz     short loc_180115314
0x1801152f0  mov     rcx, [rbp+30h]; this
0x1801152f4  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x1801152fb  mov     ebx, 8000FFFFh
0x180115300  mov     edx, 0FEh; void *
0x180115305  mov     r9d, ebx; char *
0x180115308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011530d  mov     eax, ebx
0x18011530f  jmp     loc_1801154BF
0x180115314  cmp     qword ptr [rdx+18h], 7
0x180115319  mov     [rbp+hKey], 0
0x180115321  jbe     short loc_180115326
0x180115323  mov     rdx, [rdx]; lpSubKey
0x180115326  mov     rcx, [rcx]; hKey
0x180115329  lea     rax, [rbp+hKey]
0x18011532d  mov     r9d, 80000h; samDesired
0x180115333  mov     [rsp+48h+phkResult], rax; unsigned int
0x180115338  xor     r8d, r8d; ulOptions
0x18011533b  call    cs:__imp_RegOpenKeyExW
0x180115342  nop     dword ptr [rax+rax+00h]
0x180115347  test    eax, eax
0x180115349  jz      short loc_18011537C
0x18011534b  mov     edx, 100h; void *
0x180115350  mov     rcx, [rbp+30h]; this
0x180115354  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x18011535b  mov     r9d, eax; char *
0x18011535e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180115363  mov     ebx, eax
0x180115365  mov     rcx, [rbp+hKey]; hKey
0x180115369  test    rcx, rcx
0x18011536c  jz      short loc_18011530D
0x18011536e  call    cs:__imp_RegCloseKey
0x180115375  nop     dword ptr [rax+rax+00h]
0x18011537a  jmp     short loc_18011530D
0x18011537c  mov     r9, [rdi+20h]; psidOwner
0x180115380  mov     edx, 4; ObjectType
0x180115385  mov     rcx, [rbp+hKey]; handle
0x180115389  mov     [rsp+48h+pSacl], 0; pSacl
0x180115392  mov     [rsp+48h+pDacl], 0; pDacl
0x18011539b  lea     r8d, [rdx-3]; SecurityInfo
0x18011539f  mov     [rsp+48h+phkResult], 0; int
0x1801153a8  call    cs:__imp_SetSecurityInfo
0x1801153af  nop     dword ptr [rax+rax+00h]
0x1801153b4  test    eax, eax
0x1801153b6  jz      short loc_1801153BF
0x1801153b8  mov     edx, 103h
0x1801153bd  jmp     short loc_180115350
0x1801153bf  lea     rsi, [rdi+38h]
0x1801153c3  mov     rax, [rsi+8]
0x1801153c7  cmp     [rsi], rax
0x1801153ca  jnz     short loc_1801153EE
0x1801153cc  mov     rcx, [rbp+30h]; this
0x1801153d0  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x1801153d7  mov     ebx, 8000FFFFh
0x1801153dc  mov     edx, 106h; void *
0x1801153e1  mov     r9d, ebx; char *
0x1801153e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801153e9  jmp     loc_180115365
0x1801153ee  mov     r14, [rbp+hKey]
0x1801153f2  test    r14, r14
0x1801153f5  jz      short loc_180115422
0x1801153f7  call    cs:__imp_GetLastError
0x1801153fe  nop     dword ptr [rax+rax+00h]
0x180115403  mov     rcx, r14; hKey
0x180115406  mov     ebx, eax
0x180115408  call    cs:__imp_RegCloseKey
0x18011540f  nop     dword ptr [rax+rax+00h]
0x180115414  mov     ecx, ebx; dwErrCode
0x180115416  call    cs:__imp_SetLastError
0x18011541d  nop     dword ptr [rax+rax+00h]
0x180115422  cmp     qword ptr [rdi+18h], 7
0x180115427  mov     [rbp+hKey], 0
0x18011542f  jbe     short loc_180115434
0x180115431  mov     rdi, [rdi]
0x180115434  mov     rcx, [r15]; hKey
0x180115437  lea     rax, [rbp+hKey]
0x18011543b  mov     r9d, 40000h; samDesired
0x180115441  mov     [rsp+48h+phkResult], rax; phkResult
0x180115446  xor     r8d, r8d; ulOptions
0x180115449  mov     rdx, rdi; lpSubKey
0x18011544c  call    cs:__imp_RegOpenKeyExW
0x180115453  nop     dword ptr [rax+rax+00h]
0x180115458  test    eax, eax
0x18011545a  jz      short loc_180115466
0x18011545c  mov     edx, 108h
0x180115461  jmp     loc_180115350
0x180115466  mov     rax, [rsi]
0x180115469  xor     r9d, r9d; psidOwner
0x18011546c  mov     rcx, [rbp+hKey]; handle
0x180115470  mov     [rsp+48h+pSacl], 0; pSacl
0x180115479  mov     [rsp+48h+pDacl], rax; pDacl
0x18011547e  lea     edx, [r9+4]; ObjectType
0x180115482  mov     [rsp+48h+phkResult], 0; psidGroup
0x18011548b  mov     r8d, edx; SecurityInfo
0x18011548e  call    cs:__imp_SetSecurityInfo
0x180115495  nop     dword ptr [rax+rax+00h]
0x18011549a  test    eax, eax
0x18011549c  jz      short loc_1801154A8
0x18011549e  mov     edx, 10Bh
0x1801154a3  jmp     loc_180115350
0x1801154a8  mov     rcx, [rbp+hKey]; hKey
0x1801154ac  test    rcx, rcx
0x1801154af  jz      short loc_1801154BD
0x1801154b1  call    cs:__imp_RegCloseKey
0x1801154b8  nop     dword ptr [rax+rax+00h]
0x1801154bd  xor     eax, eax
0x1801154bf  add     rsp, 48h
0x1801154c3  pop     r15
0x1801154c5  pop     r14
0x1801154c7  pop     rdi
0x1801154c8  pop     rsi
0x1801154c9  pop     rbx
0x1801154ca  pop     rbp
0x1801154cb  retn
```
