# EnablePrivilegeInternal

- ea: `0x18002d69c`
- end: `0x18002d793`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d640`

## callees

- `0x18002d69c`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d6e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d6e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d6f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d76a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d76a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d736`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d736`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeInternal(LUID a1, DWORD a2, DWORD *a3)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  v3 = 0;
  NewState = 0;
  ReturnLength = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.Privileges[0].Luid = a1;
    v3 = 1;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) || GetLastError() )
    {
      v3 = 0;
    }
    else if ( a3 )
    {
      if ( PreviousState.PrivilegeCount )
        *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
      else
        *a3 = a2;
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18002d69c  mov     [rsp-18h+arg_8], rbx
0x18002d6a1  mov     [rsp-18h+arg_18], rsi
0x18002d6a6  push    rbp
0x18002d6a7  push    rdi
0x18002d6a8  push    r14
0x18002d6aa  mov     rbp, rsp
0x18002d6ad  sub     rsp, 70h
0x18002d6b1  mov     rax, cs:__security_cookie
0x18002d6b8  xor     rax, rsp
0x18002d6bb  mov     [rbp+var_10], rax
0x18002d6bf  xorps   xmm0, xmm0
0x18002d6c2  mov     [rbp+TokenHandle], 0
0x18002d6ca  xorps   xmm1, xmm1
0x18002d6cd  xor     edi, edi
0x18002d6cf  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18002d6d3  mov     [rbp+var_40], edi
0x18002d6d6  mov     rsi, r8
0x18002d6d9  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18002d6dd  mov     r14d, edx
0x18002d6e0  mov     rbx, rcx
0x18002d6e3  call    cs:__imp_GetCurrentProcess
0x18002d6e9  mov     rcx, rax; ProcessHandle
0x18002d6ec  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002d6f0  lea     edx, [rdi+28h]; DesiredAccess
0x18002d6f3  call    cs:__imp_OpenProcessToken
0x18002d6f9  test    eax, eax
0x18002d6fb  jz      short loc_18002D770
0x18002d6fd  mov     eax, r14d
0x18002d700  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x18002d704  neg     eax
0x18002d706  lea     r8, [rbp+NewState]; NewState
0x18002d70a  mov     edi, 1
0x18002d70f  lea     rax, [rbp+var_40]
0x18002d713  sbb     ecx, ecx
0x18002d715  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d71a  and     ecx, 2
0x18002d71d  mov     [rbp+NewState.PrivilegeCount], edi
0x18002d720  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18002d723  lea     rax, [rbp+var_20]
0x18002d727  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002d72b  lea     r9d, [rdi+0Fh]; BufferLength
0x18002d72f  xor     edx, edx; DisableAllPrivileges
0x18002d731  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18002d736  call    cs:__imp_AdjustTokenPrivileges
0x18002d73c  test    eax, eax
0x18002d73e  jz      short loc_18002D764
0x18002d740  call    cs:__imp_GetLastError
0x18002d746  test    eax, eax
0x18002d748  jnz     short loc_18002D764
0x18002d74a  test    rsi, rsi
0x18002d74d  jz      short loc_18002D766
0x18002d74f  cmp     [rbp+var_20.PrivilegeCount], eax
0x18002d752  jnz     short loc_18002D759
0x18002d754  mov     [rsi], r14d
0x18002d757  jmp     short loc_18002D766
0x18002d759  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18002d75c  shr     eax, 1
0x18002d75e  and     eax, edi
0x18002d760  mov     [rsi], eax
0x18002d762  jmp     short loc_18002D766
0x18002d764  xor     edi, edi
0x18002d766  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d76a  call    cs:__imp_CloseHandle
0x18002d770  mov     eax, edi
0x18002d772  mov     rcx, [rbp+var_10]
0x18002d776  xor     rcx, rsp; StackCookie
0x18002d779  call    __security_check_cookie
0x18002d77e  lea     r11, [rsp+70h+var_s0]
0x18002d783  mov     rbx, [r11+28h]
0x18002d787  mov     rsi, [r11+38h]
0x18002d78b  mov     rsp, r11
0x18002d78e  pop     r14
0x18002d790  pop     rdi
0x18002d791  pop     rbp
0x18002d792  retn
```
