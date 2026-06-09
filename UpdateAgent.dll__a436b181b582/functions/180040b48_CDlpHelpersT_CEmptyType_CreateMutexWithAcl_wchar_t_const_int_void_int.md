# CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(wchar_t const *,int,void * *,int *)

- ea: `0x180040b48`
- end: `0x180040e78`
- name: `?CreateMutexWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEB_WHPEAPEAXPEAH@Z`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800753f8`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180040b48`
- `0x180077664`
- `0x180221ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180040d7b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180040d7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040e2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040e2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040ca0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040db7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180040d4a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180040d4a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180040c0a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180040c0a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180040e19`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180040e19`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180040d2e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180040d2e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180040cc9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180040cc9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040c6a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040c7b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040c6a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040c7b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180040cef`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180040d0f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180040cef`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180040d0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  struct _ACL *v6; // rbx
  PSID v7; // rsi
  unsigned int v8; // edi
  signed int LastError; // eax
  __int64 v10; // rdx
  PSID v11; // rdi
  DWORD LengthSid; // ebx
  DWORD v13; // edi
  HANDLE ProcessHeap; // rax
  struct _ACL *v15; // rax
  HANDLE v16; // r14
  DWORD v17; // eax
  int v18; // ecx
  signed int v19; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  PSID lpMem[4]; // [rsp+68h] [rbp-59h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+88h] [rbp-39h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp-21h] BYREF
  PSID pSid; // [rsp+A8h] [rbp-19h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v28; // [rsp+D0h] [rbp+Fh]

  lpMem[2] = (PSID)-2LL;
  v6 = 0;
  lpMem[3] = 0;
  pSid = 0;
  v7 = 0;
  lpMem[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v28 = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  lpMem[1] = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
LABEL_24:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8, a2);
    goto LABEL_25;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_20;
  if ( !(unsigned int)GetCurrentUserSID(lpMem) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8, v10);
    v7 = lpMem[0];
    goto LABEL_25;
  }
  v11 = pSid;
  v7 = lpMem[0];
  LengthSid = GetLengthSid(lpMem[0]);
  v13 = LengthSid + GetLengthSid(v11) + 24;
  ProcessHeap = GetProcessHeap();
  v15 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v13);
  v6 = v15;
  if ( !v15 )
  {
    v6 = 0;
    v8 = -2147024882;
    goto LABEL_24;
  }
  if ( !InitializeAcl(v15, v13, 2u)
    || !AddAccessAllowedAce(v6, 2u, 0x10000000u, pSid)
    || !AddAccessAllowedAce(v6, 2u, 0x10000000u, v7)
    || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v6, 0)
    || (*(_QWORD *)&MutexAttributes.nLength = 24,
        *(_QWORD *)&MutexAttributes.bInheritHandle = 0,
        MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor,
        (v16 = CreateMutexW(&MutexAttributes, 0, L"Global\\Microsoft.Windows.Setup.Box")) == 0) )
  {
LABEL_20:
    v19 = GetLastError();
    v8 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    goto LABEL_24;
  }
  v8 = 0;
  v17 = GetLastError();
  v18 = 0;
  *a3 = v16;
  if ( a4 )
  {
    LOBYTE(v18) = v17 == 183;
    *a4 = v18;
  }
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v7 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v7);
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x180040b48  mov     rax, rsp
0x180040b4b  push    rbp
0x180040b4c  push    rsi
0x180040b4d  push    rdi
0x180040b4e  push    r12
0x180040b50  push    r13
0x180040b52  push    r14
0x180040b54  push    r15
0x180040b56  lea     rbp, [rax-5Fh]
0x180040b5a  sub     rsp, 0E0h
0x180040b61  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x180040b69  mov     [rax+8], rbx
0x180040b6d  mov     rax, cs:__security_cookie
0x180040b74  xor     rax, rsp
0x180040b77  mov     [rbp+57h+var_40], rax
0x180040b7b  mov     r15, r9
0x180040b7e  mov     r12, r8
0x180040b81  xor     r13d, r13d
0x180040b84  mov     ebx, r13d
0x180040b87  mov     [rbp+57h+var_98], rbx
0x180040b8b  mov     [rbp+57h+pSid], r13
0x180040b8f  mov     esi, r13d
0x180040b92  mov     [rbp+57h+lpMem], r13
0x180040b96  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180040b9a  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180040ba0  xorps   xmm0, xmm0
0x180040ba3  xor     eax, eax
0x180040ba5  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180040ba9  movups  [rbp+57h+var_58], xmm0
0x180040bad  mov     [rbp+57h+var_48], rax
0x180040bb1  movups  xmmword ptr [rbp+57h+MutexAttributes.nLength], xmm0
0x180040bb5  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], rax
0x180040bb9  mov     [rbp+57h+var_A8], r13
0x180040bbd  test    r8, r8
0x180040bc0  jnz     short loc_180040BCC
0x180040bc2  mov     edi, 80070057h
0x180040bc7  jmp     loc_180040DDB
0x180040bcc  lea     rax, [rbp+57h+pSid]
0x180040bd0  mov     [rsp+50h], rax; pSid
0x180040bd5  mov     [rsp+110h+nSubAuthority7], r13d; nSubAuthority7
0x180040bda  mov     [rsp+110h+nSubAuthority6], r13d; nSubAuthority6
0x180040bdf  mov     [rsp+110h+nSubAuthority5], r13d; nSubAuthority5
0x180040be4  mov     [rsp+110h+nSubAuthority4], r13d; nSubAuthority4
0x180040be9  mov     [rsp+110h+nSubAuthority3], r13d; nSubAuthority3
0x180040bee  mov     [rsp+110h+nSubAuthority2], r13d; nSubAuthority2
0x180040bf3  mov     r9d, 220h; nSubAuthority1
0x180040bf9  mov     r8d, 20h ; ' '; nSubAuthority0
0x180040bff  lea     r14d, [r8-1Eh]
0x180040c03  mov     dl, r14b; nSubAuthorityCount
0x180040c06  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180040c0a  call    cs:__imp_AllocateAndInitializeSid
0x180040c11  nop     dword ptr [rax+rax+00h]
0x180040c16  test    eax, eax
0x180040c18  jz      loc_180040DB7
0x180040c1e  lea     rcx, [rbp+57h+lpMem]
0x180040c22  call    GetCurrentUserSID
0x180040c27  test    eax, eax
0x180040c29  jnz     short loc_180040C5F
0x180040c2b  call    cs:__imp_GetLastError
0x180040c32  nop     dword ptr [rax+rax+00h]
0x180040c37  mov     edi, eax
0x180040c39  test    eax, eax
0x180040c3b  jnz     short loc_180040C44
0x180040c3d  mov     edi, 80004005h
0x180040c42  jmp     short loc_180040C4F
0x180040c44  jle     short loc_180040C4F
0x180040c46  movzx   edi, ax
0x180040c49  or      edi, 80070000h
0x180040c4f  mov     ecx, edi
0x180040c51  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180040c56  mov     rsi, [rbp+57h+lpMem]
0x180040c5a  jmp     loc_180040DE2
0x180040c5f  mov     rdi, [rbp+57h+pSid]
0x180040c63  mov     rsi, [rbp+57h+lpMem]
0x180040c67  mov     rcx, rsi; pSid
0x180040c6a  call    cs:__imp_GetLengthSid
0x180040c71  nop     dword ptr [rax+rax+00h]
0x180040c76  mov     ebx, eax
0x180040c78  mov     rcx, rdi; pSid
0x180040c7b  call    cs:__imp_GetLengthSid
0x180040c82  nop     dword ptr [rax+rax+00h]
0x180040c87  lea     edi, [rax+18h]
0x180040c8a  add     edi, ebx
0x180040c8c  call    cs:__imp_GetProcessHeap
0x180040c93  nop     dword ptr [rax+rax+00h]
0x180040c98  mov     rcx, rax; hHeap
0x180040c9b  mov     r8d, edi; dwBytes
0x180040c9e  xor     edx, edx; dwFlags
0x180040ca0  call    cs:__imp_HeapAlloc
0x180040ca7  nop     dword ptr [rax+rax+00h]
0x180040cac  mov     rbx, rax
0x180040caf  test    rax, rax
0x180040cb2  jnz     short loc_180040CC1
0x180040cb4  mov     rbx, r13
0x180040cb7  mov     edi, 8007000Eh
0x180040cbc  jmp     loc_180040DDB
0x180040cc1  mov     r8d, r14d; dwAclRevision
0x180040cc4  mov     edx, edi; nAclLength
0x180040cc6  mov     rcx, rbx; pAcl
0x180040cc9  call    cs:__imp_InitializeAcl
0x180040cd0  nop     dword ptr [rax+rax+00h]
0x180040cd5  test    eax, eax
0x180040cd7  jz      loc_180040DB7
0x180040cdd  mov     r9, [rbp+57h+pSid]; pSid
0x180040ce1  mov     edi, 10000000h
0x180040ce6  mov     r8d, edi; AccessMask
0x180040ce9  mov     edx, r14d; dwAceRevision
0x180040cec  mov     rcx, rbx; pAcl
0x180040cef  call    cs:__imp_AddAccessAllowedAce
0x180040cf6  nop     dword ptr [rax+rax+00h]
0x180040cfb  test    eax, eax
0x180040cfd  jz      loc_180040DB7
0x180040d03  mov     r9, rsi; pSid
0x180040d06  mov     r8d, edi; AccessMask
0x180040d09  mov     edx, r14d; dwAceRevision
0x180040d0c  mov     rcx, rbx; pAcl
0x180040d0f  call    cs:__imp_AddAccessAllowedAce
0x180040d16  nop     dword ptr [rax+rax+00h]
0x180040d1b  test    eax, eax
0x180040d1d  jz      loc_180040DB7
0x180040d23  mov     edi, 1
0x180040d28  mov     edx, edi; dwRevision
0x180040d2a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180040d2e  call    cs:__imp_InitializeSecurityDescriptor
0x180040d35  nop     dword ptr [rax+rax+00h]
0x180040d3a  test    eax, eax
0x180040d3c  jz      short loc_180040DB7
0x180040d3e  xor     r9d, r9d; bDaclDefaulted
0x180040d41  mov     r8, rbx; pDacl
0x180040d44  mov     edx, edi; bDaclPresent
0x180040d46  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180040d4a  call    cs:__imp_SetSecurityDescriptorDacl
0x180040d51  nop     dword ptr [rax+rax+00h]
0x180040d56  test    eax, eax
0x180040d58  jz      short loc_180040DB7
0x180040d5a  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x180040d62  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], r13
0x180040d66  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180040d6a  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x180040d6e  lea     r8, Name; "Global\\Microsoft.Windows.Setup.Box"
0x180040d75  xor     edx, edx; bInitialOwner
0x180040d77  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x180040d7b  call    cs:__imp_CreateMutexW
0x180040d82  nop     dword ptr [rax+rax+00h]
0x180040d87  mov     r14, rax
0x180040d8a  test    rax, rax
0x180040d8d  jz      short loc_180040DB7
0x180040d8f  mov     edi, r13d
0x180040d92  call    cs:__imp_GetLastError
0x180040d99  nop     dword ptr [rax+rax+00h]
0x180040d9e  mov     ecx, r13d
0x180040da1  cmp     eax, 0B7h
0x180040da6  setz    cl
0x180040da9  mov     [r12], r14
0x180040dad  test    r15, r15
0x180040db0  jz      short loc_180040DE2
0x180040db2  mov     [r15], ecx
0x180040db5  jmp     short loc_180040DE2
0x180040db7  call    cs:__imp_GetLastError
0x180040dbe  nop     dword ptr [rax+rax+00h]
0x180040dc3  mov     edi, eax
0x180040dc5  test    eax, eax
0x180040dc7  jnz     short loc_180040DD0
0x180040dc9  mov     edi, 80004005h
0x180040dce  jmp     short loc_180040DDB
0x180040dd0  jle     short loc_180040DDB
0x180040dd2  movzx   edi, ax
0x180040dd5  or      edi, 80070000h
0x180040ddb  mov     ecx, edi
0x180040ddd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180040de2  mov     ecx, edi
0x180040de4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180040de9  nop
0x180040dea  test    rsi, rsi
0x180040ded  jz      short loc_180040E10
0x180040def  call    cs:__imp_GetProcessHeap
0x180040df6  nop     dword ptr [rax+rax+00h]
0x180040dfb  mov     rcx, rax; hHeap
0x180040dfe  mov     r8, rsi; lpMem
0x180040e01  xor     edx, edx; dwFlags
0x180040e03  call    cs:__imp_HeapFree
0x180040e0a  nop     dword ptr [rax+rax+00h]
0x180040e0f  nop
0x180040e10  mov     rcx, [rbp+57h+pSid]; pSid
0x180040e14  test    rcx, rcx
0x180040e17  jz      short loc_180040E29
0x180040e19  call    cs:__imp_FreeSid
0x180040e20  nop     dword ptr [rax+rax+00h]
0x180040e25  mov     [rbp+57h+pSid], r13
0x180040e29  test    rbx, rbx
0x180040e2c  jz      short loc_180040E4E
0x180040e2e  call    cs:__imp_GetProcessHeap
0x180040e35  nop     dword ptr [rax+rax+00h]
0x180040e3a  mov     rcx, rax; hHeap
0x180040e3d  mov     r8, rbx; lpMem
0x180040e40  xor     edx, edx; dwFlags
0x180040e42  call    cs:__imp_HeapFree
0x180040e49  nop     dword ptr [rax+rax+00h]
0x180040e4e  mov     eax, edi
0x180040e50  mov     rcx, [rbp+57h+var_40]
0x180040e54  xor     rcx, rsp; StackCookie
0x180040e57  call    __security_check_cookie
0x180040e5c  mov     rbx, [rsp+110h+arg_0]
0x180040e64  add     rsp, 0E0h
0x180040e6b  pop     r15
0x180040e6d  pop     r14
0x180040e6f  pop     r13
0x180040e71  pop     r12
0x180040e73  pop     rdi
0x180040e74  pop     rsi
0x180040e75  pop     rbp
0x180040e76  retn
```
