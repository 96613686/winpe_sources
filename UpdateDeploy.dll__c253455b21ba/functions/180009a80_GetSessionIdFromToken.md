# GetSessionIdFromToken

- ea: `0x180009a80`
- end: `0x180009bb3`
- name: `GetSessionIdFromToken`
- size: `307`
- prototype: `__int64 __fastcall(LPVOID TokenInformation, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800465f0`

## callees

- `0x180002214`
- `0x180003180`
- `0x180009a80`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009ad9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009ad9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009b38`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009b38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009aee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009b68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009b68`

## string_xrefs

- `0x180009ab6`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x180009b7c`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetSessionIdFromToken(LPVOID TokenInformation, HANDLE TokenHandle)
{
  HANDLE v2; // rax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HANDLE CurrentProcess; // rax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  void *TokenHandlea; // [rsp+30h] [rbp-28h] BYREF
  DWORD v12; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = 0;
  v2 = TokenHandle;
  TokenHandlea = 0;
  if ( !TokenInformation )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_16;
  }
  if ( !TokenHandle )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
    {
      if ( GetLastError() != 1008 )
      {
        v7 = 228;
LABEL_14:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                      v6);
        goto LABEL_16;
      }
      if ( TokenHandlea )
      {
        CloseHandle(TokenHandlea);
        TokenHandlea = 0;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandlea) )
      {
        v7 = 230;
        goto LABEL_14;
      }
    }
    v2 = TokenHandlea;
  }
  if ( !GetTokenInformation(v2, TokenSessionId, TokenInformation, 4u, &v12) )
  {
    v7 = 238;
    goto LABEL_14;
  }
  LastError = 0;
LABEL_16:
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  return LastError;
}

```

## disassembly

```asm
0x180009a80  push    rbx
0x180009a82  sub     rsp, 50h
0x180009a86  mov     rax, cs:__security_cookie
0x180009a8d  xor     rax, rsp
0x180009a90  mov     [rsp+58h+var_18], rax
0x180009a95  mov     [rsp+58h+var_20], 0
0x180009a9d  mov     rax, rdx
0x180009aa0  mov     [rsp+58h+TokenHandle], 0
0x180009aa9  mov     rbx, rcx
0x180009aac  test    rcx, rcx
0x180009aaf  jnz     short loc_180009AD4
0x180009ab1  mov     rcx, [rsp+58h]; this
0x180009ab6  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009abd  mov     ebx, 80004003h
0x180009ac2  mov     edx, 0DEh; void *
0x180009ac7  mov     r9d, ebx; char *
0x180009aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009acf  jmp     loc_180009B8E
0x180009ad4  test    rax, rax
0x180009ad7  jnz     short loc_180009B4E
0x180009ad9  call    cs:__imp_GetCurrentThread
0x180009adf  xor     r8d, r8d; OpenAsSelf
0x180009ae2  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180009ae7  mov     rcx, rax; ThreadHandle
0x180009aea  lea     edx, [r8+8]; DesiredAccess
0x180009aee  call    cs:__imp_OpenThreadToken
0x180009af4  test    eax, eax
0x180009af6  jnz     short loc_180009B49
0x180009af8  call    cs:__imp_GetLastError
0x180009afe  cmp     eax, 3F0h
0x180009b03  jz      short loc_180009B0C
0x180009b05  mov     edx, 0E4h
0x180009b0a  jmp     short loc_180009B77
0x180009b0c  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180009b11  test    rcx, rcx
0x180009b14  jz      short loc_180009B25
0x180009b16  call    cs:__imp_CloseHandle
0x180009b1c  mov     [rsp+58h+TokenHandle], 0
0x180009b25  call    cs:__imp_GetCurrentProcess
0x180009b2b  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180009b30  mov     edx, 8; DesiredAccess
0x180009b35  mov     rcx, rax; ProcessHandle
0x180009b38  call    cs:__imp_OpenProcessToken
0x180009b3e  test    eax, eax
0x180009b40  jnz     short loc_180009B49
0x180009b42  mov     edx, 0E6h
0x180009b47  jmp     short loc_180009B77
0x180009b49  mov     rax, [rsp+58h+TokenHandle]
0x180009b4e  mov     r9d, 4; TokenInformationLength
0x180009b54  lea     rcx, [rsp+58h+var_20]
0x180009b59  mov     qword ptr [rsp+58h+ReturnLength], rcx; ReturnLength
0x180009b5e  mov     r8, rbx; TokenInformation
0x180009b61  mov     rcx, rax; TokenHandle
0x180009b64  lea     edx, [r9+8]; TokenInformationClass
0x180009b68  call    cs:__imp_GetTokenInformation
0x180009b6e  test    eax, eax
0x180009b70  jnz     short loc_180009B8C
0x180009b72  mov     edx, 0EEh; void *
0x180009b77  mov     rcx, [rsp+58h]; this
0x180009b7c  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009b83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b88  mov     ebx, eax
0x180009b8a  jmp     short loc_180009B8E
0x180009b8c  xor     ebx, ebx
0x180009b8e  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180009b93  test    rcx, rcx
0x180009b96  jz      short loc_180009B9E
0x180009b98  call    cs:__imp_CloseHandle
0x180009b9e  mov     eax, ebx
0x180009ba0  mov     rcx, [rsp+58h+var_18]
0x180009ba5  xor     rcx, rsp; StackCookie
0x180009ba8  call    __security_check_cookie
0x180009bad  add     rsp, 50h
0x180009bb1  pop     rbx
0x180009bb2  retn
```
