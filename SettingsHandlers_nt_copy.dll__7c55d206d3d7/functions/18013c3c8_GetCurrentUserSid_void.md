# GetCurrentUserSid(void * *)

- ea: `0x18013c3c8`
- end: `0x18013c4eb`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013d3e8`

## callees

- `0x18000c840`
- `0x18004e5f0`
- `0x18013b64c`
- `0x18013c3c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18013c3fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18013c3fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18013c417`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18013c417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18013c435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18013c435`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18013c44e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18013c44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013c4bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013c4bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18013c48c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18013c48c`

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
0x18013c3c8  mov     [rsp+arg_8], rbx
0x18013c3cd  push    rdi
0x18013c3ce  sub     rsp, 0B0h
0x18013c3d5  mov     rax, cs:__security_cookie
0x18013c3dc  xor     rax, rsp
0x18013c3df  mov     [rsp+0B8h+var_18], rax
0x18013c3e7  mov     rdi, rcx
0x18013c3ea  mov     qword ptr [rcx], 0
0x18013c3f1  mov     [rsp+0B8h+TokenHandle], 0
0x18013c3fa  call    cs:__imp_GetCurrentThread
0x18013c401  nop     dword ptr [rax+rax+00h]
0x18013c406  mov     edx, 8; DesiredAccess
0x18013c40b  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18013c410  mov     rcx, rax; ThreadHandle
0x18013c413  lea     r8d, [rdx-7]; OpenAsSelf
0x18013c417  call    cs:__imp_OpenThreadToken
0x18013c41e  nop     dword ptr [rax+rax+00h]
0x18013c423  test    eax, eax
0x18013c425  jnz     short loc_18013C469
0x18013c427  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18013c42c  mov     ebx, eax
0x18013c42e  cmp     eax, 800703F0h
0x18013c433  jnz     short loc_18013C465
0x18013c435  call    cs:__imp_GetCurrentProcess
0x18013c43c  nop     dword ptr [rax+rax+00h]
0x18013c441  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x18013c446  mov     edx, 8; DesiredAccess
0x18013c44b  mov     rcx, rax; ProcessHandle
0x18013c44e  call    cs:__imp_OpenProcessToken
0x18013c455  nop     dword ptr [rax+rax+00h]
0x18013c45a  test    eax, eax
0x18013c45c  jnz     short loc_18013C469
0x18013c45e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18013c463  mov     ebx, eax
0x18013c465  test    ebx, ebx
0x18013c467  js      short loc_18013C4C7
0x18013c469  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18013c46e  lea     rax, [rsp+0B8h+var_80]
0x18013c473  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18013c479  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18013c47e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18013c483  mov     [rsp+0B8h+var_80], r9d
0x18013c488  lea     edx, [r9-57h]; TokenInformationClass
0x18013c48c  call    cs:__imp_GetTokenInformation
0x18013c493  nop     dword ptr [rax+rax+00h]
0x18013c498  test    eax, eax
0x18013c49a  jnz     short loc_18013C4A7
0x18013c49c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18013c4a1  mov     ebx, eax
0x18013c4a3  test    eax, eax
0x18013c4a5  js      short loc_18013C4B6
0x18013c4a7  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x18013c4ac  mov     rdx, rdi; void **
0x18013c4af  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x18013c4b4  mov     ebx, eax
0x18013c4b6  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18013c4bb  call    cs:__imp_CloseHandle
0x18013c4c2  nop     dword ptr [rax+rax+00h]
0x18013c4c7  mov     eax, ebx
0x18013c4c9  mov     rcx, [rsp+0B8h+var_18]
0x18013c4d1  xor     rcx, rsp; StackCookie
0x18013c4d4  call    __security_check_cookie
0x18013c4d9  mov     rbx, [rsp+0B8h+arg_8]
0x18013c4e1  add     rsp, 0B0h
0x18013c4e8  pop     rdi
0x18013c4e9  retn
```
