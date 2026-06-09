# WcGrantFullAccessToAdmin

- ea: `0x18018d6e4`
- end: `0x18018d919`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18018e0f4`

## callees

- `0x1800aed10`
- `0x18018d6e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d788`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18018d8d2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18018d8d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018d8e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018d8e7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18018d778`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18018d778`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18018d848`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18018d848`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d802`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d87e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d8b0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d802`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d87e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018d8b0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18018d7d4`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18018d7d4`

## pseudocode

```c
__int64 __fastcall WcGrantFullAccessToAdmin(
        LPWSTR pObjectName,
        PACL *ppDacl,
        PSECURITY_DESCRIPTOR *ppSecurityDescriptor)
{
  signed int NamedSecurityInfoW; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  struct _ACL *v9; // r8
  PSID psidOwner; // [rsp+60h] [rbp-29h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-21h] BYREF
  PSID ppsidOwner; // [rsp+70h] [rbp-19h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *ppSecurityDescriptor = 0;
  *ppDacl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  psidOwner = 0;
  NewAcl = 0;
  ppsidOwner = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           pObjectName,
                           SE_FILE_OBJECT,
                           5u,
                           &ppsidOwner,
                           0,
                           ppDacl,
                           0,
                           ppSecurityDescriptor);
    v7 = NamedSecurityInfoW;
    v8 = NamedSecurityInfoW <= 0;
    if ( !NamedSecurityInfoW )
    {
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
      v7 = NamedSecurityInfoW;
      v8 = NamedSecurityInfoW <= 0;
      if ( !NamedSecurityInfoW )
      {
        v9 = *ppDacl;
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
        pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
        *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
        pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
        pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
        NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, v9, &NewAcl);
        v7 = NamedSecurityInfoW;
        v8 = NamedSecurityInfoW <= 0;
        if ( !NamedSecurityInfoW )
        {
          NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
          v7 = NamedSecurityInfoW;
          v8 = NamedSecurityInfoW <= 0;
          if ( !NamedSecurityInfoW )
          {
            NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, ppsidOwner, 0, 0, 0);
            v7 = NamedSecurityInfoW;
            v8 = NamedSecurityInfoW <= 0;
            if ( !NamedSecurityInfoW )
            {
              v7 = 0;
              goto LABEL_11;
            }
          }
        }
      }
    }
  }
  else
  {
    NamedSecurityInfoW = GetLastError();
    v7 = NamedSecurityInfoW;
    v8 = NamedSecurityInfoW <= 0;
  }
  if ( !v8 )
    v7 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
LABEL_11:
  if ( psidOwner )
    FreeSid(psidOwner);
  if ( NewAcl )
    LocalFree(NewAcl);
  return v7;
}

