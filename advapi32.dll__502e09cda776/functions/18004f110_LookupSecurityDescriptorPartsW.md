# LookupSecurityDescriptorPartsW

- ea: `0x18004f110`
- end: `0x18004f3a7`
- name: `LookupSecurityDescriptorPartsW`
- size: `663`
- prototype: `DWORD __stdcall(PTRUSTEE_W *ppOwner, PTRUSTEE_W *ppGroup, PULONG pcCountOfAccessEntries, PEXPLICIT_ACCESS_W *ppListOfAccessEntries, PULONG pcCountOfAuditEntries, PEXPLICIT_ACCESS_W *ppListOfAuditEntries, PSECURITY_DESCRIPTOR pSD)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002dcc8`
- `0x18004f110`
- `0x180074010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004f185`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004f185`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004f237`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004f237`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004f2ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004f2ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004f1d8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004f1d8`
- `KERNEL32!LocalFree` at `0x18004f35a`
- `KERNEL32!LocalFree` at `0x18004f36f`
- `KERNEL32!LocalFree` at `0x18004f384`
- `KERNEL32!LocalFree` at `0x18004f399`
- `KERNEL32!LocalFree` at `0x18004f35a`
- `KERNEL32!LocalFree` at `0x18004f36f`
- `KERNEL32!LocalFree` at `0x18004f384`
- `KERNEL32!LocalFree` at `0x18004f399`
- `KERNEL32!GetLastError` at `0x18004f1b1`
- `KERNEL32!GetLastError` at `0x18004f203`
- `KERNEL32!GetLastError` at `0x18004f262`
- `KERNEL32!GetLastError` at `0x18004f2d8`
- `KERNEL32!GetLastError` at `0x18004f1b1`
- `KERNEL32!GetLastError` at `0x18004f203`
- `KERNEL32!GetLastError` at `0x18004f262`
- `KERNEL32!GetLastError` at `0x18004f2d8`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f254`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f2ca`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f254`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f2ca`

## pseudocode

```c
DWORD __stdcall LookupSecurityDescriptorPartsW(
        PTRUSTEE_W *ppOwner,
        PTRUSTEE_W *ppGroup,
        PULONG pcCountOfAccessEntries,
        PEXPLICIT_ACCESS_W *ppListOfAccessEntries,
        PULONG pcCountOfAuditEntries,
        PEXPLICIT_ACCESS_W *ppListOfAuditEntries,
        PSECURITY_DESCRIPTOR pSD)
{
  DWORD result; // eax
  DWORD v12; // ebx
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD ExplicitEntriesFromAclW; // eax
  DWORD LastError; // eax
  BOOL bOwnerDefaulted; // [rsp+20h] [rbp-40h] BYREF
  BOOL bDaclPresent; // [rsp+24h] [rbp-3Ch] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+28h] [rbp-38h] BYREF
  ULONG v20; // [rsp+2Ch] [rbp-34h] BYREF
  PSID pOwner; // [rsp+30h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL v24; // [rsp+48h] [rbp-18h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-10h] BYREF
  PEXPLICIT_ACCESS_W v26; // [rsp+58h] [rbp-8h] BYREF

  pDacl = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  hMem = 0;
  v24 = 0;
  pcCountOfExplicitEntries = 0;
  v20 = 0;
  pListOfExplicitEntries = 0;
  v26 = 0;
  result = AccProvpLoadMartaFunctions();
  v12 = result;
  if ( !result )
  {
    if ( ppOwner )
    {
      v13 = GetSecurityDescriptorOwner(pSD, &pOwner, &bOwnerDefaulted)
          ? (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800B1048)(0, pOwner, &hMem)
          : GetLastError();
      v12 = v13;
      if ( v13 )
        goto LABEL_38;
    }
    if ( ppGroup )
    {
      v14 = GetSecurityDescriptorGroup(pSD, &pOwner, &bOwnerDefaulted)
          ? (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800B1048)(0, pOwner, &v24)
          : GetLastError();
      v12 = v14;
      if ( v14 )
        goto LABEL_38;
    }
    if ( pcCountOfAccessEntries )
    {
      if ( !ppListOfAccessEntries )
        goto LABEL_37;
      if ( GetSecurityDescriptorDacl(pSD, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
        ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(pDacl, &pcCountOfExplicitEntries, &pListOfExplicitEntries);
      else
        ExplicitEntriesFromAclW = GetLastError();
      v12 = ExplicitEntriesFromAclW;
      if ( ExplicitEntriesFromAclW )
        goto LABEL_38;
    }
    else if ( ppListOfAccessEntries )
    {
      goto LABEL_37;
    }
    if ( pcCountOfAuditEntries )
    {
      if ( ppListOfAuditEntries )
      {
        if ( GetSecurityDescriptorSacl(pSD, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
          LastError = GetExplicitEntriesFromAclW(pDacl, &v20, &v26);
        else
          LastError = GetLastError();
        v12 = LastError;
        if ( !LastError )
          goto LABEL_26;
LABEL_38:
        if ( hMem )
          LocalFree(hMem);
        if ( v24 )
          LocalFree(v24);
        if ( pListOfExplicitEntries )
          LocalFree(pListOfExplicitEntries);
        if ( v26 )
          LocalFree(v26);
        return v12;
      }
    }
    else if ( !ppListOfAuditEntries )
    {
LABEL_26:
      if ( ppOwner )
        *ppOwner = (PTRUSTEE_W)hMem;
      if ( ppGroup )
        *ppGroup = (PTRUSTEE_W)v24;
      if ( ppListOfAccessEntries )
      {
        *ppListOfAccessEntries = pListOfExplicitEntries;
        *pcCountOfAccessEntries = pcCountOfExplicitEntries;
      }
      if ( ppListOfAuditEntries )
      {
        *ppListOfAuditEntries = v26;
        *pcCountOfAuditEntries = v20;
      }
      return v12;
    }
LABEL_37:
    v12 = 87;
    goto LABEL_38;
  }
  return result;
}

```

