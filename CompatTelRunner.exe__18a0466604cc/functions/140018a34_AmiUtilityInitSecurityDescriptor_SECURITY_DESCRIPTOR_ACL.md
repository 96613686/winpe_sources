# AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x140018a34`
- end: `0x140018c36`
- name: `?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL *NewAcl)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018988`
- `0x140019610`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400151b0`
- `0x140018a34`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140018b06`
- `ntdll!RtlNtStatusToDosError` at `0x140018b06`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140018afa`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140018afa`
- `ntdll!RtlFreeSid` at `0x140018c0b`
- `ntdll!RtlFreeSid` at `0x140018c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bd9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140018bcf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140018bcf`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140018ba4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140018ba4`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140018b83`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140018b83`

## string_xrefs

- `0x140018bee`: `AmiUtilityInitSecurityDescriptor`
- `0x140018bdf`: `SetSecurityDescriptorDacl failed [%d]`
- `0x140018bb4`: `InitializeSecurityDescriptor failed [%d]`
- `0x140018b8f`: `SetEntriesInAcl [%d]`
- `0x140018b0c`: `RtlAllocateAndInitializeSid failed [%d]`

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
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v13[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v14[4]; // [rsp+80h] [rbp-80h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
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
0x140018a34  mov     [rsp-8+arg_10], rbx
0x140018a39  push    rbp
0x140018a3a  push    rsi
0x140018a3b  push    rdi
0x140018a3c  push    r14
0x140018a3e  push    r15
0x140018a40  lea     rbp, [rsp-30h]
0x140018a45  sub     rsp, 130h
0x140018a4c  mov     rax, cs:__security_cookie
0x140018a53  xor     rax, rsp
0x140018a56  mov     [rbp+50h+var_30], rax
0x140018a5a  mov     rsi, rdx
0x140018a5d  mov     rdi, rcx
0x140018a60  xor     r14d, r14d
0x140018a63  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x140018a67  xor     edx, edx; Val
0x140018a69  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x140018a6d  mov     r8d, 8Ch; Size
0x140018a73  call    memset_0
0x140018a78  lea     rax, [rsp+150h+var_F0]
0x140018a7d  mov     [rsp+150h+var_E0], 101h
0x140018a85  mov     [rsp+150h+Sid], rax; Sid
0x140018a8a  lea     ebx, [r14+2]
0x140018a8e  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x140018a93  lea     r8d, [r14+20h]; SubAuthority0
0x140018a97  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x140018a9c  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x140018aa1  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x140018aa6  lea     r15d, [r14+1]
0x140018aaa  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x140018aaf  mov     r9d, 220h; SubAuthority1
0x140018ab5  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x140018aba  mov     dl, bl; SubAuthorityCount
0x140018abc  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x140018ac1  mov     [rsp+150h+var_DC], 5000000h
0x140018ac9  mov     [rsp+150h+var_D8], 12h
0x140018ad1  mov     [rbp+50h+var_D0], 101h
0x140018ad8  mov     [rbp+50h+var_CC], 5000000h
0x140018adf  mov     [rbp+50h+var_C8], 13h
0x140018ae6  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x140018aeb  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x140018af2  mov     [rsi], r14
0x140018af5  mov     [rsp+150h+var_F0], r14
0x140018afa  call    cs:__imp_RtlAllocateAndInitializeSid
0x140018b00  test    eax, eax
0x140018b02  jns     short loc_140018B1E
0x140018b04  mov     ecx, eax; Status
0x140018b06  call    cs:__imp_RtlNtStatusToDosError
0x140018b0c  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x140018b13  mov     r8d, 8Eh
0x140018b19  jmp     loc_140018BEC
0x140018b1e  mov     ecx, 100F0000h
0x140018b23  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x140018b26  mov     r10d, 3
0x140018b2c  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x140018b2f  lea     rax, [rsp+150h+var_E0]
0x140018b34  mov     [rbp+50h+var_90], ecx
0x140018b37  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x140018b3b  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140018b3f  lea     rax, [rbp+50h+var_D0]
0x140018b43  mov     [rbp+50h+var_60], ecx
0x140018b46  mov     [rbp+50h+var_68], rax
0x140018b4a  mov     r9, rsi; NewAcl
0x140018b4d  mov     rax, [rsp+150h+var_F0]
0x140018b52  xor     r8d, r8d; OldAcl
0x140018b55  mov     ecx, r10d; cCountOfExplicitEntries
0x140018b58  mov     [rbp+50h+var_38], rax
0x140018b5c  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x140018b60  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x140018b64  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x140018b67  mov     [rbp+50h+var_8C], ebx
0x140018b6a  mov     [rbp+50h+var_88], r10d
0x140018b6e  mov     [rbp+50h+var_74], r14d
0x140018b72  mov     [rbp+50h+var_70], ebx
0x140018b75  mov     [rbp+50h+var_5C], ebx
0x140018b78  mov     [rbp+50h+var_58], r10d
0x140018b7c  mov     [rbp+50h+var_44], r14d
0x140018b80  mov     [rbp+50h+var_40], ebx
0x140018b83  call    cs:__imp_SetEntriesInAclW
0x140018b89  mov     ebx, eax
0x140018b8b  test    eax, eax
0x140018b8d  jz      short loc_140018B9E
0x140018b8f  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x140018b96  mov     r8d, 0B1h
0x140018b9c  jmp     short loc_140018BEE
0x140018b9e  mov     edx, r15d; dwRevision
0x140018ba1  mov     rcx, rdi; pSecurityDescriptor
0x140018ba4  call    cs:__imp_InitializeSecurityDescriptor
0x140018baa  test    eax, eax
0x140018bac  jnz     short loc_140018BC3
0x140018bae  call    cs:__imp_GetLastError
0x140018bb4  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x140018bbb  mov     r8d, 0B8h
0x140018bc1  jmp     short loc_140018BEC
0x140018bc3  mov     r8, [rsi]; pDacl
0x140018bc6  xor     r9d, r9d; bDaclDefaulted
0x140018bc9  mov     edx, r15d; bDaclPresent
0x140018bcc  mov     rcx, rdi; pSecurityDescriptor
0x140018bcf  call    cs:__imp_SetSecurityDescriptorDacl
0x140018bd5  test    eax, eax
0x140018bd7  jnz     short loc_140018C01
0x140018bd9  call    cs:__imp_GetLastError
0x140018bdf  lea     r9, aSetsecuritydes_0; "SetSecurityDescriptorDacl failed [%d]"
0x140018be6  mov     r8d, 0C1h
0x140018bec  mov     ebx, eax
0x140018bee  lea     rdx, aAmiutilityinit; "AmiUtilityInitSecurityDescriptor"
0x140018bf5  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x140018bf9  mov     ecx, r15d
0x140018bfc  call    AslLogCallPrintf
0x140018c01  mov     rcx, [rsp+150h+var_F0]; Sid
0x140018c06  test    rcx, rcx
0x140018c09  jz      short loc_140018C11
0x140018c0b  call    cs:__imp_RtlFreeSid
0x140018c11  mov     eax, ebx
0x140018c13  mov     rcx, [rbp+50h+var_30]
0x140018c17  xor     rcx, rsp; StackCookie
0x140018c1a  call    __security_check_cookie
0x140018c1f  mov     rbx, [rsp+150h+arg_10]
0x140018c27  add     rsp, 130h
0x140018c2e  pop     r15
0x140018c30  pop     r14
0x140018c32  pop     rdi
0x140018c33  pop     rsi
0x140018c34  pop     rbp
0x140018c35  retn
```