```

## disassembly

```asm
0x18018d6e4  mov     [rsp-8+arg_18], rbx
0x18018d6e9  push    rbp
0x18018d6ea  push    rsi
0x18018d6eb  push    rdi
0x18018d6ec  push    r14
0x18018d6ee  push    r15
0x18018d6f0  lea     rbp, [rsp-37h]
0x18018d6f5  sub     rsp, 0C0h
0x18018d6fc  mov     rax, cs:__security_cookie
0x18018d703  xor     rax, rsp
0x18018d706  mov     [rbp+57h+var_30], rax
0x18018d70a  xor     r14d, r14d
0x18018d70d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18018d713  xorps   xmm0, xmm0
0x18018d716  mov     [r8], r14
0x18018d719  lea     rax, [rbp+57h+psidOwner]
0x18018d71d  mov     [rdx], r14
0x18018d720  mov     [rsp+0E0h+pSid], rax; pSid
0x18018d725  mov     rbx, r8
0x18018d728  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18018d72d  lea     r8d, [r14+20h]; nSubAuthority0
0x18018d731  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18018d736  mov     rsi, rdx
0x18018d739  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18018d73e  mov     rdi, rcx
0x18018d741  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18018d746  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18018d74a  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18018d74f  mov     r9d, 220h; nSubAuthority1
0x18018d755  mov     dl, 2; nSubAuthorityCount
0x18018d757  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x18018d75c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18018d760  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18018d764  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18018d768  mov     [rbp+57h+psidOwner], r14
0x18018d76c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18018d770  mov     [rbp+57h+NewAcl], r14
0x18018d774  mov     [rbp+57h+ppsidOwner], r14
0x18018d778  call    cs:__imp_AllocateAndInitializeSid
0x18018d77f  nop     dword ptr [rax+rax+00h]
0x18018d784  test    eax, eax
0x18018d786  jnz     short loc_18018D7AC
0x18018d788  call    cs:__imp_GetLastError
0x18018d78f  nop     dword ptr [rax+rax+00h]
0x18018d794  mov     ebx, eax
0x18018d796  test    eax, eax
0x18018d798  jle     loc_18018D8C9
0x18018d79e  movzx   ebx, ax
0x18018d7a1  or      ebx, 80070000h
0x18018d7a7  jmp     loc_18018D8C9
0x18018d7ac  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x18018d7b1  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18018d7b5  mov     r8d, 5; SecurityInfo
0x18018d7bb  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x18018d7c0  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x18018d7c5  mov     rcx, rdi; pObjectName
0x18018d7c8  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x18018d7cd  lea     r15d, [r8-4]
0x18018d7d1  mov     edx, r15d; ObjectType
0x18018d7d4  call    cs:__imp_GetNamedSecurityInfoW
0x18018d7db  nop     dword ptr [rax+rax+00h]
0x18018d7e0  mov     ebx, eax
0x18018d7e2  test    eax, eax
0x18018d7e4  jnz     short loc_18018D798
0x18018d7e6  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x18018d7ea  mov     r8d, r15d; SecurityInfo
0x18018d7ed  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18018d7f2  mov     edx, r15d; ObjectType
0x18018d7f5  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x18018d7fa  mov     rcx, rdi; pObjectName
0x18018d7fd  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18018d802  call    cs:__imp_SetNamedSecurityInfoW
0x18018d809  nop     dword ptr [rax+rax+00h]
0x18018d80e  mov     ebx, eax
0x18018d810  test    eax, eax
0x18018d812  jnz     short loc_18018D798
0x18018d814  mov     rax, [rbp+57h+psidOwner]
0x18018d818  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18018d81c  mov     r8, [rsi]; OldAcl
0x18018d81f  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18018d823  mov     ecx, r15d; cCountOfExplicitEntries
0x18018d826  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18018d82a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18018d831  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18018d839  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x18018d83d  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x18018d841  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18018d848  call    cs:__imp_SetEntriesInAclW
0x18018d84f  nop     dword ptr [rax+rax+00h]
0x18018d854  mov     ebx, eax
0x18018d856  test    eax, eax
0x18018d858  jnz     loc_18018D798
0x18018d85e  mov     rax, [rbp+57h+NewAcl]
0x18018d862  lea     r8d, [r15+3]; SecurityInfo
0x18018d866  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18018d86b  xor     r9d, r9d; psidOwner
0x18018d86e  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x18018d873  mov     edx, r15d; ObjectType
0x18018d876  mov     rcx, rdi; pObjectName
0x18018d879  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18018d87e  call    cs:__imp_SetNamedSecurityInfoW
0x18018d885  nop     dword ptr [rax+rax+00h]
0x18018d88a  mov     ebx, eax
0x18018d88c  test    eax, eax
0x18018d88e  jnz     loc_18018D798
0x18018d894  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x18018d898  mov     r8d, r15d; SecurityInfo
0x18018d89b  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18018d8a0  mov     edx, r15d; ObjectType
0x18018d8a3  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x18018d8a8  mov     rcx, rdi; pObjectName
0x18018d8ab  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18018d8b0  call    cs:__imp_SetNamedSecurityInfoW
0x18018d8b7  nop     dword ptr [rax+rax+00h]
0x18018d8bc  mov     ebx, eax
0x18018d8be  test    eax, eax
0x18018d8c0  jnz     loc_18018D798
0x18018d8c6  mov     ebx, r14d
0x18018d8c9  mov     rcx, [rbp+57h+psidOwner]; pSid
0x18018d8cd  test    rcx, rcx
0x18018d8d0  jz      short loc_18018D8DE
0x18018d8d2  call    cs:__imp_FreeSid
0x18018d8d9  nop     dword ptr [rax+rax+00h]
0x18018d8de  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18018d8e2  test    rcx, rcx
0x18018d8e5  jz      short loc_18018D8F3
0x18018d8e7  call    cs:__imp_LocalFree
0x18018d8ee  nop     dword ptr [rax+rax+00h]
0x18018d8f3  mov     eax, ebx
0x18018d8f5  mov     rcx, [rbp+57h+var_30]
0x18018d8f9  xor     rcx, rsp; StackCookie
0x18018d8fc  call    __security_check_cookie
0x18018d901  mov     rbx, [rsp+0E0h+arg_18]
0x18018d909  add     rsp, 0C0h
0x18018d910  pop     r15
0x18018d912  pop     r14
0x18018d914  pop     rdi
0x18018d915  pop     rsi
0x18018d916  pop     rbp
0x18018d917  retn
```
