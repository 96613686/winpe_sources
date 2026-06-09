# GetCurrentUserSid(void * *)

- ea: `0x180014eb4`
- end: `0x180015027`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `371`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f0b0`
- `0x180020490`

## callees

- `0x180002380`
- `0x180014eb4`
- `0x180018af8`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180014fb5`
- `KERNELBASE!LocalAlloc` at `0x180014fb5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014f09`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014eee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014eee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014f31`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014f31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ff7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014fec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014fec`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014f94`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014f94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014fa1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014fa1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014fcb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014fcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014f6b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014f6b`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *v5; // rsi
  void *v6; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v8; // rax
  void *v9; // rdi
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_6;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_6;
    Error = ResultFromKnownLastError();
  }
  if ( Error >= 0 )
  {
LABEL_6:
    ReturnLength = 88;
    if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_15;
    }
    v5 = TokenInformation;
    Error = -2147024809;
    v6 = TokenInformation;
    *a1 = 0;
    if ( !IsValidSid(v6) )
      goto LABEL_15;
    LengthSid = GetLengthSid(v5);
    Error = -2147024882;
    v8 = LocalAlloc(0x40u, LengthSid);
    v9 = v8;
    if ( !v8 )
      goto LABEL_15;
    if ( CopySid(LengthSid, v8, v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        LocalFree(v9);
        goto LABEL_15;
      }
    }
    *a1 = v9;
LABEL_15:
    CloseHandle(TokenHandle);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180014eb4  mov     [rsp+arg_8], rbx
0x180014eb9  mov     [rsp+arg_10], rbp
0x180014ebe  push    rsi
0x180014ebf  push    rdi
0x180014ec0  push    r14
0x180014ec2  sub     rsp, 0B0h
0x180014ec9  mov     rax, cs:__security_cookie
0x180014ed0  xor     rax, rsp
0x180014ed3  mov     [rsp+0C8h+var_28], rax
0x180014edb  mov     r14, rcx
0x180014ede  mov     qword ptr [rcx], 0
0x180014ee5  mov     [rsp+0C8h+TokenHandle], 0
0x180014eee  call    cs:__imp_GetCurrentThread
0x180014ef4  mov     esi, 1
0x180014ef9  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180014efe  mov     rcx, rax; ThreadHandle
0x180014f01  mov     r8d, esi; OpenAsSelf
0x180014f04  lea     edi, [rsi+7]
0x180014f07  mov     edx, edi; DesiredAccess
0x180014f09  call    cs:__imp_OpenThreadToken
0x180014f0f  test    eax, eax
0x180014f11  jnz     short loc_180014F4A
0x180014f13  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014f18  mov     ebx, eax
0x180014f1a  cmp     eax, 800703F0h
0x180014f1f  jnz     short loc_180014F42
0x180014f21  call    cs:__imp_GetCurrentProcess
0x180014f27  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180014f2c  mov     edx, edi; DesiredAccess
0x180014f2e  mov     rcx, rax; ProcessHandle
0x180014f31  call    cs:__imp_OpenProcessToken
0x180014f37  test    eax, eax
0x180014f39  jnz     short loc_180014F4A
0x180014f3b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014f40  mov     ebx, eax
0x180014f42  test    ebx, ebx
0x180014f44  js      loc_180014FFD
0x180014f4a  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180014f4f  lea     rax, [rsp+0C8h+var_90]
0x180014f54  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180014f5a  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180014f5f  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180014f64  mov     [rsp+0C8h+var_90], r9d
0x180014f69  mov     edx, esi; TokenInformationClass
0x180014f6b  call    cs:__imp_GetTokenInformation
0x180014f71  test    eax, eax
0x180014f73  jnz     short loc_180014F80
0x180014f75  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014f7a  mov     ebx, eax
0x180014f7c  test    eax, eax
0x180014f7e  js      short loc_180014FF2
0x180014f80  mov     rsi, [rsp+0C8h+TokenInformation]
0x180014f85  mov     ebx, 80070057h
0x180014f8a  mov     rcx, rsi; pSid
0x180014f8d  mov     qword ptr [r14], 0
0x180014f94  call    cs:__imp_IsValidSid
0x180014f9a  test    eax, eax
0x180014f9c  jz      short loc_180014FF2
0x180014f9e  mov     rcx, rsi; pSid
0x180014fa1  call    cs:__imp_GetLengthSid
0x180014fa7  mov     edx, eax; uBytes
0x180014fa9  mov     ecx, 40h ; '@'; uFlags
0x180014fae  mov     ebp, eax
0x180014fb0  mov     ebx, 8007000Eh
0x180014fb5  call    cs:__imp_LocalAlloc
0x180014fbb  mov     rdi, rax
0x180014fbe  test    rax, rax
0x180014fc1  jz      short loc_180014FF2
0x180014fc3  mov     r8, rsi; pSourceSid
0x180014fc6  mov     rdx, rax; pDestinationSid
0x180014fc9  mov     ecx, ebp; nDestinationSidLength
0x180014fcb  call    cs:__imp_CopySid
0x180014fd1  test    eax, eax
0x180014fd3  jz      short loc_180014FD9
0x180014fd5  xor     ebx, ebx
0x180014fd7  jmp     short loc_180014FE4
0x180014fd9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014fde  mov     ebx, eax
0x180014fe0  test    eax, eax
0x180014fe2  js      short loc_180014FE9
0x180014fe4  mov     [r14], rdi
0x180014fe7  jmp     short loc_180014FF2
0x180014fe9  mov     rcx, rdi; hMem
0x180014fec  call    cs:__imp_LocalFree
0x180014ff2  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x180014ff7  call    cs:__imp_CloseHandle
0x180014ffd  mov     eax, ebx
0x180014fff  mov     rcx, [rsp+0C8h+var_28]
0x180015007  xor     rcx, rsp; StackCookie
0x18001500a  call    __security_check_cookie
0x18001500f  lea     r11, [rsp+0C8h+var_18]
0x180015017  mov     rbx, [r11+28h]
0x18001501b  mov     rbp, [r11+30h]
0x18001501f  mov     rsp, r11
0x180015022  pop     r14
0x180015024  pop     rdi
0x180015025  pop     rsi
0x180015026  retn
```
