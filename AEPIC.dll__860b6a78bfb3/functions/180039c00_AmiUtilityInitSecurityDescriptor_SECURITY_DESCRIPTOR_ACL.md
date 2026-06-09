# AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180039c00`
- end: `0x180039e02`
- name: `?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL *NewAcl)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180039b54`
- `0x18003a5a8`

## callees

- `0x180005890`
- `0x180006938`
- `0x1800295dc`
- `0x180039c00`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180039cc6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180039cc6`
- `ntdll!RtlNtStatusToDosError` at `0x180039cd2`
- `ntdll!RtlNtStatusToDosError` at `0x180039cd2`
- `ntdll!RtlFreeSid` at `0x180039dd7`
- `ntdll!RtlFreeSid` at `0x180039dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039da5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180039d70`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180039d70`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180039d9b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180039d9b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180039d4f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180039d4f`

## string_xrefs

- `0x180039cd8`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x180039d5b`: `SetEntriesInAcl [%d]`
- `0x180039d80`: `InitializeSecurityDescriptor failed [%d]`
- `0x180039dab`: `SetSecurityDescriptorDacl failed [%d]`
- `0x180039dba`: `AmiUtilityInitSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall AmiUtilityInitSecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL *NewAcl)
{
  int v4; // eax
  ULONG LastError; // eax
  const char *v6; // r9
  __int64 v7; // r8
  ULONG v8; // ebx
  __int64 SubAuthority2; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v13[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v14[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  int v16; // [rsp+C0h] [rbp-40h]
  int v17; // [rsp+C4h] [rbp-3Ch]
  int v18; // [rsp+C8h] [rbp-38h]
  int v19; // [rsp+DCh] [rbp-24h]
  int v20; // [rsp+E0h] [rbp-20h]
  _DWORD *v21; // [rsp+E8h] [rbp-18h]
  int v22; // [rsp+F0h] [rbp-10h]
  int v23; // [rsp+F4h] [rbp-Ch]
  int v24; // [rsp+F8h] [rbp-8h]
  int v25; // [rsp+10Ch] [rbp+Ch]
  int v26; // [rsp+110h] [rbp+10h]
  PSID v27; // [rsp+118h] [rbp+18h]

  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  v13[0] = 257;
  v13[1] = 83886080;
  v13[2] = 18;
  v14[0] = 257;
  v14[1] = 83886080;
  v14[2] = 19;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *NewAcl = 0;
  Sid = 0;
  v4 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v4 < 0 )
  {
    LastError = RtlNtStatusToDosError(v4);
    v6 = "RtlAllocateAndInitializeSid failed [%d]";
    v7 = 142;
LABEL_9:
    v8 = LastError;
    goto LABEL_10;
  }
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 269418496;
  v16 = 269418496;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v13;
  v22 = 269418496;
  v21 = v14;
  v27 = Sid;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  v17 = 2;
  v18 = 3;
  v19 = 0;
  v20 = 2;
  v23 = 2;
  v24 = 3;
  v25 = 0;
  v26 = 2;
  LastError = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, NewAcl);
  v8 = LastError;
  if ( !LastError )
  {
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, *NewAcl, 0) )
        goto LABEL_11;
      LastError = GetLastError();
      v6 = "SetSecurityDescriptorDacl failed [%d]";
      v7 = 193;
    }
    else
    {
      LastError = GetLastError();
      v6 = "InitializeSecurityDescriptor failed [%d]";
      v7 = 184;
    }
    goto LABEL_9;
  }
  v6 = "SetEntriesInAcl [%d]";
  v7 = 177;
LABEL_10:
  LODWORD(SubAuthority2) = LastError;
  AslLogCallPrintf(1, "AmiUtilityInitSecurityDescriptor", v7, v6, SubAuthority2);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v8;
}

```

## disassembly

