# GetUserTokenFromSid(ushort const *,ulong,void * *)

- ea: `0x140016ecc`
- end: `0x140016fe8`
- name: `?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(wchar_t *String2, ULONG SessionId, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000a5e0`
- `0x140017610`

## callees

- `0x14000740c`
- `0x140016ecc`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140016f73`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140016f73`
- `ADVAPI32!GetTokenInformation` at `0x140016f56`
- `ADVAPI32!GetTokenInformation` at `0x140016f56`
- `KERNEL32!GetLastError` at `0x140016f9b`
- `KERNEL32!GetLastError` at `0x140016f9b`
- `msvcrt!_wcsicmp` at `0x140016f87`
- `msvcrt!_wcsicmp` at `0x140016f87`
- `WTSAPI32!WTSQueryUserToken` at `0x140016f30`
- `WTSAPI32!WTSQueryUserToken` at `0x140016f30`

## string_xrefs

- `0x140016fb7`: `Failed to get Token for user - %1 from session %2!d!. Error 0x%3!x!`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSid(wchar_t *String2, ULONG SessionId, void **a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  void *phToken; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[128]; // [rsp+50h] [rbp-B0h] BYREF

  phToken = 0;
  ReturnLength = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  *a3 = 0;
  if ( WTSQueryUserToken(SessionId, &phToken)
    && GetTokenInformation(phToken, TokenUser, TokenInformation, 0x400u, &ReturnLength)
    && (StringSid = 0, ConvertSidToStringSidW(TokenInformation[0], &StringSid)) )
  {
    v6 = 0;
    if ( !_wcsicmp(StringSid, String2) )
      *a3 = phToken;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 )
      LogError(L"Failed to get Token for user - %1 from session %2!d!. Error 0x%3!x!", String2, SessionId, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140016ecc  push    rbp
0x140016ece  push    rbx
0x140016ecf  push    rsi
0x140016ed0  push    rdi
0x140016ed1  push    r14
0x140016ed3  lea     rbp, [rsp-360h]
0x140016edb  sub     rsp, 460h
0x140016ee2  mov     rax, cs:__security_cookie
0x140016ee9  xor     rax, rsp
0x140016eec  mov     [rbp+380h+var_30], rax
0x140016ef3  mov     rdi, r8
0x140016ef6  mov     [rsp+480h+phToken], 0
0x140016eff  mov     r14d, edx
0x140016f02  mov     [rsp+480h+var_450], 0
0x140016f0a  mov     rsi, rcx
0x140016f0d  mov     ebx, 400h
0x140016f12  mov     r8d, ebx; Size
0x140016f15  lea     rcx, [rsp+480h+TokenInformation]; void *
0x140016f1a  xor     edx, edx; Val
0x140016f1c  call    memset_0
0x140016f21  lea     rdx, [rsp+480h+phToken]; phToken
0x140016f26  mov     qword ptr [rdi], 0
0x140016f2d  mov     ecx, r14d; SessionId
0x140016f30  call    cs:__imp_WTSQueryUserToken
0x140016f36  test    eax, eax
0x140016f38  jz      short loc_140016F9B
0x140016f3a  mov     rcx, [rsp+480h+phToken]; TokenHandle
0x140016f3f  lea     rax, [rsp+480h+var_450]
0x140016f44  mov     r9d, ebx; TokenInformationLength
0x140016f47  mov     [rsp+480h+ReturnLength], rax; ReturnLength
0x140016f4c  lea     r8, [rsp+480h+TokenInformation]; TokenInformation
0x140016f51  mov     edx, 1; TokenInformationClass
0x140016f56  call    cs:__imp_GetTokenInformation
0x140016f5c  test    eax, eax
0x140016f5e  jz      short loc_140016F9B
0x140016f60  mov     rcx, [rsp+480h+TokenInformation]; Sid
0x140016f65  lea     rdx, [rsp+480h+StringSid]; StringSid
0x140016f6a  mov     [rsp+480h+StringSid], 0
0x140016f73  call    cs:__imp_ConvertSidToStringSidW
0x140016f79  test    eax, eax
0x140016f7b  jz      short loc_140016F9B
0x140016f7d  mov     rcx, [rsp+480h+StringSid]; String1
0x140016f82  mov     rdx, rsi; String2
0x140016f85  xor     ebx, ebx
0x140016f87  call    cs:__imp__wcsicmp
0x140016f8d  test    eax, eax
0x140016f8f  jnz     short loc_140016FC9
0x140016f91  mov     rax, [rsp+480h+phToken]
0x140016f96  mov     [rdi], rax
0x140016f99  jmp     short loc_140016FC9
0x140016f9b  call    cs:__imp_GetLastError
0x140016fa1  mov     ebx, eax
0x140016fa3  test    eax, eax
0x140016fa5  jle     short loc_140016FB0
0x140016fa7  movzx   ebx, ax
0x140016faa  or      ebx, 80070000h
0x140016fb0  test    ebx, ebx
0x140016fb2  jz      short loc_140016FC9
0x140016fb4  mov     r9d, ebx
0x140016fb7  lea     rcx, aFailedToGetTok; "Failed to get Token for user - %1 from "...
0x140016fbe  mov     r8d, r14d
0x140016fc1  mov     rdx, rsi
0x140016fc4  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016fc9  mov     eax, ebx
0x140016fcb  mov     rcx, [rbp+380h+var_30]
0x140016fd2  xor     rcx, rsp; StackCookie
0x140016fd5  call    __security_check_cookie
0x140016fda  add     rsp, 460h
0x140016fe1  pop     r14
0x140016fe3  pop     rdi
0x140016fe4  pop     rsi
0x140016fe5  pop     rbx
0x140016fe6  pop     rbp
0x140016fe7  retn
```
