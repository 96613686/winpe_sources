# WcGrantFullAccessToAdmin

- ea: `0x18000d5d0`
- end: `0x18000d805`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000e320`

## callees

- `0x180002140`
- `0x18000d5d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d674`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d7be`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d7be`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d664`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d7d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d7d3`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18000d6c0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18000d6c0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d6ee`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d76a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d79c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d6ee`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d76a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d79c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000d734`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000d734`

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
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

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
0x18000d5d0  mov     [rsp-8+arg_18], rbx
0x18000d5d5  push    rbp
0x18000d5d6  push    rsi
0x18000d5d7  push    rdi
0x18000d5d8  push    r14
0x18000d5da  push    r15
0x18000d5dc  lea     rbp, [rsp-37h]
0x18000d5e1  sub     rsp, 0C0h
0x18000d5e8  mov     rax, cs:__security_cookie
0x18000d5ef  xor     rax, rsp
0x18000d5f2  mov     [rbp+57h+var_30], rax
0x18000d5f6  xor     r14d, r14d
0x18000d5f9  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000d5ff  xorps   xmm0, xmm0
0x18000d602  mov     [r8], r14
0x18000d605  lea     rax, [rbp+57h+psidOwner]
0x18000d609  mov     [rdx], r14
0x18000d60c  mov     [rsp+0E0h+pSid], rax; pSid
0x18000d611  mov     rbx, r8
0x18000d614  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18000d619  lea     r8d, [r14+20h]; nSubAuthority0
0x18000d61d  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18000d622  mov     rsi, rdx
0x18000d625  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18000d62a  mov     rdi, rcx
0x18000d62d  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18000d632  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d636  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18000d63b  mov     r9d, 220h; nSubAuthority1
0x18000d641  mov     dl, 2; nSubAuthorityCount
0x18000d643  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x18000d648  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18000d64c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18000d650  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18000d654  mov     [rbp+57h+psidOwner], r14
0x18000d658  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18000d65c  mov     [rbp+57h+NewAcl], r14
0x18000d660  mov     [rbp+57h+ppsidOwner], r14
0x18000d664  call    cs:__imp_AllocateAndInitializeSid
0x18000d66b  nop     dword ptr [rax+rax+00h]
0x18000d670  test    eax, eax
0x18000d672  jnz     short loc_18000D698
0x18000d674  call    cs:__imp_GetLastError
0x18000d67b  nop     dword ptr [rax+rax+00h]
0x18000d680  mov     ebx, eax
0x18000d682  test    eax, eax
0x18000d684  jle     loc_18000D7B5
0x18000d68a  movzx   ebx, ax
0x18000d68d  or      ebx, 80070000h
0x18000d693  jmp     loc_18000D7B5
0x18000d698  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x18000d69d  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18000d6a1  mov     r8d, 5; SecurityInfo
0x18000d6a7  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x18000d6ac  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x18000d6b1  mov     rcx, rdi; pObjectName
0x18000d6b4  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x18000d6b9  lea     r15d, [r8-4]
0x18000d6bd  mov     edx, r15d; ObjectType
0x18000d6c0  call    cs:__imp_GetNamedSecurityInfoW
0x18000d6c7  nop     dword ptr [rax+rax+00h]
0x18000d6cc  mov     ebx, eax
0x18000d6ce  test    eax, eax
0x18000d6d0  jnz     short loc_18000D684
0x18000d6d2  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x18000d6d6  mov     r8d, r15d; SecurityInfo
0x18000d6d9  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18000d6de  mov     edx, r15d; ObjectType
0x18000d6e1  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x18000d6e6  mov     rcx, rdi; pObjectName
0x18000d6e9  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18000d6ee  call    cs:__imp_SetNamedSecurityInfoW
0x18000d6f5  nop     dword ptr [rax+rax+00h]
0x18000d6fa  mov     ebx, eax
0x18000d6fc  test    eax, eax
0x18000d6fe  jnz     short loc_18000D684
0x18000d700  mov     rax, [rbp+57h+psidOwner]
0x18000d704  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18000d708  mov     r8, [rsi]; OldAcl
0x18000d70b  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18000d70f  mov     ecx, r15d; cCountOfExplicitEntries
0x18000d712  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18000d716  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18000d71d  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18000d725  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x18000d729  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x18000d72d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18000d734  call    cs:__imp_SetEntriesInAclW
0x18000d73b  nop     dword ptr [rax+rax+00h]
0x18000d740  mov     ebx, eax
0x18000d742  test    eax, eax
0x18000d744  jnz     loc_18000D684
0x18000d74a  mov     rax, [rbp+57h+NewAcl]
0x18000d74e  lea     r8d, [r15+3]; SecurityInfo
0x18000d752  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18000d757  xor     r9d, r9d; psidOwner
0x18000d75a  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x18000d75f  mov     edx, r15d; ObjectType
0x18000d762  mov     rcx, rdi; pObjectName
0x18000d765  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18000d76a  call    cs:__imp_SetNamedSecurityInfoW
0x18000d771  nop     dword ptr [rax+rax+00h]
0x18000d776  mov     ebx, eax
0x18000d778  test    eax, eax
0x18000d77a  jnz     loc_18000D684
0x18000d780  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x18000d784  mov     r8d, r15d; SecurityInfo
0x18000d787  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18000d78c  mov     edx, r15d; ObjectType
0x18000d78f  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x18000d794  mov     rcx, rdi; pObjectName
0x18000d797  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x18000d79c  call    cs:__imp_SetNamedSecurityInfoW
0x18000d7a3  nop     dword ptr [rax+rax+00h]
0x18000d7a8  mov     ebx, eax
0x18000d7aa  test    eax, eax
0x18000d7ac  jnz     loc_18000D684
0x18000d7b2  mov     ebx, r14d
0x18000d7b5  mov     rcx, [rbp+57h+psidOwner]; pSid
0x18000d7b9  test    rcx, rcx
0x18000d7bc  jz      short loc_18000D7CA
0x18000d7be  call    cs:__imp_FreeSid
0x18000d7c5  nop     dword ptr [rax+rax+00h]
0x18000d7ca  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18000d7ce  test    rcx, rcx
0x18000d7d1  jz      short loc_18000D7DF
0x18000d7d3  call    cs:__imp_LocalFree
0x18000d7da  nop     dword ptr [rax+rax+00h]
0x18000d7df  mov     eax, ebx
0x18000d7e1  mov     rcx, [rbp+57h+var_30]
0x18000d7e5  xor     rcx, rsp; StackCookie
0x18000d7e8  call    __security_check_cookie
0x18000d7ed  mov     rbx, [rsp+0E0h+arg_18]
0x18000d7f5  add     rsp, 0C0h
0x18000d7fc  pop     r15
0x18000d7fe  pop     r14
0x18000d800  pop     rdi
0x18000d801  pop     rsi
0x18000d802  pop     rbp
0x18000d803  retn
```
