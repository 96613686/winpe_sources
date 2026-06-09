# CPimcManager::UserIsLocalSystem(void)

- ea: `0x18000a954`
- end: `0x18000aa8c`
- name: `?UserIsLocalSystem@CPimcManager@@IEAAHXZ`
- size: `312`
- prototype: `__int64 __fastcall(CPimcManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000a49c`

## callees

- `0x18000a954`
- `0x18000cdb0`
- `0x18000ce0c`
- `0x18000ce14`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18000a98b`
- `ADVAPI32!OpenProcessToken` at `0x18000a98b`
- `ADVAPI32!GetTokenInformation` at `0x18000a9b2`
- `ADVAPI32!GetTokenInformation` at `0x18000a9f3`
- `ADVAPI32!GetTokenInformation` at `0x18000a9b2`
- `ADVAPI32!GetTokenInformation` at `0x18000a9f3`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000aa34`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000aa34`
- `ADVAPI32!EqualSid` at `0x18000aa45`
- `ADVAPI32!EqualSid` at `0x18000aa45`
- `ADVAPI32!FreeSid` at `0x18000aa51`
- `ADVAPI32!FreeSid` at `0x18000aa51`
- `KERNEL32!CloseHandle` at `0x18000aa63`
- `KERNEL32!CloseHandle` at `0x18000aa63`
- `KERNEL32!GetCurrentProcess` at `0x18000a97b`
- `KERNEL32!GetCurrentProcess` at `0x18000a97b`

## pseudocode

```c
__int64 __fastcall CPimcManager::UserIsLocalSystem(CPimcManager *this)
{
  unsigned int v1; // ebx
  HANDLE CurrentProcess; // rax
  PSID *v3; // rdi
  DWORD TokenInformationLength; // [rsp+60h] [rbp+27h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+2Fh] BYREF
  PSID pSid2; // [rsp+70h] [rbp+37h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF

  v1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v3 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v3 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
        {
          *(_DWORD *)pIdentifierAuthority.Value = 0;
          *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
          if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
          {
            v1 = EqualSid(*v3, pSid2);
            FreeSid(pSid2);
          }
        }
        operator delete(v3);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x18000a954  mov     [rsp-8+arg_0], rbx
0x18000a959  mov     [rsp-8+arg_8], rdi
0x18000a95e  push    rbp
0x18000a95f  lea     rbp, [rsp-57h]
0x18000a964  sub     rsp, 90h
0x18000a96b  mov     rax, cs:__security_cookie
0x18000a972  xor     rax, rsp
0x18000a975  mov     [rbp+57h+var_10], rax
0x18000a979  xor     ebx, ebx
0x18000a97b  call    cs:__imp_GetCurrentProcess
0x18000a981  mov     rcx, rax; ProcessHandle
0x18000a984  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000a988  lea     edx, [rbx+8]; DesiredAccess
0x18000a98b  call    cs:__imp_OpenProcessToken
0x18000a991  test    eax, eax
0x18000a993  jz      loc_18000AA69
0x18000a999  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000a99d  lea     rax, [rbp+57h+TokenInformationLength]
0x18000a9a1  xor     r9d, r9d; TokenInformationLength
0x18000a9a4  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18000a9a9  xor     r8d, r8d; TokenInformation
0x18000a9ac  mov     [rbp+57h+TokenInformationLength], ebx
0x18000a9af  lea     edx, [rbx+1]; TokenInformationClass
0x18000a9b2  call    cs:__imp_GetTokenInformation
0x18000a9b8  cmp     [rbp+57h+TokenInformationLength], ebx
0x18000a9bb  jz      loc_18000AA5F
0x18000a9c1  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x18000a9c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a9cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a9d0  mov     rdi, rax
0x18000a9d3  test    rax, rax
0x18000a9d6  jz      loc_18000AA5F
0x18000a9dc  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000a9e0  lea     rax, [rbp+57h+TokenInformationLength]
0x18000a9e4  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000a9e8  lea     edx, [rbx+1]; TokenInformationClass
0x18000a9eb  mov     r8, rdi; TokenInformation
0x18000a9ee  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18000a9f3  call    cs:__imp_GetTokenInformation
0x18000a9f9  test    eax, eax
0x18000a9fb  jz      short loc_18000AA57
0x18000a9fd  lea     rax, [rbp+57h+pSid2]
0x18000aa01  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x18000aa04  mov     [rsp+90h+pSid], rax; pSid
0x18000aa09  lea     r8d, [rbx+12h]; nSubAuthority0
0x18000aa0d  mov     [rsp+90h+nSubAuthority7], ebx; nSubAuthority7
0x18000aa11  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000aa15  mov     [rsp+90h+nSubAuthority6], ebx; nSubAuthority6
0x18000aa19  xor     r9d, r9d; nSubAuthority1
0x18000aa1c  mov     [rsp+90h+nSubAuthority5], ebx; nSubAuthority5
0x18000aa20  mov     dl, 1; nSubAuthorityCount
0x18000aa22  mov     [rsp+90h+nSubAuthority4], ebx; nSubAuthority4
0x18000aa26  mov     [rsp+90h+nSubAuthority3], ebx; nSubAuthority3
0x18000aa2a  mov     dword ptr [rsp+90h+ReturnLength], ebx; nSubAuthority2
0x18000aa2e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000aa34  call    cs:__imp_AllocateAndInitializeSid
0x18000aa3a  test    eax, eax
0x18000aa3c  jz      short loc_18000AA57
0x18000aa3e  mov     rdx, [rbp+57h+pSid2]; pSid2
0x18000aa42  mov     rcx, [rdi]; pSid1
0x18000aa45  call    cs:__imp_EqualSid
0x18000aa4b  mov     rcx, [rbp+57h+pSid2]; pSid
0x18000aa4f  mov     ebx, eax
0x18000aa51  call    cs:__imp_FreeSid
0x18000aa57  mov     rcx, rdi; Block
0x18000aa5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000aa5f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000aa63  call    cs:__imp_CloseHandle
0x18000aa69  mov     eax, ebx
0x18000aa6b  mov     rcx, [rbp+57h+var_10]
0x18000aa6f  xor     rcx, rsp; StackCookie
0x18000aa72  call    __security_check_cookie
0x18000aa77  lea     r11, [rsp+90h+var_s0]
0x18000aa7f  mov     rbx, [r11+10h]
0x18000aa83  mov     rdi, [r11+18h]
0x18000aa87  mov     rsp, r11
0x18000aa8a  pop     rbp
0x18000aa8b  retn
```
