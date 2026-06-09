# LookupSecurityDescriptorPartsA

- ea: `0x1800491f0`
- end: `0x180049490`
- name: `LookupSecurityDescriptorPartsA`
- size: `672`
- prototype: `DWORD __stdcall(PTRUSTEE_A *ppOwner, PTRUSTEE_A *ppGroup, PULONG pcCountOfAccessEntries, PEXPLICIT_ACCESS_A *ppListOfAccessEntries, PULONG pcCountOfAuditEntries, PEXPLICIT_ACCESS_A *ppListOfAuditEntries, PSECURITY_DESCRIPTOR pSD)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a420`
- `0x1800491f0`
- `0x18004ccf0`
- `0x180066010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180049272`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180049272`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049362`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049362`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800493c5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800493c5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800492e3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800492e3`
- `KERNEL32!LocalFree` at `0x1800492b7`
- `KERNEL32!LocalFree` at `0x180049327`
- `KERNEL32!LocalFree` at `0x18004945c`
- `KERNEL32!LocalFree` at `0x18004946a`
- `KERNEL32!LocalFree` at `0x180049479`
- `KERNEL32!LocalFree` at `0x180049488`
- `KERNEL32!LocalFree` at `0x1800492b7`
- `KERNEL32!LocalFree` at `0x180049327`
- `KERNEL32!LocalFree` at `0x18004945c`
- `KERNEL32!LocalFree` at `0x18004946a`
- `KERNEL32!LocalFree` at `0x180049479`
- `KERNEL32!LocalFree` at `0x180049488`
- `KERNEL32!GetLastError` at `0x1800492c3`
- `KERNEL32!GetLastError` at `0x180049333`
- `KERNEL32!GetLastError` at `0x180049381`
- `KERNEL32!GetLastError` at `0x1800493e4`
- `KERNEL32!GetLastError` at `0x1800492c3`
- `KERNEL32!GetLastError` at `0x180049333`
- `KERNEL32!GetLastError` at `0x180049381`
- `KERNEL32!GetLastError` at `0x1800493e4`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180049379`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800493dc`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180049379`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800493dc`

## pseudocode

