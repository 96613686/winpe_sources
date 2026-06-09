# GetCurrentUserSid(void * *)

- ea: `0x180039d24`
- end: `0x180039e22`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800140e0`
- `0x180021928`
- `0x180038e34`
- `0x180039c30`
- `0x180047a54`
- `0x180049de8`

## callees

- `0x180039d24`
- `0x18003aa84`
- `0x180050ba0`
- `0x1800aeae4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039d6d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039d6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039d56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039d56`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039d98`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039d98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039df9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039dd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039dd0`

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
0x180039d24  mov     [rsp+arg_8], rbx
0x180039d29  push    rdi
0x180039d2a  sub     rsp, 0B0h
0x180039d31  mov     rax, cs:__security_cookie
0x180039d38  xor     rax, rsp
0x180039d3b  mov     [rsp+0B8h+var_18], rax
0x180039d43  mov     rdi, rcx
0x180039d46  mov     qword ptr [rcx], 0
0x180039d4d  mov     [rsp+0B8h+TokenHandle], 0
0x180039d56  call    cs:__imp_GetCurrentThread
0x180039d5c  mov     edx, 8; DesiredAccess
0x180039d61  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039d66  mov     rcx, rax; ThreadHandle
0x180039d69  lea     r8d, [rdx-7]; OpenAsSelf
0x180039d6d  call    cs:__imp_OpenThreadToken
0x180039d73  test    eax, eax
0x180039d75  jnz     short loc_180039DAD
0x180039d77  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180039d7c  mov     ebx, eax
0x180039d7e  cmp     eax, 800703F0h
0x180039d83  jnz     short loc_180039DA9
0x180039d85  call    cs:__imp_GetCurrentProcess
0x180039d8b  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039d90  mov     edx, 8; DesiredAccess
0x180039d95  mov     rcx, rax; ProcessHandle
0x180039d98  call    cs:__imp_OpenProcessToken
0x180039d9e  test    eax, eax
0x180039da0  jnz     short loc_180039DAD
0x180039da2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180039da7  mov     ebx, eax
0x180039da9  test    ebx, ebx
0x180039dab  js      short loc_180039DFF
0x180039dad  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039db2  lea     rax, [rsp+0B8h+var_80]
0x180039db7  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180039dbd  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180039dc2  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180039dc7  mov     [rsp+0B8h+var_80], r9d
0x180039dcc  lea     edx, [r9-57h]; TokenInformationClass
0x180039dd0  call    cs:__imp_GetTokenInformation
0x180039dd6  test    eax, eax
0x180039dd8  jnz     short loc_180039DE5
0x180039dda  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180039ddf  mov     ebx, eax
0x180039de1  test    eax, eax
0x180039de3  js      short loc_180039DF4
0x180039de5  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x180039dea  mov     rdx, rdi; void **
0x180039ded  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x180039df2  mov     ebx, eax
0x180039df4  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180039df9  call    cs:__imp_CloseHandle
0x180039dff  mov     eax, ebx
0x180039e01  mov     rcx, [rsp+0B8h+var_18]
0x180039e09  xor     rcx, rsp; StackCookie
0x180039e0c  call    __security_check_cookie
0x180039e11  mov     rbx, [rsp+0B8h+arg_8]
0x180039e19  add     rsp, 0B0h
0x180039e20  pop     rdi
0x180039e21  retn
```
