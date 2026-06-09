# WinMain_ExecuteCommands

- ea: `0x140002b98`
- end: `0x140002ce0`
- name: `WinMain_ExecuteCommands`
- size: `328`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002ce8`

## callees

- `0x140002b98`
- `0x1400174bc`
- `0x140017c58`
- `0x140017d70`
- `0x140019ad8`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140002c66`
- `KERNEL32!EnterCriticalSection` at `0x140002c66`
- `KERNEL32!LeaveCriticalSection` at `0x140002ca0`
- `KERNEL32!LeaveCriticalSection` at `0x140002ca0`
- `KERNEL32!HeapFree` at `0x140002c49`
- `KERNEL32!HeapFree` at `0x140002c49`
- `KERNEL32!GetProcessHeap` at `0x140002bbd`
- `KERNEL32!GetProcessHeap` at `0x140002bbd`
- `KERNEL32!SetLastError` at `0x140002c2a`
- `KERNEL32!SetLastError` at `0x140002cbf`
- `KERNEL32!SetLastError` at `0x140002c2a`
- `KERNEL32!SetLastError` at `0x140002cbf`
- `KERNEL32!GetLastError` at `0x140002c34`
- `KERNEL32!GetLastError` at `0x140002cb5`
- `KERNEL32!GetLastError` at `0x140002c34`
- `KERNEL32!GetLastError` at `0x140002cb5`

## pseudocode

