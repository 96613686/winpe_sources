# GetUserSid(void * *)

- ea: `0x1800193a8`
- end: `0x1800194d4`
- name: `?GetUserSid@@YAKPEAPEAX@Z`
- size: `300`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800178a4`

## callees

- `0x18001448c`
- `0x1800144b4`
- `0x180019290`
- `0x1800193a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019462`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800193dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800193dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800193c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800193c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180019475`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180019475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001947f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001947f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0f2`

## pseudocode

```c
__int64 __fastcall GetUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int SidFromToken; // ebx
  CIdentityProfileHandler *v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_14;
  LastError = GetLastError();
  SidFromToken = LastError;
  if ( LastError != 1008 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 11;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids, LastError);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids);
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
LABEL_14:
    SidFromToken = GetSidFromToken(TokenHandle, a1);
    goto LABEL_15;
  }
  LastError = GetLastError();
  SidFromToken = LastError;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = 13;
    goto LABEL_6;
  }
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return SidFromToken;
}

```

## disassembly

```asm
0x1800193a8  mov     [rsp+arg_0], rbx
0x1800193ad  mov     [rsp+arg_10], rsi
0x1800193b2  push    rdi
0x1800193b3  sub     rsp, 20h
0x1800193b7  mov     rsi, rcx
0x1800193ba  mov     [rsp+28h+TokenHandle], 0
0x1800193c3  call    cs:__imp_GetCurrentThread
0x1800193c9  mov     rcx, rax; ThreadHandle
0x1800193cc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800193d1  mov     edx, 20008h; DesiredAccess
0x1800193d6  mov     r8d, 1; OpenAsSelf
0x1800193dc  call    cs:__imp_OpenThreadToken
0x1800193e2  test    eax, eax
0x1800193e4  jnz     loc_1800194A3
0x1800193ea  call    cs:__imp_GetLastError
0x1800193f0  mov     ebx, eax
0x1800193f2  cmp     eax, 3F0h
0x1800193f7  jz      short loc_180019434
0x1800193f9  lea     rdi, WPP_GLOBAL_Control
0x180019400  mov     rcx, cs:WPP_GLOBAL_Control
0x180019407  cmp     rcx, rdi
0x18001940a  jz      loc_1800194B2
0x180019410  test    byte ptr [rcx+1Ch], 4
0x180019414  jz      loc_1800194B2
0x18001941a  mov     edx, 0Bh
0x18001941f  mov     r9d, eax
0x180019422  lea     r8, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids
0x180019429  mov     rcx, [rcx+10h]
0x18001942d  call    WPP_SF_d
0x180019432  jmp     short loc_1800194B2
0x180019434  lea     rdi, WPP_GLOBAL_Control
0x18001943b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019442  cmp     rcx, rdi
0x180019445  jz      short loc_180019462
0x180019447  test    byte ptr [rcx+1Ch], 10h
0x18001944b  jz      short loc_180019462
0x18001944d  mov     edx, 0Ch
0x180019452  lea     r8, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids
0x180019459  mov     rcx, [rcx+10h]
0x18001945d  call    WPP_SF_
0x180019462  call    cs:__imp_GetCurrentProcess
0x180019468  mov     rcx, rax; ProcessHandle
0x18001946b  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180019470  mov     edx, 20008h; DesiredAccess
0x180019475  call    cs:__imp_OpenProcessToken
0x18001947b  test    eax, eax
0x18001947d  jnz     short loc_1800194A3
0x18001947f  call    cs:__imp_GetLastError
0x180019485  mov     ebx, eax
0x180019487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001948e  cmp     rcx, rdi
0x180019491  jz      short loc_1800194B2
0x180019493  test    byte ptr [rcx+1Ch], 4
0x180019497  jz      short loc_1800194B2
0x180019499  mov     edx, 0Dh
0x18001949e  jmp     loc_18001941F
0x1800194a3  mov     rdx, rsi; void **
0x1800194a6  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800194ab  call    ?GetSidFromToken@@YAKPEAXPEAPEAX@Z; GetSidFromToken(void *,void * *)
0x1800194b0  mov     ebx, eax
0x1800194b2  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800194b7  test    rcx, rcx
0x1800194ba  jz      short loc_1800194C2
0x1800194bc  call    cs:__imp_CloseHandle
0x1800194c2  mov     eax, ebx
0x1800194c4  mov     rbx, [rsp+28h+arg_0]
0x1800194c9  mov     rsi, [rsp+28h+arg_10]
0x1800194ce  add     rsp, 20h
0x1800194d2  pop     rdi
0x1800194d3  retn
0x18001a0e0  push    rbp
0x18001a0e2  sub     rsp, 20h
0x18001a0e6  mov     rbp, rdx
0x18001a0e9  mov     rcx, [rbp+38h]; hObject
0x18001a0ed  test    rcx, rcx
0x18001a0f0  jz      short loc_18001A0F9
0x18001a0f2  call    cs:__imp_CloseHandle
0x18001a0f8  nop
0x18001a0f9  add     rsp, 20h
0x18001a0fd  pop     rbp
0x18001a0fe  retn
```
