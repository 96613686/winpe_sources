# CreateSecurePrivateNamespace(void *,void *,ushort const *,void * *)

- ea: `0x18000f94c`
- end: `0x18000fbd4`
- name: `?CreateSecurePrivateNamespace@@YAKPEAX0PEBGPEAPEAX@Z`
- size: `648`
- prototype: `unsigned int __fastcall(void *lpBoundaryDescriptor, PSID pSid, LPCWSTR lpAliasPrefix, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fd5c`

## callees

- `0x18000f94c`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000fa50`
- `KERNEL32!HeapAlloc` at `0x18000fa50`
- `KERNEL32!GetProcessHeap` at `0x18000fa42`
- `KERNEL32!GetProcessHeap` at `0x18000fb78`
- `KERNEL32!GetProcessHeap` at `0x18000fa42`
- `KERNEL32!GetProcessHeap` at `0x18000fb78`
- `KERNEL32!HeapFree` at `0x18000fb86`
- `KERNEL32!HeapFree` at `0x18000fb86`
- `KERNEL32!GetLastError` at `0x18000fb5c`
- `KERNEL32!GetLastError` at `0x18000fb5c`
- `KERNEL32!ClosePrivateNamespace` at `0x18000fb9e`
- `KERNEL32!ClosePrivateNamespace` at `0x18000fb9e`
- `KERNEL32!CreatePrivateNamespaceW` at `0x18000fb4a`
- `KERNEL32!CreatePrivateNamespaceW` at `0x18000fb4a`
- `ADVAPI32!FreeSid` at `0x18000fb6d`
- `ADVAPI32!FreeSid` at `0x18000fb6d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f9ea`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f9ea`
- `ADVAPI32!IsValidSid` at `0x18000f9fc`
- `ADVAPI32!IsValidSid` at `0x18000fa17`
- `ADVAPI32!IsValidSid` at `0x18000f9fc`
- `ADVAPI32!IsValidSid` at `0x18000fa17`
- `ADVAPI32!GetLengthSid` at `0x18000fa2a`
- `ADVAPI32!GetLengthSid` at `0x18000fa36`
- `ADVAPI32!GetLengthSid` at `0x18000fa2a`
- `ADVAPI32!GetLengthSid` at `0x18000fa36`
- `ADVAPI32!InitializeAcl` at `0x18000fa74`
- `ADVAPI32!InitializeAcl` at `0x18000fa74`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000fa9c`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000facc`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000fa9c`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000facc`
- `ADVAPI32!IsValidAcl` at `0x18000faad`
- `ADVAPI32!IsValidAcl` at `0x18000fadd`
- `ADVAPI32!IsValidAcl` at `0x18000faad`
- `ADVAPI32!IsValidAcl` at `0x18000fadd`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000faf7`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000faf7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000fb0d`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000fb0d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000fb1e`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000fb1e`

## pseudocode

