# LookupSecurityDescriptorPartsA

- ea: `0x18004ee00`
- end: `0x18004f101`
- name: `LookupSecurityDescriptorPartsA`
- size: `769`
- prototype: `DWORD __stdcall(PTRUSTEE_A *ppOwner, PTRUSTEE_A *ppGroup, PULONG pcCountOfAccessEntries, PEXPLICIT_ACCESS_A *ppListOfAccessEntries, PULONG pcCountOfAuditEntries, PEXPLICIT_ACCESS_A *ppListOfAuditEntries, PSECURITY_DESCRIPTOR pSD)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002dcc8`
- `0x18004ee00`
- `0x180052cac`
- `0x180074010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004ee82`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004ee82`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004ef96`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004ef96`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004f00b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004f00b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004ef05`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004ef05`
- `KERNEL32!LocalFree` at `0x18004eecd`
- `KERNEL32!LocalFree` at `0x18004ef4f`
- `KERNEL32!LocalFree` at `0x18004f0b5`
- `KERNEL32!LocalFree` at `0x18004f0c9`
- `KERNEL32!LocalFree` at `0x18004f0de`
- `KERNEL32!LocalFree` at `0x18004f0f3`
- `KERNEL32!LocalFree` at `0x18004eecd`
- `KERNEL32!LocalFree` at `0x18004ef4f`
- `KERNEL32!LocalFree` at `0x18004f0b5`
- `KERNEL32!LocalFree` at `0x18004f0c9`
- `KERNEL32!LocalFree` at `0x18004f0de`
- `KERNEL32!LocalFree` at `0x18004f0f3`
- `KERNEL32!GetLastError` at `0x18004eedf`
- `KERNEL32!GetLastError` at `0x18004ef61`
- `KERNEL32!GetLastError` at `0x18004efc1`
- `KERNEL32!GetLastError` at `0x18004f036`
- `KERNEL32!GetLastError` at `0x18004eedf`
- `KERNEL32!GetLastError` at `0x18004ef61`
- `KERNEL32!GetLastError` at `0x18004efc1`
- `KERNEL32!GetLastError` at `0x18004f036`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004efb3`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f028`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004efb3`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004f028`

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
      LastError = (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800B1048)(0, pOwner, &hMem);
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
        LastError = (*(__int64 (__fastcall **)(_QWORD, PSID, HLOCAL *))qword_1800B1048)(0, pOwner, &hMem);
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
0x18004ee00  mov     rax, rsp
0x18004ee03  mov     [rax+20h], rbx
0x18004ee07  mov     [rax+18h], r8
0x18004ee0b  mov     [rax+10h], rdx
0x18004ee0f  mov     [rax+8], rcx
0x18004ee13  push    rbp
0x18004ee14  push    rsi
0x18004ee15  push    rdi
0x18004ee16  push    r12
0x18004ee18  push    r13
0x18004ee1a  push    r14
0x18004ee1c  push    r15
0x18004ee1e  mov     rbp, rsp
0x18004ee21  sub     rsp, 70h
0x18004ee25  xor     r13d, r13d
0x18004ee28  mov     r12, r9
0x18004ee2b  mov     [rbp+pDacl], r13
0x18004ee2f  mov     esi, r13d
0x18004ee32  mov     [rbp+pOwner], r13
0x18004ee36  mov     r14d, r13d
0x18004ee39  mov     [rbp+bOwnerDefaulted], r13d
0x18004ee3d  mov     rdi, rdx
0x18004ee40  mov     [rbp+bDaclPresent], r13d
0x18004ee44  mov     r15, rcx
0x18004ee47  mov     [rbp+var_10], r13
0x18004ee4b  mov     [rbp+var_8], r13
0x18004ee4f  mov     [rbp+pcCountOfExplicitEntries], r13d
0x18004ee53  mov     [rbp+var_38], r13d
0x18004ee57  mov     [rbp+pListOfExplicitEntries], r13
0x18004ee5b  mov     [rbp+var_18], r13
0x18004ee5f  call    AccProvpLoadMartaFunctions
0x18004ee64  mov     ebx, eax
0x18004ee66  test    eax, eax
0x18004ee68  jnz     loc_18004F08A
0x18004ee6e  mov     r13, [rbp+pSD]
0x18004ee72  test    r15, r15
0x18004ee75  jz      short loc_18004EEF5
0x18004ee77  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004ee7b  mov     rcx, r13; pSecurityDescriptor
0x18004ee7e  lea     rdx, [rbp+pOwner]; pOwner
0x18004ee82  call    cs:__imp_GetSecurityDescriptorOwner
0x18004ee89  nop     dword ptr [rax+rax+00h]
0x18004ee8e  cmp     eax, 1
0x18004ee91  jnz     short loc_18004EEDF
0x18004ee93  mov     rax, cs:qword_1800B1048
0x18004ee9a  lea     r8, [rbp+hMem]
0x18004ee9e  mov     rdx, [rbp+pOwner]
0x18004eea2  xor     ecx, ecx
0x18004eea4  mov     [rbp+hMem], r14
0x18004eea8  mov     rax, [rax]
0x18004eeab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeb0  mov     ebx, eax
0x18004eeb2  test    eax, eax
0x18004eeb4  jnz     loc_18004F0D5
0x18004eeba  mov     rcx, [rbp+hMem]; struct _TRUSTEE_W *
0x18004eebe  lea     rdx, [rbp+var_10]; struct _TRUSTEE_A **
0x18004eec2  call    ?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z; ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)
0x18004eec7  mov     rcx, [rbp+hMem]; hMem
0x18004eecb  mov     ebx, eax
0x18004eecd  call    cs:__imp_LocalFree
0x18004eed4  nop     dword ptr [rax+rax+00h]
0x18004eed9  mov     rsi, [rbp+var_10]
0x18004eedd  jmp     short loc_18004EEED
0x18004eedf  call    cs:__imp_GetLastError
0x18004eee6  nop     dword ptr [rax+rax+00h]
0x18004eeeb  mov     ebx, eax
0x18004eeed  test    ebx, ebx
0x18004eeef  jnz     loc_18004F0AD
0x18004eef5  test    rdi, rdi
0x18004eef8  jz      short loc_18004EF77
0x18004eefa  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18004eefe  mov     rcx, r13; pSecurityDescriptor
0x18004ef01  lea     rdx, [rbp+pOwner]; pGroup
0x18004ef05  call    cs:__imp_GetSecurityDescriptorGroup
0x18004ef0c  nop     dword ptr [rax+rax+00h]
0x18004ef11  test    eax, eax
0x18004ef13  jz      short loc_18004EF61
0x18004ef15  mov     rax, cs:qword_1800B1048
0x18004ef1c  lea     r8, [rbp+hMem]
0x18004ef20  mov     rdx, [rbp+pOwner]
0x18004ef24  xor     ecx, ecx
0x18004ef26  mov     [rbp+hMem], r14
0x18004ef2a  mov     rax, [rax]
0x18004ef2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef32  mov     ebx, eax
0x18004ef34  test    eax, eax
0x18004ef36  jnz     loc_18004F0AD
0x18004ef3c  mov     rcx, [rbp+hMem]; struct _TRUSTEE_W *
0x18004ef40  lea     rdx, [rbp+var_8]; struct _TRUSTEE_A **
0x18004ef44  call    ?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z; ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)
0x18004ef49  mov     rcx, [rbp+hMem]; hMem
0x18004ef4d  mov     ebx, eax
0x18004ef4f  call    cs:__imp_LocalFree
0x18004ef56  nop     dword ptr [rax+rax+00h]
0x18004ef5b  mov     r14, [rbp+var_8]
0x18004ef5f  jmp     short loc_18004EF6F
0x18004ef61  call    cs:__imp_GetLastError
0x18004ef68  nop     dword ptr [rax+rax+00h]
0x18004ef6d  mov     ebx, eax
0x18004ef6f  test    ebx, ebx
0x18004ef71  jnz     loc_18004F0AD
0x18004ef77  cmp     [rbp+arg_10], 0
0x18004ef7c  jz      short loc_18004EFD9
0x18004ef7e  test    r12, r12
0x18004ef81  jz      loc_18004F0A8
0x18004ef87  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18004ef8b  mov     rcx, r13; pSecurityDescriptor
0x18004ef8e  lea     r8, [rbp+pDacl]; pDacl
0x18004ef92  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004ef96  call    cs:__imp_GetSecurityDescriptorDacl
0x18004ef9d  nop     dword ptr [rax+rax+00h]
0x18004efa2  cmp     eax, 1
0x18004efa5  jnz     short loc_18004EFC1
0x18004efa7  mov     rcx, [rbp+pDacl]; pacl
0x18004efab  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004efaf  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18004efb3  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004efba  nop     dword ptr [rax+rax+00h]
0x18004efbf  jmp     short loc_18004EFCD
0x18004efc1  call    cs:__imp_GetLastError
0x18004efc8  nop     dword ptr [rax+rax+00h]
0x18004efcd  mov     ebx, eax
0x18004efcf  test    eax, eax
0x18004efd1  jnz     loc_18004F0AD
0x18004efd7  jmp     short loc_18004EFE2
0x18004efd9  test    r12, r12
0x18004efdc  jnz     loc_18004F0A8
0x18004efe2  mov     r15, [rbp+pcCountOfAuditEntries]
0x18004efe6  mov     rdi, [rbp+ppListOfAuditEntries]
0x18004efea  test    r15, r15
0x18004efed  jz      loc_18004F0A3
0x18004eff3  test    rdi, rdi
0x18004eff6  jz      loc_18004F0A8
0x18004effc  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18004f000  mov     rcx, r13; pSecurityDescriptor
0x18004f003  lea     r8, [rbp+pDacl]; pSacl
0x18004f007  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18004f00b  call    cs:__imp_GetSecurityDescriptorSacl
0x18004f012  nop     dword ptr [rax+rax+00h]
0x18004f017  cmp     eax, 1
0x18004f01a  jnz     short loc_18004F036
0x18004f01c  mov     rcx, [rbp+pDacl]; pacl
0x18004f020  lea     r8, [rbp+var_18]; pListOfExplicitEntries
0x18004f024  lea     rdx, [rbp+var_38]; pcCountOfExplicitEntries
0x18004f028  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004f02f  nop     dword ptr [rax+rax+00h]
0x18004f034  jmp     short loc_18004F042
0x18004f036  call    cs:__imp_GetLastError
0x18004f03d  nop     dword ptr [rax+rax+00h]
0x18004f042  mov     ebx, eax
0x18004f044  test    eax, eax
0x18004f046  jnz     short loc_18004F0AD
0x18004f048  mov     rax, [rbp+arg_0]
0x18004f04c  test    rax, rax
0x18004f04f  jz      short loc_18004F054
0x18004f051  mov     [rax], rsi
0x18004f054  mov     rax, [rbp+arg_8]
0x18004f058  test    rax, rax
0x18004f05b  jz      short loc_18004F060
0x18004f05d  mov     [rax], r14
0x18004f060  test    r12, r12
0x18004f063  jz      short loc_18004F076
0x18004f065  mov     rax, [rbp+pListOfExplicitEntries]
0x18004f069  mov     rcx, [rbp+arg_10]
0x18004f06d  mov     [r12], rax
0x18004f071  mov     eax, [rbp+pcCountOfExplicitEntries]
0x18004f074  mov     [rcx], eax
0x18004f076  test    rdi, rdi
0x18004f079  jz      short loc_18004F088
0x18004f07b  mov     rax, [rbp+var_18]
0x18004f07f  mov     [rdi], rax
0x18004f082  mov     eax, [rbp+var_38]
0x18004f085  mov     [r15], eax
0x18004f088  mov     eax, ebx
0x18004f08a  mov     rbx, [rsp+70h+arg_18]
0x18004f092  add     rsp, 70h
0x18004f096  pop     r15
0x18004f098  pop     r14
0x18004f09a  pop     r13
0x18004f09c  pop     r12
0x18004f09e  pop     rdi
0x18004f09f  pop     rsi
0x18004f0a0  pop     rbp
0x18004f0a1  retn
0x18004f0a3  test    rdi, rdi
0x18004f0a6  jz      short loc_18004F048
0x18004f0a8  mov     ebx, 57h ; 'W'
0x18004f0ad  test    rsi, rsi
0x18004f0b0  jz      short loc_18004F0C1
0x18004f0b2  mov     rcx, rsi; hMem
0x18004f0b5  call    cs:__imp_LocalFree
0x18004f0bc  nop     dword ptr [rax+rax+00h]
0x18004f0c1  test    r14, r14
0x18004f0c4  jz      short loc_18004F0D5
0x18004f0c6  mov     rcx, r14; hMem
0x18004f0c9  call    cs:__imp_LocalFree
0x18004f0d0  nop     dword ptr [rax+rax+00h]
0x18004f0d5  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x18004f0d9  test    rcx, rcx
0x18004f0dc  jz      short loc_18004F0EA
0x18004f0de  call    cs:__imp_LocalFree
0x18004f0e5  nop     dword ptr [rax+rax+00h]
0x18004f0ea  mov     rcx, [rbp+var_18]; hMem
0x18004f0ee  test    rcx, rcx
0x18004f0f1  jz      short loc_18004F088
0x18004f0f3  call    cs:__imp_LocalFree
0x18004f0fa  nop     dword ptr [rax+rax+00h]
0x18004f0ff  jmp     short loc_18004F088
```
