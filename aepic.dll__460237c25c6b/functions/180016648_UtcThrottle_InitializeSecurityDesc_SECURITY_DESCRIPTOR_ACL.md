# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180016648`
- end: `0x18001684a`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016330`

## callees

- `0x180005890`
- `0x180006938`
- `0x180016648`
- `0x1800295dc`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18001670e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001670e`
- `ntdll!RtlNtStatusToDosError` at `0x18001671a`
- `ntdll!RtlNtStatusToDosError` at `0x18001671a`
- `ntdll!RtlFreeSid` at `0x18001681f`
- `ntdll!RtlFreeSid` at `0x18001681f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167ed`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800167b8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800167b8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800167e3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800167e3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180016797`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180016797`

## string_xrefs

- `0x180016720`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x1800167a3`: `SetEntriesInAcl [%d]`
- `0x1800167c8`: `InitializeSecurityDescriptor failed [%d]`
- `0x1800167f3`: `SetSecurityDescriptorDacl failed [%d]`
- `0x180016802`: `UtcThrottle::InitializeSecurityDesc`

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
0x180016648  mov     [rsp-8+arg_0], rbx
0x18001664d  push    rbp
0x18001664e  push    rsi
0x18001664f  push    rdi
0x180016650  push    r14
0x180016652  push    r15
0x180016654  lea     rbp, [rsp-30h]
0x180016659  sub     rsp, 130h
0x180016660  mov     rax, cs:__security_cookie
0x180016667  xor     rax, rsp
0x18001666a  mov     [rbp+50h+var_30], rax
0x18001666e  mov     rsi, r8
0x180016671  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x180016675  mov     rdi, rdx
0x180016678  xor     r14d, r14d
0x18001667b  xor     edx, edx; Val
0x18001667d  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180016681  mov     r8d, 8Ch; Size
0x180016687  call    memset_0
0x18001668c  lea     rax, [rsp+150h+var_F0]
0x180016691  mov     [rsp+150h+var_E0], 101h
0x180016699  mov     [rsp+150h+Sid], rax; Sid
0x18001669e  lea     ebx, [r14+2]
0x1800166a2  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x1800166a7  lea     r8d, [r14+20h]; SubAuthority0
0x1800166ab  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x1800166b0  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x1800166b5  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x1800166ba  lea     r15d, [r14+1]
0x1800166be  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x1800166c3  mov     r9d, 220h; SubAuthority1
0x1800166c9  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x1800166ce  mov     dl, bl; SubAuthorityCount
0x1800166d0  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x1800166d5  mov     [rsp+150h+var_DC], 5000000h
0x1800166dd  mov     [rsp+150h+var_D8], 12h
0x1800166e5  mov     [rbp+50h+var_D0], 101h
0x1800166ec  mov     [rbp+50h+var_CC], 5000000h
0x1800166f3  mov     [rbp+50h+var_C8], 13h
0x1800166fa  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x1800166ff  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180016706  mov     [rsi], r14
0x180016709  mov     [rsp+150h+var_F0], r14
0x18001670e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180016714  test    eax, eax
0x180016716  jns     short loc_180016732
0x180016718  mov     ecx, eax; Status
0x18001671a  call    cs:__imp_RtlNtStatusToDosError
0x180016720  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180016727  mov     r8d, 237h
0x18001672d  jmp     loc_180016800
0x180016732  mov     ecx, 100F0000h
0x180016737  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x18001673a  mov     r10d, 3
0x180016740  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180016743  lea     rax, [rsp+150h+var_E0]
0x180016748  mov     [rbp+50h+var_90], ecx
0x18001674b  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18001674f  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180016753  lea     rax, [rbp+50h+var_D0]
0x180016757  mov     [rbp+50h+var_60], ecx
0x18001675a  mov     [rbp+50h+var_68], rax
0x18001675e  mov     r9, rsi; NewAcl
0x180016761  mov     rax, [rsp+150h+var_F0]
0x180016766  xor     r8d, r8d; OldAcl
0x180016769  mov     ecx, r10d; cCountOfExplicitEntries
0x18001676c  mov     [rbp+50h+var_38], rax
0x180016770  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180016774  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180016778  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x18001677b  mov     [rbp+50h+var_8C], ebx
0x18001677e  mov     [rbp+50h+var_88], r10d
0x180016782  mov     [rbp+50h+var_74], r14d
0x180016786  mov     [rbp+50h+var_70], ebx
0x180016789  mov     [rbp+50h+var_5C], ebx
0x18001678c  mov     [rbp+50h+var_58], r10d
0x180016790  mov     [rbp+50h+var_44], r14d
0x180016794  mov     [rbp+50h+var_40], ebx
0x180016797  call    cs:__imp_SetEntriesInAclW
0x18001679d  mov     ebx, eax
0x18001679f  test    eax, eax
0x1800167a1  jz      short loc_1800167B2
0x1800167a3  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x1800167aa  mov     r8d, 25Ah
0x1800167b0  jmp     short loc_180016802
0x1800167b2  mov     edx, r15d; dwRevision
0x1800167b5  mov     rcx, rdi; pSecurityDescriptor
0x1800167b8  call    cs:__imp_InitializeSecurityDescriptor
0x1800167be  test    eax, eax
0x1800167c0  jnz     short loc_1800167D7
0x1800167c2  call    cs:__imp_GetLastError
0x1800167c8  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x1800167cf  mov     r8d, 261h
0x1800167d5  jmp     short loc_180016800
0x1800167d7  mov     r8, [rsi]; pDacl
0x1800167da  xor     r9d, r9d; bDaclDefaulted
0x1800167dd  mov     edx, r15d; bDaclPresent
0x1800167e0  mov     rcx, rdi; pSecurityDescriptor
0x1800167e3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800167e9  test    eax, eax
0x1800167eb  jnz     short loc_180016815
0x1800167ed  call    cs:__imp_GetLastError
0x1800167f3  lea     r9, aSetsecuritydes_0; "SetSecurityDescriptorDacl failed [%d]"
0x1800167fa  mov     r8d, 26Ah
0x180016800  mov     ebx, eax
0x180016802  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x180016809  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x18001680d  mov     ecx, r15d
0x180016810  call    AslLogCallPrintf
0x180016815  mov     rcx, [rsp+150h+var_F0]; Sid
0x18001681a  test    rcx, rcx
0x18001681d  jz      short loc_180016825
0x18001681f  call    cs:__imp_RtlFreeSid
0x180016825  mov     eax, ebx
0x180016827  mov     rcx, [rbp+50h+var_30]
0x18001682b  xor     rcx, rsp; StackCookie
0x18001682e  call    __security_check_cookie
0x180016833  mov     rbx, [rsp+150h+arg_0]
0x18001683b  add     rsp, 130h
0x180016842  pop     r15
0x180016844  pop     r14
0x180016846  pop     rdi
0x180016847  pop     rsi
0x180016848  pop     rbp
0x180016849  retn
```