```c
__int64 __fastcall CreateSecurePrivateNamespace(
        void *lpBoundaryDescriptor,
        PSID pSid,
        LPCWSTR lpAliasPrefix,
        void **a4)
{
  ACL *v7; // rdi
  DWORD LengthSid; // r14d
  DWORD v9; // r14d
  HANDLE ProcessHeap; // rax
  ACL *v11; // rax
  DWORD LastError; // ebx
  HANDLE v13; // rax
  PSID v15; // [rsp+60h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+68h] [rbp-31h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+7h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v18 = 0;
  v15 = 0;
  v7 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  g_hDmrcPrivateNamespace = 0;
  memset(&PrivateNamespaceAttributes, 0, sizeof(PrivateNamespaceAttributes));
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v15) )
    goto LABEL_21;
  if ( !IsValidSid(v15) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !pSid )
    goto LABEL_21;
  if ( !IsValidSid(pSid) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LengthSid = GetLengthSid(v15);
  v9 = GetLengthSid(pSid) + 24 + LengthSid;
  ProcessHeap = GetProcessHeap();
  v11 = (ACL *)HeapAlloc(ProcessHeap, 0, v9);
  v7 = v11;
  if ( !v11 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  if ( !InitializeAcl(v11, v9, 2u) || !AddAccessAllowedAceEx(v7, 2u, 0, 0x10000000u, v15) )
    goto LABEL_21;
  if ( !IsValidAcl(v7) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !AddAccessAllowedAceEx(v7, 2u, 0, 0x10000000u, pSid) )
    goto LABEL_21;
  if ( !IsValidAcl(v7) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v7, 0) )
  {
    goto LABEL_21;
  }
  LastError = 0;
  if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  PrivateNamespaceAttributes.nLength = 24;
  PrivateNamespaceAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  PrivateNamespaceAttributes.bInheritHandle = 0;
  g_hDmrcPrivateNamespace = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, lpBoundaryDescriptor, lpAliasPrefix);
  if ( !g_hDmrcPrivateNamespace )
LABEL_21:
    LastError = GetLastError();
LABEL_22:
  if ( v15 )
    FreeSid(v15);
  if ( v7 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v7);
  }
  if ( LastError && g_hDmrcPrivateNamespace )
  {
    ClosePrivateNamespace(g_hDmrcPrivateNamespace, 0);
    g_hDmrcPrivateNamespace = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000f94c  mov     [rsp-8+arg_18], rbx
0x18000f951  push    rbp
0x18000f952  push    rsi
0x18000f953  push    rdi
0x18000f954  push    r12
0x18000f956  push    r13
0x18000f958  push    r14
0x18000f95a  push    r15
0x18000f95c  lea     rbp, [rsp-27h]
0x18000f961  sub     rsp, 0C0h
0x18000f968  mov     rax, cs:__security_cookie
0x18000f96f  xor     rax, rsp
0x18000f972  mov     [rbp+57h+var_40], rax
0x18000f976  xor     r13d, r13d
0x18000f979  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000f97f  xor     eax, eax
0x18000f981  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18000f985  xorps   xmm0, xmm0
0x18000f988  mov     [rbp+57h+var_50], rax
0x18000f98c  mov     qword ptr [rbp+57h+PrivateNamespaceAttributes.bInheritHandle], rax
0x18000f990  mov     r12, r8
0x18000f993  lea     rax, [rbp+57h+var_90]
0x18000f997  mov     [rbp+57h+var_90], r13
0x18000f99b  mov     [rsp+0F0h+pSid], rax; pSid
0x18000f9a0  lea     r8d, [r13+20h]; nSubAuthority0
0x18000f9a4  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x18000f9a9  mov     rsi, rdx
0x18000f9ac  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x18000f9b1  mov     r15, rcx
0x18000f9b4  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x18000f9b9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000f9bd  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x18000f9c2  mov     r9d, 220h; nSubAuthority1
0x18000f9c8  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x18000f9cd  mov     dl, 2; nSubAuthorityCount
0x18000f9cf  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x18000f9d4  mov     edi, r13d
0x18000f9d7  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18000f9db  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, r13; void * g_hDmrcPrivateNamespace
0x18000f9e2  movups  [rbp+57h+var_60], xmm0
0x18000f9e6  movups  xmmword ptr [rbp+57h+PrivateNamespaceAttributes.nLength], xmm0
0x18000f9ea  call    cs:__imp_AllocateAndInitializeSid
0x18000f9f0  test    eax, eax
0x18000f9f2  jz      loc_18000FB5C
0x18000f9f8  mov     rcx, [rbp+57h+var_90]; pSid
0x18000f9fc  call    cs:__imp_IsValidSid
0x18000fa02  test    eax, eax
0x18000fa04  jnz     short loc_18000FA0B
0x18000fa06  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fa0b  test    rsi, rsi
0x18000fa0e  jz      loc_18000FB5C
0x18000fa14  mov     rcx, rsi; pSid
0x18000fa17  call    cs:__imp_IsValidSid
0x18000fa1d  test    eax, eax
0x18000fa1f  jnz     short loc_18000FA26
0x18000fa21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fa26  mov     rcx, [rbp+57h+var_90]; pSid
0x18000fa2a  call    cs:__imp_GetLengthSid
0x18000fa30  mov     rcx, rsi; pSid
0x18000fa33  mov     r14d, eax
0x18000fa36  call    cs:__imp_GetLengthSid
0x18000fa3c  add     eax, 18h
0x18000fa3f  add     r14d, eax
0x18000fa42  call    cs:__imp_GetProcessHeap
0x18000fa48  mov     r8d, r14d; dwBytes
0x18000fa4b  xor     edx, edx; dwFlags
0x18000fa4d  mov     rcx, rax; hHeap
0x18000fa50  call    cs:__imp_HeapAlloc
0x18000fa56  mov     rdi, rax
0x18000fa59  test    rax, rax
0x18000fa5c  jnz     short loc_18000FA66
0x18000fa5e  lea     ebx, [rax+8]
0x18000fa61  jmp     loc_18000FB64
0x18000fa66  mov     ebx, 2
0x18000fa6b  mov     edx, r14d; nAclLength
0x18000fa6e  mov     r8d, ebx; dwAclRevision
0x18000fa71  mov     rcx, rdi; pAcl
0x18000fa74  call    cs:__imp_InitializeAcl
0x18000fa7a  test    eax, eax
0x18000fa7c  jz      loc_18000FB5C
0x18000fa82  mov     rax, [rbp+57h+var_90]
0x18000fa86  mov     r14d, 10000000h
0x18000fa8c  mov     r9d, r14d; AccessMask
0x18000fa8f  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x18000fa94  xor     r8d, r8d; AceFlags
0x18000fa97  mov     edx, ebx; dwAceRevision
0x18000fa99  mov     rcx, rdi; pAcl
0x18000fa9c  call    cs:__imp_AddAccessAllowedAceEx
0x18000faa2  test    eax, eax
0x18000faa4  jz      loc_18000FB5C
0x18000faaa  mov     rcx, rdi; pAcl
0x18000faad  call    cs:__imp_IsValidAcl
0x18000fab3  test    eax, eax
0x18000fab5  jnz     short loc_18000FABC
0x18000fab7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fabc  mov     r9d, r14d; AccessMask
0x18000fabf  mov     qword ptr [rsp+0F0h+nSubAuthority2], rsi; pSid
0x18000fac4  xor     r8d, r8d; AceFlags
0x18000fac7  mov     edx, ebx; dwAceRevision
0x18000fac9  mov     rcx, rdi; pAcl
0x18000facc  call    cs:__imp_AddAccessAllowedAceEx
0x18000fad2  test    eax, eax
0x18000fad4  jz      loc_18000FB5C
0x18000fada  mov     rcx, rdi; pAcl
0x18000fadd  call    cs:__imp_IsValidAcl
0x18000fae3  test    eax, eax
0x18000fae5  jnz     short loc_18000FAEC
0x18000fae7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000faec  mov     ebx, 1
0x18000faf1  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000faf5  mov     edx, ebx; dwRevision
0x18000faf7  call    cs:__imp_InitializeSecurityDescriptor
0x18000fafd  test    eax, eax
0x18000faff  jz      short loc_18000FB5C
0x18000fb01  xor     r9d, r9d; bDaclDefaulted
0x18000fb04  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000fb08  mov     r8, rdi; pDacl
0x18000fb0b  mov     edx, ebx; bDaclPresent
0x18000fb0d  call    cs:__imp_SetSecurityDescriptorDacl
0x18000fb13  test    eax, eax
0x18000fb15  jz      short loc_18000FB5C
0x18000fb17  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000fb1b  mov     ebx, r13d
0x18000fb1e  call    cs:__imp_IsValidSecurityDescriptor
0x18000fb24  test    eax, eax
0x18000fb26  jnz     short loc_18000FB2D
0x18000fb28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fb2d  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000fb31  mov     [rbp+57h+PrivateNamespaceAttributes.nLength], 18h
0x18000fb38  mov     r8, r12; lpAliasPrefix
0x18000fb3b  mov     [rbp+57h+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x18000fb3f  mov     rdx, r15; lpBoundaryDescriptor
0x18000fb42  mov     [rbp+57h+PrivateNamespaceAttributes.bInheritHandle], r13d
0x18000fb46  lea     rcx, [rbp+57h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x18000fb4a  call    cs:__imp_CreatePrivateNamespaceW
0x18000fb50  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, rax; void * g_hDmrcPrivateNamespace
0x18000fb57  test    rax, rax
0x18000fb5a  jnz     short loc_18000FB64
0x18000fb5c  call    cs:__imp_GetLastError
0x18000fb62  mov     ebx, eax
0x18000fb64  mov     rcx, [rbp+57h+var_90]; pSid
0x18000fb68  test    rcx, rcx
0x18000fb6b  jz      short loc_18000FB73
0x18000fb6d  call    cs:__imp_FreeSid
0x18000fb73  test    rdi, rdi
0x18000fb76  jz      short loc_18000FB8C
0x18000fb78  call    cs:__imp_GetProcessHeap
0x18000fb7e  mov     r8, rdi; lpMem
0x18000fb81  xor     edx, edx; dwFlags
0x18000fb83  mov     rcx, rax; hHeap
0x18000fb86  call    cs:__imp_HeapFree
0x18000fb8c  test    ebx, ebx
0x18000fb8e  jz      short loc_18000FBAB
0x18000fb90  mov     rcx, cs:?g_hDmrcPrivateNamespace@@3PEAXEA; Handle
0x18000fb97  test    rcx, rcx
0x18000fb9a  jz      short loc_18000FBAB
0x18000fb9c  xor     edx, edx; Flags
0x18000fb9e  call    cs:__imp_ClosePrivateNamespace
0x18000fba4  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, r13; void * g_hDmrcPrivateNamespace
0x18000fbab  mov     eax, ebx
0x18000fbad  mov     rcx, [rbp+57h+var_40]
0x18000fbb1  xor     rcx, rsp; StackCookie
0x18000fbb4  call    __security_check_cookie
0x18000fbb9  mov     rbx, [rsp+0F0h+arg_18]
0x18000fbc1  add     rsp, 0C0h
0x18000fbc8  pop     r15
0x18000fbca  pop     r14
0x18000fbcc  pop     r13
0x18000fbce  pop     r12
0x18000fbd0  pop     rdi
0x18000fbd1  pop     rsi
0x18000fbd2  pop     rbp
0x18000fbd3  retn
```
