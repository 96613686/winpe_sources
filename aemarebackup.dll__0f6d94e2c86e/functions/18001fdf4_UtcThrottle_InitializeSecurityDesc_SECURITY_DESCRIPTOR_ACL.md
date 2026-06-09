# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x18001fdf4`
- end: `0x18001fff6`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f868`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18001fdf4`
- `0x18004c020`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001fec6`
- `ntdll!RtlNtStatusToDosError` at `0x18001fec6`
- `ntdll!RtlFreeSid` at `0x18001ffcb`
- `ntdll!RtlFreeSid` at `0x18001ffcb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001feba`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff99`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001ff64`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001ff64`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001ff8f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001ff8f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001ff43`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001ff43`

## string_xrefs

- `0x18001fecc`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x18001ff4f`: `SetEntriesInAcl [%d]`
- `0x18001ff74`: `InitializeSecurityDescriptor failed [%d]`
- `0x18001ff9f`: `SetSecurityDescriptorDacl failed [%d]`
- `0x18001ffae`: `UtcThrottle::InitializeSecurityDesc`

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
0x18001fdf4  mov     [rsp-8+arg_0], rbx
0x18001fdf9  push    rbp
0x18001fdfa  push    rsi
0x18001fdfb  push    rdi
0x18001fdfc  push    r14
0x18001fdfe  push    r15
0x18001fe00  lea     rbp, [rsp-30h]
0x18001fe05  sub     rsp, 130h
0x18001fe0c  mov     rax, cs:__security_cookie
0x18001fe13  xor     rax, rsp
0x18001fe16  mov     [rbp+50h+var_30], rax
0x18001fe1a  mov     rsi, r8
0x18001fe1d  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x18001fe21  mov     rdi, rdx
0x18001fe24  xor     r14d, r14d
0x18001fe27  xor     edx, edx; Val
0x18001fe29  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x18001fe2d  mov     r8d, 8Ch; Size
0x18001fe33  call    memset_0
0x18001fe38  lea     rax, [rsp+150h+var_F0]
0x18001fe3d  mov     [rsp+150h+var_E0], 101h
0x18001fe45  mov     [rsp+150h+Sid], rax; Sid
0x18001fe4a  lea     ebx, [r14+2]
0x18001fe4e  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x18001fe53  lea     r8d, [r14+20h]; SubAuthority0
0x18001fe57  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x18001fe5c  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x18001fe61  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x18001fe66  lea     r15d, [r14+1]
0x18001fe6a  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x18001fe6f  mov     r9d, 220h; SubAuthority1
0x18001fe75  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x18001fe7a  mov     dl, bl; SubAuthorityCount
0x18001fe7c  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x18001fe81  mov     [rsp+150h+var_DC], 5000000h
0x18001fe89  mov     [rsp+150h+var_D8], 12h
0x18001fe91  mov     [rbp+50h+var_D0], 101h
0x18001fe98  mov     [rbp+50h+var_CC], 5000000h
0x18001fe9f  mov     [rbp+50h+var_C8], 13h
0x18001fea6  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x18001feab  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x18001feb2  mov     [rsi], r14
0x18001feb5  mov     [rsp+150h+var_F0], r14
0x18001feba  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001fec0  test    eax, eax
0x18001fec2  jns     short loc_18001FEDE
0x18001fec4  mov     ecx, eax; Status
0x18001fec6  call    cs:__imp_RtlNtStatusToDosError
0x18001fecc  lea     r9, aRtlallocateand_0; "RtlAllocateAndInitializeSid failed [%d]"
0x18001fed3  mov     r8d, 237h
0x18001fed9  jmp     loc_18001FFAC
0x18001fede  mov     ecx, 100F0000h
0x18001fee3  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x18001fee6  mov     r10d, 3
0x18001feec  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x18001feef  lea     rax, [rsp+150h+var_E0]
0x18001fef4  mov     [rbp+50h+var_90], ecx
0x18001fef7  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18001fefb  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001feff  lea     rax, [rbp+50h+var_D0]
0x18001ff03  mov     [rbp+50h+var_60], ecx
0x18001ff06  mov     [rbp+50h+var_68], rax
0x18001ff0a  mov     r9, rsi; NewAcl
0x18001ff0d  mov     rax, [rsp+150h+var_F0]
0x18001ff12  xor     r8d, r8d; OldAcl
0x18001ff15  mov     ecx, r10d; cCountOfExplicitEntries
0x18001ff18  mov     [rbp+50h+var_38], rax
0x18001ff1c  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x18001ff20  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18001ff24  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x18001ff27  mov     [rbp+50h+var_8C], ebx
0x18001ff2a  mov     [rbp+50h+var_88], r10d
0x18001ff2e  mov     [rbp+50h+var_74], r14d
0x18001ff32  mov     [rbp+50h+var_70], ebx
0x18001ff35  mov     [rbp+50h+var_5C], ebx
0x18001ff38  mov     [rbp+50h+var_58], r10d
0x18001ff3c  mov     [rbp+50h+var_44], r14d
0x18001ff40  mov     [rbp+50h+var_40], ebx
0x18001ff43  call    cs:__imp_SetEntriesInAclW
0x18001ff49  mov     ebx, eax
0x18001ff4b  test    eax, eax
0x18001ff4d  jz      short loc_18001FF5E
0x18001ff4f  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x18001ff56  mov     r8d, 25Ah
0x18001ff5c  jmp     short loc_18001FFAE
0x18001ff5e  mov     edx, r15d; dwRevision
0x18001ff61  mov     rcx, rdi; pSecurityDescriptor
0x18001ff64  call    cs:__imp_InitializeSecurityDescriptor
0x18001ff6a  test    eax, eax
0x18001ff6c  jnz     short loc_18001FF83
0x18001ff6e  call    cs:__imp_GetLastError
0x18001ff74  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x18001ff7b  mov     r8d, 261h
0x18001ff81  jmp     short loc_18001FFAC
0x18001ff83  mov     r8, [rsi]; pDacl
0x18001ff86  xor     r9d, r9d; bDaclDefaulted
0x18001ff89  mov     edx, r15d; bDaclPresent
0x18001ff8c  mov     rcx, rdi; pSecurityDescriptor
0x18001ff8f  call    cs:__imp_SetSecurityDescriptorDacl
0x18001ff95  test    eax, eax
0x18001ff97  jnz     short loc_18001FFC1
0x18001ff99  call    cs:__imp_GetLastError
0x18001ff9f  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x18001ffa6  mov     r8d, 26Ah
0x18001ffac  mov     ebx, eax
0x18001ffae  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x18001ffb5  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x18001ffb9  mov     ecx, r15d
0x18001ffbc  call    AslLogCallPrintf
0x18001ffc1  mov     rcx, [rsp+150h+var_F0]; Sid
0x18001ffc6  test    rcx, rcx
0x18001ffc9  jz      short loc_18001FFD1
0x18001ffcb  call    cs:__imp_RtlFreeSid
0x18001ffd1  mov     eax, ebx
0x18001ffd3  mov     rcx, [rbp+50h+var_30]
0x18001ffd7  xor     rcx, rsp; StackCookie
0x18001ffda  call    __security_check_cookie
0x18001ffdf  mov     rbx, [rsp+150h+arg_0]
0x18001ffe7  add     rsp, 130h
0x18001ffee  pop     r15
0x18001fff0  pop     r14
0x18001fff2  pop     rdi
0x18001fff3  pop     rsi
0x18001fff4  pop     rbp
0x18001fff5  retn
```
