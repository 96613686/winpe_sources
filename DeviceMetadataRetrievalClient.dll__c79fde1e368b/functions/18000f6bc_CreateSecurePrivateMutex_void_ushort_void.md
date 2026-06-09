# CreateSecurePrivateMutex(void *,ushort *,void * *)

- ea: `0x18000f6bc`
- end: `0x18000f943`
- name: `?CreateSecurePrivateMutex@@YAKPEAXPEAGPEAPEAX@Z`
- size: `647`
- prototype: `__int64 __fastcall(PSID pSid, LPCWSTR lpName, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fd5c`

## callees

- `0x18000f6bc`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000f7c0`
- `KERNEL32!HeapAlloc` at `0x18000f7c0`
- `KERNEL32!GetProcessHeap` at `0x18000f7b2`
- `KERNEL32!GetProcessHeap` at `0x18000f8e8`
- `KERNEL32!GetProcessHeap` at `0x18000f7b2`
- `KERNEL32!GetProcessHeap` at `0x18000f8e8`
- `KERNEL32!HeapFree` at `0x18000f8f6`
- `KERNEL32!HeapFree` at `0x18000f8f6`
- `KERNEL32!GetLastError` at `0x18000f8cc`
- `KERNEL32!GetLastError` at `0x18000f8cc`
- `KERNEL32!CloseHandle` at `0x18000f90c`
- `KERNEL32!CloseHandle` at `0x18000f90c`
- `KERNEL32!CreateMutexW` at `0x18000f8ba`
- `KERNEL32!CreateMutexW` at `0x18000f8ba`
- `ADVAPI32!FreeSid` at `0x18000f8dd`
- `ADVAPI32!FreeSid` at `0x18000f8dd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f75a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f75a`
- `ADVAPI32!IsValidSid` at `0x18000f76c`
- `ADVAPI32!IsValidSid` at `0x18000f787`
- `ADVAPI32!IsValidSid` at `0x18000f76c`
- `ADVAPI32!IsValidSid` at `0x18000f787`
- `ADVAPI32!GetLengthSid` at `0x18000f79a`
- `ADVAPI32!GetLengthSid` at `0x18000f7a6`
- `ADVAPI32!GetLengthSid` at `0x18000f79a`
- `ADVAPI32!GetLengthSid` at `0x18000f7a6`
- `ADVAPI32!InitializeAcl` at `0x18000f7e2`
- `ADVAPI32!InitializeAcl` at `0x18000f7e2`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000f80b`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000f83d`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000f80b`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18000f83d`
- `ADVAPI32!IsValidAcl` at `0x18000f81c`
- `ADVAPI32!IsValidAcl` at `0x18000f84e`
- `ADVAPI32!IsValidAcl` at `0x18000f81c`
- `ADVAPI32!IsValidAcl` at `0x18000f84e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000f868`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000f868`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000f87e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000f87e`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000f88f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000f88f`

## pseudocode

