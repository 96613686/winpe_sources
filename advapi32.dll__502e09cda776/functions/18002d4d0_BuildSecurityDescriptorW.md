# BuildSecurityDescriptorW

- ea: `0x18002d4d0`
- end: `0x18002d898`
- name: `BuildSecurityDescriptorW`
- size: `968`
- prototype: `DWORD __stdcall(PTRUSTEE_W pOwner, PTRUSTEE_W pGroup, ULONG cCountOfAccessEntries, PEXPLICIT_ACCESS_W pListOfAccessEntries, ULONG cCountOfAuditEntries, PEXPLICIT_ACCESS_W pListOfAuditEntries, PSECURITY_DESCRIPTOR pOldSD, PULONG pSizeNewSD, PSECURITY_DESCRIPTOR *pNewSD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e9d0`

## callees

- `0x18002d4d0`
- `0x18002d8a0`
- `0x180074010`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002d6da`
- `KERNELBASE!LocalAlloc` at `0x18002d6da`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18002d687`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18002d687`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002d53d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002d53d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002d6ae`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002d703`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002d6ae`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002d703`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18002d645`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18002d645`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18002d626`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18002d626`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002d666`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002d666`
- `KERNEL32!LocalFree` at `0x18002d734`
- `KERNEL32!LocalFree` at `0x18002d749`
- `KERNEL32!LocalFree` at `0x18002d84f`
- `KERNEL32!LocalFree` at `0x18002d872`
- `KERNEL32!LocalFree` at `0x18002d887`
- `KERNEL32!LocalFree` at `0x18002d734`
- `KERNEL32!LocalFree` at `0x18002d749`
- `KERNEL32!LocalFree` at `0x18002d84f`
- `KERNEL32!LocalFree` at `0x18002d872`
- `KERNEL32!LocalFree` at `0x18002d887`
- `KERNEL32!GetLastError` at `0x18002d6c2`
- `KERNEL32!GetLastError` at `0x18002d85b`
- `KERNEL32!GetLastError` at `0x18002d6c2`
- `KERNEL32!GetLastError` at `0x18002d85b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d5f0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d82e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d5f0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d82e`

## pseudocode

```c
DWORD __stdcall BuildSecurityDescriptorW(
        PTRUSTEE_W pOwner,
        PTRUSTEE_W pGroup,
        ULONG cCountOfAccessEntries,
        PEXPLICIT_ACCESS_W pListOfAccessEntries,
        ULONG cCountOfAuditEntries,
        PEXPLICIT_ACCESS_W pListOfAuditEntries,
        PSECURITY_DESCRIPTOR pOldSD,
        PULONG pSizeNewSD,
        PSECURITY_DESCRIPTOR *pNewSD)
{
  int v9; // r13d
  DWORD result; // eax
  ACL *v12; // rsi
  ACL *v13; // rdi
  __int16 v14; // dx
  char *v15; // rcx
  char *v16; // rcx
  int v17; // r12d
  int v18; // r15d
  int v19; // r14d
  DWORD LastError; // ebx
  HLOCAL v21; // rax
  int v22; // [rsp+30h] [rbp-50h] BYREF
  PSID pOwnera; // [rsp+38h] [rbp-48h] BYREF
  PSID pGroupa; // [rsp+40h] [rbp-40h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-38h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+78h] [rbp-8h]

  v9 = 0;
  NewAcl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v28 = 0;
  pSacl = 0;
  pOwnera = 0;
  pGroupa = 0;
  result = AccProvpInitProviders((__int64)pOwner);
  if ( !result )
  {
    v12 = 0;
    v13 = 0;
    InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
    if ( pOldSD )
    {
      v14 = *((_WORD *)pOldSD + 1);
      if ( v14 >= 0 )
        return 1338;
      if ( *((_QWORD *)pOldSD + 1) )
      {
        if ( *((_DWORD *)pOldSD + 1) )
          v15 = (char *)pOldSD + *((unsigned int *)pOldSD + 1);
        else
          v15 = 0;
        pOwnera = v15;
      }
      if ( *((_QWORD *)pOldSD + 2) )
      {
        if ( *((_DWORD *)pOldSD + 2) )
          v16 = (char *)pOldSD + *((unsigned int *)pOldSD + 2);
        else
          v16 = 0;
        pGroupa = v16;
      }
      if ( *((_QWORD *)pOldSD + 4) && (v14 & 4) != 0 && *((_DWORD *)pOldSD + 4) )
        v12 = (ACL *)((char *)pOldSD + *((unsigned int *)pOldSD + 4));
      if ( *((_QWORD *)pOldSD + 3) && (v14 & 0x10) != 0 && *((_DWORD *)pOldSD + 3) )
        v13 = (ACL *)((char *)pOldSD + *((unsigned int *)pOldSD + 3));
    }
    v17 = 0;
    if ( !pOwner )
      goto LABEL_19;
    v22 = 0;
    LastError = (*(__int64 (__fastcall **)(_QWORD, PTRUSTEE_W, PSID *, int *))(qword_1800B1048 + 16))(
                  0,
                  pOwner,
                  &pOwnera,
                  &v22);
    if ( !LastError )
    {
      v17 = 1;
LABEL_19:
      v18 = 0;
      v19 = 0;
      if ( pGroup )
      {
        v22 = 0;
        LastError = (*(__int64 (__fastcall **)(_QWORD, PTRUSTEE_W, PSID *, int *))(qword_1800B1048 + 16))(
                      0,
                      pGroup,
                      &pGroupa,
                      &v22);
        if ( LastError )
          goto LABEL_34;
        v9 = 1;
      }
      if ( cCountOfAccessEntries )
      {
        LastError = SetEntriesInAclW(cCountOfAccessEntries, pListOfAccessEntries, v12, &NewAcl);
        if ( LastError )
          goto LABEL_34;
        v18 = 1;
      }
      else
      {
        NewAcl = v12;
      }
      if ( cCountOfAuditEntries )
      {
        LastError = SetEntriesInAclW(cCountOfAuditEntries, pListOfAuditEntries, v13, &pSacl);
        if ( LastError )
          goto LABEL_34;
        v19 = 1;
      }
      else
      {
        pSacl = v13;
      }
      if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwnera, 0)
        || !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroupa, 0)
        || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0)
        || !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, pSacl, 0) )
      {
        goto LABEL_59;
      }
      *pSizeNewSD = 0;
      if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, pSizeNewSD) )
      {
        LastError = 87;
        goto LABEL_34;
      }
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v21 = LocalAlloc(0x40u, *pSizeNewSD);
        *pNewSD = v21;
        if ( !v21 )
        {
          LastError = 8;
          goto LABEL_34;
        }
        if ( MakeSelfRelativeSD(pSecurityDescriptor, v21, pSizeNewSD) )
        {
          LastError = 0;
          goto LABEL_34;
        }
        LocalFree(*pNewSD);
