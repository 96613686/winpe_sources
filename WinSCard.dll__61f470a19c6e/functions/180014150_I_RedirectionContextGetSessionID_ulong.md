# I_RedirectionContextGetSessionID(ulong *)

- ea: `0x180014150`
- end: `0x180014210`
- name: `?I_RedirectionContextGetSessionID@@YAKPEAK@Z`
- size: `192`
- prototype: `unsigned int __fastcall(unsigned int *TokenInformation)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013d34`
- `0x1800176a0`

## callees

- `0x180014150`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800141dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800141dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800141b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800141b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001416e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001416e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014187`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014187`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800141a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800141a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014202`

## pseudocode

```c
__int64 __fastcall I_RedirectionContextGetSessionID(unsigned int *TokenInformation)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_6;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_5;
  }
  LastError = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, TokenInformation, 4u, &ReturnLength) )
LABEL_5:
    LastError = GetLastError();
LABEL_6:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180014150  push    rbx
0x180014152  sub     rsp, 30h
0x180014156  mov     [rsp+38h+arg_0], rsi
0x18001415b  xor     esi, esi
0x18001415d  mov     [rsp+38h+arg_18], rdi
0x180014162  mov     rdi, rcx
0x180014165  mov     [rsp+38h+TokenHandle], rsi
0x18001416a  mov     [rsp+38h+arg_8], esi
0x18001416e  call    cs:__imp_GetCurrentThread
0x180014174  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180014179  mov     edx, 8; DesiredAccess
0x18001417e  mov     rcx, rax; ThreadHandle
0x180014181  mov     r8d, 1; OpenAsSelf
0x180014187  call    cs:__imp_OpenThreadToken
0x18001418d  test    eax, eax
0x18001418f  jnz     short loc_1800141BD
0x180014191  call    cs:__imp_GetLastError
0x180014197  mov     ebx, eax
0x180014199  cmp     eax, 3F0h
0x18001419e  jnz     short loc_1800141EE
0x1800141a0  call    cs:__imp_GetCurrentProcess
0x1800141a6  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800141ab  mov     edx, 8; DesiredAccess
0x1800141b0  mov     rcx, rax; ProcessHandle
0x1800141b3  call    cs:__imp_OpenProcessToken
0x1800141b9  test    eax, eax
0x1800141bb  jz      short loc_1800141E6
0x1800141bd  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800141c2  lea     rax, [rsp+38h+arg_8]
0x1800141c7  mov     r9d, 4; TokenInformationLength
0x1800141cd  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800141d2  mov     r8, rdi; TokenInformation
0x1800141d5  mov     edx, 0Ch; TokenInformationClass
0x1800141da  mov     ebx, esi
0x1800141dc  call    cs:__imp_GetTokenInformation
0x1800141e2  test    eax, eax
0x1800141e4  jnz     short loc_1800141EE
0x1800141e6  call    cs:__imp_GetLastError
0x1800141ec  mov     ebx, eax
0x1800141ee  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800141f3  mov     rdi, [rsp+38h+arg_18]
0x1800141f8  mov     rsi, [rsp+38h+arg_0]
0x1800141fd  test    rcx, rcx
0x180014200  jz      short loc_180014208
0x180014202  call    cs:__imp_CloseHandle
0x180014208  mov     eax, ebx
0x18001420a  add     rsp, 30h
0x18001420e  pop     rbx
0x18001420f  retn
```
