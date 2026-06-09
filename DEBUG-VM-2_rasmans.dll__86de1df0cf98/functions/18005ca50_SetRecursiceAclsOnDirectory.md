# SetRecursiceAclsOnDirectory

- ea: `0x18005ca50`
- end: `0x18005cb94`
- name: `SetRecursiceAclsOnDirectory`
- size: `324`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007a880`

## callees

- `0x18005c94c`
- `0x18005ca50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005caae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005caae`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005cac9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005cac9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005cb05`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005cb05`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005caef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005caef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cb81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005caa4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005caa4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005cb3f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005cb70`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005cb3f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005cb70`

## pseudocode

```c
__int64 __fastcall SetRecursiceAclsOnDirectory(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)
{
  DWORD LastError; // eax
  unsigned int v4; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  PSID pGroup; // [rsp+48h] [rbp-18h] BYREF
  PSID pOwner; // [rsp+50h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+80h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+28h] BYREF

  bDaclDefaulted = 0;
  pDacl = 0;
  SecurityDescriptor = 0;
  pOwner = 0;
  pGroup = 0;
  bDaclPresent = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
    || !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    goto LABEL_2;
  }
  if ( !bDaclPresent )
  {
    v4 = 1338;
    goto LABEL_10;
  }
  if ( GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bDaclDefaulted)
    && GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bDaclDefaulted) )
  {
    SetPrivilege();
    SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 3u, pOwner, pGroup, 0, 0);
    LastError = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
  v4 = LastError;
LABEL_10:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x18005ca50  mov     [rsp-8+arg_0], rbx
0x18005ca55  mov     [rsp-8+bDaclDefaulted], r8d
0x18005ca5a  push    rbp
0x18005ca5b  mov     rbp, rsp
0x18005ca5e  sub     rsp, 60h
0x18005ca62  mov     rax, rdx
0x18005ca65  mov     [rbp+bDaclDefaulted], 0
0x18005ca6c  xor     r9d, r9d; SecurityDescriptorSize
0x18005ca6f  mov     [rbp+pDacl], 0
0x18005ca77  mov     rbx, rcx
0x18005ca7a  mov     [rbp+SecurityDescriptor], 0
0x18005ca82  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005ca86  mov     [rbp+pOwner], 0
0x18005ca8e  mov     rcx, rax; StringSecurityDescriptor
0x18005ca91  mov     [rbp+pGroup], 0
0x18005ca99  lea     edx, [r9+1]; StringSDRevision
0x18005ca9d  mov     [rbp+bDaclPresent], 0
0x18005caa4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005caaa  test    eax, eax
0x18005caac  jnz     short loc_18005CAB9
0x18005caae  call    cs:__imp_GetLastError
0x18005cab4  jmp     loc_18005CB76
0x18005cab9  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005cabd  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18005cac1  lea     r8, [rbp+pDacl]; pDacl
0x18005cac5  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18005cac9  call    cs:__imp_GetSecurityDescriptorDacl
0x18005cacf  test    eax, eax
0x18005cad1  jz      short loc_18005CAAE
0x18005cad3  cmp     [rbp+bDaclPresent], 0
0x18005cad7  jnz     short loc_18005CAE3
0x18005cad9  mov     ebx, 53Ah
0x18005cade  jmp     loc_18005CB78
0x18005cae3  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005cae7  lea     r8, [rbp+bDaclDefaulted]; lpbOwnerDefaulted
0x18005caeb  lea     rdx, [rbp+pOwner]; pOwner
0x18005caef  call    cs:__imp_GetSecurityDescriptorOwner
0x18005caf5  test    eax, eax
0x18005caf7  jz      short loc_18005CAAE
0x18005caf9  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005cafd  lea     r8, [rbp+bDaclDefaulted]; lpbGroupDefaulted
0x18005cb01  lea     rdx, [rbp+pGroup]; pGroup
0x18005cb05  call    cs:__imp_GetSecurityDescriptorGroup
0x18005cb0b  test    eax, eax
0x18005cb0d  jz      short loc_18005CAAE
0x18005cb0f  call    SetPrivilege
0x18005cb14  mov     rax, [rbp+pGroup]
0x18005cb18  mov     edx, 1; ObjectType
0x18005cb1d  mov     r9, [rbp+pOwner]; psidOwner
0x18005cb21  mov     rcx, rbx; pObjectName
0x18005cb24  mov     [rsp+60h+pSacl], 0; pSacl
0x18005cb2d  mov     [rsp+60h+var_38], 0; pDacl
0x18005cb36  lea     r8d, [rdx+2]; SecurityInfo
0x18005cb3a  mov     [rsp+60h+psidGroup], rax; psidGroup
0x18005cb3f  call    cs:__imp_SetNamedSecurityInfoW
0x18005cb45  mov     rax, [rbp+pDacl]
0x18005cb49  xor     r9d, r9d; psidOwner
0x18005cb4c  mov     [rsp+60h+pSacl], 0; pSacl
0x18005cb55  mov     r8d, 80000004h; SecurityInfo
0x18005cb5b  mov     [rsp+60h+var_38], rax; pDacl
0x18005cb60  mov     rcx, rbx; pObjectName
0x18005cb63  mov     [rsp+60h+psidGroup], 0; psidGroup
0x18005cb6c  lea     edx, [r9+1]; ObjectType
0x18005cb70  call    cs:__imp_SetNamedSecurityInfoW
0x18005cb76  mov     ebx, eax
0x18005cb78  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18005cb7c  test    rcx, rcx
0x18005cb7f  jz      short loc_18005CB87
0x18005cb81  call    cs:__imp_LocalFree
0x18005cb87  mov     eax, ebx
0x18005cb89  mov     rbx, [rsp+60h+arg_0]
0x18005cb8e  add     rsp, 60h
0x18005cb92  pop     rbp
0x18005cb93  retn
```