```c
DWORD __stdcall LookupSecurityDescriptorPartsA(
        PTRUSTEE_A *ppOwner,
        PTRUSTEE_A *ppGroup,
        PULONG pcCountOfAccessEntries,
        PEXPLICIT_ACCESS_A *ppListOfAccessEntries,
        PULONG pcCountOfAuditEntries,
        PEXPLICIT_ACCESS_A *ppListOfAuditEntries,
        PSECURITY_DESCRIPTOR pSD)
{
  struct _TRUSTEE_A *v8; // rsi
  struct _TRUSTEE_A *v9; // r14
  DWORD result; // eax
  unsigned int LastError; // ebx
  DWORD ExplicitEntriesFromAclW; // eax
  DWORD v15; // eax
  BOOL bOwnerDefaulted; // [rsp+20h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-48h] BYREF
  BOOL bDaclPresent; // [rsp+30h] [rbp-40h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+34h] [rbp-3Ch] BYREF
  ULONG v20; // [rsp+38h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+40h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-28h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-20h] BYREF
  PEXPLICIT_ACCESS_W v24; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL v25; // [rsp+60h] [rbp-10h] BYREF
  struct _TRUSTEE_A *v26; // [rsp+68h] [rbp-8h] BYREF

  pDacl = 0;
  v8 = 0;
  pOwner = 0;
  v9 = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  v25 = 0;
  v26 = 0;
  pcCountOfExplicitEntries = 0;
  v20 = 0;
  pListOfExplicitEntries = 0;
  v24 = 0;
  result = AccProvpLoadMartaFunctions();
  LastError = result;
  if ( !result )
  {
    if ( !ppOwner )
      goto LABEL_8;
    if ( GetSecurityDescriptorOwner(pSD, &pOwner, &bOwnerDefaulted) )
    {
      hMem = 0;
      LastError = (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800A2048)(0, pOwner, &hMem);
      if ( LastError )
      {
LABEL_44:
        if ( pListOfExplicitEntries )
          LocalFree(pListOfExplicitEntries);
        if ( v24 )
          LocalFree(v24);
        return LastError;
      }
      LastError = ConvertTrusteeWToTrusteeA((struct _TRUSTEE_W *)hMem, (struct _TRUSTEE_A **)&v25);
      LocalFree(hMem);
      v8 = (struct _TRUSTEE_A *)v25;
    }
    else
    {
      LastError = GetLastError();
    }
    if ( !LastError )
    {
LABEL_8:
      if ( !ppGroup )
        goto LABEL_14;
      if ( GetSecurityDescriptorGroup(pSD, &pOwner, &bOwnerDefaulted) )
      {
        hMem = 0;
        LastError = (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800A2048)(0, pOwner, &hMem);
        if ( LastError )
          goto LABEL_40;
        LastError = ConvertTrusteeWToTrusteeA((struct _TRUSTEE_W *)hMem, &v26);
        LocalFree(hMem);
        v9 = v26;
      }
      else
      {
        LastError = GetLastError();
      }
      if ( !LastError )
      {
LABEL_14:
        if ( pcCountOfAccessEntries )
        {
          if ( ppListOfAccessEntries )
          {
            if ( GetSecurityDescriptorDacl(pSD, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
              ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(
                                          pDacl,
                                          &pcCountOfExplicitEntries,
                                          &pListOfExplicitEntries);
            else
              ExplicitEntriesFromAclW = GetLastError();
            LastError = ExplicitEntriesFromAclW;
            if ( ExplicitEntriesFromAclW )
              goto LABEL_40;
            goto LABEL_22;
          }
        }
        else if ( !ppListOfAccessEntries )
        {
LABEL_22:
          if ( pcCountOfAuditEntries )
          {
            if ( ppListOfAuditEntries )
            {
              if ( GetSecurityDescriptorSacl(pSD, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
                v15 = GetExplicitEntriesFromAclW(pDacl, &v20, &v24);
              else
                v15 = GetLastError();
              LastError = v15;
              if ( !v15 )
                goto LABEL_28;
              goto LABEL_40;
            }
          }
          else if ( !ppListOfAuditEntries )
          {
LABEL_28:
            if ( ppOwner )
              *ppOwner = v8;
            if ( ppGroup )
              *ppGroup = v9;
            if ( ppListOfAccessEntries )
            {
              *ppListOfAccessEntries = (PEXPLICIT_ACCESS_A)pListOfExplicitEntries;
              *pcCountOfAccessEntries = pcCountOfExplicitEntries;
            }
            if ( ppListOfAuditEntries )
            {
              *ppListOfAuditEntries = (PEXPLICIT_ACCESS_A)v24;
              *pcCountOfAuditEntries = v20;
            }
            return LastError;
          }
        }
        LastError = 87;
      }
    }
LABEL_40:
    if ( v8 )
      LocalFree(v8);
    if ( v9 )
      LocalFree(v9);
    goto LABEL_44;
  }
  return result;
}

```

## disassembly

