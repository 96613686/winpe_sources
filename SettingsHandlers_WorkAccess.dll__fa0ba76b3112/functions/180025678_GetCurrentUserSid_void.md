# GetCurrentUserSid(void * *)

- ea: `0x180025678`
- end: `0x18002579b`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800257a4`

## callees

- `0x180002a60`
- `0x18001f164`
- `0x1800247d0`
- `0x180025678`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800256fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800256fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800256e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800256e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800256c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800256c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800256aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800256aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002576b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002576b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002573c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002573c`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147023888 )
      goto LABEL_5;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
LABEL_5:
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AllocAndCopySid(TokenInformation[0], a1);
  }
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180025678  mov     [rsp+arg_8], rbx
0x18002567d  push    rdi
0x18002567e  sub     rsp, 0B0h
0x180025685  mov     rax, cs:__security_cookie
0x18002568c  xor     rax, rsp
0x18002568f  mov     [rsp+0B8h+var_18], rax
0x180025697  mov     rdi, rcx
0x18002569a  mov     qword ptr [rcx], 0
0x1800256a1  mov     [rsp+0B8h+TokenHandle], 0
0x1800256aa  call    cs:__imp_GetCurrentThread
0x1800256b1  nop     dword ptr [rax+rax+00h]
0x1800256b6  mov     edx, 8; DesiredAccess
0x1800256bb  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800256c0  mov     rcx, rax; ThreadHandle
0x1800256c3  lea     r8d, [rdx-7]; OpenAsSelf
0x1800256c7  call    cs:__imp_OpenThreadToken
0x1800256ce  nop     dword ptr [rax+rax+00h]
0x1800256d3  test    eax, eax
0x1800256d5  jnz     short loc_180025719
0x1800256d7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800256dc  mov     ebx, eax
0x1800256de  cmp     eax, 800703F0h
0x1800256e3  jnz     short loc_180025715
0x1800256e5  call    cs:__imp_GetCurrentProcess
0x1800256ec  nop     dword ptr [rax+rax+00h]
0x1800256f1  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800256f6  mov     edx, 8; DesiredAccess
0x1800256fb  mov     rcx, rax; ProcessHandle
0x1800256fe  call    cs:__imp_OpenProcessToken
0x180025705  nop     dword ptr [rax+rax+00h]
0x18002570a  test    eax, eax
0x18002570c  jnz     short loc_180025719
0x18002570e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025713  mov     ebx, eax
0x180025715  test    ebx, ebx
0x180025717  js      short loc_180025777
0x180025719  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18002571e  lea     rax, [rsp+0B8h+var_80]
0x180025723  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180025729  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18002572e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180025733  mov     [rsp+0B8h+var_80], r9d
0x180025738  lea     edx, [r9-57h]; TokenInformationClass
0x18002573c  call    cs:__imp_GetTokenInformation
0x180025743  nop     dword ptr [rax+rax+00h]
0x180025748  test    eax, eax
0x18002574a  jnz     short loc_180025757
0x18002574c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025751  mov     ebx, eax
0x180025753  test    eax, eax
0x180025755  js      short loc_180025766
0x180025757  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x18002575c  mov     rdx, rdi; void **
0x18002575f  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x180025764  mov     ebx, eax
0x180025766  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18002576b  call    cs:__imp_CloseHandle
0x180025772  nop     dword ptr [rax+rax+00h]
0x180025777  mov     eax, ebx
0x180025779  mov     rcx, [rsp+0B8h+var_18]
0x180025781  xor     rcx, rsp; StackCookie
0x180025784  call    __security_check_cookie
0x180025789  mov     rbx, [rsp+0B8h+arg_8]
0x180025791  add     rsp, 0B0h
0x180025798  pop     rdi
0x180025799  retn
```
