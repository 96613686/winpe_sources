# ABO_MAPPER_LOG::SetAdminACLOnLogFile(ushort const *)

- ea: `0x1800270a4`
- end: `0x1800271dc`
- name: `?SetAdminACLOnLogFile@ABO_MAPPER_LOG@@QEAAJPEBG@Z`
- size: `312`
- prototype: `__int64 __fastcall(ABO_MAPPER_LOG *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001500`

## callees

- `0x180003460`
- `0x1800270a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002713a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002713a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271a4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180027130`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180027130`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800271b3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800271b3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180027160`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180027160`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180027193`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180027193`

## pseudocode

```c
__int64 __fastcall ABO_MAPPER_LOG::SetAdminACLOnLogFile(ABO_MAPPER_LOG *this, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  signed int v3; // ebx
  PACL NewAcl; // [rsp+68h] [rbp+7h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp+Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  NewAcl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
  pListOfExplicitEntries.grfAccessPermissions = 269484032;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  if ( AllocateAndInitializeSid(
         &pIdentifierAuthority,
         2u,
         0x20u,
         0x220u,
         0,
         0,
         0,
         0,
         0,
         0,
         (PSID *)&pListOfExplicitEntries.Trustee.ptstrName) )
  {
    v3 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
    if ( v3 >= 0 )
      v3 = SetNamedSecurityInfoW((LPWSTR)L"abomapper.log", SE_FILE_OBJECT, 0x80000004, 0, 0, NewAcl, 0);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pListOfExplicitEntries.Trustee.ptstrName )
    FreeSid(pListOfExplicitEntries.Trustee.ptstrName);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800270a4  mov     r11, rsp
0x1800270a7  mov     [r11+8], rbx
0x1800270ab  mov     [r11+10h], rdi
0x1800270af  push    rbp
0x1800270b0  lea     rbp, [r11-5Fh]
0x1800270b4  sub     rsp, 0B0h
0x1800270bb  mov     rax, cs:__security_cookie
0x1800270c2  xor     rax, rsp
0x1800270c5  mov     [rbp+57h+var_10], rax
0x1800270c9  xor     edi, edi
0x1800270cb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800270d1  lea     rax, [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName]
0x1800270d5  mov     [rbp+57h+NewAcl], rdi
0x1800270d9  mov     [r11-68h], rax
0x1800270dd  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800270e1  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x1800270e5  xorps   xmm0, xmm0
0x1800270e8  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x1800270ec  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800270f0  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x1800270f4  xorps   xmm1, xmm1
0x1800270f7  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x1800270fb  mov     r9d, 220h; nSubAuthority1
0x180027101  mov     [rsp+0B0h+nSubAuthority3], edi; nSubAuthority3
0x180027105  mov     dl, 2; nSubAuthorityCount
0x180027107  mov     [rsp+0B0h+nSubAuthority2], edi; nSubAuthority2
0x18002710b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18002710e  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x180027113  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10100000h
0x18002711a  movdqu  xmmword ptr [rbp+2Fh], xmm1
0x18002711f  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180027126  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18002712d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x180027130  call    cs:__imp_AllocateAndInitializeSid
0x180027136  test    eax, eax
0x180027138  jnz     short loc_180027151
0x18002713a  call    cs:__imp_GetLastError
0x180027140  mov     ebx, eax
0x180027142  test    eax, eax
0x180027144  jle     short loc_18002719B
0x180027146  movzx   ebx, ax
0x180027149  or      ebx, 80070000h
0x18002714f  jmp     short loc_18002719B
0x180027151  xor     r8d, r8d; OldAcl
0x180027154  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180027158  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002715c  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x180027160  call    cs:__imp_SetEntriesInAclW
0x180027166  mov     ebx, eax
0x180027168  test    eax, eax
0x18002716a  js      short loc_18002719B
0x18002716c  mov     rax, [rbp+57h+NewAcl]
0x180027170  lea     rcx, pObjectName; "abomapper.log"
0x180027177  xor     r9d, r9d; psidOwner
0x18002717a  mov     qword ptr [rsp+0B0h+nSubAuthority4], rdi; pSacl
0x18002717f  mov     qword ptr [rsp+0B0h+nSubAuthority3], rax; pDacl
0x180027184  mov     r8d, 80000004h; SecurityInfo
0x18002718a  mov     qword ptr [rsp+0B0h+nSubAuthority2], rdi; psidGroup
0x18002718f  lea     edx, [r9+1]; ObjectType
0x180027193  call    cs:__imp_SetNamedSecurityInfoW
0x180027199  mov     ebx, eax
0x18002719b  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18002719f  test    rcx, rcx
0x1800271a2  jz      short loc_1800271AA
0x1800271a4  call    cs:__imp_LocalFree
0x1800271aa  mov     rcx, [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName]; pSid
0x1800271ae  test    rcx, rcx
0x1800271b1  jz      short loc_1800271B9
0x1800271b3  call    cs:__imp_FreeSid
0x1800271b9  mov     eax, ebx
0x1800271bb  mov     rcx, [rbp+57h+var_10]
0x1800271bf  xor     rcx, rsp; StackCookie
0x1800271c2  call    __security_check_cookie
0x1800271c7  lea     r11, [rsp+0B0h+var_s0]
0x1800271cf  mov     rbx, [r11+10h]
0x1800271d3  mov     rdi, [r11+18h]
0x1800271d7  mov     rsp, r11
0x1800271da  pop     rbp
0x1800271db  retn
```
