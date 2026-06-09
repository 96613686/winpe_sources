# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x1800649a8`
- end: `0x180064baa`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180064688`

## callees

- `0x1800197d4`
- `0x180059920`
- `0x18005a8bc`
- `0x1800649a8`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180064a6e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180064a6e`
- `ntdll!RtlNtStatusToDosError` at `0x180064a7a`
- `ntdll!RtlNtStatusToDosError` at `0x180064a7a`
- `ntdll!RtlFreeSid` at `0x180064b7f`
- `ntdll!RtlFreeSid` at `0x180064b7f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180064b43`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180064b43`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180064b18`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180064b18`
- `ADVAPI32!SetEntriesInAclW` at `0x180064af7`
- `ADVAPI32!SetEntriesInAclW` at `0x180064af7`
- `KERNEL32!GetLastError` at `0x180064b22`
- `KERNEL32!GetLastError` at `0x180064b4d`
- `KERNEL32!GetLastError` at `0x180064b22`
- `KERNEL32!GetLastError` at `0x180064b4d`

## string_xrefs

- `0x180064a80`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x180064b03`: `SetEntriesInAcl [%d]`
- `0x180064b28`: `InitializeSecurityDescriptor failed [%d]`
- `0x180064b53`: `SetSecurityDescriptorDacl failed [%d]`
- `0x180064b62`: `UtcThrottle::InitializeSecurityDesc`

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
  DWORD v9; // ebx
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
  v9 = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, a3);
  if ( !v9 )
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
  AslLogCallPrintf(1, (unsigned int)"UtcThrottle::InitializeSecurityDesc", v8, (_DWORD)v7);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v9;
}

