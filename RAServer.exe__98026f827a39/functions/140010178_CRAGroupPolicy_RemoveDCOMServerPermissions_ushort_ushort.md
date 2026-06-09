# CRAGroupPolicy::RemoveDCOMServerPermissions(ushort *,ushort *)

- ea: `0x140010178`
- end: `0x14001058d`
- name: `?RemoveDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0@Z`
- size: `1045`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fcf4`

## callees

- `0x140010178`
- `0x1400111c8`
- `0x140015240`
- `0x140015400`
- `0x140015a62`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400103e4`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400103e4`
- `ADVAPI32!InitializeAcl` at `0x14001036c`
- `ADVAPI32!InitializeAcl` at `0x14001036c`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400104d0`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400104d0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010249`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400102e3`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010465`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010249`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400102e3`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010465`
- `ADVAPI32!GetLengthSid` at `0x14001030b`
- `ADVAPI32!GetLengthSid` at `0x14001030b`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001039d`
- `ADVAPI32!AddAccessAllowedAce` at `0x1400103be`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001039d`
- `ADVAPI32!AddAccessAllowedAce` at `0x1400103be`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14001040f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14001040f`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14001048d`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14001048d`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400104b2`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400104b2`
- `ADVAPI32!FreeSid` at `0x14001053f`
- `ADVAPI32!FreeSid` at `0x140010552`
- `ADVAPI32!FreeSid` at `0x140010565`
- `ADVAPI32!FreeSid` at `0x14001053f`
- `ADVAPI32!FreeSid` at `0x140010552`
- `ADVAPI32!FreeSid` at `0x140010565`
- `KERNEL32!GetLastError` at `0x140010253`
- `KERNEL32!GetLastError` at `0x1400102ed`
- `KERNEL32!GetLastError` at `0x140010379`
- `KERNEL32!GetLastError` at `0x1400103a7`
- `KERNEL32!GetLastError` at `0x1400103c8`
- `KERNEL32!GetLastError` at `0x1400103ee`
- `KERNEL32!GetLastError` at `0x140010419`
- `KERNEL32!GetLastError` at `0x14001046f`
- `KERNEL32!GetLastError` at `0x140010497`
- `KERNEL32!GetLastError` at `0x1400104bc`
- `KERNEL32!GetLastError` at `0x1400104da`
- `KERNEL32!GetLastError` at `0x140010253`
- `KERNEL32!GetLastError` at `0x1400102ed`
- `KERNEL32!GetLastError` at `0x140010379`
- `KERNEL32!GetLastError` at `0x1400103a7`
- `KERNEL32!GetLastError` at `0x1400103c8`
- `KERNEL32!GetLastError` at `0x1400103ee`
- `KERNEL32!GetLastError` at `0x140010419`
- `KERNEL32!GetLastError` at `0x14001046f`
- `KERNEL32!GetLastError` at `0x140010497`
- `KERNEL32!GetLastError` at `0x1400104bc`
- `KERNEL32!GetLastError` at `0x1400104da`
- `KERNEL32!HeapAlloc` at `0x140010323`
- `KERNEL32!HeapAlloc` at `0x140010323`
- `KERNEL32!GetProcessHeap` at `0x140010315`
- `KERNEL32!GetProcessHeap` at `0x140010522`
- `KERNEL32!GetProcessHeap` at `0x140010315`
- `KERNEL32!GetProcessHeap` at `0x140010522`
- `KERNEL32!HeapFree` at `0x140010530`
- `KERNEL32!HeapFree` at `0x140010530`

## string_xrefs

- `0x1400101db`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14001025f`: `CRAGroupPolicy::RemoveDCOMServerPermissions`
- `0x140010331`: `CRAGroupPolicy::RemoveDCOMServerPermissions`
- `0x140010509`: `CRAGroupPolicy::RemoveDCOMServerPermissions`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RemoveDCOMServerPermissions(
        CRAGroupPolicy *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CEventLogger *v4; // rcx
  CEventLogger *v5; // rcx
  DWORD LastError; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  unsigned int v8; // r9d
  DWORD v9; // ebx
  PSID v10; // rcx
  int v11; // r15d
  DWORD v12; // r14d
  CEventLogger *v13; // rcx
  DWORD v14; // r12d
  HANDLE ProcessHeap; // rax
  ACL *v16; // rax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  ACL *v18; // rsi
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  unsigned int v20; // r9d
  CRAGroupPolicy *v21; // rcx
  HANDLE v22; // rax
  PSID pSid; // [rsp+60h] [rbp-39h] BYREF
  PSID v25; // [rsp+68h] [rbp-31h] BYREF
  PSID pOwner; // [rsp+70h] [rbp-29h] BYREF
  struct _SECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp-21h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+7h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v25 = 0;
  pSid = 0;
  memset(&pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  pOwner = 0;
  if ( !wcscmp_0(a3, L"LaunchPermission") )
  {
    CEventLogger::LogEvent(v4, &Enter_Conditional_Block, 0x48Du, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    CEventLogger::LogEvent(v5, &Exit_Conditional_Block, 0x48Fu, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      LastError = GetLastError();
      v8 = 1199;
LABEL_4:
      v9 = LastError;
      CEventLogger::LogError(
        (CEventLogger *)L"CRAGroupPolicy::RemoveDCOMServerPermissions",
        v7,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        v8,
        L"CRAGroupPolicy::RemoveDCOMServerPermissions",
        0);
      goto LABEL_34;
    }
    v10 = pSid;
    v11 = 1;
    v12 = 11;
  }
  else
  {
    CEventLogger::LogEvent(v4, &Enter_Conditional_Block, 0x492u, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    CEventLogger::LogEvent(v13, &Exit_Conditional_Block, 0x495u, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &v25) )
    {
      LastError = GetLastError();
      v8 = 1226;
      goto LABEL_4;
    }
    v10 = v25;
    v11 = 0;
    v12 = 3;
  }
  v14 = GetLengthSid(v10) + 16;
  ProcessHeap = GetProcessHeap();
  v16 = (ACL *)HeapAlloc(ProcessHeap, 0, v14);
  v18 = v16;
  if ( !v16 )
  {
    v9 = 8;
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::RemoveDCOMServerPermissions",
      v17,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x4E1u,
      L"CRAGroupPolicy::RemoveDCOMServerPermissions",
      0x8007000E);
    goto LABEL_34;
  }
  if ( !InitializeAcl(v16, v14, 2u) )
  {
    v9 = GetLastError();
    v20 = 1265;
LABEL_32:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::RemoveDCOMServerPermissions",
      v19,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v20,
      L"CRAGroupPolicy::RemoveDCOMServerPermissions",
      0);
    goto LABEL_33;
  }
  if ( v11 )
  {
    if ( !AddAccessAllowedAce(v18, 2u, v12, pSid) )
    {
      v9 = GetLastError();
      v20 = 1284;
      goto LABEL_32;
    }
  }
  else if ( !AddAccessAllowedAce(v18, 2u, v12, v25) )
  {
    v9 = GetLastError();
    v20 = 1302;
    goto LABEL_32;
  }
  if ( !InitializeSecurityDescriptor(&pSecurityDescriptor, 1u) )
  {
    v9 = GetLastError();
    v20 = 1316;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorDacl(&pSecurityDescriptor, 1, v18, 0) )
  {
    v9 = GetLastError();
    v20 = 1331;
    goto LABEL_32;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner) )
  {
    v9 = GetLastError();
    v20 = 1352;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorOwner(&pSecurityDescriptor, pOwner, 0) )
  {
    v9 = GetLastError();
    v20 = 1362;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorGroup(&pSecurityDescriptor, pOwner, 0) )
  {
    v9 = GetLastError();
    v20 = 1371;
    goto LABEL_32;
  }
  if ( !IsValidSecurityDescriptor(&pSecurityDescriptor) )
  {
    v9 = GetLastError();
    v20 = 1380;
    goto LABEL_32;
  }
  v9 = CRAGroupPolicy::SetSDToRegistry(
         v21,
         L"SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}",
         a3,
         &pSecurityDescriptor);
  if ( v9 )
  {
    v20 = 1389;
    goto LABEL_32;
  }
