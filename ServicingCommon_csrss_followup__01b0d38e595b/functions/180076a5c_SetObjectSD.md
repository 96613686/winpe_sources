# SetObjectSD

- ea: `0x180076a5c`
- end: `0x180076b8c`
- name: `SetObjectSD`
- size: `304`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180076714`

## callees

- `0x180076a5c`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x180076b6a`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180076b6a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076b2a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076b2a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076b02`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076b02`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076ab4`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076ab4`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076ad9`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076ad9`

## pseudocode

```c
DWORD __fastcall SetObjectSD(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  SECURITY_INFORMATION v6; // ebx
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-30h] BYREF
  PSID pGroup; // [rsp+48h] [rbp-28h] BYREF
  PSID pOwner; // [rsp+50h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+58h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-10h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+A8h] [rbp+38h] BYREF

  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  v6 = 0;
  if ( GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
    v6 = pOwner != 0;
  if ( GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted) && pGroup )
    v6 |= 2u;
  if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) && bDaclPresent )
    v6 |= 4u;
  if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pSacl, &bOwnerDefaulted) && bDaclPresent )
    v6 |= 8u;
  return SetNamedSecurityInfoW(pObjectName, ObjectType, v6, pOwner, pGroup, pDacl, pSacl);
}

```

## disassembly

```asm
0x180076a5c  mov     [rsp-18h+arg_0], rbx
0x180076a61  mov     [rsp-18h+arg_8], rsi
0x180076a66  push    rbp
0x180076a67  push    rdi
0x180076a68  push    r14
0x180076a6a  mov     rbp, rsp
0x180076a6d  sub     rsp, 70h
0x180076a71  mov     rdi, r8
0x180076a74  mov     [rbp+pOwner], 0
0x180076a7c  mov     esi, edx
0x180076a7e  mov     [rbp+pGroup], 0
0x180076a86  mov     r14, rcx
0x180076a89  mov     [rbp+pDacl], 0
0x180076a91  mov     rcx, rdi; pSecurityDescriptor
0x180076a94  mov     [rbp+pSacl], 0
0x180076a9c  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180076aa0  mov     [rbp+bDaclPresent], 0
0x180076aa7  lea     rdx, [rbp+pOwner]; pOwner
0x180076aab  mov     [rbp+bOwnerDefaulted], 0
0x180076ab2  xor     ebx, ebx
0x180076ab4  call    cs:__imp_GetSecurityDescriptorOwner
0x180076abb  nop     dword ptr [rax+rax+00h]
0x180076ac0  test    eax, eax
0x180076ac2  jz      short loc_180076ACE
0x180076ac4  cmp     [rbp+pOwner], rbx
0x180076ac8  lea     eax, [rbx+1]
0x180076acb  cmovnz  ebx, eax
0x180076ace  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180076ad2  mov     rcx, rdi; pSecurityDescriptor
0x180076ad5  lea     rdx, [rbp+pGroup]; pGroup
0x180076ad9  call    cs:__imp_GetSecurityDescriptorGroup
0x180076ae0  nop     dword ptr [rax+rax+00h]
0x180076ae5  test    eax, eax
0x180076ae7  jz      short loc_180076AF3
0x180076ae9  cmp     [rbp+pGroup], 0
0x180076aee  jz      short loc_180076AF3
0x180076af0  or      ebx, 2
0x180076af3  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x180076af7  mov     rcx, rdi; pSecurityDescriptor
0x180076afa  lea     r8, [rbp+pDacl]; pDacl
0x180076afe  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180076b02  call    cs:__imp_GetSecurityDescriptorDacl
0x180076b09  nop     dword ptr [rax+rax+00h]
0x180076b0e  test    eax, eax
0x180076b10  jz      short loc_180076B1B
0x180076b12  cmp     [rbp+bDaclPresent], 0
0x180076b16  jz      short loc_180076B1B
0x180076b18  or      ebx, 4
0x180076b1b  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180076b1f  mov     rcx, rdi; pSecurityDescriptor
0x180076b22  lea     r8, [rbp+pSacl]; pSacl
0x180076b26  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180076b2a  call    cs:__imp_GetSecurityDescriptorSacl
0x180076b31  nop     dword ptr [rax+rax+00h]
0x180076b36  test    eax, eax
0x180076b38  jz      short loc_180076B43
0x180076b3a  cmp     [rbp+bDaclPresent], 0
0x180076b3e  jz      short loc_180076B43
0x180076b40  or      ebx, 8
0x180076b43  mov     rax, [rbp+pSacl]
0x180076b47  mov     r8d, ebx; SecurityInfo
0x180076b4a  mov     r9, [rbp+pOwner]; psidOwner
0x180076b4e  mov     edx, esi; ObjectType
0x180076b50  mov     [rsp+70h+var_40], rax; pSacl
0x180076b55  mov     rcx, r14; pObjectName
0x180076b58  mov     rax, [rbp+pDacl]
0x180076b5c  mov     [rsp+70h+var_48], rax; pDacl
0x180076b61  mov     rax, [rbp+pGroup]
0x180076b65  mov     [rsp+70h+psidGroup], rax; psidGroup
0x180076b6a  call    cs:__imp_SetNamedSecurityInfoW
0x180076b71  nop     dword ptr [rax+rax+00h]
0x180076b76  lea     r11, [rsp+70h+var_s0]
0x180076b7b  mov     rbx, [r11+20h]
0x180076b7f  mov     rsi, [r11+28h]
0x180076b83  mov     rsp, r11
0x180076b86  pop     r14
0x180076b88  pop     rdi
0x180076b89  pop     rbp
0x180076b8a  retn
```
