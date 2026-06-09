# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009314`
- end: `0x18000946c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180057db0`

## callees

- `0x180009314`
- `0x18000e840`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009424`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009416`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009335`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009367`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009348`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000943e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009348`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000943e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000935f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009455`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000935f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009455`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009356`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000944c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009356`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000944c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180009314  mov     [rsp+arg_0], rbx
0x180009319  mov     [rsp+arg_8], rsi
0x18000931e  push    rdi
0x18000931f  sub     rsp, 20h
0x180009323  mov     rdi, rcx
0x180009326  mov     dword ptr [rcx], 0
0x18000932c  mov     rsi, [rcx+10h]
0x180009330  test    rsi, rsi
0x180009333  jz      short loc_18000936D
0x180009335  call    cs:__imp_GetLastError
0x18000933b  mov     ebx, eax
0x18000933d  xor     r9d, r9d; msWindowLength
0x180009340  xor     r8d, r8d; msPeriod
0x180009343  xor     edx, edx; pftDueTime
0x180009345  mov     rcx, rsi; pti
0x180009348  call    cs:__imp_SetThreadpoolTimer
0x18000934e  mov     edx, 1; fCancelPendingCallbacks
0x180009353  mov     rcx, rsi; pti
0x180009356  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000935c  mov     rcx, rsi; pti
0x18000935f  call    cs:__imp_CloseThreadpoolTimer
0x180009365  mov     ecx, ebx; dwErrCode
0x180009367  call    cs:__imp_SetLastError
0x18000936d  mov     qword ptr [rdi+10h], 0
0x180009375  mov     rcx, rdi; this
0x180009378  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000937d  mov     rcx, [rdi+68h]
0x180009381  test    rcx, rcx
0x180009384  jz      short loc_1800093B6
0x180009386  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000938d  test    rax, rax
0x180009390  jnz     short loc_1800093A1
0x180009392  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009399  test    rdx, rdx
0x18000939c  jz      short loc_1800093B4
0x18000939e  mov     rax, rdx
0x1800093a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800093ad  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800093b4  jmp     short loc_1800093C4
0x1800093b6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800093bd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800093c4  mov     rcx, [rdi+60h]
0x1800093c8  test    rcx, rcx
0x1800093cb  jz      short loc_1800093E0
0x1800093cd  test    rax, rax
0x1800093d0  jnz     short loc_1800093DA
0x1800093d2  test    rdx, rdx
0x1800093d5  jz      short loc_1800093E0
0x1800093d7  mov     rax, rdx
0x1800093da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093df  nop
0x1800093e0  mov     rbx, [rdi+58h]
0x1800093e4  mov     qword ptr [rdi+58h], 0
0x1800093ec  test    rbx, rbx
0x1800093ef  jz      short loc_180009405
0x1800093f1  call    cs:__imp_GetProcessHeap
0x1800093f7  mov     rcx, rax; hHeap
0x1800093fa  mov     r8, rbx; lpMem
0x1800093fd  xor     edx, edx; dwFlags
0x1800093ff  call    cs:__imp_HeapFree
0x180009405  mov     rbx, [rdi+38h]
0x180009409  mov     qword ptr [rdi+38h], 0
0x180009411  test    rbx, rbx
0x180009414  jz      short loc_18000942A
0x180009416  call    cs:__imp_GetProcessHeap
0x18000941c  mov     rcx, rax; hHeap
0x18000941f  mov     r8, rbx; lpMem
0x180009422  xor     edx, edx; dwFlags
0x180009424  call    cs:__imp_HeapFree
0x18000942a  mov     rbx, [rdi+10h]
0x18000942e  test    rbx, rbx
0x180009431  jz      short loc_18000945C
0x180009433  xor     r9d, r9d; msWindowLength
0x180009436  xor     r8d, r8d; msPeriod
0x180009439  xor     edx, edx; pftDueTime
0x18000943b  mov     rcx, rbx; pti
0x18000943e  call    cs:__imp_SetThreadpoolTimer
0x180009444  mov     edx, 1; fCancelPendingCallbacks
0x180009449  mov     rcx, rbx; pti
0x18000944c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009452  mov     rcx, rbx; pti
0x180009455  call    cs:__imp_CloseThreadpoolTimer
0x18000945b  nop
0x18000945c  mov     rbx, [rsp+28h+arg_0]
0x180009461  mov     rsi, [rsp+28h+arg_8]
0x180009466  add     rsp, 20h
0x18000946a  pop     rdi
0x18000946b  retn
```
