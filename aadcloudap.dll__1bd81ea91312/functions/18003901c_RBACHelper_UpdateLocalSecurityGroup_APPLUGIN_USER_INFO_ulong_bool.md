# RBACHelper::UpdateLocalSecurityGroup(_APPLUGIN_USER_INFO *,ulong,bool)

- ea: `0x18003901c`
- end: `0x18003940b`
- name: `?UpdateLocalSecurityGroup@RBACHelper@@CAJPEAU_APPLUGIN_USER_INFO@@K_N@Z`
- size: `1007`
- prototype: `__int64 __fastcall(struct _APPLUGIN_USER_INFO *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037e20`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x18001ceb4`
- `0x180038a20`
- `0x18003901c`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003912b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003912b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391bf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180039107`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180039107`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800393cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800393cb`
- `samcli!NetLocalGroupAddMembers` at `0x18003926f`
- `samcli!NetLocalGroupAddMembers` at `0x18003926f`
- `samcli!NetLocalGroupDelMembers` at `0x18003931c`
- `samcli!NetLocalGroupDelMembers` at `0x18003931c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800391a1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800391a1`

## string_xrefs

- `0x1800390b0`: `RBACHelper::UpdateLocalSecurityGroup`
- `0x1800392e1`: `Added user to admins security group`
- `0x18003938e`: `Removed user from admins security group`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RBACHelper::UpdateLocalSecurityGroup(struct _APPLUGIN_USER_INFO *a1, __int64 a2, bool a3)
{
  signed int matched; // ecx
  signed int v6; // eax
  __int64 v7; // r8
  signed int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  DWORD nSubAuthority2[2]; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority4[2]; // [rsp+30h] [rbp-D0h]
  const char *nSubAuthority5; // [rsp+38h] [rbp-C8h]
  bool v15; // [rsp+60h] [rbp-A0h] BYREF
  signed int v16; // [rsp+64h] [rbp-9Ch] BYREF
  _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  BYTE buf[8]; // [rsp+78h] [rbp-88h] BYREF
  PSID Sid; // [rsp+80h] [rbp-80h] BYREF
  const char *v22[6]; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v24[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v16 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 260;
  memset_0(ReferencedDomainName, 0, 0x208u);
  cchReferencedDomainName = 260;
  peUse = 0;
  *(_QWORD *)buf = 0;
  v15 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v22,
    (int)"rbachelper.cpp",
    (int)"RBACHelper::UpdateLocalSecurityGroup",
    (int)&v16);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    matched = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v16 = matched;
    if ( matched < 0 )
    {
      nSubAuthority4[0] = 394;
LABEL_7:
      nSubAuthority2[0] = matched;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        *(_QWORD *)nSubAuthority2,
        "rbachelper.cpp",
        *(_QWORD *)nSubAuthority4,
        "NTSTATUS",
        &base);
      goto LABEL_34;
    }
  }
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    matched = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v16 = matched;
    if ( matched < 0 )
    {
      nSubAuthority4[0] = 399;
      goto LABEL_7;
    }
  }
  matched = RBACHelper::MatchGroupMembership(a1, Name, a3, &v15);
  v16 = matched;
  if ( matched < 0 )
  {
    nSubAuthority4[0] = 402;
    goto LABEL_7;
  }
  *(_QWORD *)buf = *((_QWORD *)a1 + 2);
  if ( a3 )
  {
    if ( v15 )
      goto LABEL_34;
    v6 = NetLocalGroupAddMembers(0, Name, 0, buf, 1u);
    matched = v6;
    if ( v6 > 0 )
      matched = (unsigned __int16)v6 | 0xC0070000;
    v16 = matched;
    if ( matched < 0 )
    {
      nSubAuthority4[0] = 409;
      goto LABEL_7;
    }
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_RBAC_UserAddedToAdminSecurityGroup,
        v7,
        1,
        v24);
    nSubAuthority5 = "Added user to admins security group";
    nSubAuthority4[0] = 411;
  }
  else
  {
    if ( !v15 )
      goto LABEL_34;
    v8 = NetLocalGroupDelMembers(0, Name, 0, buf, 1u);
    matched = v8;
    if ( v8 > 0 )
      matched = (unsigned __int16)v8 | 0xC0070000;
    v16 = matched;
    if ( matched < 0 )
    {
      nSubAuthority4[0] = 416;
      goto LABEL_7;
    }
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_RBAC_UserRemovedFromAdminSecurityGroup,
        v9,
        1,
        v24);
    nSubAuthority5 = "Removed user from admins security group";
    nSubAuthority4[0] = 418;
  }
  WPPTraceLogA(
    4,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    4,
    0,
    "rbachelper.cpp",
    *(_QWORD *)nSubAuthority4,
    nSubAuthority5,
    &base);
