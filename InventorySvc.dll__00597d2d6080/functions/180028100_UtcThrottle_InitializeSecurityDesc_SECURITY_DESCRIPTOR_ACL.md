# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180028100`
- end: `0x180028302`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027bc8`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800152d0`
- `0x180028100`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800282d7`
- `ntdll!RtlFreeSid` at `0x1800282d7`
- `ntdll!RtlNtStatusToDosError` at `0x1800281d2`
- `ntdll!RtlNtStatusToDosError` at `0x1800281d2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800281c6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800281c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282a5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180028270`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180028270`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002829b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002829b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002824f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002824f`

## string_xrefs

- `0x1800281d8`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x18002825b`: `SetEntriesInAcl [%d]`
- `0x180028280`: `InitializeSecurityDescriptor failed [%d]`
- `0x1800282ba`: `UtcThrottle::InitializeSecurityDesc`
- `0x1800282ab`: `SetSecurityDescriptorDacl failed [%d]`

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
0x180028100  mov     [rsp-8+arg_0], rbx
0x180028105  push    rbp
0x180028106  push    rsi
0x180028107  push    rdi
0x180028108  push    r14
0x18002810a  push    r15
0x18002810c  lea     rbp, [rsp-30h]
0x180028111  sub     rsp, 130h
0x180028118  mov     rax, cs:__security_cookie
0x18002811f  xor     rax, rsp
0x180028122  mov     [rbp+50h+var_30], rax
0x180028126  mov     rsi, r8
0x180028129  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x18002812d  mov     rdi, rdx
0x180028130  xor     r14d, r14d
0x180028133  xor     edx, edx; Val
0x180028135  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180028139  mov     r8d, 8Ch; Size
0x18002813f  call    memset_0
0x180028144  lea     rax, [rsp+150h+var_F0]
0x180028149  mov     [rsp+150h+var_E0], 101h
0x180028151  mov     [rsp+150h+Sid], rax; Sid
0x180028156  lea     ebx, [r14+2]
0x18002815a  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x18002815f  lea     r8d, [r14+20h]; SubAuthority0
0x180028163  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180028168  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x18002816d  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180028172  lea     r15d, [r14+1]
0x180028176  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x18002817b  mov     r9d, 220h; SubAuthority1
0x180028181  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180028186  mov     dl, bl; SubAuthorityCount
0x180028188  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x18002818d  mov     [rsp+150h+var_DC], 5000000h
0x180028195  mov     [rsp+150h+var_D8], 12h
0x18002819d  mov     [rbp+50h+var_D0], 101h
0x1800281a4  mov     [rbp+50h+var_CC], 5000000h
0x1800281ab  mov     [rbp+50h+var_C8], 13h
0x1800281b2  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x1800281b7  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x1800281be  mov     [rsi], r14
0x1800281c1  mov     [rsp+150h+var_F0], r14
0x1800281c6  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800281cc  test    eax, eax
0x1800281ce  jns     short loc_1800281EA
0x1800281d0  mov     ecx, eax; Status
0x1800281d2  call    cs:__imp_RtlNtStatusToDosError
0x1800281d8  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x1800281df  mov     r8d, 237h
0x1800281e5  jmp     loc_1800282B8
0x1800281ea  mov     ecx, 100F0000h
0x1800281ef  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x1800281f2  mov     r10d, 3
0x1800281f8  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x1800281fb  lea     rax, [rsp+150h+var_E0]
0x180028200  mov     [rbp+50h+var_90], ecx
0x180028203  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180028207  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002820b  lea     rax, [rbp+50h+var_D0]
0x18002820f  mov     [rbp+50h+var_60], ecx
0x180028212  mov     [rbp+50h+var_68], rax
0x180028216  mov     r9, rsi; NewAcl
0x180028219  mov     rax, [rsp+150h+var_F0]
0x18002821e  xor     r8d, r8d; OldAcl
0x180028221  mov     ecx, r10d; cCountOfExplicitEntries
0x180028224  mov     [rbp+50h+var_38], rax
0x180028228  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x18002822c  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180028230  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x180028233  mov     [rbp+50h+var_8C], ebx
0x180028236  mov     [rbp+50h+var_88], r10d
0x18002823a  mov     [rbp+50h+var_74], r14d
0x18002823e  mov     [rbp+50h+var_70], ebx
0x180028241  mov     [rbp+50h+var_5C], ebx
0x180028244  mov     [rbp+50h+var_58], r10d
0x180028248  mov     [rbp+50h+var_44], r14d
0x18002824c  mov     [rbp+50h+var_40], ebx
0x18002824f  call    cs:__imp_SetEntriesInAclW
0x180028255  mov     ebx, eax
0x180028257  test    eax, eax
0x180028259  jz      short loc_18002826A
0x18002825b  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x180028262  mov     r8d, 25Ah
0x180028268  jmp     short loc_1800282BA
0x18002826a  mov     edx, r15d; dwRevision
0x18002826d  mov     rcx, rdi; pSecurityDescriptor
0x180028270  call    cs:__imp_InitializeSecurityDescriptor
0x180028276  test    eax, eax
0x180028278  jnz     short loc_18002828F
0x18002827a  call    cs:__imp_GetLastError
0x180028280  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180028287  mov     r8d, 261h
0x18002828d  jmp     short loc_1800282B8
0x18002828f  mov     r8, [rsi]; pDacl
0x180028292  xor     r9d, r9d; bDaclDefaulted
0x180028295  mov     edx, r15d; bDaclPresent
0x180028298  mov     rcx, rdi; pSecurityDescriptor
0x18002829b  call    cs:__imp_SetSecurityDescriptorDacl
0x1800282a1  test    eax, eax
0x1800282a3  jnz     short loc_1800282CD
0x1800282a5  call    cs:__imp_GetLastError
0x1800282ab  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x1800282b2  mov     r8d, 26Ah
0x1800282b8  mov     ebx, eax
0x1800282ba  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x1800282c1  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x1800282c5  mov     ecx, r15d
0x1800282c8  call    AslLogCallPrintf
0x1800282cd  mov     rcx, [rsp+150h+var_F0]; Sid
0x1800282d2  test    rcx, rcx
0x1800282d5  jz      short loc_1800282DD
0x1800282d7  call    cs:__imp_RtlFreeSid
0x1800282dd  mov     eax, ebx
0x1800282df  mov     rcx, [rbp+50h+var_30]
0x1800282e3  xor     rcx, rsp; StackCookie
0x1800282e6  call    __security_check_cookie
0x1800282eb  mov     rbx, [rsp+150h+arg_0]
0x1800282f3  add     rsp, 130h
0x1800282fa  pop     r15
0x1800282fc  pop     r14
0x1800282fe  pop     rdi
0x1800282ff  pop     rsi
0x180028300  pop     rbp
0x180028301  retn
```
