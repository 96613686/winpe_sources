# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180028dfc`
- end: `0x180028ffe`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028a24`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18001a2f4`
- `0x180028dfc`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180028fd3`
- `ntdll!RtlFreeSid` at `0x180028fd3`
- `ntdll!RtlNtStatusToDosError` at `0x180028ece`
- `ntdll!RtlNtStatusToDosError` at `0x180028ece`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180028ec2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180028ec2`
- `KERNEL32!GetLastError` at `0x180028f76`
- `KERNEL32!GetLastError` at `0x180028fa1`
- `KERNEL32!GetLastError` at `0x180028f76`
- `KERNEL32!GetLastError` at `0x180028fa1`
- `ADVAPI32!SetEntriesInAclW` at `0x180028f4b`
- `ADVAPI32!SetEntriesInAclW` at `0x180028f4b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180028f6c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180028f6c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180028f97`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180028f97`

## string_xrefs

- `0x180028ed4`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x180028f57`: `SetEntriesInAcl [%d]`
- `0x180028f7c`: `InitializeSecurityDescriptor failed [%d]`
- `0x180028fa7`: `SetSecurityDescriptorDacl failed [%d]`
- `0x180028fb6`: `UtcThrottle::InitializeSecurityDesc`

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
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
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
  AslLogCallPrintf(1, "UtcThrottle::InitializeSecurityDesc", v8, v7, SubAuthority2);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v9;
}

```

## disassembly

```asm
0x180028dfc  mov     [rsp-8+arg_0], rbx
0x180028e01  push    rbp
0x180028e02  push    rsi
0x180028e03  push    rdi
0x180028e04  push    r14
0x180028e06  push    r15
0x180028e08  lea     rbp, [rsp-30h]
0x180028e0d  sub     rsp, 130h
0x180028e14  mov     rax, cs:__security_cookie
0x180028e1b  xor     rax, rsp
0x180028e1e  mov     [rbp+50h+var_30], rax
0x180028e22  mov     rsi, r8
0x180028e25  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x180028e29  mov     rdi, rdx
0x180028e2c  xor     r14d, r14d
0x180028e2f  xor     edx, edx; Val
0x180028e31  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180028e35  mov     r8d, 8Ch; Size
0x180028e3b  call    memset_0
0x180028e40  lea     rax, [rsp+150h+var_F0]
0x180028e45  mov     [rsp+150h+var_E0], 101h
0x180028e4d  mov     [rsp+150h+Sid], rax; Sid
0x180028e52  lea     ebx, [r14+2]
0x180028e56  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x180028e5b  lea     r8d, [r14+20h]; SubAuthority0
0x180028e5f  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180028e64  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x180028e69  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180028e6e  lea     r15d, [r14+1]
0x180028e72  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x180028e77  mov     r9d, 220h; SubAuthority1
0x180028e7d  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180028e82  mov     dl, bl; SubAuthorityCount
0x180028e84  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x180028e89  mov     [rsp+150h+var_DC], 5000000h
0x180028e91  mov     [rsp+150h+var_D8], 12h
0x180028e99  mov     [rbp+50h+var_D0], 101h
0x180028ea0  mov     [rbp+50h+var_CC], 5000000h
0x180028ea7  mov     [rbp+50h+var_C8], 13h
0x180028eae  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x180028eb3  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180028eba  mov     [rsi], r14
0x180028ebd  mov     [rsp+150h+var_F0], r14
0x180028ec2  call    cs:__imp_RtlAllocateAndInitializeSid
0x180028ec8  test    eax, eax
0x180028eca  jns     short loc_180028EE6
0x180028ecc  mov     ecx, eax; Status
0x180028ece  call    cs:__imp_RtlNtStatusToDosError
0x180028ed4  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180028edb  mov     r8d, 237h
0x180028ee1  jmp     loc_180028FB4
0x180028ee6  mov     ecx, 100F0000h
0x180028eeb  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x180028eee  mov     r10d, 3
0x180028ef4  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180028ef7  lea     rax, [rsp+150h+var_E0]
0x180028efc  mov     [rbp+50h+var_90], ecx
0x180028eff  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180028f03  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180028f07  lea     rax, [rbp+50h+var_D0]
0x180028f0b  mov     [rbp+50h+var_60], ecx
0x180028f0e  mov     [rbp+50h+var_68], rax
0x180028f12  mov     r9, rsi; NewAcl
0x180028f15  mov     rax, [rsp+150h+var_F0]
0x180028f1a  xor     r8d, r8d; OldAcl
0x180028f1d  mov     ecx, r10d; cCountOfExplicitEntries
0x180028f20  mov     [rbp+50h+var_38], rax
0x180028f24  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180028f28  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180028f2c  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x180028f2f  mov     [rbp+50h+var_8C], ebx
0x180028f32  mov     [rbp+50h+var_88], r10d
0x180028f36  mov     [rbp+50h+var_74], r14d
0x180028f3a  mov     [rbp+50h+var_70], ebx
0x180028f3d  mov     [rbp+50h+var_5C], ebx
0x180028f40  mov     [rbp+50h+var_58], r10d
0x180028f44  mov     [rbp+50h+var_44], r14d
0x180028f48  mov     [rbp+50h+var_40], ebx
0x180028f4b  call    cs:__imp_SetEntriesInAclW
0x180028f51  mov     ebx, eax
0x180028f53  test    eax, eax
0x180028f55  jz      short loc_180028F66
0x180028f57  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x180028f5e  mov     r8d, 25Ah
0x180028f64  jmp     short loc_180028FB6
0x180028f66  mov     edx, r15d; dwRevision
0x180028f69  mov     rcx, rdi; pSecurityDescriptor
0x180028f6c  call    cs:__imp_InitializeSecurityDescriptor
0x180028f72  test    eax, eax
0x180028f74  jnz     short loc_180028F8B
0x180028f76  call    cs:__imp_GetLastError
0x180028f7c  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180028f83  mov     r8d, 261h
0x180028f89  jmp     short loc_180028FB4
0x180028f8b  mov     r8, [rsi]; pDacl
0x180028f8e  xor     r9d, r9d; bDaclDefaulted
0x180028f91  mov     edx, r15d; bDaclPresent
0x180028f94  mov     rcx, rdi; pSecurityDescriptor
0x180028f97  call    cs:__imp_SetSecurityDescriptorDacl
0x180028f9d  test    eax, eax
0x180028f9f  jnz     short loc_180028FC9
0x180028fa1  call    cs:__imp_GetLastError
0x180028fa7  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x180028fae  mov     r8d, 26Ah
0x180028fb4  mov     ebx, eax
0x180028fb6  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x180028fbd  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x180028fc1  mov     ecx, r15d
0x180028fc4  call    AslLogCallPrintf
0x180028fc9  mov     rcx, [rsp+150h+var_F0]; Sid
0x180028fce  test    rcx, rcx
0x180028fd1  jz      short loc_180028FD9
0x180028fd3  call    cs:__imp_RtlFreeSid
0x180028fd9  mov     eax, ebx
0x180028fdb  mov     rcx, [rbp+50h+var_30]
0x180028fdf  xor     rcx, rsp; StackCookie
0x180028fe2  call    __security_check_cookie
0x180028fe7  mov     rbx, [rsp+150h+arg_0]
0x180028fef  add     rsp, 130h
0x180028ff6  pop     r15
0x180028ff8  pop     r14
0x180028ffa  pop     rdi
0x180028ffb  pop     rsi
0x180028ffc  pop     rbp
0x180028ffd  retn
```