LABEL_34:
  if ( Sid )
    FreeSid(Sid);
  v10 = v16;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v22);
  return v10;
}

```

## disassembly

```asm
0x18003901c  mov     [rsp-8+arg_8], rbx
0x180039021  mov     [rsp-8+arg_18], rsi
0x180039026  push    rbp
0x180039027  push    rdi
0x180039028  push    r12
0x18003902a  push    r14
0x18003902c  push    r15
0x18003902e  lea     rbp, [rsp-400h]
0x180039036  sub     rsp, 500h
0x18003903d  mov     rax, cs:__security_cookie
0x180039044  xor     rax, rsp
0x180039047  mov     [rbp+420h+var_30], rax
0x18003904e  mov     dil, r8b
0x180039051  mov     rbx, rcx
0x180039054  xor     r15d, r15d
0x180039057  mov     [rsp+520h+var_4BC], r15d
0x18003905c  mov     dword ptr [rbp+420h+pIdentifierAuthority.Value], r15d
0x180039060  mov     word ptr [rbp+420h+pIdentifierAuthority.Value+4], 500h
0x180039066  mov     [rbp+420h+Sid], r15
0x18003906a  mov     r14d, 208h
0x180039070  mov     r8d, r14d; Size
0x180039073  xor     edx, edx; Val
0x180039075  lea     rcx, [rbp+420h+Name]; void *
0x180039079  call    memset_0
0x18003907e  mov     esi, 104h
0x180039083  mov     [rsp+520h+cchName], esi
0x180039087  mov     r8d, r14d; Size
0x18003908a  xor     edx, edx; Val
0x18003908c  lea     rcx, [rbp+420h+ReferencedDomainName]; void *
0x180039093  call    memset_0
0x180039098  mov     [rsp+520h+cchReferencedDomainName], esi
0x18003909c  mov     [rsp+520h+peUse], r15d
0x1800390a1  mov     qword ptr [rsp+520h+buf], r15
0x1800390a6  mov     [rsp+520h+var_4C0], r15b
0x1800390ab  lea     r9, [rsp+520h+var_4BC]
0x1800390b0  lea     r8, aRbachelperUpda; "RBACHelper::UpdateLocalSecurityGroup"
0x1800390b7  lea     r14, aOnecoreuapDsEx_18+21h; "rbachelper.cpp"
0x1800390be  mov     rdx, r14
0x1800390c1  lea     rcx, [rbp+420h+var_498]
0x1800390c5  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800390ca  nop
0x1800390cb  lea     rax, [rbp+420h+Sid]
0x1800390cf  mov     [rsp+520h+pSid], rax; pSid
0x1800390d4  mov     [rsp+520h+nSubAuthority7], r15d; nSubAuthority7
0x1800390d9  mov     [rsp+520h+nSubAuthority6], r15d; nSubAuthority6
0x1800390de  mov     [rsp+520h+nSubAuthority5], r15d; nSubAuthority5
0x1800390e3  mov     [rsp+520h+nSubAuthority4], r15d; nSubAuthority4
0x1800390e8  mov     [rsp+520h+nSubAuthority3], r15d; nSubAuthority3
0x1800390ed  mov     [rsp+520h+nSubAuthority2], r15d; nSubAuthority2
0x1800390f2  lea     esi, [r15+2]
0x1800390f6  mov     r9d, 220h; nSubAuthority1
0x1800390fc  lea     r8d, [r15+20h]; nSubAuthority0
0x180039100  mov     dl, sil; nSubAuthorityCount
0x180039103  lea     rcx, [rbp+420h+pIdentifierAuthority]; pIdentifierAuthority
0x180039107  call    cs:__imp_AllocateAndInitializeSid
0x18003910d  mov     r12d, 0C0070000h
0x180039113  test    eax, eax
0x180039115  jnz     short loc_180039172
0x180039117  call    cs:__imp_GetLastError
0x18003911d  test    eax, eax
0x18003911f  jg      short loc_18003912B
0x180039121  call    cs:__imp_GetLastError
0x180039127  mov     ecx, eax
0x180039129  jmp     short loc_180039137
0x18003912b  call    cs:__imp_GetLastError
0x180039131  movzx   ecx, ax
0x180039134  or      ecx, r12d
0x180039137  mov     [rsp+520h+var_4BC], ecx
0x18003913b  test    ecx, ecx
0x18003913d  jns     short loc_180039172
0x18003913f  lea     rax, base
0x180039146  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x18003914b  lea     rax, aNtstatus; "NTSTATUS"
0x180039152  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x180039157  mov     [rsp+520h+nSubAuthority4], 18Ah
0x18003915f  mov     qword ptr [rsp+520h+nSubAuthority3], r14
0x180039164  mov     [rsp+520h+nSubAuthority2], ecx
0x180039168  mov     r9d, esi
0x18003916b  mov     ecx, esi
0x18003916d  jmp     loc_1800393B4
0x180039172  lea     rax, [rsp+520h+peUse]
0x180039177  mov     qword ptr [rsp+520h+nSubAuthority4], rax; peUse
0x18003917c  lea     rax, [rsp+520h+cchReferencedDomainName]
0x180039181  mov     qword ptr [rsp+520h+nSubAuthority3], rax; cchReferencedDomainName
0x180039186  lea     rax, [rbp+420h+ReferencedDomainName]
0x18003918d  mov     qword ptr [rsp+520h+nSubAuthority2], rax; ReferencedDomainName
0x180039192  lea     r9, [rsp+520h+cchName]; cchName
0x180039197  lea     r8, [rbp+420h+Name]; Name
0x18003919b  mov     rdx, [rbp+420h+Sid]; Sid
0x18003919f  xor     ecx, ecx; lpSystemName
0x1800391a1  call    cs:__imp_LookupAccountSidW
0x1800391a7  test    eax, eax
0x1800391a9  jnz     short loc_1800391F8
0x1800391ab  call    cs:__imp_GetLastError
0x1800391b1  test    eax, eax
0x1800391b3  jg      short loc_1800391BF
0x1800391b5  call    cs:__imp_GetLastError
0x1800391bb  mov     ecx, eax
0x1800391bd  jmp     short loc_1800391CB
0x1800391bf  call    cs:__imp_GetLastError
0x1800391c5  movzx   ecx, ax
0x1800391c8  or      ecx, r12d
0x1800391cb  mov     [rsp+520h+var_4BC], ecx
0x1800391cf  test    ecx, ecx
0x1800391d1  jns     short loc_1800391F8
0x1800391d3  lea     rax, base
0x1800391da  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x1800391df  lea     rax, aNtstatus; "NTSTATUS"
0x1800391e6  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x1800391eb  mov     [rsp+520h+nSubAuthority4], 18Fh
0x1800391f3  jmp     loc_18003915F
0x1800391f8  lea     r9, [rsp+520h+var_4C0]; bool *
0x1800391fd  mov     r8b, dil; bool
0x180039200  lea     rdx, [rbp+420h+Name]; unsigned __int16 *
0x180039204  mov     rcx, rbx; struct _APPLUGIN_USER_INFO *
0x180039207  call    ?MatchGroupMembership@RBACHelper@@CAJPEAU_APPLUGIN_USER_INFO@@PEAG_NPEA_N@Z; RBACHelper::MatchGroupMembership(_APPLUGIN_USER_INFO *,ushort *,bool,bool *)
0x18003920c  mov     ecx, eax
0x18003920e  mov     [rsp+520h+var_4BC], eax
0x180039212  test    eax, eax
0x180039214  jns     short loc_18003923B
0x180039216  lea     rax, base
0x18003921d  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x180039222  lea     rax, aNtstatus; "NTSTATUS"
0x180039229  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x18003922e  mov     [rsp+520h+nSubAuthority4], 192h
0x180039236  jmp     loc_18003915F
0x18003923b  mov     rax, [rbx+10h]
0x18003923f  mov     qword ptr [rsp+520h+buf], rax
0x180039244  test    dil, dil
0x180039247  jz      loc_1800392FA
0x18003924d  cmp     [rsp+520h+var_4C0], r15b
0x180039252  jnz     loc_1800393C2
0x180039258  mov     ebx, 1
0x18003925d  mov     [rsp+520h+nSubAuthority2], ebx; totalentries
0x180039261  lea     r9, [rsp+520h+buf]; buf
0x180039266  xor     r8d, r8d; level
0x180039269  lea     rdx, [rbp+420h+Name]; groupname
0x18003926d  xor     ecx, ecx; servername
0x18003926f  call    cs:__imp_NetLocalGroupAddMembers
0x180039275  mov     ecx, eax
0x180039277  test    eax, eax
0x180039279  jle     short loc_180039281
0x18003927b  movzx   ecx, ax
0x18003927e  or      ecx, r12d
0x180039281  mov     [rsp+520h+var_4BC], ecx
0x180039285  test    ecx, ecx
0x180039287  jns     short loc_1800392AE
0x180039289  lea     rax, base
0x180039290  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x180039295  lea     rax, aNtstatus; "NTSTATUS"
0x18003929c  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x1800392a1  mov     [rsp+520h+nSubAuthority4], 199h
0x1800392a9  jmp     loc_18003915F
0x1800392ae  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x1800392b4  jz      short loc_1800392D5
0x1800392b6  lea     rax, [rbp+420h+var_460]
0x1800392ba  mov     qword ptr [rsp+520h+nSubAuthority2], rax
0x1800392bf  mov     r9d, ebx
0x1800392c2  lea     rdx, Aad_CloudAPPlugin_RBAC_UserAddedToAdminSecurityGroup
0x1800392c9  lea     rcx, Microsoft_Windows_AAD_Context
0x1800392d0  call    McGenEventWrite_EventWriteTransfer
0x1800392d5  lea     rax, base
0x1800392dc  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x1800392e1  lea     rax, aAddedUserToAdm; "Added user to admins security group"
0x1800392e8  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x1800392ed  mov     [rsp+520h+nSubAuthority4], 19Bh
0x1800392f5  jmp     loc_1800393A2
0x1800392fa  cmp     [rsp+520h+var_4C0], r15b
0x1800392ff  jz      loc_1800393C2
0x180039305  mov     ebx, 1
0x18003930a  mov     [rsp+520h+nSubAuthority2], ebx; totalentries
0x18003930e  lea     r9, [rsp+520h+buf]; buf
0x180039313  xor     r8d, r8d; level
0x180039316  lea     rdx, [rbp+420h+Name]; groupname
0x18003931a  xor     ecx, ecx; servername
0x18003931c  call    cs:__imp_NetLocalGroupDelMembers
0x180039322  mov     ecx, eax
0x180039324  test    eax, eax
0x180039326  jle     short loc_18003932E
0x180039328  movzx   ecx, ax
0x18003932b  or      ecx, r12d
0x18003932e  mov     [rsp+520h+var_4BC], ecx
0x180039332  test    ecx, ecx
0x180039334  jns     short loc_18003935B
0x180039336  lea     rax, base
0x18003933d  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x180039342  lea     rax, aNtstatus; "NTSTATUS"
0x180039349  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x18003934e  mov     [rsp+520h+nSubAuthority4], 1A0h
0x180039356  jmp     loc_18003915F
0x18003935b  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x180039361  jz      short loc_180039382
0x180039363  lea     rax, [rbp+420h+var_460]
0x180039367  mov     qword ptr [rsp+520h+nSubAuthority2], rax
0x18003936c  mov     r9d, ebx
0x18003936f  lea     rdx, Aad_CloudAPPlugin_RBAC_UserRemovedFromAdminSecurityGroup
0x180039376  lea     rcx, Microsoft_Windows_AAD_Context
0x18003937d  call    McGenEventWrite_EventWriteTransfer
0x180039382  lea     rax, base
0x180039389  mov     qword ptr [rsp+520h+nSubAuthority6], rax
0x18003938e  lea     rax, aRemovedUserFro; "Removed user from admins security group"
0x180039395  mov     qword ptr [rsp+520h+nSubAuthority5], rax
0x18003939a  mov     [rsp+520h+nSubAuthority4], 1A2h
0x1800393a2  mov     ecx, 4
0x1800393a7  mov     qword ptr [rsp+520h+nSubAuthority3], r14
0x1800393ac  mov     r9d, ecx
0x1800393af  mov     qword ptr [rsp+520h+nSubAuthority2], r15
0x1800393b4  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800393bb  xor     edx, edx
0x1800393bd  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800393c2  mov     rcx, [rbp+420h+Sid]; pSid
0x1800393c6  test    rcx, rcx
0x1800393c9  jz      short loc_1800393D1
0x1800393cb  call    cs:__imp_FreeSid
0x1800393d1  mov     ebx, [rsp+520h+var_4BC]
0x1800393d5  lea     rcx, [rbp+420h+var_498]
0x1800393d9  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800393de  mov     eax, ebx
0x1800393e0  mov     rcx, [rbp+420h+var_30]
0x1800393e7  xor     rcx, rsp; StackCookie
0x1800393ea  call    __security_check_cookie
0x1800393ef  lea     r11, [rsp+520h+var_20]
0x1800393f7  mov     rbx, [r11+38h]
0x1800393fb  mov     rsi, [r11+48h]
0x1800393ff  mov     rsp, r11
0x180039402  pop     r15
0x180039404  pop     r14
0x180039406  pop     r12
0x180039408  pop     rdi
0x180039409  pop     rbp
0x18003940a  retn
```
