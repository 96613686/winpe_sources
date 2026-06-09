# GetCurrentUserSid(void * *)

- ea: `0x180089c80`
- end: `0x180089df3`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `371`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180089ec0`

## callees

- `0x180004b80`
- `0x18001b2c0`
- `0x180089c80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089cfd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089ced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089ced`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089cd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089cd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089cba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089dc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089dc3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180089d60`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180089d60`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180089d6d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180089d6d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180089d37`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180089d37`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180089d97`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180089d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089db8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089d81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089d81`

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
0x180089c80  mov     [rsp+arg_8], rbx
0x180089c85  mov     [rsp+arg_10], rbp
0x180089c8a  push    rsi
0x180089c8b  push    rdi
0x180089c8c  push    r14
0x180089c8e  sub     rsp, 0B0h
0x180089c95  mov     rax, cs:__security_cookie
0x180089c9c  xor     rax, rsp
0x180089c9f  mov     [rsp+0C8h+var_28], rax
0x180089ca7  mov     r14, rcx
0x180089caa  mov     qword ptr [rcx], 0
0x180089cb1  mov     [rsp+0C8h+TokenHandle], 0
0x180089cba  call    cs:__imp_GetCurrentThread
0x180089cc0  mov     esi, 1
0x180089cc5  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180089cca  mov     rcx, rax; ThreadHandle
0x180089ccd  mov     r8d, esi; OpenAsSelf
0x180089cd0  lea     edi, [rsi+7]
0x180089cd3  mov     edx, edi; DesiredAccess
0x180089cd5  call    cs:__imp_OpenThreadToken
0x180089cdb  test    eax, eax
0x180089cdd  jnz     short loc_180089D16
0x180089cdf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180089ce4  mov     ebx, eax
0x180089ce6  cmp     eax, 800703F0h
0x180089ceb  jnz     short loc_180089D0E
0x180089ced  call    cs:__imp_GetCurrentProcess
0x180089cf3  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180089cf8  mov     edx, edi; DesiredAccess
0x180089cfa  mov     rcx, rax; ProcessHandle
0x180089cfd  call    cs:__imp_OpenProcessToken
0x180089d03  test    eax, eax
0x180089d05  jnz     short loc_180089D16
0x180089d07  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180089d0c  mov     ebx, eax
0x180089d0e  test    ebx, ebx
0x180089d10  js      loc_180089DC9
0x180089d16  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180089d1b  lea     rax, [rsp+0C8h+var_90]
0x180089d20  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180089d26  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180089d2b  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180089d30  mov     [rsp+0C8h+var_90], r9d
0x180089d35  mov     edx, esi; TokenInformationClass
0x180089d37  call    cs:__imp_GetTokenInformation
0x180089d3d  test    eax, eax
0x180089d3f  jnz     short loc_180089D4C
0x180089d41  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180089d46  mov     ebx, eax
0x180089d48  test    eax, eax
0x180089d4a  js      short loc_180089DBE
0x180089d4c  mov     rsi, [rsp+0C8h+TokenInformation]
0x180089d51  mov     ebx, 80070057h
0x180089d56  mov     rcx, rsi; pSid
0x180089d59  mov     qword ptr [r14], 0
0x180089d60  call    cs:__imp_IsValidSid
0x180089d66  test    eax, eax
0x180089d68  jz      short loc_180089DBE
0x180089d6a  mov     rcx, rsi; pSid
0x180089d6d  call    cs:__imp_GetLengthSid
0x180089d73  mov     edx, eax; uBytes
0x180089d75  mov     ecx, 40h ; '@'; uFlags
0x180089d7a  mov     ebp, eax
0x180089d7c  mov     ebx, 8007000Eh
0x180089d81  call    cs:__imp_LocalAlloc
0x180089d87  mov     rdi, rax
0x180089d8a  test    rax, rax
0x180089d8d  jz      short loc_180089DBE
0x180089d8f  mov     r8, rsi; pSourceSid
0x180089d92  mov     rdx, rax; pDestinationSid
0x180089d95  mov     ecx, ebp; nDestinationSidLength
0x180089d97  call    cs:__imp_CopySid
0x180089d9d  test    eax, eax
0x180089d9f  jz      short loc_180089DA5
0x180089da1  xor     ebx, ebx
0x180089da3  jmp     short loc_180089DB0
0x180089da5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180089daa  mov     ebx, eax
0x180089dac  test    eax, eax
0x180089dae  js      short loc_180089DB5
0x180089db0  mov     [r14], rdi
0x180089db3  jmp     short loc_180089DBE
0x180089db5  mov     rcx, rdi; hMem
0x180089db8  call    cs:__imp_LocalFree
0x180089dbe  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x180089dc3  call    cs:__imp_CloseHandle
0x180089dc9  mov     eax, ebx
0x180089dcb  mov     rcx, [rsp+0C8h+var_28]
0x180089dd3  xor     rcx, rsp; StackCookie
0x180089dd6  call    __security_check_cookie
0x180089ddb  lea     r11, [rsp+0C8h+var_18]
0x180089de3  mov     rbx, [r11+28h]
0x180089de7  mov     rbp, [r11+30h]
0x180089deb  mov     rsp, r11
0x180089dee  pop     r14
0x180089df0  pop     rdi
0x180089df1  pop     rsi
0x180089df2  retn
```