```c
__int64 WinMain_ExecuteCommands()
{
  struct TASK_REQUEST *v0; // rdi
  HANDLE ProcessHeap; // r15
  int v2; // ecx
  int v3; // r14d
  unsigned int v4; // ebx
  DWORD LastError; // esi
  BOOL v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // eax
  int *v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+30h] [rbp-48h] BYREF
  DWORD dwErrCode; // [rsp+34h] [rbp-44h] BYREF
  struct TASK_REQUEST *v13; // [rsp+38h] [rbp-40h] BYREF
  void *v14[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+50h] [rbp-28h]
  __int64 v16; // [rsp+60h] [rbp-18h]

  dwErrCode = 0;
  v0 = 0;
  v11 = 0;
  ProcessHeap = GetProcessHeap();
  v13 = 0;
  v3 = InitializeTaskServer();
  if ( v3 )
  {
    while ( 1 )
    {
      v4 = WaitForTaskRequest(v2, ProcessHeap, &v11, &dwErrCode, v10, &v13);
      if ( !v4 )
        break;
      if ( v11 )
      {
        if ( dwErrCode )
        {
          v4 = 0;
          SetLastError(dwErrCode);
        }
        break;
      }
      v0 = v13;
      if ( v13 )
      {
        v4 = HandleTaskRequest(v13);
        if ( !v4 )
          goto LABEL_11;
      }
    }
    v0 = v13;
  }
  else
  {
    v4 = 0;
  }
LABEL_11:
  LastError = GetLastError();
  if ( v0 )
  {
    v6 = HeapFree(ProcessHeap, 0, v0);
    if ( v4 )
    {
      v4 = v6;
      LastError = 6;
    }
  }
  if ( v3 )
  {
    EnterCriticalSection(&TaskLock);
    dword_140027D8C = 0;
    *(_OWORD *)v14 = xmmword_140027AA0;
    v16 = qword_140027AC0;
    v15 = xmmword_140027AB0;
    LeaveCriticalSection(&TaskLock);
    v8 = CloseMultipleHandles(v7, v14);
    if ( v4 )
    {
      v4 = v8;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x140002b98  push    rbp
0x140002b9a  push    rbx
0x140002b9b  push    rsi
0x140002b9c  push    rdi
0x140002b9d  push    r14
0x140002b9f  push    r15
0x140002ba1  mov     rbp, rsp
0x140002ba4  sub     rsp, 78h
0x140002ba8  mov     rax, cs:__security_cookie
0x140002baf  xor     rax, rsp
0x140002bb2  mov     [rbp+var_10], rax
0x140002bb6  mov     [rbp+dwErrCode], 0
0x140002bbd  call    cs:__imp_GetProcessHeap
0x140002bc3  xor     edi, edi
0x140002bc5  mov     [rbp+var_48], 0
0x140002bcc  mov     r15, rax
0x140002bcf  mov     [rbp+var_40], rdi
0x140002bd3  call    ?InitializeTaskServer@@YAHXZ; InitializeTaskServer(void)
0x140002bd8  mov     r14d, eax
0x140002bdb  test    eax, eax
0x140002bdd  jnz     short loc_140002BE3
0x140002bdf  xor     ebx, ebx
0x140002be1  jmp     short loc_140002C34
0x140002be3  lea     rax, [rbp+var_40]
0x140002be7  mov     rdx, r15; void *
0x140002bea  lea     r9, [rbp+dwErrCode]; unsigned int *
0x140002bee  mov     [rsp+78h+var_50], rax; struct TASK_REQUEST **
0x140002bf3  lea     r8, [rbp+var_48]; int *
0x140002bf7  call    ?WaitForTaskRequest@@YAHHPEAXPEAHPEAK1PEAPEAUTASK_REQUEST@@@Z; WaitForTaskRequest(int,void *,int *,ulong *,int *,TASK_REQUEST * *)
0x140002bfc  mov     ebx, eax
0x140002bfe  test    eax, eax
0x140002c00  jz      short loc_140002C30
0x140002c02  cmp     [rbp+var_48], 0
0x140002c06  jnz     short loc_140002C21
0x140002c08  mov     rdi, [rbp+var_40]
0x140002c0c  test    rdi, rdi
0x140002c0f  jz      short loc_140002BE3
0x140002c11  mov     rcx, rdi; struct TASK_REQUEST *
0x140002c14  call    ?HandleTaskRequest@@YAHPEBUTASK_REQUEST@@@Z; HandleTaskRequest(TASK_REQUEST const *)
0x140002c19  mov     ebx, eax
0x140002c1b  test    eax, eax
0x140002c1d  jnz     short loc_140002BE3
0x140002c1f  jmp     short loc_140002C34
0x140002c21  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x140002c24  test    ecx, ecx
0x140002c26  jz      short loc_140002C30
0x140002c28  xor     ebx, ebx
0x140002c2a  call    cs:__imp_SetLastError
0x140002c30  mov     rdi, [rbp+var_40]
0x140002c34  call    cs:__imp_GetLastError
0x140002c3a  mov     esi, eax
0x140002c3c  test    rdi, rdi
0x140002c3f  jz      short loc_140002C5A
0x140002c41  mov     r8, rdi; lpMem
0x140002c44  xor     edx, edx; dwFlags
0x140002c46  mov     rcx, r15; hHeap
0x140002c49  call    cs:__imp_HeapFree
0x140002c4f  test    ebx, ebx
0x140002c51  jz      short loc_140002C5A
0x140002c53  mov     ebx, eax
0x140002c55  mov     esi, 6
0x140002c5a  test    r14d, r14d
0x140002c5d  jz      short loc_140002CBD
0x140002c5f  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x140002c66  call    cs:__imp_EnterCriticalSection
0x140002c6c  movups  xmm0, cs:xmmword_140027AA0
0x140002c73  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x140002c7a  mov     cs:dword_140027D8C, 0
0x140002c84  movups  xmm1, cs:xmmword_140027AB0
0x140002c8b  movups  xmmword ptr [rbp+var_38], xmm0
0x140002c8f  movsd   xmm0, cs:qword_140027AC0
0x140002c97  movsd   [rbp+var_18], xmm0
0x140002c9c  movups  [rbp+var_28], xmm1
0x140002ca0  call    cs:__imp_LeaveCriticalSection
0x140002ca6  lea     rdx, [rbp+var_38]; void **
0x140002caa  call    ?CloseMultipleHandles@@YAHIPEAPEAX@Z; CloseMultipleHandles(uint,void * *)
0x140002caf  test    ebx, ebx
0x140002cb1  jz      short loc_140002CBD
0x140002cb3  mov     ebx, eax
0x140002cb5  call    cs:__imp_GetLastError
0x140002cbb  mov     esi, eax
0x140002cbd  mov     ecx, esi; dwErrCode
0x140002cbf  call    cs:__imp_SetLastError
0x140002cc5  mov     eax, ebx
0x140002cc7  mov     rcx, [rbp+var_10]
0x140002ccb  xor     rcx, rsp; StackCookie
0x140002cce  call    __security_check_cookie
0x140002cd3  add     rsp, 78h
0x140002cd7  pop     r15
0x140002cd9  pop     r14
0x140002cdb  pop     rdi
0x140002cdc  pop     rsi
0x140002cdd  pop     rbx
0x140002cde  pop     rbp
0x140002cdf  retn
```