LABEL_59:
        LastError = GetLastError();
      }
LABEL_34:
      if ( v17 )
        LocalFree(pOwnera);
      if ( v9 )
        LocalFree(pGroupa);
      if ( v18 )
        LocalFree(NewAcl);
      if ( v19 )
        LocalFree(pSacl);
    }
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18002d4d0  mov     rax, rsp
0x18002d4d3  mov     [rax+8], rbx
0x18002d4d7  mov     [rax+20h], r9
0x18002d4db  mov     [rax+18h], r8d
0x18002d4df  mov     [rax+10h], rdx
0x18002d4e3  push    rbp
0x18002d4e4  push    rsi
0x18002d4e5  push    rdi
0x18002d4e6  push    r12
0x18002d4e8  push    r13
0x18002d4ea  push    r14
0x18002d4ec  push    r15
0x18002d4ee  mov     rbp, rsp
0x18002d4f1  sub     rsp, 80h
0x18002d4f8  xor     r13d, r13d
0x18002d4fb  xorps   xmm0, xmm0
0x18002d4fe  xor     eax, eax
0x18002d500  mov     [rbp+NewAcl], r13
0x18002d504  movups  [rbp+pSecurityDescriptor], xmm0
0x18002d508  mov     [rbp+var_8], rax
0x18002d50c  mov     rbx, rcx
0x18002d50f  movups  [rbp+var_18], xmm0
0x18002d513  mov     [rbp+pSacl], r13
0x18002d517  mov     [rbp+pOwner], r13
0x18002d51b  mov     [rbp+pGroup], r13
0x18002d51f  call    AccProvpInitProviders
0x18002d524  test    eax, eax
0x18002d526  jnz     loc_18002D780
0x18002d52c  lea     r14d, [r13+1]
0x18002d530  mov     esi, r13d
0x18002d533  mov     edx, r14d; dwRevision
0x18002d536  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002d53a  mov     edi, r13d
0x18002d53d  call    cs:__imp_InitializeSecurityDescriptor
0x18002d544  nop     dword ptr [rax+rax+00h]
0x18002d549  mov     rax, [rbp+pOldSD]
0x18002d54d  test    rax, rax
0x18002d550  jz      short loc_18002D5B9
0x18002d552  movzx   edx, word ptr [rax+2]
0x18002d556  test    dx, dx
0x18002d559  jns     loc_18002D7E3
0x18002d55f  cmp     [rax+8], r13
0x18002d563  jz      short loc_18002D579
0x18002d565  cmp     [rax+4], r13d
0x18002d569  jz      loc_18002D79C
0x18002d56f  mov     ecx, [rax+4]
0x18002d572  add     rcx, rax
0x18002d575  mov     [rbp+pOwner], rcx
0x18002d579  cmp     [rax+10h], r13
0x18002d57d  jz      short loc_18002D593
0x18002d57f  cmp     [rax+8], r13d
0x18002d583  jz      loc_18002D7D1
0x18002d589  mov     ecx, [rax+8]
0x18002d58c  add     rcx, rax
0x18002d58f  mov     [rbp+pGroup], rcx
0x18002d593  cmp     [rax+20h], r13
0x18002d597  jz      short loc_18002D5AA
0x18002d599  test    dl, 4
0x18002d59c  jz      short loc_18002D5AA
0x18002d59e  cmp     [rax+10h], r13d
0x18002d5a2  jz      short loc_18002D5AA
0x18002d5a4  mov     esi, [rax+10h]
0x18002d5a7  add     rsi, rax
0x18002d5aa  cmp     [rax+18h], r13
0x18002d5ae  jz      short loc_18002D5B9
0x18002d5b0  test    dl, 10h
0x18002d5b3  jnz     loc_18002D7BC
0x18002d5b9  mov     r12d, r13d
0x18002d5bc  test    rbx, rbx
0x18002d5bf  jnz     loc_18002D757
0x18002d5c5  mov     rdx, [rbp+arg_8]
0x18002d5c9  mov     r15d, r13d
0x18002d5cc  mov     r14d, r13d
0x18002d5cf  test    rdx, rdx
0x18002d5d2  jnz     loc_18002D7F2
0x18002d5d8  mov     eax, [rbp+cCountOfExplicitEntries]
0x18002d5db  test    eax, eax
0x18002d5dd  jz      loc_18002D7AE
0x18002d5e3  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002d5e7  lea     r9, [rbp+NewAcl]; NewAcl
0x18002d5eb  mov     r8, rsi; OldAcl
0x18002d5ee  mov     ecx, eax; cCountOfExplicitEntries
0x18002d5f0  call    cs:__imp_SetEntriesInAclW
0x18002d5f7  nop     dword ptr [rax+rax+00h]
0x18002d5fc  mov     ebx, eax
0x18002d5fe  test    eax, eax
0x18002d600  jnz     loc_18002D719
0x18002d606  lea     esi, [rax+1]
0x18002d609  mov     r15d, esi
0x18002d60c  mov     ecx, [rbp+cCountOfAuditEntries]; cCountOfExplicitEntries
0x18002d60f  test    ecx, ecx
0x18002d611  jnz     loc_18002D823
0x18002d617  mov     [rbp+pSacl], rdi
0x18002d61b  mov     rdx, [rbp+pOwner]; pOwner
0x18002d61f  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002d623  xor     r8d, r8d; bOwnerDefaulted
0x18002d626  call    cs:__imp_SetSecurityDescriptorOwner
0x18002d62d  nop     dword ptr [rax+rax+00h]
0x18002d632  test    eax, eax
0x18002d634  jz      loc_18002D85B
0x18002d63a  mov     rdx, [rbp+pGroup]; pGroup
0x18002d63e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002d642  xor     r8d, r8d; bGroupDefaulted
0x18002d645  call    cs:__imp_SetSecurityDescriptorGroup
0x18002d64c  nop     dword ptr [rax+rax+00h]
0x18002d651  test    eax, eax
0x18002d653  jz      loc_18002D85B
0x18002d659  mov     r8, [rbp+NewAcl]; pDacl
0x18002d65d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002d661  xor     r9d, r9d; bDaclDefaulted
0x18002d664  mov     edx, esi; bDaclPresent
0x18002d666  call    cs:__imp_SetSecurityDescriptorDacl
0x18002d66d  nop     dword ptr [rax+rax+00h]
0x18002d672  test    eax, eax
0x18002d674  jz      loc_18002D85B
0x18002d67a  mov     r8, [rbp+pSacl]; pSacl
0x18002d67e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002d682  xor     r9d, r9d; bSaclDefaulted
0x18002d685  mov     edx, esi; bSaclPresent
0x18002d687  call    cs:__imp_SetSecurityDescriptorSacl
0x18002d68e  nop     dword ptr [rax+rax+00h]
0x18002d693  test    eax, eax
0x18002d695  jz      loc_18002D85B
0x18002d69b  mov     rdi, [rbp+pSizeNewSD]
0x18002d69f  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18002d6a3  mov     r8, rdi; lpdwBufferLength
0x18002d6a6  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18002d6a8  mov     dword ptr [rdi], 0
0x18002d6ae  call    cs:__imp_MakeSelfRelativeSD
0x18002d6b5  nop     dword ptr [rax+rax+00h]
0x18002d6ba  test    eax, eax
0x18002d6bc  jnz     loc_18002D7D9
0x18002d6c2  call    cs:__imp_GetLastError
0x18002d6c9  nop     dword ptr [rax+rax+00h]
0x18002d6ce  mov     ebx, eax
0x18002d6d0  cmp     eax, 7Ah ; 'z'
0x18002d6d3  jnz     short loc_18002D719
0x18002d6d5  mov     edx, [rdi]; uBytes
0x18002d6d7  lea     ecx, [rax-3Ah]; uFlags
0x18002d6da  call    cs:__imp_LocalAlloc
0x18002d6e1  nop     dword ptr [rax+rax+00h]
0x18002d6e6  mov     rbx, [rbp+pNewSD]
0x18002d6ed  mov     [rbx], rax
0x18002d6f0  test    rax, rax
0x18002d6f3  jz      loc_18002D7A4
0x18002d6f9  mov     r8, rdi; lpdwBufferLength
0x18002d6fc  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18002d700  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18002d703  call    cs:__imp_MakeSelfRelativeSD
0x18002d70a  nop     dword ptr [rax+rax+00h]
0x18002d70f  test    eax, eax
0x18002d711  jz      loc_18002D84C
0x18002d717  xor     ebx, ebx
0x18002d719  test    r12d, r12d
0x18002d71c  jnz     loc_18002D86E
0x18002d722  test    r13d, r13d
0x18002d725  jnz     loc_18002D883
0x18002d72b  test    r15d, r15d
0x18002d72e  jz      short loc_18002D740
0x18002d730  mov     rcx, [rbp+NewAcl]; hMem
0x18002d734  call    cs:__imp_LocalFree
0x18002d73b  nop     dword ptr [rax+rax+00h]
0x18002d740  test    r14d, r14d
0x18002d743  jz      short loc_18002D77E
0x18002d745  mov     rcx, [rbp+pSacl]; hMem
0x18002d749  call    cs:__imp_LocalFree
0x18002d750  nop     dword ptr [rax+rax+00h]
0x18002d755  jmp     short loc_18002D77E
0x18002d757  mov     rax, cs:qword_1800B1048
0x18002d75e  lea     r9, [rbp+var_50]
0x18002d762  mov     [rbp+var_50], r13d
0x18002d766  lea     r8, [rbp+pOwner]
0x18002d76a  mov     rdx, rbx
0x18002d76d  xor     ecx, ecx
0x18002d76f  mov     rax, [rax+10h]
0x18002d773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d778  mov     ebx, eax
0x18002d77a  test    eax, eax
0x18002d77c  jz      short loc_18002D7EA
0x18002d77e  mov     eax, ebx
0x18002d780  mov     rbx, [rsp+80h+arg_0]
0x18002d788  add     rsp, 80h
0x18002d78f  pop     r15
0x18002d791  pop     r14
0x18002d793  pop     r13
0x18002d795  pop     r12
0x18002d797  pop     rdi
0x18002d798  pop     rsi
0x18002d799  pop     rbp
0x18002d79a  retn
0x18002d79c  mov     rcx, r13
0x18002d79f  jmp     loc_18002D575
0x18002d7a4  mov     ebx, 8
0x18002d7a9  jmp     loc_18002D719
0x18002d7ae  mov     [rbp+NewAcl], rsi
0x18002d7b2  mov     esi, 1
0x18002d7b7  jmp     loc_18002D60C
0x18002d7bc  cmp     [rax+0Ch], r13d
0x18002d7c0  jz      loc_18002D5B9
0x18002d7c6  mov     edi, [rax+0Ch]
0x18002d7c9  add     rdi, rax
0x18002d7cc  jmp     loc_18002D5B9
0x18002d7d1  mov     rcx, r13
0x18002d7d4  jmp     loc_18002D58F
0x18002d7d9  mov     ebx, 57h ; 'W'
0x18002d7de  jmp     loc_18002D719
0x18002d7e3  mov     ebx, 53Ah
0x18002d7e8  jmp     short loc_18002D77E
0x18002d7ea  mov     r12d, r14d
0x18002d7ed  jmp     loc_18002D5C5
0x18002d7f2  mov     rax, cs:qword_1800B1048
0x18002d7f9  lea     r9, [rbp+var_50]
0x18002d7fd  mov     [rbp+var_50], r13d
0x18002d801  lea     r8, [rbp+pGroup]
0x18002d805  xor     ecx, ecx
0x18002d807  mov     rax, [rax+10h]
0x18002d80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d810  mov     ebx, eax
0x18002d812  test    eax, eax
0x18002d814  jnz     loc_18002D719
0x18002d81a  lea     r13d, [rax+1]
0x18002d81e  jmp     loc_18002D5D8
0x18002d823  mov     rdx, [rbp+pListOfAuditEntries]; pListOfExplicitEntries
0x18002d827  lea     r9, [rbp+pSacl]; NewAcl
0x18002d82b  mov     r8, rdi; OldAcl
0x18002d82e  call    cs:__imp_SetEntriesInAclW
0x18002d835  nop     dword ptr [rax+rax+00h]
0x18002d83a  mov     ebx, eax
0x18002d83c  test    eax, eax
0x18002d83e  jnz     loc_18002D719
0x18002d844  mov     r14d, esi
0x18002d847  jmp     loc_18002D61B
0x18002d84c  mov     rcx, [rbx]; hMem
0x18002d84f  call    cs:__imp_LocalFree
0x18002d856  nop     dword ptr [rax+rax+00h]
0x18002d85b  call    cs:__imp_GetLastError
0x18002d862  nop     dword ptr [rax+rax+00h]
0x18002d867  mov     ebx, eax
0x18002d869  jmp     loc_18002D719
0x18002d86e  mov     rcx, [rbp+pOwner]; hMem
0x18002d872  call    cs:__imp_LocalFree
0x18002d879  nop     dword ptr [rax+rax+00h]
0x18002d87e  jmp     loc_18002D722
0x18002d883  mov     rcx, [rbp+pGroup]; hMem
0x18002d887  call    cs:__imp_LocalFree
0x18002d88e  nop     dword ptr [rax+rax+00h]
0x18002d893  jmp     loc_18002D72B
```
