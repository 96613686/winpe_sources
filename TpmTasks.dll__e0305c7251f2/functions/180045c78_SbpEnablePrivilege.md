# SbpEnablePrivilege

- ea: `0x180045c78`
- end: `0x180045e2e`
- name: `SbpEnablePrivilege`
- size: `438`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045b6c`

## callees

- `0x1800078b0`
- `0x180045c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045cf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045cf4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045da3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045dce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045da3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045dce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180045d31`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180045d31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045d1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045d08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e0f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180045d6a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180045d6a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180045d8f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180045d8f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180045cc5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180045cc5`

## pseudocode

```c
__int64 __fastcall SbpEnablePrivilege(LPCWSTR lpName)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v5; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  Token = 0;
  if ( lpName )
  {
    NewState = 0;
    NewState.PrivilegeCount = 1;
    if ( !LookupPrivilegeValueW(0, lpName, &NewState.Privileges[0].Luid) )
      goto LABEL_3;
    NewState.Privileges[0].Attributes = 2;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
    {
      v5 = TokenHandle;
      hObject = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008
        || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
      {
LABEL_3:
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_18;
      }
      v5 = TokenHandle;
    }
    if ( DuplicateTokenEx(v5, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
      && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
      && SetThreadToken(0, Token) )
    {
      dword_1800A4110 = 1;
      goto LABEL_18;
    }
    goto LABEL_3;
  }
  if ( dword_1800A4110 )
  {
    SetThreadToken(0, hObject);
    dword_1800A4110 = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_18:
  if ( TokenHandle != hObject )
    CloseHandle(TokenHandle);
  if ( Token )
    CloseHandle(Token);
  return v1;
}

```

## disassembly

```asm
0x180045c78  mov     [rsp-8+arg_8], rbx
0x180045c7d  push    rbp
0x180045c7e  mov     rbp, rsp
0x180045c81  sub     rsp, 60h
0x180045c85  mov     rax, cs:__security_cookie
0x180045c8c  xor     rax, rsp
0x180045c8f  mov     [rbp+var_10], rax
0x180045c93  xor     ebx, ebx
0x180045c95  mov     [rbp+TokenHandle], 0
0x180045c9d  mov     [rbp+Token], 0
0x180045ca5  test    rcx, rcx
0x180045ca8  jz      loc_180045DBD
0x180045cae  xorps   xmm0, xmm0
0x180045cb1  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x180045cb5  mov     rdx, rcx; lpName
0x180045cb8  xor     ecx, ecx; lpSystemName
0x180045cba  movups  xmmword ptr [rbp-20h], xmm0
0x180045cbe  mov     [rbp+NewState.PrivilegeCount], 1
0x180045cc5  call    cs:__imp_LookupPrivilegeValueW
0x180045ccb  test    eax, eax
0x180045ccd  jnz     short loc_180045CED
0x180045ccf  call    cs:__imp_GetLastError
0x180045cd5  mov     ebx, eax
0x180045cd7  test    eax, eax
0x180045cd9  jle     loc_180045DF3
0x180045cdf  movzx   ebx, ax
0x180045ce2  or      ebx, 80070000h
0x180045ce8  jmp     loc_180045DF3
0x180045ced  mov     [rbp+NewState.Privileges.Attributes], 2
0x180045cf4  call    cs:__imp_GetCurrentThread
0x180045cfa  xor     r8d, r8d; OpenAsSelf
0x180045cfd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180045d01  mov     rcx, rax; ThreadHandle
0x180045d04  lea     edx, [r8+6]; DesiredAccess
0x180045d08  call    cs:__imp_OpenThreadToken
0x180045d0e  test    eax, eax
0x180045d10  jnz     short loc_180045D41
0x180045d12  call    cs:__imp_GetLastError
0x180045d18  cmp     eax, 3F0h
0x180045d1d  jnz     short loc_180045CCF
0x180045d1f  call    cs:__imp_GetCurrentProcess
0x180045d25  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180045d29  mov     edx, 2; DesiredAccess
0x180045d2e  mov     rcx, rax; ProcessHandle
0x180045d31  call    cs:__imp_OpenProcessToken
0x180045d37  test    eax, eax
0x180045d39  jz      short loc_180045CCF
0x180045d3b  mov     rcx, [rbp+TokenHandle]
0x180045d3f  jmp     short loc_180045D4C
0x180045d41  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180045d45  mov     cs:hObject, rcx
0x180045d4c  mov     r9d, 2; ImpersonationLevel
0x180045d52  lea     rax, [rbp+Token]
0x180045d56  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180045d5b  xor     r8d, r8d; lpTokenAttributes
0x180045d5e  mov     [rsp+60h+TokenType], 2; TokenType
0x180045d66  lea     edx, [r9+2Ah]; dwDesiredAccess
0x180045d6a  call    cs:__imp_DuplicateTokenEx
0x180045d70  test    eax, eax
0x180045d72  jz      loc_180045CCF
0x180045d78  mov     rcx, [rbp+Token]; TokenHandle
0x180045d7c  lea     r8, [rbp+NewState]; NewState
0x180045d80  mov     [rsp+60h+phNewToken], rbx; ReturnLength
0x180045d85  xor     r9d, r9d; BufferLength
0x180045d88  xor     edx, edx; DisableAllPrivileges
0x180045d8a  mov     qword ptr [rsp+60h+TokenType], rbx; PreviousState
0x180045d8f  call    cs:__imp_AdjustTokenPrivileges
0x180045d95  test    eax, eax
0x180045d97  jz      loc_180045CCF
0x180045d9d  mov     rdx, [rbp+Token]; Token
0x180045da1  xor     ecx, ecx; Thread
0x180045da3  call    cs:__imp_SetThreadToken
0x180045da9  test    eax, eax
0x180045dab  jz      loc_180045CCF
0x180045db1  mov     cs:dword_1800A4110, 1
0x180045dbb  jmp     short loc_180045DF3
0x180045dbd  cmp     cs:dword_1800A4110, ebx
0x180045dc3  jz      short loc_180045DDA
0x180045dc5  mov     rdx, cs:hObject; Token
0x180045dcc  xor     ecx, ecx; Thread
0x180045dce  call    cs:__imp_SetThreadToken
0x180045dd4  mov     cs:dword_1800A4110, ebx
0x180045dda  mov     rcx, cs:hObject; hObject
0x180045de1  test    rcx, rcx
0x180045de4  jz      short loc_180045DF3
0x180045de6  call    cs:__imp_CloseHandle
0x180045dec  mov     cs:hObject, rbx
0x180045df3  mov     rcx, [rbp+TokenHandle]; hObject
0x180045df7  cmp     rcx, cs:hObject
0x180045dfe  jz      short loc_180045E06
0x180045e00  call    cs:__imp_CloseHandle
0x180045e06  mov     rcx, [rbp+Token]; hObject
0x180045e0a  test    rcx, rcx
0x180045e0d  jz      short loc_180045E15
0x180045e0f  call    cs:__imp_CloseHandle
0x180045e15  mov     eax, ebx
0x180045e17  mov     rcx, [rbp+var_10]
0x180045e1b  xor     rcx, rsp; StackCookie
0x180045e1e  call    __security_check_cookie
0x180045e23  mov     rbx, [rsp+60h+arg_8]
0x180045e28  add     rsp, 60h
0x180045e2c  pop     rbp
0x180045e2d  retn
```
