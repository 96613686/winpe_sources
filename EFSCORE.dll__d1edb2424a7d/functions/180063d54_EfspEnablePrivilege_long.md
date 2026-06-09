# EfspEnablePrivilege(long)

- ea: `0x180063d54`
- end: `0x180063e42`
- name: `?EfspEnablePrivilege@@YAKJ@Z`
- size: `238`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064b08`
- `0x180065c90`

## callees

- `0x180063698`
- `0x180063d54`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e15`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180063d94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180063d94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063e27`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180063e0f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180063e0f`

## pseudocode

```c
__int64 __fastcall EfspEnablePrivilege(int a1)
{
  LUID v1; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v1 = (LUID)a1;
  NewState = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = v1;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    LastError = GetLastError();
  }
  else
  {
    LastError = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 11, 241);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180063d54  push    rbx
0x180063d56  sub     rsp, 50h
0x180063d5a  mov     rax, cs:__security_cookie
0x180063d61  xor     rax, rsp
0x180063d64  mov     [rsp+58h+var_10], rax
0x180063d69  xorps   xmm0, xmm0
0x180063d6c  movsxd  rbx, ecx
0x180063d6f  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x180063d74  mov     [rsp+58h+TokenHandle], 0
0x180063d7d  call    cs:__imp_GetCurrentThread
0x180063d83  mov     edx, 28h ; '('; DesiredAccess
0x180063d88  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180063d8d  mov     rcx, rax; ThreadHandle
0x180063d90  lea     r8d, [rdx-27h]; OpenAsSelf
0x180063d94  call    cs:__imp_OpenThreadToken
0x180063d9a  test    eax, eax
0x180063d9c  jnz     short loc_180063DCC
0x180063d9e  call    cs:__imp_GetLastError
0x180063da4  mov     rcx, cs:g_hPublisher
0x180063dab  lea     rdx, EFS_API_ERROR
0x180063db2  mov     r8d, eax
0x180063db5  mov     dword ptr [rsp+58h+PreviousState], 0BF1h
0x180063dbd  mov     r9d, 0Bh
0x180063dc3  mov     ebx, eax
0x180063dc5  call    fnEfsLogTrace1
0x180063dca  jmp     short loc_180063E1D
0x180063dcc  mov     rcx, rbx
0x180063dcf  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180063dd8  shr     rcx, 20h
0x180063ddc  lea     r8, [rsp+58h+NewState]; NewState
0x180063de1  mov     [rsp+58h+NewState.Privileges.Luid.HighPart], ecx
0x180063de5  mov     r9d, 10h; BufferLength
0x180063deb  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180063df0  xor     edx, edx; DisableAllPrivileges
0x180063df2  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x180063dfa  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x180063e02  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], ebx
0x180063e06  mov     [rsp+58h+PreviousState], 0; PreviousState
0x180063e0f  call    cs:__imp_AdjustTokenPrivileges
0x180063e15  call    cs:__imp_GetLastError
0x180063e1b  mov     ebx, eax
0x180063e1d  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180063e22  test    rcx, rcx
0x180063e25  jz      short loc_180063E2D
0x180063e27  call    cs:__imp_CloseHandle
0x180063e2d  mov     eax, ebx
0x180063e2f  mov     rcx, [rsp+58h+var_10]
0x180063e34  xor     rcx, rsp; StackCookie
0x180063e37  call    __security_check_cookie
0x180063e3c  add     rsp, 50h
0x180063e40  pop     rbx
0x180063e41  retn
```
