# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800033c8`
- end: `0x18000350e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cc50`

## callees

- `0x1800033c8`
- `0x18000624c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000341b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000341b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003413`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003413`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000340a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000340a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034ef`

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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x1800033c8  mov     [rsp+arg_0], rbx
0x1800033cd  mov     [rsp+arg_8], rsi
0x1800033d2  push    rdi
0x1800033d3  sub     rsp, 20h
0x1800033d7  mov     dword ptr [rcx], 0
0x1800033dd  mov     rdi, rcx
0x1800033e0  mov     rsi, [rcx+10h]
0x1800033e4  test    rsi, rsi
0x1800033e7  jz      short loc_180003421
0x1800033e9  call    cs:__imp_GetLastError
0x1800033ef  xor     r9d, r9d; msWindowLength
0x1800033f2  xor     r8d, r8d; msPeriod
0x1800033f5  xor     edx, edx; pftDueTime
0x1800033f7  mov     rcx, rsi; pti
0x1800033fa  mov     ebx, eax
0x1800033fc  call    cs:__imp_SetThreadpoolTimer
0x180003402  mov     edx, 1; fCancelPendingCallbacks
0x180003407  mov     rcx, rsi; pti
0x18000340a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003410  mov     rcx, rsi; pti
0x180003413  call    cs:__imp_CloseThreadpoolTimer
0x180003419  mov     ecx, ebx; dwErrCode
0x18000341b  call    cs:__imp_SetLastError
0x180003421  mov     rcx, rdi; this
0x180003424  mov     qword ptr [rdi+10h], 0
0x18000342c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003431  mov     rcx, [rdi+68h]
0x180003435  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000343c  test    rcx, rcx
0x18000343f  jz      short loc_180003461
0x180003441  test    rax, rax
0x180003444  jnz     short loc_180003455
0x180003446  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000344d  test    rdx, rdx
0x180003450  jz      short loc_180003468
0x180003452  mov     rax, rdx
0x180003455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003461  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003468  mov     rcx, [rdi+60h]
0x18000346c  test    rcx, rcx
0x18000346f  jz      short loc_180003483
0x180003471  test    rax, rax
0x180003474  jnz     short loc_18000347E
0x180003476  test    rdx, rdx
0x180003479  jz      short loc_180003483
0x18000347b  mov     rax, rdx
0x18000347e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003483  mov     rbx, [rdi+58h]
0x180003487  mov     qword ptr [rdi+58h], 0
0x18000348f  test    rbx, rbx
0x180003492  jz      short loc_1800034A8
0x180003494  call    cs:__imp_GetProcessHeap
0x18000349a  mov     r8, rbx; lpMem
0x18000349d  xor     edx, edx; dwFlags
0x18000349f  mov     rcx, rax; hHeap
0x1800034a2  call    cs:__imp_HeapFree
0x1800034a8  mov     rbx, [rdi+38h]
0x1800034ac  mov     qword ptr [rdi+38h], 0
0x1800034b4  test    rbx, rbx
0x1800034b7  jz      short loc_1800034CD
0x1800034b9  call    cs:__imp_GetProcessHeap
0x1800034bf  mov     r8, rbx; lpMem
0x1800034c2  xor     edx, edx; dwFlags
0x1800034c4  mov     rcx, rax; hHeap
0x1800034c7  call    cs:__imp_HeapFree
0x1800034cd  mov     rbx, [rdi+10h]
0x1800034d1  test    rbx, rbx
0x1800034d4  jz      short loc_1800034FE
0x1800034d6  xor     r9d, r9d; msWindowLength
0x1800034d9  xor     r8d, r8d; msPeriod
0x1800034dc  xor     edx, edx; pftDueTime
0x1800034de  mov     rcx, rbx; pti
0x1800034e1  call    cs:__imp_SetThreadpoolTimer
0x1800034e7  mov     edx, 1; fCancelPendingCallbacks
0x1800034ec  mov     rcx, rbx; pti
0x1800034ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800034f5  mov     rcx, rbx; pti
0x1800034f8  call    cs:__imp_CloseThreadpoolTimer
0x1800034fe  mov     rbx, [rsp+28h+arg_0]
0x180003503  mov     rsi, [rsp+28h+arg_8]
0x180003508  add     rsp, 20h
0x18000350c  pop     rdi
0x18000350d  retn
```
