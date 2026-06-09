# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x1800a1c68`
- end: `0x1800a1e6a`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040648`

## callees

- `0x180012920`
- `0x18007a9cf`
- `0x1800a1c68`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800a1e3f`
- `ntdll!RtlFreeSid` at `0x1800a1e3f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800a1d2e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800a1d2e`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1d3a`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e0d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a1e03`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a1e03`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a1dd8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a1dd8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800a1db7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800a1db7`

## string_xrefs

- `0x1800a1d40`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x1800a1e22`: `UtcThrottle::InitializeSecurityDesc`
- `0x1800a1dc3`: `SetEntriesInAcl [%d]`
- `0x1800a1de8`: `InitializeSecurityDescriptor failed [%d]`
- `0x1800a1e13`: `SetSecurityDescriptorDacl failed [%d]`

## pseudocode

```c
__int64 __fastcall UtcThrottle::InitializeSecurityDesc(
        UtcThrottle *this,
        struct _SECURITY_DESCRIPTOR *a2,
        struct _ACL **a3)
{
  int v5; // eax
  ULONG LastError; // eax
  const char *v7; // r9
  int v8; // r8d
  ULONG v9; // ebx
  __int64 SubAuthority2; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v14[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v15[4]; // [rsp+80h] [rbp-80h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C4h] [rbp-3Ch]
  int v19; // [rsp+C8h] [rbp-38h]
  int v20; // [rsp+DCh] [rbp-24h]
  int v21; // [rsp+E0h] [rbp-20h]
  _DWORD *v22; // [rsp+E8h] [rbp-18h]
  int v23; // [rsp+F0h] [rbp-10h]
  int v24; // [rsp+F4h] [rbp-Ch]
  int v25; // [rsp+F8h] [rbp-8h]
  int v26; // [rsp+10Ch] [rbp+Ch]
  int v27; // [rsp+110h] [rbp+10h]
  PSID v28; // [rsp+118h] [rbp+18h]

  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  v14[0] = 257;
  v14[1] = 83886080;
  v14[2] = 18;
  v15[0] = 257;
  v15[1] = 83886080;
  v15[2] = 19;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a3 = 0;
  Sid = 0;
  v5 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v5 < 0 )
  {
    LastError = RtlNtStatusToDosError(v5);
    v7 = "RtlAllocateAndInitializeSid failed [%d]";
    v8 = 567;
LABEL_9:
    v9 = LastError;
    goto LABEL_10;
  }
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 269418496;
  v17 = 269418496;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v14;
  v23 = 269418496;
  v22 = v15;
  v28 = Sid;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  v18 = 2;
  v19 = 3;
  v20 = 0;
  v21 = 2;
  v24 = 2;
  v25 = 3;
  v26 = 0;
  v27 = 2;
  LastError = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, a3);
  v9 = LastError;
  if ( !LastError )
  {
    if ( InitializeSecurityDescriptor(a2, 1u) )
    {
      if ( SetSecurityDescriptorDacl(a2, 1, *a3, 0) )
        goto LABEL_11;
      LastError = GetLastError();
      v7 = "SetSecurityDescriptorDacl failed [%d]";
      v8 = 618;
    }
    else
    {
      LastError = GetLastError();
      v7 = "InitializeSecurityDescriptor failed [%d]";
      v8 = 609;
    }
    goto LABEL_9;
  }
  v7 = "SetEntriesInAcl [%d]";
  v8 = 602;
LABEL_10:
  LODWORD(SubAuthority2) = LastError;
  AslLogCallPrintf(1, (unsigned int)"UtcThrottle::InitializeSecurityDesc", v8, (_DWORD)v7, SubAuthority2);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v9;
}

