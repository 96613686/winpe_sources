# FvepAcquirePrivilege

- ea: `0x1801edf74`
- end: `0x1801ee0da`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ee0e0`

## callees

- `0x180006290`
- `0x1801edf74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ee049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ee049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801edfe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801edfe4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801edff3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801edff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801edfb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801edfb8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801edfcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801edfcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801ee08f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801ee08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ee0ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ee0bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ee0ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ee0bd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801ee03f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801ee03f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801ee07f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801ee07f`

## pseudocode

```c
__int64 __fastcall FvepAcquirePrivilege(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  void *v8; // rcx
  signed int v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState.Privileges[0].Attributes = 2;
  Token = (HANDLE)-1LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)17LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
  {
    v8 = TokenHandle;
    v4 = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008
      || (v4 = 0, CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      goto LABEL_17;
    }
    v8 = TokenHandle;
  }
  if ( DuplicateTokenEx(v8, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
    && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
    && SetThreadToken(0, Token) )
  {
    v7 = 0;
    *a2 = v4;
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( !v4 )
    goto LABEL_15;
LABEL_17:
  if ( Token != (HANDLE)-1LL )
    CloseHandle(Token);
  return v7;
}

```

## disassembly

```asm
0x1801edf74  push    rbp
0x1801edf76  push    rbx
0x1801edf77  push    rsi
0x1801edf78  push    rdi
0x1801edf79  mov     rbp, rsp
0x1801edf7c  sub     rsp, 68h
0x1801edf80  mov     rax, cs:__security_cookie
0x1801edf87  xor     rax, rsp
0x1801edf8a  mov     [rbp+var_18], rax
0x1801edf8e  mov     ebx, 2
0x1801edf93  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801edf9b  mov     [rbp+NewState.Privileges.Attributes], ebx
0x1801edf9e  mov     rsi, rdx
0x1801edfa1  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1801edfa9  mov     [rbp+NewState.PrivilegeCount], 1
0x1801edfb0  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x1801edfb8  call    cs:__imp_GetCurrentThread
0x1801edfbe  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1801edfc2  xor     r8d, r8d; OpenAsSelf
0x1801edfc5  mov     rcx, rax; ThreadHandle
0x1801edfc8  lea     edx, [rbx+4]; DesiredAccess
0x1801edfcb  call    cs:__imp_OpenThreadToken
0x1801edfd1  test    eax, eax
0x1801edfd3  jnz     short loc_1801EE021
0x1801edfd5  call    cs:__imp_GetLastError
0x1801edfdb  cmp     eax, 3F0h
0x1801edfe0  jnz     short loc_1801EDFFD
0x1801edfe2  xor     edi, edi
0x1801edfe4  call    cs:__imp_GetCurrentProcess
0x1801edfea  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801edfee  mov     edx, ebx; DesiredAccess
0x1801edff0  mov     rcx, rax; ProcessHandle
0x1801edff3  call    cs:__imp_OpenProcessToken
0x1801edff9  test    eax, eax
0x1801edffb  jnz     short loc_1801EE01B
0x1801edffd  call    cs:__imp_GetLastError
0x1801ee003  mov     ebx, eax
0x1801ee005  test    eax, eax
0x1801ee007  jle     loc_1801EE0A3
0x1801ee00d  movzx   ebx, ax
0x1801ee010  or      ebx, 80070000h
0x1801ee016  jmp     loc_1801EE0A3
0x1801ee01b  mov     rcx, [rbp+TokenHandle]
0x1801ee01f  jmp     short loc_1801EE028
0x1801ee021  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1801ee025  mov     rdi, rcx
0x1801ee028  xor     r8d, r8d; lpTokenAttributes
0x1801ee02b  lea     rax, [rbp+Token]
0x1801ee02f  mov     [rsp+68h+phNewToken], rax; phNewToken
0x1801ee034  mov     r9d, ebx; ImpersonationLevel
0x1801ee037  mov     [rsp+68h+TokenType], ebx; TokenType
0x1801ee03b  lea     edx, [r8+2Ch]; dwDesiredAccess
0x1801ee03f  call    cs:__imp_DuplicateTokenEx
0x1801ee045  test    eax, eax
0x1801ee047  jnz     short loc_1801EE060
0x1801ee049  call    cs:__imp_GetLastError
0x1801ee04f  mov     ebx, eax
0x1801ee051  test    eax, eax
0x1801ee053  jle     short loc_1801EE09E
0x1801ee055  movzx   ebx, ax
0x1801ee058  or      ebx, 80070000h
0x1801ee05e  jmp     short loc_1801EE09E
0x1801ee060  mov     rcx, [rbp+Token]; TokenHandle
0x1801ee064  lea     r8, [rbp+NewState]; NewState
0x1801ee068  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x1801ee071  xor     r9d, r9d; BufferLength
0x1801ee074  xor     edx, edx; DisableAllPrivileges
0x1801ee076  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x1801ee07f  call    cs:__imp_AdjustTokenPrivileges
0x1801ee085  test    eax, eax
0x1801ee087  jz      short loc_1801EE049
0x1801ee089  mov     rdx, [rbp+Token]; Token
0x1801ee08d  xor     ecx, ecx; Thread
0x1801ee08f  call    cs:__imp_SetThreadToken
0x1801ee095  test    eax, eax
0x1801ee097  jz      short loc_1801EE049
0x1801ee099  xor     ebx, ebx
0x1801ee09b  mov     [rsi], rdi
0x1801ee09e  test    rdi, rdi
0x1801ee0a1  jnz     short loc_1801EE0B3
0x1801ee0a3  mov     rcx, [rbp+TokenHandle]; hObject
0x1801ee0a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801ee0ab  jz      short loc_1801EE0B3
0x1801ee0ad  call    cs:__imp_CloseHandle
0x1801ee0b3  mov     rcx, [rbp+Token]; hObject
0x1801ee0b7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801ee0bb  jz      short loc_1801EE0C3
0x1801ee0bd  call    cs:__imp_CloseHandle
0x1801ee0c3  mov     eax, ebx
0x1801ee0c5  mov     rcx, [rbp+var_18]
0x1801ee0c9  xor     rcx, rsp; StackCookie
0x1801ee0cc  call    __security_check_cookie
0x1801ee0d1  add     rsp, 68h
0x1801ee0d5  pop     rdi
0x1801ee0d6  pop     rsi
0x1801ee0d7  pop     rbx
0x1801ee0d8  pop     rbp
0x1801ee0d9  retn
```
