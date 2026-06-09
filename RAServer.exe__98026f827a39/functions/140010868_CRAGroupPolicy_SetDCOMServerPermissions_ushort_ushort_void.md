# CRAGroupPolicy::SetDCOMServerPermissions(ushort *,ushort *,void *)

- ea: `0x140010868`
- end: `0x140010c9b`
- name: `?SetDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z`
- size: `1075`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fc0c`

## callees

- `0x140010868`
- `0x1400111c8`
- `0x140015240`
- `0x140015400`
- `0x140015a62`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x140010b55`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140010b55`
- `ADVAPI32!InitializeAcl` at `0x140010a8b`
- `ADVAPI32!InitializeAcl` at `0x140010a8b`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140010be9`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140010be9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010952`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400109f4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010952`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400109f4`
- `ADVAPI32!GetLengthSid` at `0x140010a12`
- `ADVAPI32!GetLengthSid` at `0x140010a27`
- `ADVAPI32!GetLengthSid` at `0x140010a12`
- `ADVAPI32!GetLengthSid` at `0x140010a27`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010abc`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010ae5`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010b06`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010b2f`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010abc`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010ae5`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010b06`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010b2f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140010b80`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140010b80`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140010ba7`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140010ba7`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140010bcb`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140010bcb`
- `ADVAPI32!FreeSid` at `0x140010c59`
- `ADVAPI32!FreeSid` at `0x140010c6c`
- `ADVAPI32!FreeSid` at `0x140010c59`
- `ADVAPI32!FreeSid` at `0x140010c6c`
- `KERNEL32!GetLastError` at `0x140010960`
- `KERNEL32!GetLastError` at `0x1400109fe`
- `KERNEL32!GetLastError` at `0x140010a98`
- `KERNEL32!GetLastError` at `0x140010ac6`
- `KERNEL32!GetLastError` at `0x140010aef`
- `KERNEL32!GetLastError` at `0x140010b10`
- `KERNEL32!GetLastError` at `0x140010b39`
- `KERNEL32!GetLastError` at `0x140010b5f`
- `KERNEL32!GetLastError` at `0x140010b8a`
- `KERNEL32!GetLastError` at `0x140010bb1`
- `KERNEL32!GetLastError` at `0x140010bd5`
- `KERNEL32!GetLastError` at `0x140010bf3`
- `KERNEL32!GetLastError` at `0x140010960`
- `KERNEL32!GetLastError` at `0x1400109fe`
- `KERNEL32!GetLastError` at `0x140010a98`
- `KERNEL32!GetLastError` at `0x140010ac6`
- `KERNEL32!GetLastError` at `0x140010aef`
- `KERNEL32!GetLastError` at `0x140010b10`
- `KERNEL32!GetLastError` at `0x140010b39`
- `KERNEL32!GetLastError` at `0x140010b5f`
- `KERNEL32!GetLastError` at `0x140010b8a`
- `KERNEL32!GetLastError` at `0x140010bb1`
- `KERNEL32!GetLastError` at `0x140010bd5`
- `KERNEL32!GetLastError` at `0x140010bf3`
- `KERNEL32!HeapAlloc` at `0x140010a42`
- `KERNEL32!HeapAlloc` at `0x140010a42`
- `KERNEL32!GetProcessHeap` at `0x140010a34`
- `KERNEL32!GetProcessHeap` at `0x140010c3c`
- `KERNEL32!GetProcessHeap` at `0x140010a34`
- `KERNEL32!GetProcessHeap` at `0x140010c3c`
- `KERNEL32!HeapFree` at `0x140010c4a`
- `KERNEL32!HeapFree` at `0x140010c4a`

## string_xrefs

