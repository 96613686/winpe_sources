# GetServiceWaitTimeout

- ea: `0x180044c8c`
- end: `0x180044dab`
- name: `GetServiceWaitTimeout`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e340`

## callees

- `0x180044c8c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180044cd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180044cd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044cc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044cc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d75`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180044d6a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180044d6a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180044d5d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180044d5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180044d10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180044d10`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180044d4a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180044d4a`

## pseudocode

```c
__int64 GetServiceWaitTimeout()
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid1; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[64]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    ReturnLength = 512;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    pSid1 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &ReturnLength)
      && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      v0 = EqualSid(pSid1, TokenInformation[0]);
      FreeSid(pSid1);
    }
    CloseHandle(TokenHandle);
  }
  return v0 ? 900 : 120;
}

```

## disassembly

```asm
0x180044c8c  mov     [rsp-8+arg_0], rbx
0x180044c91  mov     [rsp-8+arg_8], rdi
0x180044c96  push    rbp
0x180044c97  lea     rbp, [rsp-190h]
0x180044c9f  sub     rsp, 290h
0x180044ca6  mov     rax, cs:__security_cookie
0x180044cad  xor     rax, rsp
0x180044cb0  mov     [rbp+190h+var_10], rax
0x180044cb7  xor     edi, edi
0x180044cb9  mov     [rsp+290h+TokenHandle], rdi
0x180044cbe  mov     ebx, edi
0x180044cc0  call    cs:__imp_GetCurrentProcess
0x180044cc6  mov     rcx, rax; ProcessHandle
0x180044cc9  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180044cce  lea     edx, [rdi+8]; DesiredAccess
0x180044cd1  call    cs:__imp_OpenProcessToken
0x180044cd7  test    eax, eax
0x180044cd9  jz      loc_180044D7B
0x180044cdf  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180044ce4  lea     rax, [rsp+290h+var_230]
0x180044ce9  mov     r9d, 200h; TokenInformationLength
0x180044cef  mov     [rsp+290h+ReturnLength], rax; ReturnLength
0x180044cf4  lea     r8, [rbp+190h+TokenInformation]; TokenInformation
0x180044cf8  mov     [rsp+290h+var_230], r9d
0x180044cfd  lea     edx, [rdi+1]; TokenInformationClass
0x180044d00  mov     dword ptr [rsp+290h+pIdentifierAuthority.Value], edi
0x180044d04  mov     word ptr [rsp+290h+pIdentifierAuthority.Value+4], 500h
0x180044d0b  mov     [rsp+290h+pSid1], rdi
0x180044d10  call    cs:__imp_GetTokenInformation
0x180044d16  test    eax, eax
0x180044d18  jz      short loc_180044D70
0x180044d1a  lea     rax, [rsp+290h+pSid1]
0x180044d1f  xor     r9d, r9d; nSubAuthority1
0x180044d22  mov     [rsp+290h+pSid], rax; pSid
0x180044d27  lea     r8d, [rdi+12h]; nSubAuthority0
0x180044d2b  mov     [rsp+290h+nSubAuthority7], edi; nSubAuthority7
0x180044d2f  lea     rcx, [rsp+290h+pIdentifierAuthority]; pIdentifierAuthority
0x180044d34  mov     [rsp+290h+nSubAuthority6], edi; nSubAuthority6
0x180044d38  mov     dl, 1; nSubAuthorityCount
0x180044d3a  mov     [rsp+290h+nSubAuthority5], edi; nSubAuthority5
0x180044d3e  mov     [rsp+290h+nSubAuthority4], edi; nSubAuthority4
0x180044d42  mov     [rsp+290h+nSubAuthority3], edi; nSubAuthority3
0x180044d46  mov     dword ptr [rsp+290h+ReturnLength], edi; nSubAuthority2
0x180044d4a  call    cs:__imp_AllocateAndInitializeSid
0x180044d50  test    eax, eax
0x180044d52  jz      short loc_180044D70
0x180044d54  mov     rdx, [rbp+190h+TokenInformation]; pSid2
0x180044d58  mov     rcx, [rsp+290h+pSid1]; pSid1
0x180044d5d  call    cs:__imp_EqualSid
0x180044d63  mov     rcx, [rsp+290h+pSid1]; pSid
0x180044d68  mov     ebx, eax
0x180044d6a  call    cs:__imp_FreeSid
0x180044d70  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x180044d75  call    cs:__imp_CloseHandle
0x180044d7b  neg     ebx
0x180044d7d  sbb     eax, eax
0x180044d7f  and     eax, 30Ch
0x180044d84  add     eax, 78h ; 'x'
0x180044d87  mov     rcx, [rbp+190h+var_10]
0x180044d8e  xor     rcx, rsp; StackCookie
0x180044d91  call    __security_check_cookie
0x180044d96  lea     r11, [rsp+290h+var_s0]
0x180044d9e  mov     rbx, [r11+10h]
0x180044da2  mov     rdi, [r11+18h]
0x180044da6  mov     rsp, r11
0x180044da9  pop     rbp
0x180044daa  retn
```
