# CTemplate::BuildPersistedDACL(_ACL * *)

- ea: `0x18001a628`
- end: `0x18001a761`
- name: `?BuildPersistedDACL@CTemplate@@AEAAJPEAPEAU_ACL@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(CTemplate *this, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800121c0`

## callees

- `0x18001a628`
- `0x180023dd0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001a6f9`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001a6f9`
- `ADVAPI32!FreeSid` at `0x18001a736`
- `ADVAPI32!FreeSid` at `0x18001a736`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18001a6d1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18001a6d1`
- `ADVAPI32!SetEntriesInAclW` at `0x18001a71d`
- `ADVAPI32!SetEntriesInAclW` at `0x18001a71d`
- `KERNEL32!GetLastError` at `0x18002f7e8`
- `KERNEL32!GetLastError` at `0x18002f7e8`

## pseudocode

```c
__int64 __fastcall CTemplate::BuildPersistedDACL(CTemplate *this, struct _ACL **a2)
{
  __int64 v2; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  BOOL bDaclPresent; // [rsp+60h] [rbp-9h] BYREF
  BOOL bDaclDefaulted; // [rsp+64h] [rbp-5h] BYREF
  PACL pDacl; // [rsp+68h] [rbp-1h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+37h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *a2 = 0;
  v2 = *((_QWORD *)this + 34);
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
  pListOfExplicitEntries.grfAccessPermissions = 1114112;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  if ( !*(_QWORD *)(*(_QWORD *)v2 + 64LL) )
    return 0;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          1u,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          (PSID *)&pListOfExplicitEntries.Trustee.ptstrName)
    || !GetSecurityDescriptorDacl(
          *(PSECURITY_DESCRIPTOR *)(**((_QWORD **)this + 34) + 64LL),
          &bDaclPresent,
          &pDacl,
          &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = LastError <= 0;
LABEL_10:
    if ( !v7 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_5;
  }
  LastError = SetEntriesInAclW(
                1u,
                &pListOfExplicitEntries,
                (PACL)((unsigned __int64)pDacl & -(__int64)bDaclPresent),
                a2);
  v6 = LastError;
  v7 = LastError <= 0;
  if ( LastError )
    goto LABEL_10;
LABEL_5:
  if ( pListOfExplicitEntries.Trustee.ptstrName )
    FreeSid(pListOfExplicitEntries.Trustee.ptstrName);
  return v6;
}

```

## disassembly

```asm
0x18001a628  mov     [rsp-8+arg_10], rbx
0x18001a62d  push    rbp
0x18001a62e  push    rsi
0x18001a62f  push    rdi
0x18001a630  lea     rbp, [rsp-47h]
0x18001a635  sub     rsp, 0B0h
0x18001a63c  mov     rax, cs:__security_cookie
0x18001a643  xor     rax, rsp
0x18001a646  mov     [rbp+57h+var_18], rax
0x18001a64a  xor     esi, esi
0x18001a64c  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x18001a652  mov     [rdx], rsi
0x18001a655  xorps   xmm0, xmm0
0x18001a658  mov     rax, [rcx+110h]
0x18001a65f  xorps   xmm1, xmm1
0x18001a662  mov     [rbp+57h+bDaclPresent], esi
0x18001a665  mov     rbx, rcx
0x18001a668  mov     [rbp+57h+bDaclDefaulted], esi
0x18001a66b  mov     rdi, rdx
0x18001a66e  mov     [rbp+57h+pDacl], rsi
0x18001a672  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18001a675  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x18001a67a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 110000h
0x18001a681  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm1
0x18001a686  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x18001a68d  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18001a694  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x18001a697  mov     rcx, [rax]
0x18001a69a  cmp     [rcx+40h], rsi
0x18001a69e  jz      loc_18001A75D
0x18001a6a4  lea     rax, [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName]
0x18001a6a8  xor     r9d, r9d; nSubAuthority1
0x18001a6ab  mov     [rsp+0C0h+pSid], rax; pSid
0x18001a6b0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001a6b4  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x18001a6b8  xor     r8d, r8d; nSubAuthority0
0x18001a6bb  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x18001a6bf  mov     dl, 1; nSubAuthorityCount
0x18001a6c1  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x18001a6c5  mov     [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x18001a6c9  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x18001a6cd  mov     [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x18001a6d1  call    cs:__imp_AllocateAndInitializeSid
0x18001a6d7  test    eax, eax
0x18001a6d9  jz      loc_18002F7E8
0x18001a6df  mov     rax, [rbx+110h]
0x18001a6e6  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18001a6ea  lea     r8, [rbp+57h+pDacl]; pDacl
0x18001a6ee  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18001a6f2  mov     rcx, [rax]
0x18001a6f5  mov     rcx, [rcx+40h]; pSecurityDescriptor
0x18001a6f9  call    cs:__imp_GetSecurityDescriptorDacl
0x18001a6ff  test    eax, eax
0x18001a701  jz      loc_18002F7E8
0x18001a707  mov     eax, [rbp+57h+bDaclPresent]
0x18001a70a  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001a70e  neg     eax
0x18001a710  lea     ecx, [rsi+1]; cCountOfExplicitEntries
0x18001a713  mov     r9, rdi; NewAcl
0x18001a716  sbb     r8, r8
0x18001a719  and     r8, [rbp+57h+pDacl]; OldAcl
0x18001a71d  call    cs:__imp_SetEntriesInAclW
0x18001a723  mov     ebx, eax
0x18001a725  test    eax, eax
0x18001a727  jnz     loc_18002F7F2
0x18001a72d  mov     rcx, [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName]; pSid
0x18001a731  test    rcx, rcx
0x18001a734  jz      short loc_18001A73C
0x18001a736  call    cs:__imp_FreeSid
0x18001a73c  mov     eax, ebx
0x18001a73e  mov     rcx, [rbp+57h+var_18]
0x18001a742  xor     rcx, rsp; StackCookie
0x18001a745  call    __security_check_cookie
0x18001a74a  mov     rbx, [rsp+0C0h+arg_10]
0x18001a752  add     rsp, 0B0h
0x18001a759  pop     rdi
0x18001a75a  pop     rsi
0x18001a75b  pop     rbp
0x18001a75c  retn
0x18001a75d  xor     eax, eax
0x18001a75f  jmp     short loc_18001A73E
0x18002f7e8  call    cs:__imp_GetLastError
0x18002f7ee  mov     ebx, eax
0x18002f7f0  test    eax, eax
0x18002f7f2  jle     loc_18001A72D
0x18002f7f8  movzx   ebx, ax
0x18002f7fb  or      ebx, 80070000h
0x18002f801  jmp     loc_18001A72D
```
