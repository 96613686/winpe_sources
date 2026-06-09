# IIS_CRYPTO_BASE::AmIRunningInTheLocalSystemContext(void)

- ea: `0x1800050f0`
- end: `0x180005226`
- name: `?AmIRunningInTheLocalSystemContext@IIS_CRYPTO_BASE@@KAHXZ`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000522c`

## callees

- `0x180001124`
- `0x180001130`
- `0x1800050f0`
- `0x180008410`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005206`
- `KERNEL32!CloseHandle` at `0x180005206`
- `KERNEL32!GetCurrentProcess` at `0x180005129`
- `KERNEL32!GetCurrentProcess` at `0x180005129`
- `ADVAPI32!EqualSid` at `0x1800051d9`
- `ADVAPI32!EqualSid` at `0x1800051d9`
- `ADVAPI32!FreeSid` at `0x1800051ea`
- `ADVAPI32!FreeSid` at `0x1800051ea`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800051c8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800051c8`
- `ADVAPI32!OpenProcessToken` at `0x18000513b`
- `ADVAPI32!OpenProcessToken` at `0x18000513b`
- `ADVAPI32!GetTokenInformation` at `0x18000515f`
- `ADVAPI32!GetTokenInformation` at `0x180005190`
- `ADVAPI32!GetTokenInformation` at `0x18000515f`
- `ADVAPI32!GetTokenInformation` at `0x180005190`

## pseudocode

```c
__int64 IIS_CRYPTO_BASE::AmIRunningInTheLocalSystemContext(void)
{
  unsigned int v0; // edi
  PSID *v1; // rbx
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+7h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+Fh] BYREF
  PSID pSid2; // [rsp+70h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  TokenInformationLength = 0;
  v0 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v1 = 0;
  TokenHandle = 0;
  pSid2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v1 = (PSID *)operator new(TokenInformationLength);
      if ( v1 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength)
          && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
        {
          v0 = EqualSid(*v1, pSid2);
        }
      }
    }
  }
  if ( pSid2 )
    FreeSid(pSid2);
  if ( v1 )
    operator delete(v1);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800050f0  push    rbp
0x1800050f2  push    rbx
0x1800050f3  push    rsi
0x1800050f4  push    rdi
0x1800050f5  lea     rbp, [rsp-3Fh]
0x1800050fa  sub     rsp, 98h
0x180005101  mov     rax, cs:__security_cookie
0x180005108  xor     rax, rsp
0x18000510b  mov     [rbp+57h+var_30], rax
0x18000510f  xor     esi, esi
0x180005111  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180005117  mov     [rbp+57h+TokenInformationLength], esi
0x18000511a  mov     edi, esi
0x18000511c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000511f  mov     ebx, esi
0x180005121  mov     [rbp+57h+TokenHandle], rsi
0x180005125  mov     [rbp+57h+pSid2], rsi
0x180005129  call    cs:__imp_GetCurrentProcess
0x18000512f  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180005133  mov     edx, 20008h; DesiredAccess
0x180005138  mov     rcx, rax; ProcessHandle
0x18000513b  call    cs:__imp_OpenProcessToken
0x180005141  test    eax, eax
0x180005143  jz      loc_1800051E1
0x180005149  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000514d  lea     rax, [rbp+57h+TokenInformationLength]
0x180005151  xor     r9d, r9d; TokenInformationLength
0x180005154  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180005159  xor     r8d, r8d; TokenInformation
0x18000515c  lea     edx, [rsi+1]; TokenInformationClass
0x18000515f  call    cs:__imp_GetTokenInformation
0x180005165  test    eax, eax
0x180005167  jz      short loc_1800051E1
0x180005169  mov     ecx, [rbp+57h+TokenInformationLength]; Size
0x18000516c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005171  mov     rbx, rax
0x180005174  test    rax, rax
0x180005177  jz      short loc_1800051E1
0x180005179  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000517d  lea     rax, [rbp+57h+TokenInformationLength]
0x180005181  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180005185  lea     edx, [rsi+1]; TokenInformationClass
0x180005188  mov     r8, rbx; TokenInformation
0x18000518b  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180005190  call    cs:__imp_GetTokenInformation
0x180005196  test    eax, eax
0x180005198  jz      short loc_1800051E1
0x18000519a  lea     rax, [rbp+57h+pSid2]
0x18000519e  xor     r9d, r9d; nSubAuthority1
0x1800051a1  mov     [rsp+0B0h+pSid], rax; pSid
0x1800051a6  lea     r8d, [rsi+12h]; nSubAuthority0
0x1800051aa  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x1800051ae  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800051b2  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x1800051b6  mov     dl, 1; nSubAuthorityCount
0x1800051b8  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x1800051bc  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x1800051c0  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x1800051c4  mov     dword ptr [rsp+0B0h+ReturnLength], esi; nSubAuthority2
0x1800051c8  call    cs:__imp_AllocateAndInitializeSid
0x1800051ce  test    eax, eax
0x1800051d0  jz      short loc_1800051E1
0x1800051d2  mov     rdx, [rbp+57h+pSid2]; pSid2
0x1800051d6  mov     rcx, [rbx]; pSid1
0x1800051d9  call    cs:__imp_EqualSid
0x1800051df  mov     edi, eax
0x1800051e1  mov     rcx, [rbp+57h+pSid2]; pSid
0x1800051e5  test    rcx, rcx
0x1800051e8  jz      short loc_1800051F0
0x1800051ea  call    cs:__imp_FreeSid
0x1800051f0  test    rbx, rbx
0x1800051f3  jz      short loc_1800051FD
0x1800051f5  mov     rcx, rbx; Block
0x1800051f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051fd  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180005201  test    rcx, rcx
0x180005204  jz      short loc_18000520C
0x180005206  call    cs:__imp_CloseHandle
0x18000520c  mov     eax, edi
0x18000520e  mov     rcx, [rbp+57h+var_30]
0x180005212  xor     rcx, rsp; StackCookie
0x180005215  call    __security_check_cookie
0x18000521a  add     rsp, 98h
0x180005221  pop     rdi
0x180005222  pop     rsi
0x180005223  pop     rbx
0x180005224  pop     rbp
0x180005225  retn
```
