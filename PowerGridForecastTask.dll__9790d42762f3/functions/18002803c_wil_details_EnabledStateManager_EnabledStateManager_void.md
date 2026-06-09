# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18002803c`
- end: `0x180028194`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800364f0`

## callees

- `0x18002803c`
- `0x18002be60`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002805d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002805d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002808f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002808f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002814c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002814c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002813e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002813e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002807e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028174`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002807e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028174`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180028087`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002817d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180028087`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002817d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028070`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028166`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028070`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028166`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x18002803c  mov     [rsp+arg_0], rbx
0x180028041  mov     [rsp+arg_8], rsi
0x180028046  push    rdi
0x180028047  sub     rsp, 20h
0x18002804b  mov     rdi, rcx
0x18002804e  mov     dword ptr [rcx], 0
0x180028054  mov     rsi, [rcx+10h]
0x180028058  test    rsi, rsi
0x18002805b  jz      short loc_180028095
0x18002805d  call    cs:__imp_GetLastError
0x180028063  mov     ebx, eax
0x180028065  xor     r9d, r9d; msWindowLength
0x180028068  xor     r8d, r8d; msPeriod
0x18002806b  xor     edx, edx; pftDueTime
0x18002806d  mov     rcx, rsi; pti
0x180028070  call    cs:__imp_SetThreadpoolTimer
0x180028076  mov     edx, 1; fCancelPendingCallbacks
0x18002807b  mov     rcx, rsi; pti
0x18002807e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180028084  mov     rcx, rsi; pti
0x180028087  call    cs:__imp_CloseThreadpoolTimer
0x18002808d  mov     ecx, ebx; dwErrCode
0x18002808f  call    cs:__imp_SetLastError
0x180028095  mov     qword ptr [rdi+10h], 0
0x18002809d  mov     rcx, rdi; this
0x1800280a0  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800280a5  mov     rcx, [rdi+68h]
0x1800280a9  test    rcx, rcx
0x1800280ac  jz      short loc_1800280DE
0x1800280ae  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800280b5  test    rax, rax
0x1800280b8  jnz     short loc_1800280C9
0x1800280ba  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800280c1  test    rdx, rdx
0x1800280c4  jz      short loc_1800280DC
0x1800280c6  mov     rax, rdx
0x1800280c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280ce  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800280d5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800280dc  jmp     short loc_1800280EC
0x1800280de  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800280e5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800280ec  mov     rcx, [rdi+60h]
0x1800280f0  test    rcx, rcx
0x1800280f3  jz      short loc_180028108
0x1800280f5  test    rax, rax
0x1800280f8  jnz     short loc_180028102
0x1800280fa  test    rdx, rdx
0x1800280fd  jz      short loc_180028108
0x1800280ff  mov     rax, rdx
0x180028102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028107  nop
0x180028108  mov     rbx, [rdi+58h]
0x18002810c  mov     qword ptr [rdi+58h], 0
0x180028114  test    rbx, rbx
0x180028117  jz      short loc_18002812D
0x180028119  call    cs:__imp_GetProcessHeap
0x18002811f  mov     rcx, rax; hHeap
0x180028122  mov     r8, rbx; lpMem
0x180028125  xor     edx, edx; dwFlags
0x180028127  call    cs:__imp_HeapFree
0x18002812d  mov     rbx, [rdi+38h]
0x180028131  mov     qword ptr [rdi+38h], 0
0x180028139  test    rbx, rbx
0x18002813c  jz      short loc_180028152
0x18002813e  call    cs:__imp_GetProcessHeap
0x180028144  mov     rcx, rax; hHeap
0x180028147  mov     r8, rbx; lpMem
0x18002814a  xor     edx, edx; dwFlags
0x18002814c  call    cs:__imp_HeapFree
0x180028152  mov     rbx, [rdi+10h]
0x180028156  test    rbx, rbx
0x180028159  jz      short loc_180028184
0x18002815b  xor     r9d, r9d; msWindowLength
0x18002815e  xor     r8d, r8d; msPeriod
0x180028161  xor     edx, edx; pftDueTime
0x180028163  mov     rcx, rbx; pti
0x180028166  call    cs:__imp_SetThreadpoolTimer
0x18002816c  mov     edx, 1; fCancelPendingCallbacks
0x180028171  mov     rcx, rbx; pti
0x180028174  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002817a  mov     rcx, rbx; pti
0x18002817d  call    cs:__imp_CloseThreadpoolTimer
0x180028183  nop
0x180028184  mov     rbx, [rsp+28h+arg_0]
0x180028189  mov     rsi, [rsp+28h+arg_8]
0x18002818e  add     rsp, 20h
0x180028192  pop     rdi
0x180028193  retn
```
