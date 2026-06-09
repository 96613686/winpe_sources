# ServiceBase::QueuePreShutdownCleanupWork(void)

- ea: `0x18000e904`
- end: `0x18000e9bb`
- name: `?QueuePreShutdownCleanupWork@ServiceBase@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(char *Context)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800102c0`

## callees

- `0x18000d69c`
- `0x18000e904`
- `0x180010200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e973`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000e945`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000e945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000e94e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000e94e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e96b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e96b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000e920`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000e920`

## pseudocode

```c
void __fastcall ServiceBase::QueuePreShutdownCleanupWork(char *Context)
{
  PTP_WORK ThreadpoolWork; // rax
  struct _TP_WORK *v3; // rbp
  struct _TP_WORK *v4; // rdi
  DWORD LastError; // ebx
  signed int v6; // eax
  __int64 v7; // rdx
  signed int v8; // [rsp+40h] [rbp+8h] BYREF
  char *v9; // [rsp+48h] [rbp+10h] BYREF

  ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)ServiceBase::_PreShutdownCleanupWorker, Context, 0);
  v3 = (struct _TP_WORK *)*((_QWORD *)Context + 23);
  v4 = ThreadpoolWork;
  if ( v3 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)Context + 23) = v4;
  if ( v4 )
  {
    SubmitThreadpoolWork(v4);
  }
  else
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v8 = v6;
    v9 = Context + 8;
    ServiceHostTelemetry::ServiceBaseError<unsigned short const *,unsigned short const (&)[36],long>(&v9, v7, &v8);
    ServiceBase::_PreShutdownCleanupWorker(0, (HANDLE *)Context, 0);
  }
}

```

## disassembly

```asm
0x18000e904  mov     [rsp+arg_10], rbx
0x18000e909  push    rbp
0x18000e90a  push    rsi
0x18000e90b  push    rdi
0x18000e90c  sub     rsp, 20h
0x18000e910  mov     rsi, rcx
0x18000e913  mov     rdx, rcx; pv
0x18000e916  lea     rcx, ?_PreShutdownCleanupWorker@ServiceBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000e91d  xor     r8d, r8d; pcbe
0x18000e920  call    cs:__imp_CreateThreadpoolWork
0x18000e926  mov     rbp, [rsi+0B8h]
0x18000e92d  mov     rdi, rax
0x18000e930  test    rbp, rbp
0x18000e933  jz      short loc_18000E95C
0x18000e935  call    cs:__imp_GetLastError
0x18000e93b  mov     edx, 1; fCancelPendingCallbacks
0x18000e940  mov     rcx, rbp; pwk
0x18000e943  mov     ebx, eax
0x18000e945  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000e94b  mov     rcx, rbp; pwk
0x18000e94e  call    cs:__imp_CloseThreadpoolWork
0x18000e954  mov     ecx, ebx; dwErrCode
0x18000e956  call    cs:__imp_SetLastError
0x18000e95c  mov     [rsi+0B8h], rdi
0x18000e963  test    rdi, rdi
0x18000e966  jz      short loc_18000E973
0x18000e968  mov     rcx, rdi; pwk
0x18000e96b  call    cs:__imp_SubmitThreadpoolWork
0x18000e971  jmp     short loc_18000E9AE
0x18000e973  call    cs:__imp_GetLastError
0x18000e979  test    eax, eax
0x18000e97b  jle     short loc_18000E985
0x18000e97d  movzx   eax, ax
0x18000e980  or      eax, 80070000h
0x18000e985  mov     [rsp+38h+arg_0], eax
0x18000e989  lea     r8, [rsp+38h+arg_0]
0x18000e98e  lea     rax, [rsi+8]
0x18000e992  lea     rcx, [rsp+38h+arg_8]
0x18000e997  mov     [rsp+38h+arg_8], rax
0x18000e99c  call    ??$ServiceBaseError@PEBGAEAY0CE@$$CBGJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAY0CE@$$CBG$$QEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort const *,ushort const (&)[36],long>(ushort const * &&,ushort const (&)[36],long &&)
0x18000e9a1  xor     r8d, r8d; Work
0x18000e9a4  mov     rdx, rsi; Context
0x18000e9a7  xor     ecx, ecx; Instance
0x18000e9a9  call    ?_PreShutdownCleanupWorker@ServiceBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; ServiceBase::_PreShutdownCleanupWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18000e9ae  mov     rbx, [rsp+38h+arg_10]
0x18000e9b3  add     rsp, 20h
0x18000e9b7  pop     rdi
0x18000e9b8  pop     rsi
0x18000e9b9  pop     rbp
0x18000e9ba  retn
```
