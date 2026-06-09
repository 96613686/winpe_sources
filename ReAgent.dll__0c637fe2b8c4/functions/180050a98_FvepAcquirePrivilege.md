# FvepAcquirePrivilege

- ea: `0x180050a98`
- end: `0x180050bfe`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050c04`

## callees

- `0x180050a98`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050af9`
- `KERNEL32!GetLastError` at `0x180050b21`
- `KERNEL32!GetLastError` at `0x180050b6d`
- `KERNEL32!GetLastError` at `0x180050af9`
- `KERNEL32!GetLastError` at `0x180050b21`
- `KERNEL32!GetLastError` at `0x180050b6d`
- `KERNEL32!GetCurrentProcess` at `0x180050b08`
- `KERNEL32!GetCurrentProcess` at `0x180050b08`
- `KERNEL32!CloseHandle` at `0x180050bd1`
- `KERNEL32!CloseHandle` at `0x180050be1`
- `KERNEL32!CloseHandle` at `0x180050bd1`
- `KERNEL32!CloseHandle` at `0x180050be1`
- `KERNEL32!GetCurrentThread` at `0x180050adc`
- `KERNEL32!GetCurrentThread` at `0x180050adc`
- `ADVAPI32!OpenThreadToken` at `0x180050aef`
- `ADVAPI32!OpenThreadToken` at `0x180050aef`
- `ADVAPI32!DuplicateTokenEx` at `0x180050b63`
- `ADVAPI32!DuplicateTokenEx` at `0x180050b63`
- `ADVAPI32!SetThreadToken` at `0x180050bb3`
- `ADVAPI32!SetThreadToken` at `0x180050bb3`
- `ADVAPI32!OpenProcessToken` at `0x180050b17`
- `ADVAPI32!OpenProcessToken` at `0x180050b17`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180050ba3`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180050ba3`

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
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

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
0x180050a98  push    rbp
0x180050a9a  push    rbx
0x180050a9b  push    rsi
0x180050a9c  push    rdi
0x180050a9d  mov     rbp, rsp
0x180050aa0  sub     rsp, 68h
0x180050aa4  mov     rax, cs:__security_cookie
0x180050aab  xor     rax, rsp
0x180050aae  mov     [rbp+var_18], rax
0x180050ab2  mov     ebx, 2
0x180050ab7  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180050abf  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180050ac2  mov     rsi, rdx
0x180050ac5  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x180050acd  mov     [rbp+NewState.PrivilegeCount], 1
0x180050ad4  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x180050adc  call    cs:__imp_GetCurrentThread
0x180050ae2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180050ae6  xor     r8d, r8d; OpenAsSelf
0x180050ae9  mov     rcx, rax; ThreadHandle
0x180050aec  lea     edx, [rbx+4]; DesiredAccess
0x180050aef  call    cs:__imp_OpenThreadToken
0x180050af5  test    eax, eax
0x180050af7  jnz     short loc_180050B45
0x180050af9  call    cs:__imp_GetLastError
0x180050aff  cmp     eax, 3F0h
0x180050b04  jnz     short loc_180050B21
0x180050b06  xor     edi, edi
0x180050b08  call    cs:__imp_GetCurrentProcess
0x180050b0e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180050b12  mov     edx, ebx; DesiredAccess
0x180050b14  mov     rcx, rax; ProcessHandle
0x180050b17  call    cs:__imp_OpenProcessToken
0x180050b1d  test    eax, eax
0x180050b1f  jnz     short loc_180050B3F
0x180050b21  call    cs:__imp_GetLastError
0x180050b27  mov     ebx, eax
0x180050b29  test    eax, eax
0x180050b2b  jle     loc_180050BC7
0x180050b31  movzx   ebx, ax
0x180050b34  or      ebx, 80070000h
0x180050b3a  jmp     loc_180050BC7
0x180050b3f  mov     rcx, [rbp+TokenHandle]
0x180050b43  jmp     short loc_180050B4C
0x180050b45  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180050b49  mov     rdi, rcx
0x180050b4c  xor     r8d, r8d; lpTokenAttributes
0x180050b4f  lea     rax, [rbp+Token]
0x180050b53  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180050b58  mov     r9d, ebx; ImpersonationLevel
0x180050b5b  mov     [rsp+68h+TokenType], ebx; TokenType
0x180050b5f  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180050b63  call    cs:__imp_DuplicateTokenEx
0x180050b69  test    eax, eax
0x180050b6b  jnz     short loc_180050B84
0x180050b6d  call    cs:__imp_GetLastError
0x180050b73  mov     ebx, eax
0x180050b75  test    eax, eax
0x180050b77  jle     short loc_180050BC2
0x180050b79  movzx   ebx, ax
0x180050b7c  or      ebx, 80070000h
0x180050b82  jmp     short loc_180050BC2
0x180050b84  mov     rcx, [rbp+Token]; TokenHandle
0x180050b88  lea     r8, [rbp+NewState]; NewState
0x180050b8c  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x180050b95  xor     r9d, r9d; BufferLength
0x180050b98  xor     edx, edx; DisableAllPrivileges
0x180050b9a  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x180050ba3  call    cs:__imp_AdjustTokenPrivileges
0x180050ba9  test    eax, eax
0x180050bab  jz      short loc_180050B6D
0x180050bad  mov     rdx, [rbp+Token]; Token
0x180050bb1  xor     ecx, ecx; Thread
0x180050bb3  call    cs:__imp_SetThreadToken
0x180050bb9  test    eax, eax
0x180050bbb  jz      short loc_180050B6D
0x180050bbd  xor     ebx, ebx
0x180050bbf  mov     [rsi], rdi
0x180050bc2  test    rdi, rdi
0x180050bc5  jnz     short loc_180050BD7
0x180050bc7  mov     rcx, [rbp+TokenHandle]; hObject
0x180050bcb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180050bcf  jz      short loc_180050BD7
0x180050bd1  call    cs:__imp_CloseHandle
0x180050bd7  mov     rcx, [rbp+Token]; hObject
0x180050bdb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180050bdf  jz      short loc_180050BE7
0x180050be1  call    cs:__imp_CloseHandle
0x180050be7  mov     eax, ebx
0x180050be9  mov     rcx, [rbp+var_18]
0x180050bed  xor     rcx, rsp; StackCookie
0x180050bf0  call    __security_check_cookie
0x180050bf5  add     rsp, 68h
0x180050bf9  pop     rdi
0x180050bfa  pop     rsi
0x180050bfb  pop     rbx
0x180050bfc  pop     rbp
0x180050bfd  retn
```
