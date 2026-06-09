# SetObjectSD

- ea: `0x180076dcc`
- end: `0x180076efc`
- name: `SetObjectSD`
- size: `304`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180076a84`

## callees

- `0x180076dcc`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x180076eda`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180076eda`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076e9a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076e9a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076e72`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076e72`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076e24`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076e24`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076e49`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076e49`

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
0x180076dcc  mov     [rsp-18h+arg_0], rbx
0x180076dd1  mov     [rsp-18h+arg_8], rsi
0x180076dd6  push    rbp
0x180076dd7  push    rdi
0x180076dd8  push    r14
0x180076dda  mov     rbp, rsp
0x180076ddd  sub     rsp, 70h
0x180076de1  mov     rdi, r8
0x180076de4  mov     [rbp+pOwner], 0
0x180076dec  mov     esi, edx
0x180076dee  mov     [rbp+pGroup], 0
0x180076df6  mov     r14, rcx
0x180076df9  mov     [rbp+pDacl], 0
0x180076e01  mov     rcx, rdi; pSecurityDescriptor
0x180076e04  mov     [rbp+pSacl], 0
0x180076e0c  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180076e10  mov     [rbp+bDaclPresent], 0
0x180076e17  lea     rdx, [rbp+pOwner]; pOwner
0x180076e1b  mov     [rbp+bOwnerDefaulted], 0
0x180076e22  xor     ebx, ebx
0x180076e24  call    cs:__imp_GetSecurityDescriptorOwner
0x180076e2b  nop     dword ptr [rax+rax+00h]
0x180076e30  test    eax, eax
0x180076e32  jz      short loc_180076E3E
0x180076e34  cmp     [rbp+pOwner], rbx
0x180076e38  lea     eax, [rbx+1]
0x180076e3b  cmovnz  ebx, eax
0x180076e3e  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180076e42  mov     rcx, rdi; pSecurityDescriptor
0x180076e45  lea     rdx, [rbp+pGroup]; pGroup
0x180076e49  call    cs:__imp_GetSecurityDescriptorGroup
0x180076e50  nop     dword ptr [rax+rax+00h]
0x180076e55  test    eax, eax
0x180076e57  jz      short loc_180076E63
0x180076e59  cmp     [rbp+pGroup], 0
0x180076e5e  jz      short loc_180076E63
0x180076e60  or      ebx, 2
0x180076e63  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x180076e67  mov     rcx, rdi; pSecurityDescriptor
0x180076e6a  lea     r8, [rbp+pDacl]; pDacl
0x180076e6e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180076e72  call    cs:__imp_GetSecurityDescriptorDacl
0x180076e79  nop     dword ptr [rax+rax+00h]
0x180076e7e  test    eax, eax
0x180076e80  jz      short loc_180076E8B
0x180076e82  cmp     [rbp+bDaclPresent], 0
0x180076e86  jz      short loc_180076E8B
0x180076e88  or      ebx, 4
0x180076e8b  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180076e8f  mov     rcx, rdi; pSecurityDescriptor
0x180076e92  lea     r8, [rbp+pSacl]; pSacl
0x180076e96  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180076e9a  call    cs:__imp_GetSecurityDescriptorSacl
0x180076ea1  nop     dword ptr [rax+rax+00h]
0x180076ea6  test    eax, eax
0x180076ea8  jz      short loc_180076EB3
0x180076eaa  cmp     [rbp+bDaclPresent], 0
0x180076eae  jz      short loc_180076EB3
0x180076eb0  or      ebx, 8
0x180076eb3  mov     rax, [rbp+pSacl]
0x180076eb7  mov     r8d, ebx; SecurityInfo
0x180076eba  mov     r9, [rbp+pOwner]; psidOwner
0x180076ebe  mov     edx, esi; ObjectType
0x180076ec0  mov     [rsp+70h+var_40], rax; pSacl
0x180076ec5  mov     rcx, r14; pObjectName
0x180076ec8  mov     rax, [rbp+pDacl]
0x180076ecc  mov     [rsp+70h+var_48], rax; pDacl
0x180076ed1  mov     rax, [rbp+pGroup]
0x180076ed5  mov     [rsp+70h+psidGroup], rax; psidGroup
0x180076eda  call    cs:__imp_SetNamedSecurityInfoW
0x180076ee1  nop     dword ptr [rax+rax+00h]
0x180076ee6  lea     r11, [rsp+70h+var_s0]
0x180076eeb  mov     rbx, [r11+20h]
0x180076eef  mov     rsi, [r11+28h]
0x180076ef3  mov     rsp, r11
0x180076ef6  pop     r14
0x180076ef8  pop     rdi
0x180076ef9  pop     rbp
0x180076efa  retn
```
