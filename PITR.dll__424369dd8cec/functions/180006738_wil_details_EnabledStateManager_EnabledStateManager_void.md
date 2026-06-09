# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006738`
- end: `0x180006890`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180052770`

## callees

- `0x180006738`
- `0x1800124c8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000683a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000683a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006848`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000678b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000678b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006759`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000677a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006870`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000677a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006879`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006879`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000676c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006862`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000676c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006862`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=2
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
0x180006738  mov     [rsp+arg_0], rbx
0x18000673d  mov     [rsp+arg_8], rsi
0x180006742  push    rdi
0x180006743  sub     rsp, 20h
0x180006747  mov     rdi, rcx
0x18000674a  mov     dword ptr [rcx], 0
0x180006750  mov     rsi, [rcx+10h]
0x180006754  test    rsi, rsi
0x180006757  jz      short loc_180006791
0x180006759  call    cs:__imp_GetLastError
0x18000675f  mov     ebx, eax
0x180006761  xor     r9d, r9d; msWindowLength
0x180006764  xor     r8d, r8d; msPeriod
0x180006767  xor     edx, edx; pftDueTime
0x180006769  mov     rcx, rsi; pti
0x18000676c  call    cs:__imp_SetThreadpoolTimer
0x180006772  mov     edx, 1; fCancelPendingCallbacks
0x180006777  mov     rcx, rsi; pti
0x18000677a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006780  mov     rcx, rsi; pti
0x180006783  call    cs:__imp_CloseThreadpoolTimer
0x180006789  mov     ecx, ebx; dwErrCode
0x18000678b  call    cs:__imp_SetLastError
0x180006791  mov     qword ptr [rdi+10h], 0
0x180006799  mov     rcx, rdi; this
0x18000679c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800067a1  mov     rcx, [rdi+68h]
0x1800067a5  test    rcx, rcx
0x1800067a8  jz      short loc_1800067DA
0x1800067aa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067b1  test    rax, rax
0x1800067b4  jnz     short loc_1800067C5
0x1800067b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067bd  test    rdx, rdx
0x1800067c0  jz      short loc_1800067D8
0x1800067c2  mov     rax, rdx
0x1800067c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ca  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067d1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067d8  jmp     short loc_1800067E8
0x1800067da  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067e1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067e8  mov     rcx, [rdi+60h]
0x1800067ec  test    rcx, rcx
0x1800067ef  jz      short loc_180006804
0x1800067f1  test    rax, rax
0x1800067f4  jnz     short loc_1800067FE
0x1800067f6  test    rdx, rdx
0x1800067f9  jz      short loc_180006804
0x1800067fb  mov     rax, rdx
0x1800067fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006803  nop
0x180006804  mov     rbx, [rdi+58h]
0x180006808  mov     qword ptr [rdi+58h], 0
0x180006810  test    rbx, rbx
0x180006813  jz      short loc_180006829
0x180006815  call    cs:__imp_GetProcessHeap
0x18000681b  mov     rcx, rax; hHeap
0x18000681e  mov     r8, rbx; lpMem
0x180006821  xor     edx, edx; dwFlags
0x180006823  call    cs:__imp_HeapFree
0x180006829  mov     rbx, [rdi+38h]
0x18000682d  mov     qword ptr [rdi+38h], 0
0x180006835  test    rbx, rbx
0x180006838  jz      short loc_18000684E
0x18000683a  call    cs:__imp_GetProcessHeap
0x180006840  mov     rcx, rax; hHeap
0x180006843  mov     r8, rbx; lpMem
0x180006846  xor     edx, edx; dwFlags
0x180006848  call    cs:__imp_HeapFree
0x18000684e  mov     rbx, [rdi+10h]
0x180006852  test    rbx, rbx
0x180006855  jz      short loc_180006880
0x180006857  xor     r9d, r9d; msWindowLength
0x18000685a  xor     r8d, r8d; msPeriod
0x18000685d  xor     edx, edx; pftDueTime
0x18000685f  mov     rcx, rbx; pti
0x180006862  call    cs:__imp_SetThreadpoolTimer
0x180006868  mov     edx, 1; fCancelPendingCallbacks
0x18000686d  mov     rcx, rbx; pti
0x180006870  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006876  mov     rcx, rbx; pti
0x180006879  call    cs:__imp_CloseThreadpoolTimer
0x18000687f  nop
0x180006880  mov     rbx, [rsp+28h+arg_0]
0x180006885  mov     rsi, [rsp+28h+arg_8]
0x18000688a  add     rsp, 20h
0x18000688e  pop     rdi
0x18000688f  retn
```