```asm
0x180039c00  mov     [rsp-8+arg_10], rbx
0x180039c05  push    rbp
0x180039c06  push    rsi
0x180039c07  push    rdi
0x180039c08  push    r14
0x180039c0a  push    r15
0x180039c0c  lea     rbp, [rsp-30h]
0x180039c11  sub     rsp, 130h
0x180039c18  mov     rax, cs:__security_cookie
0x180039c1f  xor     rax, rsp
0x180039c22  mov     [rbp+50h+var_30], rax
0x180039c26  mov     rsi, rdx
0x180039c29  mov     rdi, rcx
0x180039c2c  xor     r14d, r14d
0x180039c2f  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x180039c33  xor     edx, edx; Val
0x180039c35  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180039c39  mov     r8d, 8Ch; Size
0x180039c3f  call    memset_0
0x180039c44  lea     rax, [rsp+150h+var_F0]
0x180039c49  mov     [rsp+150h+var_E0], 101h
0x180039c51  mov     [rsp+150h+Sid], rax; Sid
0x180039c56  lea     ebx, [r14+2]
0x180039c5a  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x180039c5f  lea     r8d, [r14+20h]; SubAuthority0
0x180039c63  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180039c68  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x180039c6d  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180039c72  lea     r15d, [r14+1]
0x180039c76  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x180039c7b  mov     r9d, 220h; SubAuthority1
0x180039c81  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180039c86  mov     dl, bl; SubAuthorityCount
0x180039c88  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x180039c8d  mov     [rsp+150h+var_DC], 5000000h
0x180039c95  mov     [rsp+150h+var_D8], 12h
0x180039c9d  mov     [rbp+50h+var_D0], 101h
0x180039ca4  mov     [rbp+50h+var_CC], 5000000h
0x180039cab  mov     [rbp+50h+var_C8], 13h
0x180039cb2  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x180039cb7  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180039cbe  mov     [rsi], r14
0x180039cc1  mov     [rsp+150h+var_F0], r14
0x180039cc6  call    cs:__imp_RtlAllocateAndInitializeSid
0x180039ccc  test    eax, eax
0x180039cce  jns     short loc_180039CEA
0x180039cd0  mov     ecx, eax; Status
0x180039cd2  call    cs:__imp_RtlNtStatusToDosError
0x180039cd8  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180039cdf  mov     r8d, 8Eh
0x180039ce5  jmp     loc_180039DB8
0x180039cea  mov     ecx, 100F0000h
0x180039cef  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x180039cf2  mov     r10d, 3
0x180039cf8  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180039cfb  lea     rax, [rsp+150h+var_E0]
0x180039d00  mov     [rbp+50h+var_90], ecx
0x180039d03  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180039d07  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180039d0b  lea     rax, [rbp+50h+var_D0]
0x180039d0f  mov     [rbp+50h+var_60], ecx
0x180039d12  mov     [rbp+50h+var_68], rax
0x180039d16  mov     r9, rsi; NewAcl
0x180039d19  mov     rax, [rsp+150h+var_F0]
0x180039d1e  xor     r8d, r8d; OldAcl
0x180039d21  mov     ecx, r10d; cCountOfExplicitEntries
0x180039d24  mov     [rbp+50h+var_38], rax
0x180039d28  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180039d2c  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180039d30  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x180039d33  mov     [rbp+50h+var_8C], ebx
0x180039d36  mov     [rbp+50h+var_88], r10d
0x180039d3a  mov     [rbp+50h+var_74], r14d
0x180039d3e  mov     [rbp+50h+var_70], ebx
0x180039d41  mov     [rbp+50h+var_5C], ebx
0x180039d44  mov     [rbp+50h+var_58], r10d
0x180039d48  mov     [rbp+50h+var_44], r14d
0x180039d4c  mov     [rbp+50h+var_40], ebx
0x180039d4f  call    cs:__imp_SetEntriesInAclW
0x180039d55  mov     ebx, eax
0x180039d57  test    eax, eax
0x180039d59  jz      short loc_180039D6A
0x180039d5b  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x180039d62  mov     r8d, 0B1h
0x180039d68  jmp     short loc_180039DBA
0x180039d6a  mov     edx, r15d; dwRevision
0x180039d6d  mov     rcx, rdi; pSecurityDescriptor
0x180039d70  call    cs:__imp_InitializeSecurityDescriptor
0x180039d76  test    eax, eax
0x180039d78  jnz     short loc_180039D8F
0x180039d7a  call    cs:__imp_GetLastError
0x180039d80  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180039d87  mov     r8d, 0B8h
0x180039d8d  jmp     short loc_180039DB8
0x180039d8f  mov     r8, [rsi]; pDacl
0x180039d92  xor     r9d, r9d; bDaclDefaulted
0x180039d95  mov     edx, r15d; bDaclPresent
0x180039d98  mov     rcx, rdi; pSecurityDescriptor
0x180039d9b  call    cs:__imp_SetSecurityDescriptorDacl
0x180039da1  test    eax, eax
0x180039da3  jnz     short loc_180039DCD
0x180039da5  call    cs:__imp_GetLastError
0x180039dab  lea     r9, aSetsecuritydes_0; "SetSecurityDescriptorDacl failed [%d]"
0x180039db2  mov     r8d, 0C1h
0x180039db8  mov     ebx, eax
0x180039dba  lea     rdx, aAmiutilityinit; "AmiUtilityInitSecurityDescriptor"
0x180039dc1  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x180039dc5  mov     ecx, r15d
0x180039dc8  call    AslLogCallPrintf
0x180039dcd  mov     rcx, [rsp+150h+var_F0]; Sid
0x180039dd2  test    rcx, rcx
0x180039dd5  jz      short loc_180039DDD
0x180039dd7  call    cs:__imp_RtlFreeSid
0x180039ddd  mov     eax, ebx
0x180039ddf  mov     rcx, [rbp+50h+var_30]
0x180039de3  xor     rcx, rsp; StackCookie
0x180039de6  call    __security_check_cookie
0x180039deb  mov     rbx, [rsp+150h+arg_10]
0x180039df3  add     rsp, 130h
0x180039dfa  pop     r15
0x180039dfc  pop     r14
0x180039dfe  pop     rdi
0x180039dff  pop     rsi
0x180039e00  pop     rbp
0x180039e01  retn
```
