# NtrbInitialize

- ea: `0x180009270`
- end: `0x18000937e`
- name: `NtrbInitialize`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008e98`

## callees

- `0x180009270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009355`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009355`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800092eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800092eb`

## pseudocode

```c
__int64 __fastcall NtrbInitialize(__int64 a1, __int64 a2, int a3)
{
  DWORD LastError; // ebx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax

  if ( _InterlockedCompareExchange(&NtrbState, 3, 0) )
  {
    LastError = 21;
  }
  else
  {
    NtrbTimeoutTimerTpEnvironment.Version = 3;
    NtrbTimeoutTimerTpEnvironment.CleanupGroupCancelCallback = 0;
    *(_OWORD *)&NtrbTimeoutTimerTpEnvironment.Pool = 0;
    NtrbTimeoutTimerTpEnvironment.FinalizationCallback = 0;
    *(_OWORD *)&NtrbTimeoutTimerTpEnvironment.RaceDll = 0;
    NtrbTimeoutTimerTpEnvironment.u.Flags = 0;
    NtrbTimeoutTimerTpEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    NtrbTimeoutTimerTpEnvironment.Size = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    NtrbTimeoutTimerCleanupGroup = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      NtrbTimeoutTimerTpEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
      NtrbUserCompareRequestIds = (__int64)CompareAsyncEprRequests;
      LastError = 0;
      NtrbTimeoutTimerTpEnvironment.CleanupGroupCancelCallback = 0;
      NtrbUserCleanupRequest = (__int64)&CleanupBufferedAsyncEprRequest;
      *((_QWORD *)&NtrbRequestQueueListHead + 1) = &NtrbRequestQueueListHead;
      *(_QWORD *)&NtrbRequestQueueListHead = &NtrbRequestQueueListHead;
      NtrbRequestTimeoutLength = a3;
      InitializeCriticalSection(&NtrbRequestQueuesLock);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  _InterlockedCompareExchange(&NtrbState, LastError == 0, 3);
  return LastError;
}

```

## disassembly

```asm
0x180009270  mov     [rsp+arg_0], rbx
0x180009275  mov     [rsp+arg_8], rbp
0x18000927a  push    rdi
0x18000927b  sub     rsp, 20h
0x18000927f  mov     edi, r8d
0x180009282  mov     ebp, 3
0x180009287  xor     eax, eax
0x180009289  lock cmpxchg cs:NtrbState, ebp
0x180009291  jz      short loc_18000929B
0x180009293  lea     ebx, [rbp+12h]
0x180009296  jmp     loc_18000935B
0x18000929b  xorps   xmm0, xmm0
0x18000929e  mov     cs:NtrbTimeoutTimerTpEnvironment.Version, ebp
0x1800092a4  xorps   xmm1, xmm1
0x1800092a7  mov     cs:NtrbTimeoutTimerTpEnvironment.CleanupGroupCancelCallback, 0
0x1800092b2  movdqu  xmmword ptr cs:NtrbTimeoutTimerTpEnvironment.Pool, xmm0
0x1800092ba  mov     cs:NtrbTimeoutTimerTpEnvironment.FinalizationCallback, 0
0x1800092c5  movdqu  xmmword ptr cs:NtrbTimeoutTimerTpEnvironment.RaceDll, xmm1
0x1800092cd  mov     dword ptr cs:NtrbTimeoutTimerTpEnvironment.u, 0
0x1800092d7  mov     cs:NtrbTimeoutTimerTpEnvironment.CallbackPriority, 1
0x1800092e1  mov     cs:NtrbTimeoutTimerTpEnvironment.Size, 48h ; 'H'
0x1800092eb  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800092f1  mov     cs:NtrbTimeoutTimerCleanupGroup, rax
0x1800092f8  test    rax, rax
0x1800092fb  jnz     short loc_180009307
0x1800092fd  call    cs:__imp_GetLastError
0x180009303  mov     ebx, eax
0x180009305  jmp     short loc_18000935B
0x180009307  lea     rcx, CompareAsyncEprRequests
0x18000930e  mov     cs:NtrbTimeoutTimerTpEnvironment.CleanupGroup, rax
0x180009315  mov     cs:NtrbUserCompareRequestIds, rcx
0x18000931c  xor     ebx, ebx
0x18000931e  lea     rcx, CleanupBufferedAsyncEprRequest
0x180009325  mov     cs:NtrbTimeoutTimerTpEnvironment.CleanupGroupCancelCallback, rbx
0x18000932c  mov     cs:NtrbUserCleanupRequest, rcx
0x180009333  lea     rcx, NtrbRequestQueueListHead
0x18000933a  mov     qword ptr cs:NtrbRequestQueueListHead+8, rcx
0x180009341  mov     qword ptr cs:NtrbRequestQueueListHead, rcx
0x180009348  lea     rcx, NtrbRequestQueuesLock; lpCriticalSection
0x18000934f  mov     cs:NtrbRequestTimeoutLength, edi
0x180009355  call    cs:__imp_InitializeCriticalSection
0x18000935b  xor     ecx, ecx
0x18000935d  mov     eax, ebp
0x18000935f  test    ebx, ebx
0x180009361  setz    cl
0x180009364  lock cmpxchg cs:NtrbState, ecx
0x18000936c  mov     rbp, [rsp+28h+arg_8]
0x180009371  mov     eax, ebx
0x180009373  mov     rbx, [rsp+28h+arg_0]
0x180009378  add     rsp, 20h
0x18000937c  pop     rdi
0x18000937d  retn
```
