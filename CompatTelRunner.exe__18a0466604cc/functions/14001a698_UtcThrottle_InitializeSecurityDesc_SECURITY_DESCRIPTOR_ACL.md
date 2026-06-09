# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x14001a698`
- end: `0x14001a89a`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(UtcThrottle *this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a2f4`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400151b0`
- `0x14001a698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14001a76a`
- `ntdll!RtlNtStatusToDosError` at `0x14001a76a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001a75e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001a75e`
- `ntdll!RtlFreeSid` at `0x14001a86f`
- `ntdll!RtlFreeSid` at `0x14001a86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14001a833`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14001a833`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14001a808`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14001a808`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14001a7e7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14001a7e7`

## string_xrefs

- `0x14001a843`: `SetSecurityDescriptorDacl failed [%d]`
- `0x14001a818`: `InitializeSecurityDescriptor failed [%d]`
- `0x14001a7f3`: `SetEntriesInAcl [%d]`
- `0x14001a770`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x14001a852`: `UtcThrottle::InitializeSecurityDesc`

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
  __int64 v8; // r8
  ULONG v9; // ebx
  __int64 SubAuthority2; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v14[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v15[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
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
  AslLogCallPrintf(1, "UtcThrottle::InitializeSecurityDesc", v8, v7, SubAuthority2);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v9;
}

```

## disassembly

```asm
0x14001a698  mov     [rsp-8+arg_0], rbx
0x14001a69d  push    rbp
0x14001a69e  push    rsi
0x14001a69f  push    rdi
0x14001a6a0  push    r14
0x14001a6a2  push    r15
0x14001a6a4  lea     rbp, [rsp-30h]
0x14001a6a9  sub     rsp, 130h
0x14001a6b0  mov     rax, cs:__security_cookie
0x14001a6b7  xor     rax, rsp
0x14001a6ba  mov     [rbp+50h+var_30], rax
0x14001a6be  mov     rsi, r8
0x14001a6c1  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x14001a6c5  mov     rdi, rdx
0x14001a6c8  xor     r14d, r14d
0x14001a6cb  xor     edx, edx; Val
0x14001a6cd  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x14001a6d1  mov     r8d, 8Ch; Size
0x14001a6d7  call    memset_0
0x14001a6dc  lea     rax, [rsp+150h+var_F0]
0x14001a6e1  mov     [rsp+150h+var_E0], 101h
0x14001a6e9  mov     [rsp+150h+Sid], rax; Sid
0x14001a6ee  lea     ebx, [r14+2]
0x14001a6f2  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x14001a6f7  lea     r8d, [r14+20h]; SubAuthority0
0x14001a6fb  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x14001a700  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x14001a705  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x14001a70a  lea     r15d, [r14+1]
0x14001a70e  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x14001a713  mov     r9d, 220h; SubAuthority1
0x14001a719  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x14001a71e  mov     dl, bl; SubAuthorityCount
0x14001a720  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x14001a725  mov     [rsp+150h+var_DC], 5000000h
0x14001a72d  mov     [rsp+150h+var_D8], 12h
0x14001a735  mov     [rbp+50h+var_D0], 101h
0x14001a73c  mov     [rbp+50h+var_CC], 5000000h
0x14001a743  mov     [rbp+50h+var_C8], 13h
0x14001a74a  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x14001a74f  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x14001a756  mov     [rsi], r14
0x14001a759  mov     [rsp+150h+var_F0], r14
0x14001a75e  call    cs:__imp_RtlAllocateAndInitializeSid
0x14001a764  test    eax, eax
0x14001a766  jns     short loc_14001A782
0x14001a768  mov     ecx, eax; Status
0x14001a76a  call    cs:__imp_RtlNtStatusToDosError
0x14001a770  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x14001a777  mov     r8d, 237h
0x14001a77d  jmp     loc_14001A850
0x14001a782  mov     ecx, 100F0000h
0x14001a787  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x14001a78a  mov     r10d, 3
0x14001a790  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x14001a793  lea     rax, [rsp+150h+var_E0]
0x14001a798  mov     [rbp+50h+var_90], ecx
0x14001a79b  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x14001a79f  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x14001a7a3  lea     rax, [rbp+50h+var_D0]
0x14001a7a7  mov     [rbp+50h+var_60], ecx
0x14001a7aa  mov     [rbp+50h+var_68], rax
0x14001a7ae  mov     r9, rsi; NewAcl
0x14001a7b1  mov     rax, [rsp+150h+var_F0]
0x14001a7b6  xor     r8d, r8d; OldAcl
0x14001a7b9  mov     ecx, r10d; cCountOfExplicitEntries
0x14001a7bc  mov     [rbp+50h+var_38], rax
0x14001a7c0  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x14001a7c4  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x14001a7c8  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x14001a7cb  mov     [rbp+50h+var_8C], ebx
0x14001a7ce  mov     [rbp+50h+var_88], r10d
0x14001a7d2  mov     [rbp+50h+var_74], r14d
0x14001a7d6  mov     [rbp+50h+var_70], ebx
0x14001a7d9  mov     [rbp+50h+var_5C], ebx
0x14001a7dc  mov     [rbp+50h+var_58], r10d
0x14001a7e0  mov     [rbp+50h+var_44], r14d
0x14001a7e4  mov     [rbp+50h+var_40], ebx
0x14001a7e7  call    cs:__imp_SetEntriesInAclW
0x14001a7ed  mov     ebx, eax
0x14001a7ef  test    eax, eax
0x14001a7f1  jz      short loc_14001A802
0x14001a7f3  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x14001a7fa  mov     r8d, 25Ah
0x14001a800  jmp     short loc_14001A852
0x14001a802  mov     edx, r15d; dwRevision
0x14001a805  mov     rcx, rdi; pSecurityDescriptor
0x14001a808  call    cs:__imp_InitializeSecurityDescriptor
0x14001a80e  test    eax, eax
0x14001a810  jnz     short loc_14001A827
0x14001a812  call    cs:__imp_GetLastError
0x14001a818  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x14001a81f  mov     r8d, 261h
0x14001a825  jmp     short loc_14001A850
0x14001a827  mov     r8, [rsi]; pDacl
0x14001a82a  xor     r9d, r9d; bDaclDefaulted
0x14001a82d  mov     edx, r15d; bDaclPresent
0x14001a830  mov     rcx, rdi; pSecurityDescriptor
0x14001a833  call    cs:__imp_SetSecurityDescriptorDacl
0x14001a839  test    eax, eax
0x14001a83b  jnz     short loc_14001A865
0x14001a83d  call    cs:__imp_GetLastError
0x14001a843  lea     r9, aSetsecuritydes_0; "SetSecurityDescriptorDacl failed [%d]"
0x14001a84a  mov     r8d, 26Ah
0x14001a850  mov     ebx, eax
0x14001a852  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x14001a859  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x14001a85d  mov     ecx, r15d
0x14001a860  call    AslLogCallPrintf
0x14001a865  mov     rcx, [rsp+150h+var_F0]; Sid
0x14001a86a  test    rcx, rcx
0x14001a86d  jz      short loc_14001A875
0x14001a86f  call    cs:__imp_RtlFreeSid
0x14001a875  mov     eax, ebx
0x14001a877  mov     rcx, [rbp+50h+var_30]
0x14001a87b  xor     rcx, rsp; StackCookie
0x14001a87e  call    __security_check_cookie
0x14001a883  mov     rbx, [rsp+150h+arg_0]
0x14001a88b  add     rsp, 130h
0x14001a892  pop     r15
0x14001a894  pop     r14
0x14001a896  pop     rdi
0x14001a897  pop     rsi
0x14001a898  pop     rbp
0x14001a899  retn
```
