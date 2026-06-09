# WcGrantFullAccessToAdmin

- ea: `0x1800351f8`
- end: `0x18003542d`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800364bc`

## callees

- `0x180004bd0`
- `0x1800351f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800353e6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800353e6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003528c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003528c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003529c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003529c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353fb`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035316`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035392`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800353c4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035316`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035392`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800353c4`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800352e8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800352e8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003535c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003535c`

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
0x1800351f8  mov     [rsp-8+arg_18], rbx
0x1800351fd  push    rbp
0x1800351fe  push    rsi
0x1800351ff  push    rdi
0x180035200  push    r14
0x180035202  push    r15
0x180035204  lea     rbp, [rsp-37h]
0x180035209  sub     rsp, 0C0h
0x180035210  mov     rax, cs:__security_cookie
0x180035217  xor     rax, rsp
0x18003521a  mov     [rbp+57h+var_30], rax
0x18003521e  xor     r14d, r14d
0x180035221  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180035227  xorps   xmm0, xmm0
0x18003522a  mov     [r8], r14
0x18003522d  lea     rax, [rbp+57h+psidOwner]
0x180035231  mov     [rdx], r14
0x180035234  mov     [rsp+0E0h+pSid], rax; pSid
0x180035239  mov     rbx, r8
0x18003523c  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x180035241  lea     r8d, [r14+20h]; nSubAuthority0
0x180035245  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18003524a  mov     rsi, rdx
0x18003524d  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x180035252  mov     rdi, rcx
0x180035255  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18003525a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003525e  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x180035263  mov     r9d, 220h; nSubAuthority1
0x180035269  mov     dl, 2; nSubAuthorityCount
0x18003526b  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x180035270  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180035274  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180035278  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18003527c  mov     [rbp+57h+psidOwner], r14
0x180035280  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180035284  mov     [rbp+57h+NewAcl], r14
0x180035288  mov     [rbp+57h+ppsidOwner], r14
0x18003528c  call    cs:__imp_AllocateAndInitializeSid
0x180035293  nop     dword ptr [rax+rax+00h]
0x180035298  test    eax, eax
0x18003529a  jnz     short loc_1800352C0
0x18003529c  call    cs:__imp_GetLastError
0x1800352a3  nop     dword ptr [rax+rax+00h]
0x1800352a8  mov     ebx, eax
0x1800352aa  test    eax, eax
0x1800352ac  jle     loc_1800353DD
0x1800352b2  movzx   ebx, ax
0x1800352b5  or      ebx, 80070000h
0x1800352bb  jmp     loc_1800353DD
0x1800352c0  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x1800352c5  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x1800352c9  mov     r8d, 5; SecurityInfo
0x1800352cf  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x1800352d4  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x1800352d9  mov     rcx, rdi; pObjectName
0x1800352dc  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x1800352e1  lea     r15d, [r8-4]
0x1800352e5  mov     edx, r15d; ObjectType
0x1800352e8  call    cs:__imp_GetNamedSecurityInfoW
0x1800352ef  nop     dword ptr [rax+rax+00h]
0x1800352f4  mov     ebx, eax
0x1800352f6  test    eax, eax
0x1800352f8  jnz     short loc_1800352AC
0x1800352fa  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x1800352fe  mov     r8d, r15d; SecurityInfo
0x180035301  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x180035306  mov     edx, r15d; ObjectType
0x180035309  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x18003530e  mov     rcx, rdi; pObjectName
0x180035311  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x180035316  call    cs:__imp_SetNamedSecurityInfoW
0x18003531d  nop     dword ptr [rax+rax+00h]
0x180035322  mov     ebx, eax
0x180035324  test    eax, eax
0x180035326  jnz     short loc_1800352AC
0x180035328  mov     rax, [rbp+57h+psidOwner]
0x18003532c  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180035330  mov     r8, [rsi]; OldAcl
0x180035333  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180035337  mov     ecx, r15d; cCountOfExplicitEntries
0x18003533a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18003533e  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180035345  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18003534d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x180035351  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x180035355  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18003535c  call    cs:__imp_SetEntriesInAclW
0x180035363  nop     dword ptr [rax+rax+00h]
0x180035368  mov     ebx, eax
0x18003536a  test    eax, eax
0x18003536c  jnz     loc_1800352AC
0x180035372  mov     rax, [rbp+57h+NewAcl]
0x180035376  lea     r8d, [r15+3]; SecurityInfo
0x18003537a  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x18003537f  xor     r9d, r9d; psidOwner
0x180035382  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x180035387  mov     edx, r15d; ObjectType
0x18003538a  mov     rcx, rdi; pObjectName
0x18003538d  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x180035392  call    cs:__imp_SetNamedSecurityInfoW
0x180035399  nop     dword ptr [rax+rax+00h]
0x18003539e  mov     ebx, eax
0x1800353a0  test    eax, eax
0x1800353a2  jnz     loc_1800352AC
0x1800353a8  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x1800353ac  mov     r8d, r15d; SecurityInfo
0x1800353af  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800353b4  mov     edx, r15d; ObjectType
0x1800353b7  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x1800353bc  mov     rcx, rdi; pObjectName
0x1800353bf  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800353c4  call    cs:__imp_SetNamedSecurityInfoW
0x1800353cb  nop     dword ptr [rax+rax+00h]
0x1800353d0  mov     ebx, eax
0x1800353d2  test    eax, eax
0x1800353d4  jnz     loc_1800352AC
0x1800353da  mov     ebx, r14d
0x1800353dd  mov     rcx, [rbp+57h+psidOwner]; pSid
0x1800353e1  test    rcx, rcx
0x1800353e4  jz      short loc_1800353F2
0x1800353e6  call    cs:__imp_FreeSid
0x1800353ed  nop     dword ptr [rax+rax+00h]
0x1800353f2  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800353f6  test    rcx, rcx
0x1800353f9  jz      short loc_180035407
0x1800353fb  call    cs:__imp_LocalFree
0x180035402  nop     dword ptr [rax+rax+00h]
0x180035407  mov     eax, ebx
0x180035409  mov     rcx, [rbp+57h+var_30]
0x18003540d  xor     rcx, rsp; StackCookie
0x180035410  call    __security_check_cookie
0x180035415  mov     rbx, [rsp+0E0h+arg_18]
0x18003541d  add     rsp, 0C0h
0x180035424  pop     r15
0x180035426  pop     r14
0x180035428  pop     rdi
0x180035429  pop     rsi
0x18003542a  pop     rbp
0x18003542b  retn
```