- `0x1400108ce`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14001096c`: `CRAGroupPolicy::SetDCOMServerPermissions`
- `0x140010a50`: `CRAGroupPolicy::SetDCOMServerPermissions`
- `0x140010c23`: `CRAGroupPolicy::SetDCOMServerPermissions`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::SetDCOMServerPermissions(
        CRAGroupPolicy *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4)
{
  CEventLogger *v5; // rcx
  int v6; // r15d
  DWORD v7; // r13d
  CEventLogger *v8; // rcx
  DWORD LastError; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  unsigned int v11; // r9d
  DWORD v12; // ebx
  CEventLogger *v13; // rcx
  DWORD LengthSid; // eax
  PSID v15; // rcx
  DWORD v16; // r12d
  HANDLE ProcessHeap; // rax
  ACL *v18; // rax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  ACL *v20; // rsi
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  unsigned int v22; // r9d
  CRAGroupPolicy *v23; // rcx
  HANDLE v24; // rax
  DWORD AccessMask; // [rsp+60h] [rbp-39h]
  DWORD v27; // [rsp+64h] [rbp-35h]
  PSID pSid; // [rsp+68h] [rbp-31h] BYREF
  PSID v29; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v30; // [rsp+78h] [rbp-21h]
  struct _SECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+Fh] BYREF

  v30 = a3;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v29 = 0;
  pSid = 0;
  memset(&pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( !wcscmp_0(a3, L"LaunchPermission") )
  {
    v27 = 0;
    v6 = 1;
    CEventLogger::LogEvent(v5, &Enter_Conditional_Block, 0x18Cu, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    AccessMask = 21;
    v7 = 11;
    CEventLogger::LogEvent(v8, &Exit_Conditional_Block, 0x18Fu, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      LastError = GetLastError();
      v11 = 432;
LABEL_4:
      v12 = LastError;
      CEventLogger::LogError(
        (CEventLogger *)L"CRAGroupPolicy::SetDCOMServerPermissions",
        v10,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        v11,
        L"CRAGroupPolicy::SetDCOMServerPermissions",
        0);
      goto LABEL_36;
    }
  }
  else
  {
    AccessMask = 0;
    CEventLogger::LogEvent(v5, &Enter_Conditional_Block, 0x192u, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    v27 = 7;
    v6 = 0;
    v7 = 3;
    CEventLogger::LogEvent(v13, &Exit_Conditional_Block, 0x196u, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &v29) )
    {
      LastError = GetLastError();
      v11 = 459;
      goto LABEL_4;
    }
  }
  LengthSid = GetLengthSid(a4);
  v15 = pSid;
  if ( !v6 )
    v15 = v29;
  v16 = GetLengthSid(v15) + LengthSid + 32;
  ProcessHeap = GetProcessHeap();
  v18 = (ACL *)HeapAlloc(ProcessHeap, 0, v16);
  v20 = v18;
  if ( !v18 )
  {
    v12 = 8;
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetDCOMServerPermissions",
      v19,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x1E3u,
      L"CRAGroupPolicy::SetDCOMServerPermissions",
      0x8007000E);
    goto LABEL_36;
  }
  if ( !InitializeAcl(v18, v16, 2u) )
  {
    v12 = GetLastError();
    v22 = 499;
LABEL_34:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetDCOMServerPermissions",
      v21,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v22,
      L"CRAGroupPolicy::SetDCOMServerPermissions",
      0);
    goto LABEL_35;
  }
  if ( v6 )
  {
    if ( !AddAccessAllowedAce(v20, 2u, AccessMask, a4) )
    {
      v12 = GetLastError();
      v22 = 515;
      goto LABEL_34;
    }
    if ( !AddAccessAllowedAce(v20, 2u, v7, pSid) )
    {
      v12 = GetLastError();
      v22 = 532;
      goto LABEL_34;
    }
  }
  else
  {
    if ( !AddAccessAllowedAce(v20, 2u, v27, a4) )
    {
      v12 = GetLastError();
      v22 = 547;
      goto LABEL_34;
    }
    if ( !AddAccessAllowedAce(v20, 2u, v7, v29) )
    {
      v12 = GetLastError();
      v22 = 564;
      goto LABEL_34;
    }
  }
  if ( !InitializeSecurityDescriptor(&pSecurityDescriptor, 1u) )
  {
    v12 = GetLastError();
    v22 = 578;
    goto LABEL_34;
  }
  if ( !SetSecurityDescriptorDacl(&pSecurityDescriptor, 1, v20, 0) )
  {
    v12 = GetLastError();
    v22 = 593;
    goto LABEL_34;
  }
  if ( !SetSecurityDescriptorOwner(&pSecurityDescriptor, a4, 0) )
  {
    v12 = GetLastError();
    v22 = 603;
    goto LABEL_34;
  }
  if ( !SetSecurityDescriptorGroup(&pSecurityDescriptor, a4, 0) )
  {
    v12 = GetLastError();
    v22 = 612;
    goto LABEL_34;
  }
  if ( !IsValidSecurityDescriptor(&pSecurityDescriptor) )
  {
    v12 = GetLastError();
    v22 = 621;
    goto LABEL_34;
  }
  v12 = CRAGroupPolicy::SetSDToRegistry(
          v23,
          L"SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}",
          v30,
          &pSecurityDescriptor);
  if ( v12 )
  {
    v22 = 630;
    goto LABEL_34;
  }
LABEL_35:
  v24 = GetProcessHeap();
  HeapFree(v24, 0, v20);
LABEL_36:
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v29 )
    FreeSid(v29);
  return v12;
}

```

