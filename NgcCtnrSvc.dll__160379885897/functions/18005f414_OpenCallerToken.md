# _OpenCallerToken

- ea: `0x18005f414`
- end: `0x18005f53a`
- name: `_OpenCallerToken`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f2fc`

## callees

- `0x18005f414`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f49d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f49d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005f447`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005f447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f474`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f48d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f48d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f42a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f42a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f520`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f4db`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f4db`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *v6; // rax
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  void *phNewToken; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v6 = TokenHandle;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_9;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)
      || (phNewToken = 0,
          !DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, &phNewToken)) )
    {
      LastError = GetLastError();
      goto LABEL_9;
    }
    CloseHandle(TokenHandle);
    v6 = phNewToken;
  }
  *a2 = v6;
  LastError = 0;
  TokenHandle = 0;
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18005f414  mov     [rsp+arg_0], rbx
0x18005f419  push    rdi
0x18005f41a  sub     rsp, 30h
0x18005f41e  mov     rdi, rdx
0x18005f421  mov     [rsp+38h+TokenHandle], 0
0x18005f42a  call    cs:__imp_GetCurrentThread
0x18005f431  nop     dword ptr [rax+rax+00h]
0x18005f436  mov     edx, 8; DesiredAccess
0x18005f43b  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18005f440  mov     rcx, rax; ThreadHandle
0x18005f443  lea     r8d, [rdx-7]; OpenAsSelf
0x18005f447  call    cs:__imp_OpenThreadToken
0x18005f44e  nop     dword ptr [rax+rax+00h]
0x18005f453  test    eax, eax
0x18005f455  jnz     loc_18005F503
0x18005f45b  call    cs:__imp_GetLastError
0x18005f462  nop     dword ptr [rax+rax+00h]
0x18005f467  mov     ebx, eax
0x18005f469  cmp     eax, 3F0h
0x18005f46e  jnz     loc_18005F516
0x18005f474  call    cs:__imp_GetCurrentProcess
0x18005f47b  nop     dword ptr [rax+rax+00h]
0x18005f480  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18005f485  mov     edx, 0Ah; DesiredAccess
0x18005f48a  mov     rcx, rax; ProcessHandle
0x18005f48d  call    cs:__imp_OpenProcessToken
0x18005f494  nop     dword ptr [rax+rax+00h]
0x18005f499  test    eax, eax
0x18005f49b  jnz     short loc_18005F4AD
0x18005f49d  call    cs:__imp_GetLastError
0x18005f4a4  nop     dword ptr [rax+rax+00h]
0x18005f4a9  mov     ebx, eax
0x18005f4ab  jmp     short loc_18005F516
0x18005f4ad  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18005f4b2  lea     rax, [rsp+38h+arg_18]
0x18005f4b7  mov     [rsp+38h+phNewToken], rax; phNewToken
0x18005f4bc  mov     r9d, 1; ImpersonationLevel
0x18005f4c2  xor     r8d, r8d; lpTokenAttributes
0x18005f4c5  mov     [rsp+38h+TokenType], 2; TokenType
0x18005f4cd  mov     edx, 2000000h; dwDesiredAccess
0x18005f4d2  mov     [rsp+38h+arg_18], 0
0x18005f4db  call    cs:__imp_DuplicateTokenEx
0x18005f4e2  nop     dword ptr [rax+rax+00h]
0x18005f4e7  test    eax, eax
0x18005f4e9  jz      short loc_18005F49D
0x18005f4eb  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18005f4f0  call    cs:__imp_CloseHandle
0x18005f4f7  nop     dword ptr [rax+rax+00h]
0x18005f4fc  mov     rax, [rsp+38h+arg_18]
0x18005f501  jmp     short loc_18005F508
0x18005f503  mov     rax, [rsp+38h+TokenHandle]
0x18005f508  mov     [rdi], rax
0x18005f50b  xor     ebx, ebx
0x18005f50d  mov     [rsp+38h+TokenHandle], 0
0x18005f516  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18005f51b  test    rcx, rcx
0x18005f51e  jz      short loc_18005F52C
0x18005f520  call    cs:__imp_CloseHandle
0x18005f527  nop     dword ptr [rax+rax+00h]
0x18005f52c  mov     eax, ebx
0x18005f52e  mov     rbx, [rsp+38h+arg_0]
0x18005f533  add     rsp, 30h
0x18005f537  pop     rdi
0x18005f538  retn
```
