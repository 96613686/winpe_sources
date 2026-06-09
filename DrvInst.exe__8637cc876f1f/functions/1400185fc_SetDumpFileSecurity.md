# SetDumpFileSecurity

- ea: `0x1400185fc`
- end: `0x14001878b`
- name: `SetDumpFileSecurity`
- size: `399`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140016610`

## callees

- `0x1400185fc`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018673`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001875c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001876b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001875c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001876b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140018669`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400186ac`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140018669`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400186ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001874d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001874d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14001870e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14001870e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x14001873c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x14001873c`

## pseudocode

```c
__int64 __fastcall SetDumpFileSecurity(HANDLE handle)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  PACL NewAcl; // [rsp+60h] [rbp-59h] BYREF
  PSID v6; // [rsp+68h] [rbp-51h] BYREF
  PSID pSid; // [rsp+70h] [rbp-49h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-39h] BYREF
  int v9; // [rsp+B0h] [rbp-9h]
  int v10; // [rsp+B4h] [rbp-5h]
  __int64 v11; // [rsp+B8h] [rbp-1h]
  __int64 v12; // [rsp+C0h] [rbp+7h]
  __int64 v13; // [rsp+C8h] [rbp+Fh]
  __int64 v14; // [rsp+D0h] [rbp+17h]
  PSID v15; // [rsp+D8h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+E0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  NewAcl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v6 = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v6) )
  {
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 5;
    memset(&pListOfExplicitEntries.grfInheritance, 0, 24);
    v11 = 0;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    pListOfExplicitEntries.grfAccessPermissions = 269287424;
    v9 = 269287424;
    v15 = v6;
    v14 = 5;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    v10 = 2;
    v12 = 0;
    v13 = 0;
    v3 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl);
    if ( v3 )
      goto LABEL_7;
    LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, 0x80000004, 0, 0, NewAcl, 0);
  }
  else
  {
    LastError = GetLastError();
  }
  v3 = LastError;
LABEL_7:
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v6 )
    FreeSid(v6);
  if ( pSid )
    FreeSid(pSid);
  return v3;
}

```

## disassembly

```asm
0x1400185fc  push    rbp
0x1400185fe  push    rbx
0x1400185ff  push    rsi
0x140018600  push    rdi
0x140018601  lea     rbp, [rsp-3Fh]
0x140018606  sub     rsp, 0F8h
0x14001860d  mov     rax, cs:__security_cookie
0x140018614  xor     rax, rsp
0x140018617  mov     [rbp+57h+var_28], rax
0x14001861b  xor     esi, esi
0x14001861d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140018623  lea     rax, [rbp+57h+var_A0]
0x140018627  mov     [rbp+57h+NewAcl], rsi
0x14001862b  mov     [rsp+110h+pSid], rax; pSid
0x140018630  mov     rdi, rcx
0x140018633  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x140018637  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001863b  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x14001863f  lea     ebx, [rsi+2]
0x140018642  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x140018646  lea     r8d, [rsi+20h]; nSubAuthority0
0x14001864a  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x14001864e  mov     dl, bl; nSubAuthorityCount
0x140018650  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x140018654  mov     r9d, 220h; nSubAuthority1
0x14001865a  mov     [rsp+110h+nSubAuthority2], esi; nSubAuthority2
0x14001865e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140018661  mov     [rbp+57h+var_A8], rsi
0x140018665  mov     [rbp+57h+var_A0], rsi
0x140018669  call    cs:__imp_AllocateAndInitializeSid
0x14001866f  test    eax, eax
0x140018671  jnz     short loc_14001867E
0x140018673  call    cs:__imp_GetLastError
0x140018679  jmp     loc_140018742
0x14001867e  lea     rax, [rbp+57h+var_A8]
0x140018682  xor     r9d, r9d; nSubAuthority1
0x140018685  mov     [rsp+110h+pSid], rax; pSid
0x14001868a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001868e  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x140018692  mov     dl, 1; nSubAuthorityCount
0x140018694  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x140018698  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x14001869c  lea     r8d, [r9+12h]; nSubAuthority0
0x1400186a0  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x1400186a4  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x1400186a8  mov     [rsp+110h+nSubAuthority2], esi; nSubAuthority2
0x1400186ac  call    cs:__imp_AllocateAndInitializeSid
0x1400186b2  test    eax, eax
0x1400186b4  jz      short loc_140018673
0x1400186b6  xor     eax, eax
0x1400186b8  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1400186c0  mov     ecx, 100D0000h
0x1400186c5  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfInheritance], rax
0x1400186c9  mov     [rbp+57h+var_58], rax
0x1400186cd  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1400186d1  mov     rax, [rbp+57h+var_A0]
0x1400186d5  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1400186d9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1400186dd  xor     r8d, r8d; OldAcl
0x1400186e0  mov     rax, [rbp+57h+var_A8]
0x1400186e4  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x1400186e7  mov     [rbp+57h+var_60], ecx
0x1400186ea  mov     ecx, ebx; cCountOfExplicitEntries
0x1400186ec  mov     [rbp+57h+var_38], rax
0x1400186f0  mov     [rbp+57h+var_40], 5
0x1400186f8  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], ebx
0x1400186fb  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x1400186ff  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x140018703  mov     [rbp+57h+var_5C], ebx
0x140018706  mov     [rbp+57h+var_50], rsi
0x14001870a  mov     [rbp+57h+var_48], rsi
0x14001870e  call    cs:__imp_SetEntriesInAclW
0x140018714  mov     ebx, eax
0x140018716  test    eax, eax
0x140018718  jnz     short loc_140018744
0x14001871a  mov     rax, [rbp+57h+NewAcl]
0x14001871e  lea     edx, [rbx+1]; ObjectType
0x140018721  mov     qword ptr [rsp+110h+nSubAuthority4], rsi; pSacl
0x140018726  xor     r9d, r9d; psidOwner
0x140018729  mov     qword ptr [rsp+110h+nSubAuthority3], rax; pDacl
0x14001872e  mov     r8d, 80000004h; SecurityInfo
0x140018734  mov     rcx, rdi; handle
0x140018737  mov     qword ptr [rsp+110h+nSubAuthority2], rsi; psidGroup
0x14001873c  call    cs:__imp_SetSecurityInfo
0x140018742  mov     ebx, eax
0x140018744  mov     rcx, [rbp+57h+NewAcl]; hMem
0x140018748  test    rcx, rcx
0x14001874b  jz      short loc_140018753
0x14001874d  call    cs:__imp_LocalFree
0x140018753  mov     rcx, [rbp+57h+var_A8]; pSid
0x140018757  test    rcx, rcx
0x14001875a  jz      short loc_140018762
0x14001875c  call    cs:__imp_FreeSid
0x140018762  mov     rcx, [rbp+57h+var_A0]; pSid
0x140018766  test    rcx, rcx
0x140018769  jz      short loc_140018771
0x14001876b  call    cs:__imp_FreeSid
0x140018771  mov     eax, ebx
0x140018773  mov     rcx, [rbp+57h+var_28]
0x140018777  xor     rcx, rsp; StackCookie
0x14001877a  call    __security_check_cookie
0x14001877f  add     rsp, 0F8h
0x140018786  pop     rdi
0x140018787  pop     rsi
0x140018788  pop     rbx
0x140018789  pop     rbp
0x14001878a  retn
```