## disassembly

```asm
0x140010868  mov     [rsp-8+arg_0], rbx
0x14001086d  push    rbp
0x14001086e  push    rsi
0x14001086f  push    rdi
0x140010870  push    r12
0x140010872  push    r13
0x140010874  push    r14
0x140010876  push    r15
0x140010878  lea     rbp, [rsp-27h]
0x14001087d  sub     rsp, 0C0h
0x140010884  mov     rax, cs:__security_cookie
0x14001088b  xor     rax, rsp
0x14001088e  mov     [rbp+57h+var_40], rax
0x140010892  xor     ecx, ecx
0x140010894  mov     [rbp+57h+var_78], r8
0x140010898  xorps   xmm0, xmm0
0x14001089b  mov     [rbp+57h+var_50], rcx
0x14001089f  xor     r12d, r12d
0x1400108a2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400108a8  mov     rcx, r8; String1
0x1400108ab  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1400108af  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x1400108b6  mov     [rbp+57h+var_80], r12
0x1400108ba  mov     r14, r9
0x1400108bd  mov     [rbp+57h+var_88], r12
0x1400108c1  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1400108c5  movups  [rbp+57h+var_60], xmm0
0x1400108c9  call    wcscmp_0
0x1400108ce  lea     rdi, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x1400108d5  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x1400108dc  mov     r9, rdi; unsigned __int16 *
0x1400108df  test    eax, eax
0x1400108e1  jnz     loc_14001098C
0x1400108e7  mov     r8d, 18Ch; unsigned int
0x1400108ed  mov     [rbp+57h+var_8C], r12d
0x1400108f1  lea     r15d, [r12+1]
0x1400108f6  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x1400108fb  mov     r9, rdi; unsigned __int16 *
0x1400108fe  mov     [rbp+57h+AccessMask], 15h
0x140010905  mov     r8d, 18Fh; unsigned int
0x14001090b  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x140010912  lea     r13d, [r12+0Bh]
0x140010917  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14001091c  lea     rax, [rbp+57h+var_88]
0x140010920  xor     r9d, r9d; nSubAuthority1
0x140010923  mov     [rsp+0F0h+pSid], rax; pSid
0x140010928  lea     r8d, [r12+4]; nSubAuthority0
0x14001092d  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x140010932  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140010936  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x14001093b  mov     dl, r15b; nSubAuthorityCount
0x14001093e  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x140010943  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x140010948  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x14001094d  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x140010952  call    cs:__imp_AllocateAndInitializeSid
0x140010958  test    eax, eax
0x14001095a  jnz     loc_140010A0F
0x140010960  call    cs:__imp_GetLastError
0x140010966  mov     r9d, 1B0h; unsigned int
0x14001096c  lea     rcx, aCragrouppolicy_9; "CRAGroupPolicy::SetDCOMServerPermission"...
0x140010973  mov     [rsp+0F0h+nSubAuthority3], r12d; unsigned int
0x140010978  mov     r8, rdi; unsigned __int16 *
0x14001097b  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x140010980  mov     ebx, eax
0x140010982  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010987  jmp     loc_140010C50
0x14001098c  mov     r8d, 192h; unsigned int
0x140010992  mov     [rbp+57h+AccessMask], r12d
0x140010996  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14001099b  mov     r9, rdi; unsigned __int16 *
0x14001099e  mov     [rbp+57h+var_8C], 7
0x1400109a5  mov     r8d, 196h; unsigned int
0x1400109ab  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x1400109b2  mov     r15d, r12d
0x1400109b5  mov     r13d, 3
0x1400109bb  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x1400109c0  lea     rax, [rbp+57h+var_80]
0x1400109c4  xor     r9d, r9d; nSubAuthority1
0x1400109c7  mov     [rsp+0F0h+pSid], rax; pSid
0x1400109cc  lea     r8d, [r13+7]; nSubAuthority0
0x1400109d0  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x1400109d5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400109d9  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x1400109de  mov     dl, 1; nSubAuthorityCount
0x1400109e0  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x1400109e5  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x1400109ea  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x1400109ef  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x1400109f4  call    cs:__imp_AllocateAndInitializeSid
0x1400109fa  test    eax, eax
0x1400109fc  jnz     short loc_140010A0F
0x1400109fe  call    cs:__imp_GetLastError
0x140010a04  mov     r9d, 1CBh
0x140010a0a  jmp     loc_14001096C
0x140010a0f  mov     rcx, r14; pSid
0x140010a12  call    cs:__imp_GetLengthSid
0x140010a18  mov     rcx, [rbp+57h+var_88]
0x140010a1c  mov     ebx, eax
0x140010a1e  test    r15d, r15d
0x140010a21  jnz     short loc_140010A27
0x140010a23  mov     rcx, [rbp+57h+var_80]; pSid
0x140010a27  call    cs:__imp_GetLengthSid
0x140010a2d  lea     r12d, [rbx+20h]
0x140010a31  add     r12d, eax
0x140010a34  call    cs:__imp_GetProcessHeap
0x140010a3a  mov     r8d, r12d; dwBytes
0x140010a3d  xor     edx, edx; dwFlags
0x140010a3f  mov     rcx, rax; hHeap
0x140010a42  call    cs:__imp_HeapAlloc
0x140010a48  mov     rsi, rax
0x140010a4b  test    rax, rax
0x140010a4e  jnz     short loc_140010A7D
0x140010a50  lea     rcx, aCragrouppolicy_9; "CRAGroupPolicy::SetDCOMServerPermission"...
0x140010a57  mov     [rsp+0F0h+nSubAuthority3], 8007000Eh; unsigned int
0x140010a5f  mov     r9d, 1E3h; unsigned int
0x140010a65  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x140010a6a  mov     r8, rdi; unsigned __int16 *
0x140010a6d  lea     ebx, [rax+8]
0x140010a70  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010a75  xor     r12d, r12d
0x140010a78  jmp     loc_140010C50
0x140010a7d  mov     ebx, 2
0x140010a82  mov     edx, r12d; nAclLength
0x140010a85  mov     r8d, ebx; dwAclRevision
0x140010a88  mov     rcx, rsi; pAcl
0x140010a8b  call    cs:__imp_InitializeAcl
0x140010a91  xor     r12d, r12d
0x140010a94  test    eax, eax
0x140010a96  jnz     short loc_140010AAB
0x140010a98  call    cs:__imp_GetLastError
0x140010a9e  mov     ebx, eax
0x140010aa0  mov     r9d, 1F3h
0x140010aa6  jmp     loc_140010C23
0x140010aab  mov     r9, r14; pSid
0x140010aae  mov     edx, ebx; dwAceRevision
0x140010ab0  mov     rcx, rsi; pAcl
0x140010ab3  test    r15d, r15d
0x140010ab6  jz      short loc_140010B02
0x140010ab8  mov     r8d, [rbp+57h+AccessMask]; AccessMask
0x140010abc  call    cs:__imp_AddAccessAllowedAce
0x140010ac2  test    eax, eax
0x140010ac4  jnz     short loc_140010AD9
0x140010ac6  call    cs:__imp_GetLastError
0x140010acc  mov     ebx, eax
0x140010ace  mov     r9d, 203h
0x140010ad4  jmp     loc_140010C23
0x140010ad9  mov     r9, [rbp+57h+var_88]; pSid
0x140010add  mov     r8d, r13d; AccessMask
0x140010ae0  mov     edx, ebx; dwAceRevision
0x140010ae2  mov     rcx, rsi; pAcl
0x140010ae5  call    cs:__imp_AddAccessAllowedAce
0x140010aeb  test    eax, eax
0x140010aed  jnz     short loc_140010B4C
0x140010aef  call    cs:__imp_GetLastError
0x140010af5  mov     ebx, eax
0x140010af7  mov     r9d, 214h
0x140010afd  jmp     loc_140010C23
0x140010b02  mov     r8d, [rbp+57h+var_8C]; AccessMask
0x140010b06  call    cs:__imp_AddAccessAllowedAce
0x140010b0c  test    eax, eax
0x140010b0e  jnz     short loc_140010B23
0x140010b10  call    cs:__imp_GetLastError
0x140010b16  mov     ebx, eax
0x140010b18  mov     r9d, 223h
0x140010b1e  jmp     loc_140010C23
0x140010b23  mov     r9, [rbp+57h+var_80]; pSid
0x140010b27  mov     r8d, r13d; AccessMask
0x140010b2a  mov     edx, ebx; dwAceRevision
0x140010b2c  mov     rcx, rsi; pAcl
0x140010b2f  call    cs:__imp_AddAccessAllowedAce
0x140010b35  test    eax, eax
0x140010b37  jnz     short loc_140010B4C
0x140010b39  call    cs:__imp_GetLastError
0x140010b3f  mov     ebx, eax
0x140010b41  mov     r9d, 234h
0x140010b47  jmp     loc_140010C23
0x140010b4c  mov     edx, 1; dwRevision
0x140010b51  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010b55  call    cs:__imp_InitializeSecurityDescriptor
0x140010b5b  test    eax, eax
0x140010b5d  jnz     short loc_140010B72
0x140010b5f  call    cs:__imp_GetLastError
0x140010b65  mov     ebx, eax
0x140010b67  mov     r9d, 242h
0x140010b6d  jmp     loc_140010C23
0x140010b72  xor     r9d, r9d; bDaclDefaulted
0x140010b75  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010b79  mov     r8, rsi; pDacl
0x140010b7c  lea     edx, [r9+1]; bDaclPresent
0x140010b80  call    cs:__imp_SetSecurityDescriptorDacl
0x140010b86  test    eax, eax
0x140010b88  jnz     short loc_140010B9D
0x140010b8a  call    cs:__imp_GetLastError
0x140010b90  mov     ebx, eax
0x140010b92  mov     r9d, 251h
0x140010b98  jmp     loc_140010C23
0x140010b9d  xor     r8d, r8d; bOwnerDefaulted
0x140010ba0  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010ba4  mov     rdx, r14; pOwner
0x140010ba7  call    cs:__imp_SetSecurityDescriptorOwner
0x140010bad  test    eax, eax
0x140010baf  jnz     short loc_140010BC1
0x140010bb1  call    cs:__imp_GetLastError
0x140010bb7  mov     ebx, eax
0x140010bb9  mov     r9d, 25Bh
0x140010bbf  jmp     short loc_140010C23
0x140010bc1  xor     r8d, r8d; bGroupDefaulted
0x140010bc4  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010bc8  mov     rdx, r14; pGroup
0x140010bcb  call    cs:__imp_SetSecurityDescriptorGroup
0x140010bd1  test    eax, eax
0x140010bd3  jnz     short loc_140010BE5
0x140010bd5  call    cs:__imp_GetLastError
0x140010bdb  mov     ebx, eax
0x140010bdd  mov     r9d, 264h
0x140010be3  jmp     short loc_140010C23
0x140010be5  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010be9  call    cs:__imp_IsValidSecurityDescriptor
0x140010bef  test    eax, eax
0x140010bf1  jnz     short loc_140010C03
0x140010bf3  call    cs:__imp_GetLastError
0x140010bf9  mov     ebx, eax
0x140010bfb  mov     r9d, 26Dh
0x140010c01  jmp     short loc_140010C23
0x140010c03  mov     r8, [rbp+57h+var_78]; unsigned __int16 *
0x140010c07  lea     r9, [rbp+57h+pSecurityDescriptor]; struct _SECURITY_DESCRIPTOR *
0x140010c0b  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD"...
0x140010c12  call    ?SetSDToRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAU_SECURITY_DESCRIPTOR@@@Z; CRAGroupPolicy::SetSDToRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR *)
0x140010c17  mov     ebx, eax
0x140010c19  test    eax, eax
0x140010c1b  jz      short loc_140010C3C
0x140010c1d  mov     r9d, 276h; unsigned int
0x140010c23  lea     rcx, aCragrouppolicy_9; "CRAGroupPolicy::SetDCOMServerPermission"...
0x140010c2a  mov     [rsp+0F0h+nSubAuthority3], r12d; unsigned int
0x140010c2f  mov     r8, rdi; unsigned __int16 *
0x140010c32  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x140010c37  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010c3c  call    cs:__imp_GetProcessHeap
0x140010c42  mov     r8, rsi; lpMem
0x140010c45  xor     edx, edx; dwFlags
0x140010c47  mov     rcx, rax; hHeap
0x140010c4a  call    cs:__imp_HeapFree
0x140010c50  mov     rcx, [rbp+57h+var_88]; pSid
0x140010c54  test    rcx, rcx
0x140010c57  jz      short loc_140010C63
0x140010c59  call    cs:__imp_FreeSid
0x140010c5f  mov     [rbp+57h+var_88], r12
0x140010c63  mov     rcx, [rbp+57h+var_80]; pSid
0x140010c67  test    rcx, rcx
0x140010c6a  jz      short loc_140010C72
0x140010c6c  call    cs:__imp_FreeSid
0x140010c72  mov     eax, ebx
0x140010c74  mov     rcx, [rbp+57h+var_40]
0x140010c78  xor     rcx, rsp; StackCookie
0x140010c7b  call    __security_check_cookie
0x140010c80  mov     rbx, [rsp+0F0h+arg_0]
0x140010c88  add     rsp, 0C0h
0x140010c8f  pop     r15
0x140010c91  pop     r14
0x140010c93  pop     r13
0x140010c95  pop     r12
0x140010c97  pop     rdi
0x140010c98  pop     rsi
0x140010c99  pop     rbp
0x140010c9a  retn
```
