# AddAdminAccess(ushort const *)

- ea: `0x18001a558`
- end: `0x18001a69f`
- name: `?AddAdminAccess@@YAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001a6a8`

## callees

- `0x18001a558`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a686`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18001a5c2`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18001a5c2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001a65e`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001a65e`
- `ADVAPI32!SetEntriesInAclW` at `0x18001a62a`
- `ADVAPI32!SetEntriesInAclW` at `0x18001a62a`

## pseudocode

```c
__int64 __fastcall AddAdminAccess(LPWSTR pObjectName)
{
  signed int NamedSecurityInfoW; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+40h] [rbp-30h] BYREF
  PACL NewAcl; // [rsp+98h] [rbp+28h] BYREF
  PACL OldAcl; // [rsp+A0h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+38h] BYREF

  hMem = 0;
  OldAcl = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  v3 = NamedSecurityInfoW;
  v4 = NamedSecurityInfoW <= 0;
  if ( NamedSecurityInfoW )
    goto LABEL_2;
  pListOfExplicitEntries.Trustee.ptstrName = L"Administrators";
  *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
  pListOfExplicitEntries.grfAccessPermissions = 2032127;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_NAME;
  NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  v3 = NamedSecurityInfoW;
  v4 = NamedSecurityInfoW <= 0;
  if ( NamedSecurityInfoW
    || (NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0),
        v3 = NamedSecurityInfoW,
        v4 = NamedSecurityInfoW <= 0,
        NamedSecurityInfoW) )
  {
LABEL_2:
    if ( !v4 )
      v3 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
  return v3;
}

```

## disassembly

```asm
0x18001a558  mov     r11, rsp
0x18001a55b  mov     [r11+8], rbx
0x18001a55f  push    rbp
0x18001a560  push    rdi
0x18001a561  push    r14
0x18001a563  mov     rbp, rsp
0x18001a566  sub     rsp, 70h
0x18001a56a  xorps   xmm0, xmm0
0x18001a56d  mov     [rbp+hMem], 0
0x18001a575  xor     r9d, r9d; ppsidOwner
0x18001a578  mov     [rbp+OldAcl], 0
0x18001a580  lea     rax, [rbp+hMem]
0x18001a584  mov     [rbp+NewAcl], 0
0x18001a58c  mov     [r11-50h], rax
0x18001a590  mov     rdi, rcx
0x18001a593  mov     qword ptr [r11-58h], 0
0x18001a59b  lea     rax, [rbp+OldAcl]
0x18001a59f  lea     r14d, [r9+1]
0x18001a5a3  mov     [r11-60h], rax
0x18001a5a7  mov     edx, r14d; ObjectType
0x18001a5aa  mov     qword ptr [r11-68h], 0
0x18001a5b2  lea     r8d, [r9+4]; SecurityInfo
0x18001a5b6  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18001a5ba  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001a5be  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18001a5c2  call    cs:__imp_GetNamedSecurityInfoW
0x18001a5c8  mov     ebx, eax
0x18001a5ca  test    eax, eax
0x18001a5cc  jz      short loc_18001A5E2
0x18001a5ce  jle     loc_18001A66E
0x18001a5d4  movzx   ebx, ax
0x18001a5d7  or      ebx, 80070000h
0x18001a5dd  jmp     loc_18001A66E
0x18001a5e2  mov     r8, [rbp+OldAcl]; OldAcl
0x18001a5e6  lea     rax, aAdministrators; "Administrators"
0x18001a5ed  lea     r9, [rbp+NewAcl]; NewAcl
0x18001a5f1  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18001a5f5  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001a5f9  mov     qword ptr [rbp+pListOfExplicitEntries.grfInheritance], 3
0x18001a601  mov     ecx, r14d; cCountOfExplicitEntries
0x18001a604  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18001a60c  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 1F01FFh
0x18001a613  mov     [rbp+pListOfExplicitEntries.grfAccessMode], r14d
0x18001a617  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x18001a61f  mov     [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x18001a626  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18001a62a  call    cs:__imp_SetEntriesInAclW
0x18001a630  mov     ebx, eax
0x18001a632  test    eax, eax
0x18001a634  jnz     short loc_18001A5CE
0x18001a636  mov     rax, [rbp+NewAcl]
0x18001a63a  lea     r8d, [rbx+4]; SecurityInfo
0x18001a63e  mov     [rsp+70h+pSacl], 0; pSacl
0x18001a647  xor     r9d, r9d; psidOwner
0x18001a64a  mov     [rsp+70h+pDacl], rax; pDacl
0x18001a64f  mov     edx, r14d; ObjectType
0x18001a652  mov     rcx, rdi; pObjectName
0x18001a655  mov     [rsp+70h+psidGroup], 0; psidGroup
0x18001a65e  call    cs:__imp_SetNamedSecurityInfoW
0x18001a664  mov     ebx, eax
0x18001a666  test    eax, eax
0x18001a668  jnz     loc_18001A5CE
0x18001a66e  mov     rcx, [rbp+NewAcl]; hMem
0x18001a672  test    rcx, rcx
0x18001a675  jz      short loc_18001A67D
0x18001a677  call    cs:__imp_LocalFree
0x18001a67d  mov     rcx, [rbp+hMem]; hMem
0x18001a681  test    rcx, rcx
0x18001a684  jz      short loc_18001A68C
0x18001a686  call    cs:__imp_LocalFree
0x18001a68c  mov     eax, ebx
0x18001a68e  mov     rbx, [rsp+70h+arg_0]
0x18001a696  add     rsp, 70h
0x18001a69a  pop     r14
0x18001a69c  pop     rdi
0x18001a69d  pop     rbp
0x18001a69e  retn
```