```c
__int64 __fastcall CreateSecurePrivateMutex(PSID pSid, LPCWSTR lpName, void **a3)
{
  ACL *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  DWORD LengthSid; // r14d
  DWORD v11; // r14d
  HANDLE ProcessHeap; // rax
  ACL *v13; // rax
  DWORD LastError; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  HANDLE v21; // rax
  PSID v23; // [rsp+60h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+68h] [rbp-21h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+17h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v26 = 0;
  v23 = 0;
  v5 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  g_hDmrcPrivateMutex = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v23) )
    goto LABEL_21;
  if ( !IsValidSid(v23) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  if ( !pSid )
    goto LABEL_21;
  if ( !IsValidSid(pSid) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  LengthSid = GetLengthSid(v23);
  v11 = GetLengthSid(pSid) + 24 + LengthSid;
  ProcessHeap = GetProcessHeap();
  v13 = (ACL *)HeapAlloc(ProcessHeap, 0, v11);
  v5 = v13;
  if ( !v13 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  if ( !InitializeAcl(v13, v11, 2u) || !AddAccessAllowedAceEx(v5, 2u, 0, 0x10000000u, v23) )
    goto LABEL_21;
  if ( !IsValidAcl(v5) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15);
  if ( !AddAccessAllowedAceEx(v5, 2u, 0, 0x10000000u, pSid) )
    goto LABEL_21;
  if ( !IsValidAcl(v5) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17);
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0) )
  {
    goto LABEL_21;
  }
  LastError = 0;
  if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v20, v19);
  MutexAttributes.nLength = 24;
  MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  MutexAttributes.bInheritHandle = 0;
  g_hDmrcPrivateMutex = CreateMutexW(&MutexAttributes, 0, lpName);
  if ( !g_hDmrcPrivateMutex )
LABEL_21:
    LastError = GetLastError();
LABEL_22:
  if ( v23 )
    FreeSid(v23);
  if ( v5 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v5);
  }
  if ( LastError && g_hDmrcPrivateMutex )
  {
    CloseHandle(g_hDmrcPrivateMutex);
    g_hDmrcPrivateMutex = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000f6bc  mov     [rsp-8+arg_10], rbx
0x18000f6c1  mov     [rsp-8+arg_18], rsi
0x18000f6c6  push    rbp
0x18000f6c7  push    rdi
0x18000f6c8  push    r12
0x18000f6ca  push    r14
0x18000f6cc  push    r15
0x18000f6ce  lea     rbp, [rsp-37h]
0x18000f6d3  sub     rsp, 0C0h
0x18000f6da  mov     rax, cs:__security_cookie
0x18000f6e1  xor     rax, rsp
0x18000f6e4  mov     [rbp+57h+var_30], rax
0x18000f6e8  xor     r12d, r12d
0x18000f6eb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000f6f1  xor     eax, eax
0x18000f6f3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x18000f6f7  xorps   xmm0, xmm0
0x18000f6fa  mov     [rbp+57h+var_40], rax
0x18000f6fe  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], rax
0x18000f702  mov     r15, rdx
0x18000f705  lea     rax, [rbp+57h+var_80]
0x18000f709  mov     [rbp+57h+var_80], r12
0x18000f70d  mov     [rsp+0E0h+pSid], rax; pSid
0x18000f712  lea     r8d, [r12+20h]; nSubAuthority0
0x18000f717  mov     [rsp+0E0h+nSubAuthority7], r12d; nSubAuthority7
0x18000f71c  mov     rsi, rcx
0x18000f71f  mov     [rsp+0E0h+nSubAuthority6], r12d; nSubAuthority6
0x18000f724  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000f728  mov     [rsp+0E0h+nSubAuthority5], r12d; nSubAuthority5
0x18000f72d  mov     r9d, 220h; nSubAuthority1
0x18000f733  mov     [rsp+0E0h+nSubAuthority4], r12d; nSubAuthority4
0x18000f738  mov     dl, 2; nSubAuthorityCount
0x18000f73a  mov     [rsp+0E0h+nSubAuthority3], r12d; nSubAuthority3
0x18000f73f  mov     edi, r12d
0x18000f742  mov     [rsp+0E0h+nSubAuthority2], r12d; nSubAuthority2
0x18000f747  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18000f74b  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, r12; void * g_hDmrcPrivateMutex
0x18000f752  movups  [rbp+57h+var_50], xmm0
0x18000f756  movups  xmmword ptr [rbp+57h+MutexAttributes.nLength], xmm0
0x18000f75a  call    cs:__imp_AllocateAndInitializeSid
0x18000f760  test    eax, eax
0x18000f762  jz      loc_18000F8CC
0x18000f768  mov     rcx, [rbp+57h+var_80]; pSid
0x18000f76c  call    cs:__imp_IsValidSid
0x18000f772  test    eax, eax
0x18000f774  jnz     short loc_18000F77B
0x18000f776  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f77b  test    rsi, rsi
0x18000f77e  jz      loc_18000F8CC
0x18000f784  mov     rcx, rsi; pSid
0x18000f787  call    cs:__imp_IsValidSid
0x18000f78d  test    eax, eax
0x18000f78f  jnz     short loc_18000F796
0x18000f791  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f796  mov     rcx, [rbp+57h+var_80]; pSid
0x18000f79a  call    cs:__imp_GetLengthSid
0x18000f7a0  mov     rcx, rsi; pSid
0x18000f7a3  mov     r14d, eax
0x18000f7a6  call    cs:__imp_GetLengthSid
0x18000f7ac  add     eax, 18h
0x18000f7af  add     r14d, eax
0x18000f7b2  call    cs:__imp_GetProcessHeap
0x18000f7b8  mov     r8d, r14d; dwBytes
0x18000f7bb  xor     edx, edx; dwFlags
0x18000f7bd  mov     rcx, rax; hHeap
0x18000f7c0  call    cs:__imp_HeapAlloc
0x18000f7c6  mov     rdi, rax
0x18000f7c9  test    rax, rax
0x18000f7cc  jnz     short loc_18000F7D6
0x18000f7ce  lea     ebx, [rax+8]
0x18000f7d1  jmp     loc_18000F8D4
0x18000f7d6  mov     r8d, 2; dwAclRevision
0x18000f7dc  mov     edx, r14d; nAclLength
0x18000f7df  mov     rcx, rdi; pAcl
0x18000f7e2  call    cs:__imp_InitializeAcl
0x18000f7e8  test    eax, eax
0x18000f7ea  jz      loc_18000F8CC
0x18000f7f0  mov     rax, [rbp+57h+var_80]
0x18000f7f4  xor     r8d, r8d; AceFlags
0x18000f7f7  mov     ebx, 10000000h
0x18000f7fc  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; pSid
0x18000f801  mov     r9d, ebx; AccessMask
0x18000f804  mov     rcx, rdi; pAcl
0x18000f807  lea     edx, [r8+2]; dwAceRevision
0x18000f80b  call    cs:__imp_AddAccessAllowedAceEx
0x18000f811  test    eax, eax
0x18000f813  jz      loc_18000F8CC
0x18000f819  mov     rcx, rdi; pAcl
0x18000f81c  call    cs:__imp_IsValidAcl
0x18000f822  test    eax, eax
0x18000f824  jnz     short loc_18000F82B
0x18000f826  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f82b  xor     r8d, r8d; AceFlags
0x18000f82e  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; pSid
0x18000f833  mov     r9d, ebx; AccessMask
0x18000f836  mov     rcx, rdi; pAcl
0x18000f839  lea     edx, [r8+2]; dwAceRevision
0x18000f83d  call    cs:__imp_AddAccessAllowedAceEx
0x18000f843  test    eax, eax
0x18000f845  jz      loc_18000F8CC
0x18000f84b  mov     rcx, rdi; pAcl
0x18000f84e  call    cs:__imp_IsValidAcl
0x18000f854  test    eax, eax
0x18000f856  jnz     short loc_18000F85D
0x18000f858  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f85d  mov     ebx, 1
0x18000f862  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000f866  mov     edx, ebx; dwRevision
0x18000f868  call    cs:__imp_InitializeSecurityDescriptor
0x18000f86e  test    eax, eax
0x18000f870  jz      short loc_18000F8CC
0x18000f872  xor     r9d, r9d; bDaclDefaulted
0x18000f875  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000f879  mov     r8, rdi; pDacl
0x18000f87c  mov     edx, ebx; bDaclPresent
0x18000f87e  call    cs:__imp_SetSecurityDescriptorDacl
0x18000f884  test    eax, eax
0x18000f886  jz      short loc_18000F8CC
0x18000f888  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000f88c  mov     ebx, r12d
0x18000f88f  call    cs:__imp_IsValidSecurityDescriptor
0x18000f895  test    eax, eax
0x18000f897  jnz     short loc_18000F89E
0x18000f899  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f89e  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000f8a2  mov     [rbp+57h+MutexAttributes.nLength], 18h
0x18000f8a9  mov     r8, r15; lpName
0x18000f8ac  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x18000f8b0  xor     edx, edx; bInitialOwner
0x18000f8b2  mov     [rbp+57h+MutexAttributes.bInheritHandle], r12d
0x18000f8b6  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x18000f8ba  call    cs:__imp_CreateMutexW
0x18000f8c0  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, rax; void * g_hDmrcPrivateMutex
0x18000f8c7  test    rax, rax
0x18000f8ca  jnz     short loc_18000F8D4
0x18000f8cc  call    cs:__imp_GetLastError
0x18000f8d2  mov     ebx, eax
0x18000f8d4  mov     rcx, [rbp+57h+var_80]; pSid
0x18000f8d8  test    rcx, rcx
0x18000f8db  jz      short loc_18000F8E3
0x18000f8dd  call    cs:__imp_FreeSid
0x18000f8e3  test    rdi, rdi
0x18000f8e6  jz      short loc_18000F8FC
0x18000f8e8  call    cs:__imp_GetProcessHeap
0x18000f8ee  mov     r8, rdi; lpMem
0x18000f8f1  xor     edx, edx; dwFlags
0x18000f8f3  mov     rcx, rax; hHeap
0x18000f8f6  call    cs:__imp_HeapFree
0x18000f8fc  test    ebx, ebx
0x18000f8fe  jz      short loc_18000F919
0x18000f900  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; hObject
0x18000f907  test    rcx, rcx
0x18000f90a  jz      short loc_18000F919
0x18000f90c  call    cs:__imp_CloseHandle
0x18000f912  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, r12; void * g_hDmrcPrivateMutex
0x18000f919  mov     eax, ebx
0x18000f91b  mov     rcx, [rbp+57h+var_30]
0x18000f91f  xor     rcx, rsp; StackCookie
0x18000f922  call    __security_check_cookie
0x18000f927  lea     r11, [rsp+0E0h+var_20]
0x18000f92f  mov     rbx, [r11+40h]
0x18000f933  mov     rsi, [r11+48h]
0x18000f937  mov     rsp, r11
0x18000f93a  pop     r15
0x18000f93c  pop     r14
0x18000f93e  pop     r12
0x18000f940  pop     rdi
0x18000f941  pop     rbp
0x18000f942  retn
```