## disassembly

```asm
0x18004f110  mov     [rsp-28h+arg_0], rbx
0x18004f115  mov     [rsp-28h+arg_8], rsi
0x18004f11a  mov     [rsp-28h+arg_10], r8
0x18004f11f  push    rbp
0x18004f120  push    rdi
0x18004f121  push    r12
0x18004f123  push    r13
0x18004f125  push    r14
0x18004f127  mov     rbp, rsp
0x18004f12a  sub     rsp, 60h
0x18004f12e  xor     r14d, r14d
0x18004f131  mov     rsi, r9
0x18004f134  mov     [rbp+pDacl], r14
0x18004f138  mov     rdi, r8
0x18004f13b  mov     [rbp+pOwner], r14
0x18004f13f  mov     r13, rdx
0x18004f142  mov     [rbp+bOwnerDefaulted], r14d
0x18004f146  mov     r12, rcx
0x18004f149  mov     [rbp+bDaclPresent], r14d
0x18004f14d  mov     [rbp+hMem], r14
0x18004f151  mov     [rbp+var_18], r14
0x18004f155  mov     [rbp+pcCountOfExplicitEntries], r14d
0x18004f159  mov     [rbp+var_34], r14d
0x18004f15d  mov     [rbp+pListOfExplicitEntries], r14
0x18004f161  mov     [rbp+var_8], r14
0x18004f165  call    AccProvpLoadMartaFunctions
0x18004f16a  mov     ebx, eax
0x18004f16c  test    eax, eax
0x18004f16e  jnz     loc_18004F32D
0x18004f174  test    r12, r12
0x18004f177  jz      short loc_18004F1C7
0x18004f179  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x18004f17d  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004f181  lea     rdx, [rbp+pOwner]; pOwner
0x18004f185  call    cs:__imp_GetSecurityDescriptorOwner
0x18004f18c  nop     dword ptr [rax+rax+00h]
0x18004f191  cmp     eax, 1
0x18004f194  jnz     short loc_18004F1B1
0x18004f196  mov     rax, cs:qword_1800B1048
0x18004f19d  lea     r8, [rbp+hMem]
0x18004f1a1  mov     rdx, [rbp+pOwner]
0x18004f1a5  xor     ecx, ecx
0x18004f1a7  mov     rax, [rax]
0x18004f1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1af  jmp     short loc_18004F1BD
0x18004f1b1  call    cs:__imp_GetLastError
0x18004f1b8  nop     dword ptr [rax+rax+00h]
0x18004f1bd  mov     ebx, eax
0x18004f1bf  test    eax, eax
0x18004f1c1  jnz     loc_18004F351
0x18004f1c7  test    r13, r13
0x18004f1ca  jz      short loc_18004F219
0x18004f1cc  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x18004f1d0  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18004f1d4  lea     rdx, [rbp+pOwner]; pGroup
0x18004f1d8  call    cs:__imp_GetSecurityDescriptorGroup
0x18004f1df  nop     dword ptr [rax+rax+00h]
0x18004f1e4  test    eax, eax
0x18004f1e6  jz      short loc_18004F203
0x18004f1e8  mov     rax, cs:qword_1800B1048
0x18004f1ef  lea     r8, [rbp+var_18]
0x18004f1f3  mov     rdx, [rbp+pOwner]
0x18004f1f7  xor     ecx, ecx
0x18004f1f9  mov     rax, [rax]
0x18004f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f201  jmp     short loc_18004F20F
0x18004f203  call    cs:__imp_GetLastError
0x18004f20a  nop     dword ptr [rax+rax+00h]
0x18004f20f  mov     ebx, eax
0x18004f211  test    eax, eax
0x18004f213  jnz     loc_18004F351
0x18004f219  test    rdi, rdi
0x18004f21c  jz      short loc_18004F27A
0x18004f21e  test    rsi, rsi
0x18004f221  jz      loc_18004F34C
0x18004f227  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x18004f22b  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18004f22f  lea     r8, [rbp+pDacl]; pDacl
0x18004f233  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004f237  call    cs:__imp_GetSecurityDescriptorDacl
0x18004f23e  nop     dword ptr [rax+rax+00h]
0x18004f243  cmp     eax, 1
0x18004f246  jnz     short loc_18004F262
0x18004f248  mov     rcx, [rbp+pDacl]; pacl
0x18004f24c  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004f250  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18004f254  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004f25b  nop     dword ptr [rax+rax+00h]
0x18004f260  jmp     short loc_18004F26E
0x18004f262  call    cs:__imp_GetLastError
0x18004f269  nop     dword ptr [rax+rax+00h]
0x18004f26e  mov     ebx, eax
0x18004f270  test    eax, eax
0x18004f272  jnz     loc_18004F351
0x18004f278  jmp     short loc_18004F283
0x18004f27a  test    rsi, rsi
0x18004f27d  jnz     loc_18004F34C
0x18004f283  mov     r14, [rbp+pcCountOfAuditEntries]
0x18004f287  mov     rdi, [rbp+ppListOfAuditEntries]
0x18004f28b  test    r14, r14
0x18004f28e  jz      loc_18004F347
0x18004f294  test    rdi, rdi
0x18004f297  jz      loc_18004F34C
0x18004f29d  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x18004f2a1  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18004f2a5  lea     r8, [rbp+pDacl]; pSacl
0x18004f2a9  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18004f2ad  call    cs:__imp_GetSecurityDescriptorSacl
0x18004f2b4  nop     dword ptr [rax+rax+00h]
0x18004f2b9  cmp     eax, 1
0x18004f2bc  jnz     short loc_18004F2D8
0x18004f2be  mov     rcx, [rbp+pDacl]; pacl
0x18004f2c2  lea     r8, [rbp+var_8]; pListOfExplicitEntries
0x18004f2c6  lea     rdx, [rbp+var_34]; pcCountOfExplicitEntries
0x18004f2ca  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004f2d1  nop     dword ptr [rax+rax+00h]
0x18004f2d6  jmp     short loc_18004F2E4
0x18004f2d8  call    cs:__imp_GetLastError
0x18004f2df  nop     dword ptr [rax+rax+00h]
0x18004f2e4  mov     ebx, eax
0x18004f2e6  test    eax, eax
0x18004f2e8  jnz     short loc_18004F351
0x18004f2ea  test    r12, r12
0x18004f2ed  jz      short loc_18004F2F7
0x18004f2ef  mov     rax, [rbp+hMem]
0x18004f2f3  mov     [r12], rax
0x18004f2f7  test    r13, r13
0x18004f2fa  jz      short loc_18004F304
0x18004f2fc  mov     rax, [rbp+var_18]
0x18004f300  mov     [r13+0], rax
0x18004f304  test    rsi, rsi
0x18004f307  jz      short loc_18004F319
0x18004f309  mov     rax, [rbp+pListOfExplicitEntries]
0x18004f30d  mov     rcx, [rbp+arg_10]
0x18004f311  mov     [rsi], rax
0x18004f314  mov     eax, [rbp+pcCountOfExplicitEntries]
0x18004f317  mov     [rcx], eax
0x18004f319  test    rdi, rdi
0x18004f31c  jz      short loc_18004F32B
0x18004f31e  mov     rax, [rbp+var_8]
0x18004f322  mov     [rdi], rax
0x18004f325  mov     eax, [rbp+var_34]
0x18004f328  mov     [r14], eax
0x18004f32b  mov     eax, ebx
0x18004f32d  lea     r11, [rsp+60h+var_s0]
0x18004f332  mov     rbx, [r11+30h]
0x18004f336  mov     rsi, [r11+38h]
0x18004f33a  mov     rsp, r11
0x18004f33d  pop     r14
0x18004f33f  pop     r13
0x18004f341  pop     r12
0x18004f343  pop     rdi
0x18004f344  pop     rbp
0x18004f345  retn
0x18004f347  test    rdi, rdi
0x18004f34a  jz      short loc_18004F2EA
0x18004f34c  mov     ebx, 57h ; 'W'
0x18004f351  mov     rcx, [rbp+hMem]; hMem
0x18004f355  test    rcx, rcx
0x18004f358  jz      short loc_18004F366
0x18004f35a  call    cs:__imp_LocalFree
0x18004f361  nop     dword ptr [rax+rax+00h]
0x18004f366  mov     rcx, [rbp+var_18]; hMem
0x18004f36a  test    rcx, rcx
0x18004f36d  jz      short loc_18004F37B
0x18004f36f  call    cs:__imp_LocalFree
0x18004f376  nop     dword ptr [rax+rax+00h]
0x18004f37b  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x18004f37f  test    rcx, rcx
0x18004f382  jz      short loc_18004F390
0x18004f384  call    cs:__imp_LocalFree
0x18004f38b  nop     dword ptr [rax+rax+00h]
0x18004f390  mov     rcx, [rbp+var_8]; hMem
0x18004f394  test    rcx, rcx
0x18004f397  jz      short loc_18004F32B
0x18004f399  call    cs:__imp_LocalFree
0x18004f3a0  nop     dword ptr [rax+rax+00h]
0x18004f3a5  jmp     short loc_18004F32B
```
