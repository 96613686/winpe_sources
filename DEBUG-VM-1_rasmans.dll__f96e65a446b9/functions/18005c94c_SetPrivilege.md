# SetPrivilege

- ea: `0x18005c94c`
- end: `0x18005ca48`
- name: `SetPrivilege`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ca50`

## callees

- `0x18005c94c`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005c995`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005c995`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ca26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ca26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ca15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ca15`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005c9d4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005ca0b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005c9d4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005ca0b`

## pseudocode

```c
__int64 SetPrivilege()
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD BufferLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  BufferLength = 16;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    || (NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Luid = (LUID)9LL,
        NewState.Privileges[0].Attributes = 0,
        !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength))
    || (LastError = 0,
        PreviousState.Privileges[0].Attributes |= 2u,
        PreviousState.PrivilegeCount = 1,
        PreviousState.Privileges[0].Luid = (LUID)9LL,
        !AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0)) )
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18005c94c  mov     [rsp-8+arg_0], rbx
0x18005c951  push    rbp
0x18005c952  mov     rbp, rsp
0x18005c955  sub     rsp, 70h
0x18005c959  mov     rax, cs:__security_cookie
0x18005c960  xor     rax, rsp
0x18005c963  mov     [rbp+var_10], rax
0x18005c967  xorps   xmm0, xmm0
0x18005c96a  mov     [rbp+TokenHandle], 0
0x18005c972  xorps   xmm1, xmm1
0x18005c975  mov     ebx, 10h
0x18005c97a  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18005c97e  mov     [rbp+BufferLength], ebx
0x18005c981  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm1
0x18005c985  call    cs:__imp_GetCurrentProcess
0x18005c98b  mov     rcx, rax; ProcessHandle
0x18005c98e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18005c992  lea     edx, [rbx+18h]; DesiredAccess
0x18005c995  call    cs:__imp_OpenProcessToken
0x18005c99b  test    eax, eax
0x18005c99d  jz      short loc_18005CA15
0x18005c99f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005c9a3  lea     rax, [rbp+BufferLength]
0x18005c9a7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18005c9ac  lea     r8, [rbp+NewState]; NewState
0x18005c9b0  lea     rax, [rbp+var_30]
0x18005c9b4  mov     [rbp+NewState.PrivilegeCount], 1
0x18005c9bb  mov     r9d, ebx; BufferLength
0x18005c9be  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18005c9c3  xor     edx, edx; DisableAllPrivileges
0x18005c9c5  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 9
0x18005c9cd  mov     [rbp+NewState.Privileges.Attributes], 0
0x18005c9d4  call    cs:__imp_AdjustTokenPrivileges
0x18005c9da  test    eax, eax
0x18005c9dc  jz      short loc_18005CA15
0x18005c9de  mov     r9d, [rbp+BufferLength]; BufferLength
0x18005c9e2  lea     r8, [rbp+var_30]; NewState
0x18005c9e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005c9ea  xor     ebx, ebx
0x18005c9ec  or      [rbp+var_30.Privileges.Attributes], 2
0x18005c9f0  xor     edx, edx; DisableAllPrivileges
0x18005c9f2  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x18005c9f7  mov     [rsp+70h+PreviousState], rbx; PreviousState
0x18005c9fc  mov     [rbp+var_30.PrivilegeCount], 1
0x18005ca03  mov     qword ptr [rbp+var_30.Privileges.Luid.LowPart], 9
0x18005ca0b  call    cs:__imp_AdjustTokenPrivileges
0x18005ca11  test    eax, eax
0x18005ca13  jnz     short loc_18005CA1D
0x18005ca15  call    cs:__imp_GetLastError
0x18005ca1b  mov     ebx, eax
0x18005ca1d  mov     rcx, [rbp+TokenHandle]; hObject
0x18005ca21  test    rcx, rcx
0x18005ca24  jz      short loc_18005CA2C
0x18005ca26  call    cs:__imp_CloseHandle
0x18005ca2c  mov     eax, ebx
0x18005ca2e  mov     rcx, [rbp+var_10]
0x18005ca32  xor     rcx, rsp; StackCookie
0x18005ca35  call    __security_check_cookie
0x18005ca3a  mov     rbx, [rsp+70h+arg_0]
0x18005ca42  add     rsp, 70h
0x18005ca46  pop     rbp
0x18005ca47  retn
```