```

## disassembly

```asm
0x1800649a8  mov     [rsp-8+arg_0], rbx
0x1800649ad  push    rbp
0x1800649ae  push    rsi
0x1800649af  push    rdi
0x1800649b0  push    r14
0x1800649b2  push    r15
0x1800649b4  lea     rbp, [rsp-30h]
0x1800649b9  sub     rsp, 130h
0x1800649c0  mov     rax, cs:__security_cookie
0x1800649c7  xor     rax, rsp
0x1800649ca  mov     [rbp+50h+var_30], rax
0x1800649ce  mov     rsi, r8
0x1800649d1  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x1800649d5  mov     rdi, rdx
0x1800649d8  xor     r14d, r14d
0x1800649db  xor     edx, edx; Val
0x1800649dd  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x1800649e1  mov     r8d, 8Ch; Size
0x1800649e7  call    memset_0
0x1800649ec  lea     rax, [rsp+150h+var_F0]
0x1800649f1  mov     [rsp+150h+var_E0], 101h
0x1800649f9  mov     [rsp+150h+Sid], rax; Sid
0x1800649fe  lea     ebx, [r14+2]
0x180064a02  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x180064a07  lea     r8d, [r14+20h]; SubAuthority0
0x180064a0b  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180064a10  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x180064a15  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180064a1a  lea     r15d, [r14+1]
0x180064a1e  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x180064a23  mov     r9d, 220h; SubAuthority1
0x180064a29  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180064a2e  mov     dl, bl; SubAuthorityCount
0x180064a30  mov     [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x180064a35  mov     [rsp+150h+var_DC], 5000000h
0x180064a3d  mov     [rsp+150h+var_D8], 12h
0x180064a45  mov     [rbp+50h+var_D0], 101h
0x180064a4c  mov     [rbp+50h+var_CC], 5000000h
0x180064a53  mov     [rbp+50h+var_C8], 13h
0x180064a5a  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x180064a5f  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180064a66  mov     [rsi], r14
0x180064a69  mov     [rsp+150h+var_F0], r14
0x180064a6e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180064a74  test    eax, eax
0x180064a76  jns     short loc_180064A92
0x180064a78  mov     ecx, eax; Status
0x180064a7a  call    cs:__imp_RtlNtStatusToDosError
0x180064a80  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180064a87  mov     r8d, 237h
0x180064a8d  jmp     loc_180064B60
0x180064a92  mov     ecx, 100F0000h
0x180064a97  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x180064a9a  mov     r10d, 3
0x180064aa0  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180064aa3  lea     rax, [rsp+150h+var_E0]
0x180064aa8  mov     [rbp+50h+var_90], ecx
0x180064aab  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180064aaf  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180064ab3  lea     rax, [rbp+50h+var_D0]
0x180064ab7  mov     [rbp+50h+var_60], ecx
0x180064aba  mov     [rbp+50h+var_68], rax
0x180064abe  mov     r9, rsi; NewAcl
0x180064ac1  mov     rax, [rsp+150h+var_F0]
0x180064ac6  xor     r8d, r8d; OldAcl
0x180064ac9  mov     ecx, r10d; cCountOfExplicitEntries
0x180064acc  mov     [rbp+50h+var_38], rax
0x180064ad0  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180064ad4  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180064ad8  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x180064adb  mov     [rbp+50h+var_8C], ebx
0x180064ade  mov     [rbp+50h+var_88], r10d
0x180064ae2  mov     [rbp+50h+var_74], r14d
0x180064ae6  mov     [rbp+50h+var_70], ebx
0x180064ae9  mov     [rbp+50h+var_5C], ebx
0x180064aec  mov     [rbp+50h+var_58], r10d
0x180064af0  mov     [rbp+50h+var_44], r14d
0x180064af4  mov     [rbp+50h+var_40], ebx
0x180064af7  call    cs:__imp_SetEntriesInAclW
0x180064afd  mov     ebx, eax
0x180064aff  test    eax, eax
0x180064b01  jz      short loc_180064B12
0x180064b03  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x180064b0a  mov     r8d, 25Ah
0x180064b10  jmp     short loc_180064B62
0x180064b12  mov     edx, r15d; dwRevision
0x180064b15  mov     rcx, rdi; pSecurityDescriptor
0x180064b18  call    cs:__imp_InitializeSecurityDescriptor
0x180064b1e  test    eax, eax
0x180064b20  jnz     short loc_180064B37
0x180064b22  call    cs:__imp_GetLastError
0x180064b28  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180064b2f  mov     r8d, 261h
0x180064b35  jmp     short loc_180064B60
0x180064b37  mov     r8, [rsi]; pDacl
0x180064b3a  xor     r9d, r9d; bDaclDefaulted
0x180064b3d  mov     edx, r15d; bDaclPresent
0x180064b40  mov     rcx, rdi; pSecurityDescriptor
0x180064b43  call    cs:__imp_SetSecurityDescriptorDacl
0x180064b49  test    eax, eax
0x180064b4b  jnz     short loc_180064B75
0x180064b4d  call    cs:__imp_GetLastError
0x180064b53  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x180064b5a  mov     r8d, 26Ah
0x180064b60  mov     ebx, eax
0x180064b62  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x180064b69  mov     [rsp+150h+SubAuthority2], eax
0x180064b6d  mov     ecx, r15d
0x180064b70  call    AslLogCallPrintf
0x180064b75  mov     rcx, [rsp+150h+var_F0]; Sid
0x180064b7a  test    rcx, rcx
0x180064b7d  jz      short loc_180064B85
0x180064b7f  call    cs:__imp_RtlFreeSid
0x180064b85  mov     eax, ebx
0x180064b87  mov     rcx, [rbp+50h+var_30]
0x180064b8b  xor     rcx, rsp; StackCookie
0x180064b8e  call    __security_check_cookie
0x180064b93  mov     rbx, [rsp+150h+arg_0]
0x180064b9b  add     rsp, 130h
0x180064ba2  pop     r15
0x180064ba4  pop     r14
0x180064ba6  pop     rdi
0x180064ba7  pop     rsi
0x180064ba8  pop     rbp
0x180064ba9  retn
```