LABEL_33:
  v22 = GetProcessHeap();
  HeapFree(v22, 0, v18);
LABEL_34:
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v25 )
  {
    FreeSid(v25);
    v25 = 0;
  }
  if ( pOwner )
    FreeSid(pOwner);
  return v9;
}

```

## disassembly

```asm
0x140010178  push    rbp
0x14001017a  push    rbx
0x14001017b  push    rsi
0x14001017c  push    rdi
0x14001017d  push    r12
0x14001017f  push    r13
0x140010181  push    r14
0x140010183  push    r15
0x140010185  lea     rbp, [rsp-1Fh]
0x14001018a  sub     rsp, 0B8h
0x140010191  mov     rax, cs:__security_cookie
0x140010198  xor     rax, rsp
0x14001019b  mov     [rbp+57h+var_48], rax
0x14001019f  xor     r12d, r12d
0x1400101a2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400101a8  xorps   xmm0, xmm0
0x1400101ab  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1400101af  xor     eax, eax
0x1400101b1  mov     [rbp+57h+var_88], r12
0x1400101b5  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x1400101bc  mov     [rbp+57h+var_58], rax
0x1400101c0  mov     rcx, r8; String1
0x1400101c3  mov     [rbp+57h+var_90], r12
0x1400101c7  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1400101cb  mov     [rbp+57h+pOwner], r12
0x1400101cf  mov     r13, r8
0x1400101d2  movups  [rbp+57h+var_68], xmm0
0x1400101d6  call    wcscmp_0
0x1400101db  lea     rdi, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x1400101e2  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x1400101e9  mov     r9, rdi; unsigned __int16 *
0x1400101ec  test    eax, eax
0x1400101ee  jnz     loc_14001028F
0x1400101f4  mov     r8d, 48Dh; unsigned int
0x1400101fa  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x1400101ff  mov     r9, rdi; unsigned __int16 *
0x140010202  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x140010209  mov     r8d, 48Fh; unsigned int
0x14001020f  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x140010214  lea     rax, [rbp+57h+var_90]
0x140010218  xor     r9d, r9d; nSubAuthority1
0x14001021b  mov     [rsp+0F0h+pSid], rax; pSid
0x140010220  lea     r8d, [r12+4]; nSubAuthority0
0x140010225  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x14001022a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001022e  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x140010233  mov     dl, 1; nSubAuthorityCount
0x140010235  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x14001023a  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x14001023f  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x140010244  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x140010249  call    cs:__imp_AllocateAndInitializeSid
0x14001024f  test    eax, eax
0x140010251  jnz     short loc_14001027F
0x140010253  call    cs:__imp_GetLastError
0x140010259  mov     r9d, 4AFh; unsigned int
0x14001025f  lea     rcx, aCragrouppolicy_3; "CRAGroupPolicy::RemoveDCOMServerPermiss"...
0x140010266  mov     [rsp+0F0h+nSubAuthority3], r12d; unsigned int
0x14001026b  mov     r8, rdi; unsigned __int16 *
0x14001026e  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x140010273  mov     ebx, eax
0x140010275  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001027a  jmp     loc_140010536
0x14001027f  mov     rcx, [rbp+57h+var_90]
0x140010283  mov     r15d, 1
0x140010289  lea     r14d, [r15+0Ah]
0x14001028d  jmp     short loc_14001030B
0x14001028f  mov     r8d, 492h; unsigned int
0x140010295  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14001029a  mov     r9, rdi; unsigned __int16 *
0x14001029d  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x1400102a4  mov     r8d, 495h; unsigned int
0x1400102aa  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x1400102af  lea     rax, [rbp+57h+var_88]
0x1400102b3  xor     r9d, r9d; nSubAuthority1
0x1400102b6  mov     [rsp+0F0h+pSid], rax; pSid
0x1400102bb  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400102bf  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x1400102c4  mov     dl, 1; nSubAuthorityCount
0x1400102c6  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x1400102cb  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x1400102d0  lea     r8d, [r9+0Ah]; nSubAuthority0
0x1400102d4  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x1400102d9  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x1400102de  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x1400102e3  call    cs:__imp_AllocateAndInitializeSid
0x1400102e9  test    eax, eax
0x1400102eb  jnz     short loc_1400102FE
0x1400102ed  call    cs:__imp_GetLastError
0x1400102f3  mov     r9d, 4CAh
0x1400102f9  jmp     loc_14001025F
0x1400102fe  mov     rcx, [rbp+57h+var_88]; pSid
0x140010302  mov     r15d, r12d
0x140010305  mov     r14d, 3
0x14001030b  call    cs:__imp_GetLengthSid
0x140010311  lea     r12d, [rax+10h]
0x140010315  call    cs:__imp_GetProcessHeap
0x14001031b  mov     r8d, r12d; dwBytes
0x14001031e  xor     edx, edx; dwFlags
0x140010320  mov     rcx, rax; hHeap
0x140010323  call    cs:__imp_HeapAlloc
0x140010329  mov     rsi, rax
0x14001032c  test    rax, rax
0x14001032f  jnz     short loc_14001035E
0x140010331  lea     rcx, aCragrouppolicy_3; "CRAGroupPolicy::RemoveDCOMServerPermiss"...
0x140010338  mov     [rsp+0F0h+nSubAuthority3], 8007000Eh; unsigned int
0x140010340  mov     r9d, 4E1h; unsigned int
0x140010346  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x14001034b  mov     r8, rdi; unsigned __int16 *
0x14001034e  lea     ebx, [rax+8]
0x140010351  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010356  xor     r12d, r12d
0x140010359  jmp     loc_140010536
0x14001035e  mov     ebx, 2
0x140010363  mov     edx, r12d; nAclLength
0x140010366  mov     r8d, ebx; dwAclRevision
0x140010369  mov     rcx, rsi; pAcl
0x14001036c  call    cs:__imp_InitializeAcl
0x140010372  xor     r12d, r12d
0x140010375  test    eax, eax
0x140010377  jnz     short loc_14001038C
0x140010379  call    cs:__imp_GetLastError
0x14001037f  mov     ebx, eax
0x140010381  mov     r9d, 4F1h
0x140010387  jmp     loc_140010509
0x14001038c  mov     r8d, r14d; AccessMask
0x14001038f  mov     edx, ebx; dwAceRevision
0x140010391  mov     rcx, rsi; pAcl
0x140010394  test    r15d, r15d
0x140010397  jz      short loc_1400103BA
0x140010399  mov     r9, [rbp+57h+var_90]; pSid
0x14001039d  call    cs:__imp_AddAccessAllowedAce
0x1400103a3  test    eax, eax
0x1400103a5  jnz     short loc_1400103DB
0x1400103a7  call    cs:__imp_GetLastError
0x1400103ad  mov     ebx, eax
0x1400103af  mov     r9d, 504h
0x1400103b5  jmp     loc_140010509
0x1400103ba  mov     r9, [rbp+57h+var_88]; pSid
0x1400103be  call    cs:__imp_AddAccessAllowedAce
0x1400103c4  test    eax, eax
0x1400103c6  jnz     short loc_1400103DB
0x1400103c8  call    cs:__imp_GetLastError
0x1400103ce  mov     ebx, eax
0x1400103d0  mov     r9d, 516h
0x1400103d6  jmp     loc_140010509
0x1400103db  mov     edx, 1; dwRevision
0x1400103e0  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400103e4  call    cs:__imp_InitializeSecurityDescriptor
0x1400103ea  test    eax, eax
0x1400103ec  jnz     short loc_140010401
0x1400103ee  call    cs:__imp_GetLastError
0x1400103f4  mov     ebx, eax
0x1400103f6  mov     r9d, 524h
0x1400103fc  jmp     loc_140010509
0x140010401  xor     r9d, r9d; bDaclDefaulted
0x140010404  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140010408  mov     r8, rsi; pDacl
0x14001040b  lea     edx, [r9+1]; bDaclPresent
0x14001040f  call    cs:__imp_SetSecurityDescriptorDacl
0x140010415  test    eax, eax
0x140010417  jnz     short loc_14001042C
0x140010419  call    cs:__imp_GetLastError
0x14001041f  mov     ebx, eax
0x140010421  mov     r9d, 533h
0x140010427  jmp     loc_140010509
0x14001042c  lea     rax, [rbp+57h+pOwner]
0x140010430  mov     r9d, 220h; nSubAuthority1
0x140010436  mov     [rsp+0F0h+pSid], rax; pSid
0x14001043b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001043f  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x140010444  mov     r8d, 20h ; ' '; nSubAuthority0
0x14001044a  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x14001044f  mov     dl, bl; nSubAuthorityCount
0x140010451  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x140010456  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x14001045b  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x140010460  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x140010465  call    cs:__imp_AllocateAndInitializeSid
0x14001046b  test    eax, eax
0x14001046d  jnz     short loc_140010482
0x14001046f  call    cs:__imp_GetLastError
0x140010475  mov     ebx, eax
0x140010477  mov     r9d, 548h
0x14001047d  jmp     loc_140010509
0x140010482  mov     rdx, [rbp+57h+pOwner]; pOwner
0x140010486  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14001048a  xor     r8d, r8d; bOwnerDefaulted
0x14001048d  call    cs:__imp_SetSecurityDescriptorOwner
0x140010493  test    eax, eax
0x140010495  jnz     short loc_1400104A7
0x140010497  call    cs:__imp_GetLastError
0x14001049d  mov     ebx, eax
0x14001049f  mov     r9d, 552h
0x1400104a5  jmp     short loc_140010509
0x1400104a7  mov     rdx, [rbp+57h+pOwner]; pGroup
0x1400104ab  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400104af  xor     r8d, r8d; bGroupDefaulted
0x1400104b2  call    cs:__imp_SetSecurityDescriptorGroup
0x1400104b8  test    eax, eax
0x1400104ba  jnz     short loc_1400104CC
0x1400104bc  call    cs:__imp_GetLastError
0x1400104c2  mov     ebx, eax
0x1400104c4  mov     r9d, 55Bh
0x1400104ca  jmp     short loc_140010509
0x1400104cc  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400104d0  call    cs:__imp_IsValidSecurityDescriptor
0x1400104d6  test    eax, eax
0x1400104d8  jnz     short loc_1400104EA
0x1400104da  call    cs:__imp_GetLastError
0x1400104e0  mov     ebx, eax
0x1400104e2  mov     r9d, 564h
0x1400104e8  jmp     short loc_140010509
0x1400104ea  lea     r9, [rbp+57h+pSecurityDescriptor]; struct _SECURITY_DESCRIPTOR *
0x1400104ee  mov     r8, r13; unsigned __int16 *
0x1400104f1  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD"...
0x1400104f8  call    ?SetSDToRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAU_SECURITY_DESCRIPTOR@@@Z; CRAGroupPolicy::SetSDToRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR *)
0x1400104fd  mov     ebx, eax
0x1400104ff  test    eax, eax
0x140010501  jz      short loc_140010522
0x140010503  mov     r9d, 56Dh; unsigned int
0x140010509  lea     rcx, aCragrouppolicy_3; "CRAGroupPolicy::RemoveDCOMServerPermiss"...
0x140010510  mov     [rsp+0F0h+nSubAuthority3], r12d; unsigned int
0x140010515  mov     r8, rdi; unsigned __int16 *
0x140010518  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; unsigned __int16 *
0x14001051d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010522  call    cs:__imp_GetProcessHeap
0x140010528  mov     r8, rsi; lpMem
0x14001052b  xor     edx, edx; dwFlags
0x14001052d  mov     rcx, rax; hHeap
0x140010530  call    cs:__imp_HeapFree
0x140010536  mov     rcx, [rbp+57h+var_90]; pSid
0x14001053a  test    rcx, rcx
0x14001053d  jz      short loc_140010549
0x14001053f  call    cs:__imp_FreeSid
0x140010545  mov     [rbp+57h+var_90], r12
0x140010549  mov     rcx, [rbp+57h+var_88]; pSid
0x14001054d  test    rcx, rcx
0x140010550  jz      short loc_14001055C
0x140010552  call    cs:__imp_FreeSid
0x140010558  mov     [rbp+57h+var_88], r12
0x14001055c  mov     rcx, [rbp+57h+pOwner]; pSid
0x140010560  test    rcx, rcx
0x140010563  jz      short loc_14001056B
0x140010565  call    cs:__imp_FreeSid
0x14001056b  mov     eax, ebx
0x14001056d  mov     rcx, [rbp+57h+var_48]
0x140010571  xor     rcx, rsp; StackCookie
0x140010574  call    __security_check_cookie
0x140010579  add     rsp, 0B8h
0x140010580  pop     r15
0x140010582  pop     r14
0x140010584  pop     r13
0x140010586  pop     r12
0x140010588  pop     rdi
0x140010589  pop     rsi
0x14001058a  pop     rbx
0x14001058b  pop     rbp
0x14001058c  retn
```
