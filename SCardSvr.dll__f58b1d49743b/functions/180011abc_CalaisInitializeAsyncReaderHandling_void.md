# CalaisInitializeAsyncReaderHandling(void)

- ea: `0x180011abc`
- end: `0x180011b71`
- name: `?CalaisInitializeAsyncReaderHandling@@YAXXZ`
- size: `181`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011410`

## callees

- `0x180011abc`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180011ac7`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180011ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b3e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180011b2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180011b2c`

## pseudocode

```c
void CalaisInitializeAsyncReaderHandling(void)
{
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  InitializeConditionVariable(&l_cvReaderAsyncActionFinished);
  pcbe.Version = 3;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.Pool = 0;
  pcbe.CleanupGroup = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  ptpcg = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    pExceptionObject = GetLastError();
    throw &pExceptionObject;
  }
  pcbe.CleanupGroup = ThreadpoolCleanupGroup;
  pcbe.CleanupGroupCancelCallback = 0;
}

```

## disassembly

```asm
0x180011abc  sub     rsp, 28h
0x180011ac0  lea     rcx, ?l_cvReaderAsyncActionFinished@@3U_RTL_CONDITION_VARIABLE@@A; ConditionVariable
0x180011ac7  call    cs:__imp_InitializeConditionVariable
0x180011acd  xorps   xmm0, xmm0
0x180011ad0  mov     cs:pcbe.Version, 3
0x180011ada  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x180011ae2  mov     cs:pcbe.Pool, 0
0x180011aed  mov     cs:pcbe.CleanupGroup, 0
0x180011af8  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x180011b03  mov     cs:pcbe.FinalizationCallback, 0
0x180011b0e  mov     dword ptr cs:pcbe.u, 0
0x180011b18  mov     cs:pcbe.CallbackPriority, 1
0x180011b22  mov     cs:pcbe.Size, 48h ; 'H'
0x180011b2c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180011b32  mov     cs:ptpcg, rax
0x180011b39  test    rax, rax
0x180011b3c  jnz     short loc_180011B5A
0x180011b3e  call    cs:__imp_GetLastError
0x180011b44  lea     rdx, _TI1K; pThrowInfo
0x180011b4b  mov     [rsp+28h+pExceptionObject], eax
0x180011b4f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011b54  call    _CxxThrowException_0
0x180011b5a  mov     cs:pcbe.CleanupGroup, rax
0x180011b61  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x180011b6c  add     rsp, 28h
0x180011b70  retn
```
