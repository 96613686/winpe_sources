# GrantAccessToSpecifiedUsers(ushort const *,_TypeFolderAccessNeeded)

- ea: `0x18000d530`
- end: `0x18000d8fb`
- name: `?GrantAccessToSpecifiedUsers@@YAJPEBGW4_TypeFolderAccessNeeded@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(WCHAR *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b020`
- `0x18000bc10`

## callees

- `0x180009f60`
- `0x18000d530`
- `0x180034070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8d5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d8ea`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d8ea`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d5f7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d707`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d5f7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d707`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d675`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d675`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18000d5a8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18000d5a8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000d63d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000d63d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GrantAccessToSpecifiedUsers(WCHAR *a1, int a2)
{
  unsigned int v4; // ebx
  signed int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  signed int v9; // eax
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // eax
  PACL NewAcl; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+70h] [rbp-19h] BYREF
  PACL OldAcl; // [rsp+78h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  OldAcl = 0;
  hMem = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  NewAcl = 0;
  if ( GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 56;
    goto LABEL_43;
  }
  if ( !a2 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
      goto LABEL_5;
    }
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 58;
LABEL_43:
    WPP_SF_d(v7[2], v8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v4);
    goto LABEL_8;
  }
  if ( a2 != 1 )
  {
    v4 = -2147024809;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v8 = 59;
      goto LABEL_43;
    }
    goto LABEL_8;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 57;
    goto LABEL_43;
  }
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
LABEL_5:
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  pListOfExplicitEntries.grfAccessPermissions = 2;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl) )
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 60;
    goto LABEL_43;
  }
  if ( !SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0) )
  {
    v4 = 0;
    goto LABEL_8;
  }
  v12 = GetLastError();
  v4 = v12;
  if ( v12 > 0 )
    v4 = (unsigned __int16)v12 | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v8 = 61;
    goto LABEL_43;
  }
LABEL_8:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  if ( pSid )
    FreeSid(pSid);
  return v4;
}

```

## disassembly