```

## disassembly

```asm
0x1800a1c68  mov     [rsp-8+arg_0], rbx
0x1800a1c6d  push    rbp
0x1800a1c6e  push    rsi
0x1800a1c6f  push    rdi
0x1800a1c70  push    r14
0x1800a1c72  push    r15
0x1800a1c74  lea     rbp, [rsp-30h]
0x1800a1c79  sub     rsp, 130h
0x1800a1c80  mov     rax, cs:__security_cookie
0x1800a1c87  xor     rax, rsp
0x1800a1c8a  mov     [rbp+50h+var_30], rax
0x1800a1c8e  mov     rsi, r8
0x1800a1c91  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x1800a1c95  mov     rdi, rdx
0x1800a1c98  xor     r14d, r14d
0x1800a1c9b  xor     edx, edx; Val
0x1800a1c9d  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x1800a1ca1  mov     r8d, 8Ch; Size
0x1800a1ca7  call    memset_0
0x1800a1cac  lea     rax, [rsp+150h+var_F0]
0x1800a1cb1  mov     [rsp+150h+var_E0], 101h
0x1800a1cb9  mov     [rsp+150h+Sid], rax; Sid
0x1800a1cbe  lea     ebx, [r14+2]
0x1800a1cc2  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x1800a1cc7  lea     r8d, [r14+20h]; SubAuthority0
0x1800a1ccb  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x1800a1cd0  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x1800a1cd5  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x1800a1cda  lea     r15d, [r14+1]
0x1800a1cde  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x1800a1ce3  mov     r9d, 220h; SubAuthority1
0x1800a1ce9  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x1800a1cee  mov     dl, bl; SubAuthorityCount
0x1800a1cf0  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x1800a1cf5  mov     [rsp+150h+var_DC], 5000000h
0x1800a1cfd  mov     [rsp+150h+var_D8], 12h
0x1800a1d05  mov     [rbp+50h+var_D0], 101h
0x1800a1d0c  mov     [rbp+50h+var_CC], 5000000h
0x1800a1d13  mov     [rbp+50h+var_C8], 13h
0x1800a1d1a  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x1800a1d1f  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x1800a1d26  mov     [rsi], r14
0x1800a1d29  mov     [rsp+150h+var_F0], r14
0x1800a1d2e  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800a1d34  test    eax, eax
0x1800a1d36  jns     short loc_1800A1D52
0x1800a1d38  mov     ecx, eax; Status
0x1800a1d3a  call    cs:__imp_RtlNtStatusToDosError
0x1800a1d40  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x1800a1d47  mov     r8d, 237h
0x1800a1d4d  jmp     loc_1800A1E20
0x1800a1d52  mov     ecx, 100F0000h
0x1800a1d57  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x1800a1d5a  mov     r10d, 3
0x1800a1d60  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x1800a1d63  lea     rax, [rsp+150h+var_E0]
0x1800a1d68  mov     [rbp+50h+var_90], ecx
0x1800a1d6b  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800a1d6f  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800a1d73  lea     rax, [rbp+50h+var_D0]
0x1800a1d77  mov     [rbp+50h+var_60], ecx
0x1800a1d7a  mov     [rbp+50h+var_68], rax
0x1800a1d7e  mov     r9, rsi; NewAcl
0x1800a1d81  mov     rax, [rsp+150h+var_F0]
0x1800a1d86  xor     r8d, r8d; OldAcl
0x1800a1d89  mov     ecx, r10d; cCountOfExplicitEntries
0x1800a1d8c  mov     [rbp+50h+var_38], rax
0x1800a1d90  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x1800a1d94  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x1800a1d98  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x1800a1d9b  mov     [rbp+50h+var_8C], ebx
0x1800a1d9e  mov     [rbp+50h+var_88], r10d
0x1800a1da2  mov     [rbp+50h+var_74], r14d
0x1800a1da6  mov     [rbp+50h+var_70], ebx
0x1800a1da9  mov     [rbp+50h+var_5C], ebx
0x1800a1dac  mov     [rbp+50h+var_58], r10d
0x1800a1db0  mov     [rbp+50h+var_44], r14d
0x1800a1db4  mov     [rbp+50h+var_40], ebx
0x1800a1db7  call    cs:__imp_SetEntriesInAclW
0x1800a1dbd  mov     ebx, eax
0x1800a1dbf  test    eax, eax
0x1800a1dc1  jz      short loc_1800A1DD2
0x1800a1dc3  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x1800a1dca  mov     r8d, 25Ah
0x1800a1dd0  jmp     short loc_1800A1E22
0x1800a1dd2  mov     edx, r15d; dwRevision
0x1800a1dd5  mov     rcx, rdi; pSecurityDescriptor
0x1800a1dd8  call    cs:__imp_InitializeSecurityDescriptor
0x1800a1dde  test    eax, eax
0x1800a1de0  jnz     short loc_1800A1DF7
0x1800a1de2  call    cs:__imp_GetLastError
0x1800a1de8  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x1800a1def  mov     r8d, 261h
0x1800a1df5  jmp     short loc_1800A1E20
0x1800a1df7  mov     r8, [rsi]; pDacl
0x1800a1dfa  xor     r9d, r9d; bDaclDefaulted
0x1800a1dfd  mov     edx, r15d; bDaclPresent
0x1800a1e00  mov     rcx, rdi; pSecurityDescriptor
0x1800a1e03  call    cs:__imp_SetSecurityDescriptorDacl
0x1800a1e09  test    eax, eax
0x1800a1e0b  jnz     short loc_1800A1E35
0x1800a1e0d  call    cs:__imp_GetLastError
0x1800a1e13  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x1800a1e1a  mov     r8d, 26Ah
0x1800a1e20  mov     ebx, eax
0x1800a1e22  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x1800a1e29  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x1800a1e2d  mov     ecx, r15d
0x1800a1e30  call    AslLogCallPrintf
0x1800a1e35  mov     rcx, [rsp+150h+var_F0]; Sid
0x1800a1e3a  test    rcx, rcx
0x1800a1e3d  jz      short loc_1800A1E45
0x1800a1e3f  call    cs:__imp_RtlFreeSid
0x1800a1e45  mov     eax, ebx
0x1800a1e47  mov     rcx, [rbp+50h+var_30]
0x1800a1e4b  xor     rcx, rsp; StackCookie
0x1800a1e4e  call    __security_check_cookie
0x1800a1e53  mov     rbx, [rsp+150h+arg_0]
0x1800a1e5b  add     rsp, 130h
0x1800a1e62  pop     r15
0x1800a1e64  pop     r14
0x1800a1e66  pop     rdi
0x1800a1e67  pop     rsi
0x1800a1e68  pop     rbp
0x1800a1e69  retn
```
