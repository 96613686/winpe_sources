# BuildSecurityDescriptorW

- ea: `0x180029d20`
- end: `0x18002a081`
- name: `BuildSecurityDescriptorW`
- size: `865`
- prototype: `DWORD __stdcall(PTRUSTEE_W pOwner, PTRUSTEE_W pGroup, ULONG cCountOfAccessEntries, PEXPLICIT_ACCESS_W pListOfAccessEntries, ULONG cCountOfAuditEntries, PEXPLICIT_ACCESS_W pListOfAuditEntries, PSECURITY_DESCRIPTOR pOldSD, PULONG pSizeNewSD, PSECURITY_DESCRIPTOR *pNewSD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048de0`

## callees

- `0x180029d20`
- `0x18002a088`
- `0x180066010`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180029efa`
- `KERNELBASE!LocalAlloc` at `0x180029efa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180029eb9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180029eb9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029d8d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029d8d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180029eda`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180029f1d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180029eda`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180029f1d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180029e83`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180029e83`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180029e6a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180029e6a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180029e9e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180029e9e`
- `KERNEL32!LocalFree` at `0x180029f48`
- `KERNEL32!LocalFree` at `0x180029f57`
- `KERNEL32!LocalFree` at `0x18002a050`
- `KERNEL32!LocalFree` at `0x18002a067`
- `KERNEL32!LocalFree` at `0x18002a076`
- `KERNEL32!LocalFree` at `0x180029f48`
- `KERNEL32!LocalFree` at `0x180029f57`
- `KERNEL32!LocalFree` at `0x18002a050`
- `KERNEL32!LocalFree` at `0x18002a067`
- `KERNEL32!LocalFree` at `0x18002a076`
- `KERNEL32!GetLastError` at `0x180029ee8`
- `KERNEL32!GetLastError` at `0x18002a056`
- `KERNEL32!GetLastError` at `0x180029ee8`
- `KERNEL32!GetLastError` at `0x18002a056`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180029e3a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002a035`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180029e3a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002a035`

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
    LastError = (*(__int64 (__fastcall **)(_QWORD, PTRUSTEE_W, PSID *, int *))(qword_1800A2048 + 16))(
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
        LastError = (*(__int64 (__fastcall **)(_QWORD, PTRUSTEE_W, PSID *, int *))(qword_1800A2048 + 16))(
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
0x180029d20  mov     rax, rsp
0x180029d23  mov     [rax+8], rbx
0x180029d27  mov     [rax+20h], r9
0x180029d2b  mov     [rax+18h], r8d
0x180029d2f  mov     [rax+10h], rdx
0x180029d33  push    rbp
0x180029d34  push    rsi
0x180029d35  push    rdi
0x180029d36  push    r12
0x180029d38  push    r13
0x180029d3a  push    r14
0x180029d3c  push    r15
0x180029d3e  mov     rbp, rsp
0x180029d41  sub     rsp, 80h
0x180029d48  xor     r13d, r13d
0x180029d4b  xorps   xmm0, xmm0
0x180029d4e  xor     eax, eax
0x180029d50  mov     [rbp+NewAcl], r13
0x180029d54  movups  [rbp+pSecurityDescriptor], xmm0
0x180029d58  mov     [rbp+var_8], rax
0x180029d5c  mov     rbx, rcx
0x180029d5f  movups  [rbp+var_18], xmm0
0x180029d63  mov     [rbp+pSacl], r13
0x180029d67  mov     [rbp+pOwner], r13
0x180029d6b  mov     [rbp+pGroup], r13
0x180029d6f  call    AccProvpInitProviders
0x180029d74  test    eax, eax
0x180029d76  jnz     loc_180029F88
0x180029d7c  lea     r14d, [r13+1]
0x180029d80  mov     esi, r13d
0x180029d83  mov     edx, r14d; dwRevision
0x180029d86  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180029d8a  mov     edi, r13d
0x180029d8d  call    cs:__imp_InitializeSecurityDescriptor
0x180029d93  mov     rax, [rbp+pOldSD]
0x180029d97  test    rax, rax
0x180029d9a  jz      short loc_180029E03
0x180029d9c  movzx   edx, word ptr [rax+2]
0x180029da0  test    dx, dx
0x180029da3  jns     loc_180029FEA
0x180029da9  cmp     [rax+8], r13
0x180029dad  jz      short loc_180029DC3
0x180029daf  cmp     [rax+4], r13d
0x180029db3  jz      loc_180029FA3
0x180029db9  mov     ecx, [rax+4]
0x180029dbc  add     rcx, rax
0x180029dbf  mov     [rbp+pOwner], rcx
0x180029dc3  cmp     [rax+10h], r13
0x180029dc7  jz      short loc_180029DDD
0x180029dc9  cmp     [rax+8], r13d
0x180029dcd  jz      loc_180029FD8
0x180029dd3  mov     ecx, [rax+8]
0x180029dd6  add     rcx, rax
0x180029dd9  mov     [rbp+pGroup], rcx
0x180029ddd  cmp     [rax+20h], r13
0x180029de1  jz      short loc_180029DF4
0x180029de3  test    dl, 4
0x180029de6  jz      short loc_180029DF4
0x180029de8  cmp     [rax+10h], r13d
0x180029dec  jz      short loc_180029DF4
0x180029dee  mov     esi, [rax+10h]
0x180029df1  add     rsi, rax
0x180029df4  cmp     [rax+18h], r13
0x180029df8  jz      short loc_180029E03
0x180029dfa  test    dl, 10h
0x180029dfd  jnz     loc_180029FC3
0x180029e03  mov     r12d, r13d
0x180029e06  test    rbx, rbx
0x180029e09  jnz     loc_180029F5F
0x180029e0f  mov     rdx, [rbp+arg_8]
0x180029e13  mov     r15d, r13d
0x180029e16  mov     r14d, r13d
0x180029e19  test    rdx, rdx
0x180029e1c  jnz     loc_180029FF9
0x180029e22  mov     eax, [rbp+cCountOfExplicitEntries]
0x180029e25  test    eax, eax
0x180029e27  jz      loc_180029FB5
0x180029e2d  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180029e31  lea     r9, [rbp+NewAcl]; NewAcl
0x180029e35  mov     r8, rsi; OldAcl
0x180029e38  mov     ecx, eax; cCountOfExplicitEntries
0x180029e3a  call    cs:__imp_SetEntriesInAclW
0x180029e40  mov     ebx, eax
0x180029e42  test    eax, eax
0x180029e44  jnz     loc_180029F2D
0x180029e4a  lea     esi, [rax+1]
0x180029e4d  mov     r15d, esi
0x180029e50  mov     ecx, [rbp+cCountOfAuditEntries]; cCountOfExplicitEntries
0x180029e53  test    ecx, ecx
0x180029e55  jnz     loc_18002A02A
0x180029e5b  mov     [rbp+pSacl], rdi
0x180029e5f  mov     rdx, [rbp+pOwner]; pOwner
0x180029e63  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180029e67  xor     r8d, r8d; bOwnerDefaulted
0x180029e6a  call    cs:__imp_SetSecurityDescriptorOwner
0x180029e70  test    eax, eax
0x180029e72  jz      loc_18002A056
0x180029e78  mov     rdx, [rbp+pGroup]; pGroup
0x180029e7c  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180029e80  xor     r8d, r8d; bGroupDefaulted
0x180029e83  call    cs:__imp_SetSecurityDescriptorGroup
0x180029e89  test    eax, eax
0x180029e8b  jz      loc_18002A056
0x180029e91  mov     r8, [rbp+NewAcl]; pDacl
0x180029e95  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180029e99  xor     r9d, r9d; bDaclDefaulted
0x180029e9c  mov     edx, esi; bDaclPresent
0x180029e9e  call    cs:__imp_SetSecurityDescriptorDacl
0x180029ea4  test    eax, eax
0x180029ea6  jz      loc_18002A056
0x180029eac  mov     r8, [rbp+pSacl]; pSacl
0x180029eb0  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180029eb4  xor     r9d, r9d; bSaclDefaulted
0x180029eb7  mov     edx, esi; bSaclPresent
0x180029eb9  call    cs:__imp_SetSecurityDescriptorSacl
0x180029ebf  test    eax, eax
0x180029ec1  jz      loc_18002A056
0x180029ec7  mov     rdi, [rbp+pSizeNewSD]
0x180029ecb  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180029ecf  mov     r8, rdi; lpdwBufferLength
0x180029ed2  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180029ed4  mov     dword ptr [rdi], 0
0x180029eda  call    cs:__imp_MakeSelfRelativeSD
0x180029ee0  test    eax, eax
0x180029ee2  jnz     loc_180029FE0
0x180029ee8  call    cs:__imp_GetLastError
0x180029eee  mov     ebx, eax
0x180029ef0  cmp     eax, 7Ah ; 'z'
0x180029ef3  jnz     short loc_180029F2D
0x180029ef5  mov     edx, [rdi]; uBytes
0x180029ef7  lea     ecx, [rax-3Ah]; uFlags
0x180029efa  call    cs:__imp_LocalAlloc
0x180029f00  mov     rbx, [rbp+pNewSD]
0x180029f07  mov     [rbx], rax
0x180029f0a  test    rax, rax
0x180029f0d  jz      loc_180029FAB
0x180029f13  mov     r8, rdi; lpdwBufferLength
0x180029f16  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180029f1a  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180029f1d  call    cs:__imp_MakeSelfRelativeSD
0x180029f23  test    eax, eax
0x180029f25  jz      loc_18002A04D
0x180029f2b  xor     ebx, ebx
0x180029f2d  test    r12d, r12d
0x180029f30  jnz     loc_18002A063
0x180029f36  test    r13d, r13d
0x180029f39  jnz     loc_18002A072
0x180029f3f  test    r15d, r15d
0x180029f42  jz      short loc_180029F4E
0x180029f44  mov     rcx, [rbp+NewAcl]; hMem
0x180029f48  call    cs:__imp_LocalFree
0x180029f4e  test    r14d, r14d
0x180029f51  jz      short loc_180029F86
0x180029f53  mov     rcx, [rbp+pSacl]; hMem
0x180029f57  call    cs:__imp_LocalFree
0x180029f5d  jmp     short loc_180029F86
0x180029f5f  mov     rax, cs:qword_1800A2048
0x180029f66  lea     r9, [rbp+var_50]
0x180029f6a  mov     [rbp+var_50], r13d
0x180029f6e  lea     r8, [rbp+pOwner]
0x180029f72  mov     rdx, rbx
0x180029f75  xor     ecx, ecx
0x180029f77  mov     rax, [rax+10h]
0x180029f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f80  mov     ebx, eax
0x180029f82  test    eax, eax
0x180029f84  jz      short loc_180029FF1
0x180029f86  mov     eax, ebx
0x180029f88  mov     rbx, [rsp+80h+arg_0]
0x180029f90  add     rsp, 80h
0x180029f97  pop     r15
0x180029f99  pop     r14
0x180029f9b  pop     r13
0x180029f9d  pop     r12
0x180029f9f  pop     rdi
0x180029fa0  pop     rsi
0x180029fa1  pop     rbp
0x180029fa2  retn
0x180029fa3  mov     rcx, r13
0x180029fa6  jmp     loc_180029DBF
0x180029fab  mov     ebx, 8
0x180029fb0  jmp     loc_180029F2D
0x180029fb5  mov     [rbp+NewAcl], rsi
0x180029fb9  mov     esi, 1
0x180029fbe  jmp     loc_180029E50
0x180029fc3  cmp     [rax+0Ch], r13d
0x180029fc7  jz      loc_180029E03
0x180029fcd  mov     edi, [rax+0Ch]
0x180029fd0  add     rdi, rax
0x180029fd3  jmp     loc_180029E03
0x180029fd8  mov     rcx, r13
0x180029fdb  jmp     loc_180029DD9
0x180029fe0  mov     ebx, 57h ; 'W'
0x180029fe5  jmp     loc_180029F2D
0x180029fea  mov     ebx, 53Ah
0x180029fef  jmp     short loc_180029F86
0x180029ff1  mov     r12d, r14d
0x180029ff4  jmp     loc_180029E0F
0x180029ff9  mov     rax, cs:qword_1800A2048
0x18002a000  lea     r9, [rbp+var_50]
0x18002a004  mov     [rbp+var_50], r13d
0x18002a008  lea     r8, [rbp+pGroup]
0x18002a00c  xor     ecx, ecx
0x18002a00e  mov     rax, [rax+10h]
0x18002a012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a017  mov     ebx, eax
0x18002a019  test    eax, eax
0x18002a01b  jnz     loc_180029F2D
0x18002a021  lea     r13d, [rax+1]
0x18002a025  jmp     loc_180029E22
0x18002a02a  mov     rdx, [rbp+pListOfAuditEntries]; pListOfExplicitEntries
0x18002a02e  lea     r9, [rbp+pSacl]; NewAcl
0x18002a032  mov     r8, rdi; OldAcl
0x18002a035  call    cs:__imp_SetEntriesInAclW
0x18002a03b  mov     ebx, eax
0x18002a03d  test    eax, eax
0x18002a03f  jnz     loc_180029F2D
0x18002a045  mov     r14d, esi
0x18002a048  jmp     loc_180029E5F
0x18002a04d  mov     rcx, [rbx]; hMem
0x18002a050  call    cs:__imp_LocalFree
0x18002a056  call    cs:__imp_GetLastError
0x18002a05c  mov     ebx, eax
0x18002a05e  jmp     loc_180029F2D
0x18002a063  mov     rcx, [rbp+pOwner]; hMem
0x18002a067  call    cs:__imp_LocalFree
0x18002a06d  jmp     loc_180029F36
0x18002a072  mov     rcx, [rbp+pGroup]; hMem
0x18002a076  call    cs:__imp_LocalFree
0x18002a07c  jmp     loc_180029F3F
```