```asm
0x18000d530  push    rbp
0x18000d532  push    rbx
0x18000d533  push    rsi
0x18000d534  push    rdi
0x18000d535  lea     rbp, [rsp-3Fh]
0x18000d53a  sub     rsp, 0C8h
0x18000d541  mov     rax, cs:__security_cookie
0x18000d548  xor     rax, rsp
0x18000d54b  mov     [rbp+57h+var_28], rax
0x18000d54f  xor     esi, esi
0x18000d551  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000d557  xorps   xmm0, xmm0
0x18000d55a  mov     [rbp+57h+OldAcl], rsi
0x18000d55e  lea     rax, [rbp+57h+hMem]
0x18000d562  mov     [rbp+57h+hMem], rsi
0x18000d566  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000d56b  mov     ebx, edx
0x18000d56d  lea     rax, [rbp+57h+OldAcl]
0x18000d571  mov     [rsp+0E0h+ppSacl], rsi; ppSacl
0x18000d576  mov     [rsp+0E0h+ppDacl], rax; ppDacl
0x18000d57b  xor     r9d, r9d; ppsidOwner
0x18000d57e  mov     edx, 1; ObjectType
0x18000d583  mov     [rsp+0E0h+ppsidGroup], rsi; ppsidGroup
0x18000d588  mov     r8d, 4; SecurityInfo
0x18000d58e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000d591  mov     rdi, rcx
0x18000d594  mov     [rbp+57h+var_78], rsi
0x18000d598  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18000d59c  mov     [rbp+57h+NewAcl], rsi
0x18000d5a0  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18000d5a4  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18000d5a8  call    cs:__imp_GetNamedSecurityInfoW
0x18000d5af  nop     dword ptr [rax+rax+00h]
0x18000d5b4  test    eax, eax
0x18000d5b6  jnz     loc_18000D7A6
0x18000d5bc  test    ebx, ebx
0x18000d5be  jnz     loc_18000D6CD
0x18000d5c4  lea     rax, [rbp+57h+var_78]
0x18000d5c8  mov     r9d, 220h; nSubAuthority1
0x18000d5ce  mov     [rsp+0E0h+pSid], rax; pSid
0x18000d5d3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d5d7  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x18000d5db  mov     r8d, 20h ; ' '; nSubAuthority0
0x18000d5e1  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x18000d5e5  mov     dl, 2; nSubAuthorityCount
0x18000d5e7  mov     dword ptr [rsp+0E0h+ppSecurityDescriptor], esi; nSubAuthority5
0x18000d5eb  mov     dword ptr [rsp+0E0h+ppSacl], esi; nSubAuthority4
0x18000d5ef  mov     dword ptr [rsp+0E0h+ppDacl], esi; nSubAuthority3
0x18000d5f3  mov     dword ptr [rsp+0E0h+ppsidGroup], esi; nSubAuthority2
0x18000d5f7  call    cs:__imp_AllocateAndInitializeSid
0x18000d5fe  nop     dword ptr [rax+rax+00h]
0x18000d603  test    eax, eax
0x18000d605  jz      loc_18000D723
0x18000d60b  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18000d612  mov     rax, [rbp+57h+var_78]
0x18000d616  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18000d61a  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x18000d61e  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18000d622  mov     ecx, 1; cCountOfExplicitEntries
0x18000d627  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18000d62b  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 2
0x18000d632  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18000d63a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x18000d63d  call    cs:__imp_SetEntriesInAclW
0x18000d644  nop     dword ptr [rax+rax+00h]
0x18000d649  test    eax, eax
0x18000d64b  jnz     loc_18000D7F7
0x18000d651  mov     rax, [rbp+57h+NewAcl]
0x18000d655  xor     r9d, r9d; psidOwner
0x18000d658  mov     [rsp+0E0h+ppSacl], rsi; pSacl
0x18000d65d  mov     edx, 1; ObjectType
0x18000d662  mov     [rsp+0E0h+ppDacl], rax; pDacl
0x18000d667  mov     r8d, 4; SecurityInfo
0x18000d66d  mov     rcx, rdi; pObjectName
0x18000d670  mov     [rsp+0E0h+ppsidGroup], rsi; psidGroup
0x18000d675  call    cs:__imp_SetNamedSecurityInfoW
0x18000d67c  nop     dword ptr [rax+rax+00h]
0x18000d681  test    eax, eax
0x18000d683  jnz     loc_18000D83A
0x18000d689  mov     ebx, esi
0x18000d68b  mov     rcx, [rbp+57h+hMem]; hMem
0x18000d68f  test    rcx, rcx
0x18000d692  jnz     loc_18000D8C0
0x18000d698  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18000d69c  test    rcx, rcx
0x18000d69f  jnz     loc_18000D8D5
0x18000d6a5  mov     rcx, [rbp+57h+var_78]; pSid
0x18000d6a9  test    rcx, rcx
0x18000d6ac  jnz     loc_18000D8EA
0x18000d6b2  mov     eax, ebx
0x18000d6b4  mov     rcx, [rbp+57h+var_28]
0x18000d6b8  xor     rcx, rsp; StackCookie
0x18000d6bb  call    __security_check_cookie
0x18000d6c0  add     rsp, 0C8h
0x18000d6c7  pop     rdi
0x18000d6c8  pop     rsi
0x18000d6c9  pop     rbx
0x18000d6ca  pop     rbp
0x18000d6cb  retn
0x18000d6cd  cmp     ebx, 1
0x18000d6d0  jnz     loc_18000D893
0x18000d6d6  lea     rax, [rbp+57h+var_78]
0x18000d6da  xor     r9d, r9d; nSubAuthority1
0x18000d6dd  mov     [rsp+0E0h+pSid], rax; pSid
0x18000d6e2  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d6e6  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x18000d6ea  mov     r8d, 0Bh; nSubAuthority0
0x18000d6f0  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x18000d6f4  movzx   edx, bl; nSubAuthorityCount
0x18000d6f7  mov     dword ptr [rsp+0E0h+ppSecurityDescriptor], esi; nSubAuthority5
0x18000d6fb  mov     dword ptr [rsp+0E0h+ppSacl], esi; nSubAuthority4
0x18000d6ff  mov     dword ptr [rsp+0E0h+ppDacl], esi; nSubAuthority3
0x18000d703  mov     dword ptr [rsp+0E0h+ppsidGroup], esi; nSubAuthority2
0x18000d707  call    cs:__imp_AllocateAndInitializeSid
0x18000d70e  nop     dword ptr [rax+rax+00h]
0x18000d713  test    eax, eax
0x18000d715  jz      short loc_18000D769
0x18000d717  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18000d71e  jmp     loc_18000D612
0x18000d723  call    cs:__imp_GetLastError
0x18000d72a  nop     dword ptr [rax+rax+00h]
0x18000d72f  mov     ebx, eax
0x18000d731  test    eax, eax
0x18000d733  jle     short loc_18000D73E
0x18000d735  movzx   ebx, ax
0x18000d738  or      ebx, 80070000h
0x18000d73e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d745  lea     rax, WPP_GLOBAL_Control
0x18000d74c  cmp     rcx, rax
0x18000d74f  jz      loc_18000D68B
0x18000d755  test    byte ptr [rcx+1Ch], 40h
0x18000d759  jz      loc_18000D68B
0x18000d75f  mov     edx, 3Ah ; ':'
0x18000d764  jmp     loc_18000D87B
0x18000d769  call    cs:__imp_GetLastError
0x18000d770  nop     dword ptr [rax+rax+00h]
0x18000d775  mov     ebx, eax
0x18000d777  test    eax, eax
0x18000d779  jg      short loc_18000D7EC
0x18000d77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d782  lea     rax, WPP_GLOBAL_Control
0x18000d789  cmp     rcx, rax
0x18000d78c  jz      loc_18000D68B
0x18000d792  test    byte ptr [rcx+1Ch], 40h
0x18000d796  jz      loc_18000D68B
0x18000d79c  mov     edx, 39h ; '9'
0x18000d7a1  jmp     loc_18000D87B
0x18000d7a6  call    cs:__imp_GetLastError
0x18000d7ad  nop     dword ptr [rax+rax+00h]
0x18000d7b2  mov     ebx, eax
0x18000d7b4  test    eax, eax
0x18000d7b6  jle     short loc_18000D7C1
0x18000d7b8  movzx   ebx, ax
0x18000d7bb  or      ebx, 80070000h
0x18000d7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7c8  lea     rax, WPP_GLOBAL_Control
0x18000d7cf  cmp     rcx, rax
0x18000d7d2  jz      loc_18000D68B
0x18000d7d8  test    byte ptr [rcx+1Ch], 40h
0x18000d7dc  jz      loc_18000D68B
0x18000d7e2  mov     edx, 38h ; '8'
0x18000d7e7  jmp     loc_18000D87B
0x18000d7ec  movzx   ebx, ax
0x18000d7ef  or      ebx, 80070000h
0x18000d7f5  jmp     short loc_18000D77B
0x18000d7f7  call    cs:__imp_GetLastError
0x18000d7fe  nop     dword ptr [rax+rax+00h]
0x18000d803  mov     ebx, eax
0x18000d805  test    eax, eax
0x18000d807  jle     short loc_18000D812
0x18000d809  movzx   ebx, ax
0x18000d80c  or      ebx, 80070000h
0x18000d812  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d819  lea     rax, WPP_GLOBAL_Control
0x18000d820  cmp     rcx, rax
0x18000d823  jz      loc_18000D68B
0x18000d829  test    byte ptr [rcx+1Ch], 40h
0x18000d82d  jz      loc_18000D68B
0x18000d833  mov     edx, 3Ch ; '<'
0x18000d838  jmp     short loc_18000D87B
0x18000d83a  call    cs:__imp_GetLastError
0x18000d841  nop     dword ptr [rax+rax+00h]
0x18000d846  mov     ebx, eax
0x18000d848  test    eax, eax
0x18000d84a  jle     short loc_18000D855
0x18000d84c  movzx   ebx, ax
0x18000d84f  or      ebx, 80070000h
0x18000d855  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d85c  lea     rax, WPP_GLOBAL_Control
0x18000d863  cmp     rcx, rax
0x18000d866  jz      loc_18000D68B
0x18000d86c  test    byte ptr [rcx+1Ch], 40h
0x18000d870  jz      loc_18000D68B
0x18000d876  mov     edx, 3Dh ; '='
0x18000d87b  mov     rcx, [rcx+10h]
0x18000d87f  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000d886  mov     r9d, ebx
0x18000d889  call    WPP_SF_d
0x18000d88e  jmp     loc_18000D68B
0x18000d893  mov     ebx, 80070057h
0x18000d898  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d89f  lea     rax, WPP_GLOBAL_Control
0x18000d8a6  cmp     rcx, rax
0x18000d8a9  jz      loc_18000D68B
0x18000d8af  test    byte ptr [rcx+1Ch], 40h
0x18000d8b3  jz      loc_18000D68B
0x18000d8b9  mov     edx, 3Bh ; ';'
0x18000d8be  jmp     short loc_18000D87B
0x18000d8c0  call    cs:__imp_LocalFree
0x18000d8c7  nop     dword ptr [rax+rax+00h]
0x18000d8cc  mov     [rbp+57h+hMem], rsi
0x18000d8d0  jmp     loc_18000D698
0x18000d8d5  call    cs:__imp_LocalFree
0x18000d8dc  nop     dword ptr [rax+rax+00h]
0x18000d8e1  mov     [rbp+57h+NewAcl], rsi
0x18000d8e5  jmp     loc_18000D6A5
0x18000d8ea  call    cs:__imp_FreeSid
0x18000d8f1  nop     dword ptr [rax+rax+00h]
0x18000d8f6  jmp     loc_18000D6B2
```
