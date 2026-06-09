# LookupSecurityDescriptorPartsW

- ea: `0x1800494a0`
- end: `0x1800496e2`
- name: `LookupSecurityDescriptorPartsW`
- size: `578`
- prototype: `DWORD __stdcall(PTRUSTEE_W *ppOwner, PTRUSTEE_W *ppGroup, PULONG pcCountOfAccessEntries, PEXPLICIT_ACCESS_W *ppListOfAccessEntries, PULONG pcCountOfAuditEntries, PEXPLICIT_ACCESS_W *ppListOfAuditEntries, PSECURITY_DESCRIPTOR pSD)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a420`
- `0x1800494a0`
- `0x180066010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180049515`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180049515`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800495af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800495af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180049613`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180049613`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004955c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004955c`
- `KERNEL32!LocalFree` at `0x1800496ad`
- `KERNEL32!LocalFree` at `0x1800496bc`
- `KERNEL32!LocalFree` at `0x1800496cb`
- `KERNEL32!LocalFree` at `0x1800496da`
- `KERNEL32!LocalFree` at `0x1800496ad`
- `KERNEL32!LocalFree` at `0x1800496bc`
- `KERNEL32!LocalFree` at `0x1800496cb`
- `KERNEL32!LocalFree` at `0x1800496da`
- `KERNEL32!GetLastError` at `0x18004953b`
- `KERNEL32!GetLastError` at `0x180049581`
- `KERNEL32!GetLastError` at `0x1800495ce`
- `KERNEL32!GetLastError` at `0x180049632`
- `KERNEL32!GetLastError` at `0x18004953b`
- `KERNEL32!GetLastError` at `0x180049581`
- `KERNEL32!GetLastError` at `0x1800495ce`
- `KERNEL32!GetLastError` at `0x180049632`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800495c6`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004962a`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800495c6`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004962a`

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
          ? (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800A2048)(0, pOwner, &hMem)
          : GetLastError();
      v12 = v13;
      if ( v13 )
        goto LABEL_38;
    }
    if ( ppGroup )
    {
      v14 = GetSecurityDescriptorGroup(pSD, &pOwner, &bOwnerDefaulted)
          ? (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800A2048)(0, pOwner, &v24)
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
0x1800494a0  mov     [rsp-28h+arg_0], rbx
0x1800494a5  mov     [rsp-28h+arg_8], rsi
0x1800494aa  mov     [rsp-28h+arg_10], r8
0x1800494af  push    rbp
0x1800494b0  push    rdi
0x1800494b1  push    r12
0x1800494b3  push    r13
0x1800494b5  push    r14
0x1800494b7  mov     rbp, rsp
0x1800494ba  sub     rsp, 60h
0x1800494be  xor     r14d, r14d
0x1800494c1  mov     rsi, r9
0x1800494c4  mov     [rbp+pDacl], r14
0x1800494c8  mov     rdi, r8
0x1800494cb  mov     [rbp+pOwner], r14
0x1800494cf  mov     r13, rdx
0x1800494d2  mov     [rbp+bOwnerDefaulted], r14d
0x1800494d6  mov     r12, rcx
0x1800494d9  mov     [rbp+bDaclPresent], r14d
0x1800494dd  mov     [rbp+hMem], r14
0x1800494e1  mov     [rbp+var_18], r14
0x1800494e5  mov     [rbp+pcCountOfExplicitEntries], r14d
0x1800494e9  mov     [rbp+var_34], r14d
0x1800494ed  mov     [rbp+pListOfExplicitEntries], r14
0x1800494f1  mov     [rbp+var_8], r14
0x1800494f5  call    AccProvpLoadMartaFunctions
0x1800494fa  mov     ebx, eax
0x1800494fc  test    eax, eax
0x1800494fe  jnz     loc_180049681
0x180049504  test    r12, r12
0x180049507  jz      short loc_18004954B
0x180049509  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x18004950d  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180049511  lea     rdx, [rbp+pOwner]; pOwner
0x180049515  call    cs:__imp_GetSecurityDescriptorOwner
0x18004951b  cmp     eax, 1
0x18004951e  jnz     short loc_18004953B
0x180049520  mov     rax, cs:qword_1800A2048
0x180049527  lea     r8, [rbp+hMem]
0x18004952b  mov     rdx, [rbp+pOwner]
0x18004952f  xor     ecx, ecx
0x180049531  mov     rax, [rax]
0x180049534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049539  jmp     short loc_180049541
0x18004953b  call    cs:__imp_GetLastError
0x180049541  mov     ebx, eax
0x180049543  test    eax, eax
0x180049545  jnz     loc_1800496A4
0x18004954b  test    r13, r13
0x18004954e  jz      short loc_180049591
0x180049550  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x180049554  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180049558  lea     rdx, [rbp+pOwner]; pGroup
0x18004955c  call    cs:__imp_GetSecurityDescriptorGroup
0x180049562  test    eax, eax
0x180049564  jz      short loc_180049581
0x180049566  mov     rax, cs:qword_1800A2048
0x18004956d  lea     r8, [rbp+var_18]
0x180049571  mov     rdx, [rbp+pOwner]
0x180049575  xor     ecx, ecx
0x180049577  mov     rax, [rax]
0x18004957a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004957f  jmp     short loc_180049587
0x180049581  call    cs:__imp_GetLastError
0x180049587  mov     ebx, eax
0x180049589  test    eax, eax
0x18004958b  jnz     loc_1800496A4
0x180049591  test    rdi, rdi
0x180049594  jz      short loc_1800495E0
0x180049596  test    rsi, rsi
0x180049599  jz      loc_18004969F
0x18004959f  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x1800495a3  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800495a7  lea     r8, [rbp+pDacl]; pDacl
0x1800495ab  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800495af  call    cs:__imp_GetSecurityDescriptorDacl
0x1800495b5  cmp     eax, 1
0x1800495b8  jnz     short loc_1800495CE
0x1800495ba  mov     rcx, [rbp+pDacl]; pacl
0x1800495be  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800495c2  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x1800495c6  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800495cc  jmp     short loc_1800495D4
0x1800495ce  call    cs:__imp_GetLastError
0x1800495d4  mov     ebx, eax
0x1800495d6  test    eax, eax
0x1800495d8  jnz     loc_1800496A4
0x1800495de  jmp     short loc_1800495E9
0x1800495e0  test    rsi, rsi
0x1800495e3  jnz     loc_18004969F
0x1800495e9  mov     r14, [rbp+pcCountOfAuditEntries]
0x1800495ed  mov     rdi, [rbp+ppListOfAuditEntries]
0x1800495f1  test    r14, r14
0x1800495f4  jz      loc_18004969A
0x1800495fa  test    rdi, rdi
0x1800495fd  jz      loc_18004969F
0x180049603  mov     rcx, [rbp+pSD]; pSecurityDescriptor
0x180049607  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18004960b  lea     r8, [rbp+pDacl]; pSacl
0x18004960f  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180049613  call    cs:__imp_GetSecurityDescriptorSacl
0x180049619  cmp     eax, 1
0x18004961c  jnz     short loc_180049632
0x18004961e  mov     rcx, [rbp+pDacl]; pacl
0x180049622  lea     r8, [rbp+var_8]; pListOfExplicitEntries
0x180049626  lea     rdx, [rbp+var_34]; pcCountOfExplicitEntries
0x18004962a  call    cs:__imp_GetExplicitEntriesFromAclW
0x180049630  jmp     short loc_180049638
0x180049632  call    cs:__imp_GetLastError
0x180049638  mov     ebx, eax
0x18004963a  test    eax, eax
0x18004963c  jnz     short loc_1800496A4
0x18004963e  test    r12, r12
0x180049641  jz      short loc_18004964B
0x180049643  mov     rax, [rbp+hMem]
0x180049647  mov     [r12], rax
0x18004964b  test    r13, r13
0x18004964e  jz      short loc_180049658
0x180049650  mov     rax, [rbp+var_18]
0x180049654  mov     [r13+0], rax
0x180049658  test    rsi, rsi
0x18004965b  jz      short loc_18004966D
0x18004965d  mov     rax, [rbp+pListOfExplicitEntries]
0x180049661  mov     rcx, [rbp+arg_10]
0x180049665  mov     [rsi], rax
0x180049668  mov     eax, [rbp+pcCountOfExplicitEntries]
0x18004966b  mov     [rcx], eax
0x18004966d  test    rdi, rdi
0x180049670  jz      short loc_18004967F
0x180049672  mov     rax, [rbp+var_8]
0x180049676  mov     [rdi], rax
0x180049679  mov     eax, [rbp+var_34]
0x18004967c  mov     [r14], eax
0x18004967f  mov     eax, ebx
0x180049681  lea     r11, [rsp+60h+var_s0]
0x180049686  mov     rbx, [r11+30h]
0x18004968a  mov     rsi, [r11+38h]
0x18004968e  mov     rsp, r11
0x180049691  pop     r14
0x180049693  pop     r13
0x180049695  pop     r12
0x180049697  pop     rdi
0x180049698  pop     rbp
0x180049699  retn
0x18004969a  test    rdi, rdi
0x18004969d  jz      short loc_18004963E
0x18004969f  mov     ebx, 57h ; 'W'
0x1800496a4  mov     rcx, [rbp+hMem]; hMem
0x1800496a8  test    rcx, rcx
0x1800496ab  jz      short loc_1800496B3
0x1800496ad  call    cs:__imp_LocalFree
0x1800496b3  mov     rcx, [rbp+var_18]; hMem
0x1800496b7  test    rcx, rcx
0x1800496ba  jz      short loc_1800496C2
0x1800496bc  call    cs:__imp_LocalFree
0x1800496c2  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x1800496c6  test    rcx, rcx
0x1800496c9  jz      short loc_1800496D1
0x1800496cb  call    cs:__imp_LocalFree
0x1800496d1  mov     rcx, [rbp+var_8]; hMem
0x1800496d5  test    rcx, rcx
0x1800496d8  jz      short loc_18004967F
0x1800496da  call    cs:__imp_LocalFree
0x1800496e0  jmp     short loc_18004967F
```
