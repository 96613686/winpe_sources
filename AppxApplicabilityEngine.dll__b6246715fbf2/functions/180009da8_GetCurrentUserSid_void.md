# GetCurrentUserSid(void * *)

- ea: `0x180009da8`
- end: `0x180009ea6`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009c84`
- `0x18000fb54`

## callees

- `0x180009da8`
- `0x180016c38`
- `0x180016cc8`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009dda`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009df1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009e09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009e09`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009e1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e7d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009e54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009e54`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-88h] BYREF
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
0x180009da8  mov     [rsp+arg_8], rbx
0x180009dad  push    rdi
0x180009dae  sub     rsp, 0B0h
0x180009db5  mov     rax, cs:__security_cookie
0x180009dbc  xor     rax, rsp
0x180009dbf  mov     [rsp+0B8h+var_18], rax
0x180009dc7  mov     rdi, rcx
0x180009dca  mov     qword ptr [rcx], 0
0x180009dd1  mov     [rsp+0B8h+TokenHandle], 0
0x180009dda  call    cs:__imp_GetCurrentThread
0x180009de0  mov     edx, 8; DesiredAccess
0x180009de5  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180009dea  mov     rcx, rax; ThreadHandle
0x180009ded  lea     r8d, [rdx-7]; OpenAsSelf
0x180009df1  call    cs:__imp_OpenThreadToken
0x180009df7  test    eax, eax
0x180009df9  jnz     short loc_180009E31
0x180009dfb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009e00  mov     ebx, eax
0x180009e02  cmp     eax, 800703F0h
0x180009e07  jnz     short loc_180009E2D
0x180009e09  call    cs:__imp_GetCurrentProcess
0x180009e0f  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180009e14  mov     edx, 8; DesiredAccess
0x180009e19  mov     rcx, rax; ProcessHandle
0x180009e1c  call    cs:__imp_OpenProcessToken
0x180009e22  test    eax, eax
0x180009e24  jnz     short loc_180009E31
0x180009e26  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009e2b  mov     ebx, eax
0x180009e2d  test    ebx, ebx
0x180009e2f  js      short loc_180009E83
0x180009e31  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180009e36  lea     rax, [rsp+0B8h+var_80]
0x180009e3b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180009e41  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180009e46  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180009e4b  mov     [rsp+0B8h+var_80], r9d
0x180009e50  lea     edx, [r9-57h]; TokenInformationClass
0x180009e54  call    cs:__imp_GetTokenInformation
0x180009e5a  test    eax, eax
0x180009e5c  jnz     short loc_180009E69
0x180009e5e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009e63  mov     ebx, eax
0x180009e65  test    eax, eax
0x180009e67  js      short loc_180009E78
0x180009e69  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x180009e6e  mov     rdx, rdi; void **
0x180009e71  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x180009e76  mov     ebx, eax
0x180009e78  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180009e7d  call    cs:__imp_CloseHandle
0x180009e83  mov     eax, ebx
0x180009e85  mov     rcx, [rsp+0B8h+var_18]
0x180009e8d  xor     rcx, rsp; StackCookie
0x180009e90  call    __security_check_cookie
0x180009e95  mov     rbx, [rsp+0B8h+arg_8]
0x180009e9d  add     rsp, 0B0h
0x180009ea4  pop     rdi
0x180009ea5  retn
```