```asm
0x1800491f0  mov     rax, rsp
0x1800491f3  mov     [rax+20h], rbx
0x1800491f7  mov     [rax+18h], r8
0x1800491fb  mov     [rax+10h], rdx
0x1800491ff  mov     [rax+8], rcx
0x180049203  push    rbp
0x180049204  push    rsi
0x180049205  push    rdi
0x180049206  push    r12
0x180049208  push    r13
0x18004920a  push    r14
0x18004920c  push    r15
0x18004920e  mov     rbp, rsp
0x180049211  sub     rsp, 70h
0x180049215  xor     r13d, r13d
0x180049218  mov     r12, r9
0x18004921b  mov     [rbp+pDacl], r13
0x18004921f  mov     esi, r13d
0x180049222  mov     [rbp+pOwner], r13
0x180049226  mov     r14d, r13d
0x180049229  mov     [rbp+bOwnerDefaulted], r13d
0x18004922d  mov     rdi, rdx
0x180049230  mov     [rbp+bDaclPresent], r13d
0x180049234  mov     r15, rcx
0x180049237  mov     [rbp+var_10], r13
0x18004923b  mov     [rbp+var_8], r13
0x18004923f  mov     [rbp+pcCountOfExplicitEntries], r13d
0x180049243  mov     [rbp+var_38], r13d
0x180049247  mov     [rbp+pListOfExplicitEntries], r13
0x18004924b  mov     [rbp+var_18], r13
0x18004924f  call    AccProvpLoadMartaFunctions
0x180049254  mov     ebx, eax
0x180049256  test    eax, eax
0x180049258  jnz     loc_180049432
0x18004925e  mov     r13, [rbp+pSD]
0x180049262  test    r15, r15
0x180049265  jz      short loc_1800492D3
0x180049267  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004926b  mov     rcx, r13; pSecurityDescriptor
0x18004926e  lea     rdx, [rbp+pOwner]; pOwner
0x180049272  call    cs:__imp_GetSecurityDescriptorOwner
0x180049278  cmp     eax, 1
0x18004927b  jnz     short loc_1800492C3
0x18004927d  mov     rax, cs:qword_1800A2048
0x180049284  lea     r8, [rbp+hMem]
0x180049288  mov     rdx, [rbp+pOwner]
0x18004928c  xor     ecx, ecx
0x18004928e  mov     [rbp+hMem], r14
0x180049292  mov     rax, [rax]
0x180049295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004929a  mov     ebx, eax
0x18004929c  test    eax, eax
0x18004929e  jnz     loc_180049470
0x1800492a4  mov     rcx, [rbp+hMem]; struct _TRUSTEE_W *
0x1800492a8  lea     rdx, [rbp+var_10]; struct _TRUSTEE_A **
0x1800492ac  call    ?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z; ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)
0x1800492b1  mov     rcx, [rbp+hMem]; hMem
0x1800492b5  mov     ebx, eax
0x1800492b7  call    cs:__imp_LocalFree
0x1800492bd  mov     rsi, [rbp+var_10]
0x1800492c1  jmp     short loc_1800492CB
0x1800492c3  call    cs:__imp_GetLastError
0x1800492c9  mov     ebx, eax
0x1800492cb  test    ebx, ebx
0x1800492cd  jnz     loc_180049454
0x1800492d3  test    rdi, rdi
0x1800492d6  jz      short loc_180049343
0x1800492d8  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800492dc  mov     rcx, r13; pSecurityDescriptor
0x1800492df  lea     rdx, [rbp+pOwner]; pGroup
0x1800492e3  call    cs:__imp_GetSecurityDescriptorGroup
0x1800492e9  test    eax, eax
0x1800492eb  jz      short loc_180049333
0x1800492ed  mov     rax, cs:qword_1800A2048
0x1800492f4  lea     r8, [rbp+hMem]
0x1800492f8  mov     rdx, [rbp+pOwner]
0x1800492fc  xor     ecx, ecx
0x1800492fe  mov     [rbp+hMem], r14
0x180049302  mov     rax, [rax]
0x180049305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004930a  mov     ebx, eax
0x18004930c  test    eax, eax
0x18004930e  jnz     loc_180049454
0x180049314  mov     rcx, [rbp+hMem]; struct _TRUSTEE_W *
0x180049318  lea     rdx, [rbp+var_8]; struct _TRUSTEE_A **
0x18004931c  call    ?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z; ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)
0x180049321  mov     rcx, [rbp+hMem]; hMem
0x180049325  mov     ebx, eax
0x180049327  call    cs:__imp_LocalFree
0x18004932d  mov     r14, [rbp+var_8]
0x180049331  jmp     short loc_18004933B
0x180049333  call    cs:__imp_GetLastError
0x180049339  mov     ebx, eax
0x18004933b  test    ebx, ebx
0x18004933d  jnz     loc_180049454
0x180049343  cmp     [rbp+arg_10], 0
0x180049348  jz      short loc_180049393
0x18004934a  test    r12, r12
0x18004934d  jz      loc_18004944F
0x180049353  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x180049357  mov     rcx, r13; pSecurityDescriptor
0x18004935a  lea     r8, [rbp+pDacl]; pDacl
0x18004935e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180049362  call    cs:__imp_GetSecurityDescriptorDacl
0x180049368  cmp     eax, 1
0x18004936b  jnz     short loc_180049381
0x18004936d  mov     rcx, [rbp+pDacl]; pacl
0x180049371  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180049375  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x180049379  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004937f  jmp     short loc_180049387
0x180049381  call    cs:__imp_GetLastError
0x180049387  mov     ebx, eax
0x180049389  test    eax, eax
0x18004938b  jnz     loc_180049454
0x180049391  jmp     short loc_18004939C
0x180049393  test    r12, r12
0x180049396  jnz     loc_18004944F
0x18004939c  mov     r15, [rbp+pcCountOfAuditEntries]
0x1800493a0  mov     rdi, [rbp+ppListOfAuditEntries]
0x1800493a4  test    r15, r15
0x1800493a7  jz      loc_18004944A
0x1800493ad  test    rdi, rdi
0x1800493b0  jz      loc_18004944F
0x1800493b6  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1800493ba  mov     rcx, r13; pSecurityDescriptor
0x1800493bd  lea     r8, [rbp+pDacl]; pSacl
0x1800493c1  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x1800493c5  call    cs:__imp_GetSecurityDescriptorSacl
0x1800493cb  cmp     eax, 1
0x1800493ce  jnz     short loc_1800493E4
0x1800493d0  mov     rcx, [rbp+pDacl]; pacl
0x1800493d4  lea     r8, [rbp+var_18]; pListOfExplicitEntries
0x1800493d8  lea     rdx, [rbp+var_38]; pcCountOfExplicitEntries
0x1800493dc  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800493e2  jmp     short loc_1800493EA
0x1800493e4  call    cs:__imp_GetLastError
0x1800493ea  mov     ebx, eax
0x1800493ec  test    eax, eax
0x1800493ee  jnz     short loc_180049454
0x1800493f0  mov     rax, [rbp+arg_0]
0x1800493f4  test    rax, rax
0x1800493f7  jz      short loc_1800493FC
0x1800493f9  mov     [rax], rsi
0x1800493fc  mov     rax, [rbp+arg_8]
0x180049400  test    rax, rax
0x180049403  jz      short loc_180049408
0x180049405  mov     [rax], r14
0x180049408  test    r12, r12
0x18004940b  jz      short loc_18004941E
0x18004940d  mov     rax, [rbp+pListOfExplicitEntries]
0x180049411  mov     rcx, [rbp+arg_10]
0x180049415  mov     [r12], rax
0x180049419  mov     eax, [rbp+pcCountOfExplicitEntries]
0x18004941c  mov     [rcx], eax
0x18004941e  test    rdi, rdi
0x180049421  jz      short loc_180049430
0x180049423  mov     rax, [rbp+var_18]
0x180049427  mov     [rdi], rax
0x18004942a  mov     eax, [rbp+var_38]
0x18004942d  mov     [r15], eax
0x180049430  mov     eax, ebx
0x180049432  mov     rbx, [rsp+70h+arg_18]
0x18004943a  add     rsp, 70h
0x18004943e  pop     r15
0x180049440  pop     r14
0x180049442  pop     r13
0x180049444  pop     r12
0x180049446  pop     rdi
0x180049447  pop     rsi
0x180049448  pop     rbp
0x180049449  retn
0x18004944a  test    rdi, rdi
0x18004944d  jz      short loc_1800493F0
0x18004944f  mov     ebx, 57h ; 'W'
0x180049454  test    rsi, rsi
0x180049457  jz      short loc_180049462
0x180049459  mov     rcx, rsi; hMem
0x18004945c  call    cs:__imp_LocalFree
0x180049462  test    r14, r14
0x180049465  jz      short loc_180049470
0x180049467  mov     rcx, r14; hMem
0x18004946a  call    cs:__imp_LocalFree
0x180049470  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x180049474  test    rcx, rcx
0x180049477  jz      short loc_18004947F
0x180049479  call    cs:__imp_LocalFree
0x18004947f  mov     rcx, [rbp+var_18]; hMem
0x180049483  test    rcx, rcx
0x180049486  jz      short loc_180049430
0x180049488  call    cs:__imp_LocalFree
0x18004948e  jmp     short loc_180049430
```
