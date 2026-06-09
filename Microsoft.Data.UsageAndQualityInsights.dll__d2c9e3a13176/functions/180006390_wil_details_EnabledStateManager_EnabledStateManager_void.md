# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006390`
- end: `0x1800064e8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801076d0`

## callees

- `0x180006390`
- `0x1800090fc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000647b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000647b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000646d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006492`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000646d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800063db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800064d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800063db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800064d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800063d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800064c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800063d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800064c8`

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
0x180006390  mov     [rsp+arg_0], rbx
0x180006395  mov     [rsp+arg_8], rsi
0x18000639a  push    rdi
0x18000639b  sub     rsp, 20h
0x18000639f  mov     rdi, rcx
0x1800063a2  mov     dword ptr [rcx], 0
0x1800063a8  mov     rsi, [rcx+10h]
0x1800063ac  test    rsi, rsi
0x1800063af  jz      short loc_1800063E9
0x1800063b1  call    cs:__imp_GetLastError
0x1800063b7  mov     ebx, eax
0x1800063b9  xor     r9d, r9d; msWindowLength
0x1800063bc  xor     r8d, r8d; msPeriod
0x1800063bf  xor     edx, edx; pftDueTime
0x1800063c1  mov     rcx, rsi; pti
0x1800063c4  call    cs:__imp_SetThreadpoolTimer
0x1800063ca  mov     edx, 1; fCancelPendingCallbacks
0x1800063cf  mov     rcx, rsi; pti
0x1800063d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800063d8  mov     rcx, rsi; pti
0x1800063db  call    cs:__imp_CloseThreadpoolTimer
0x1800063e1  mov     ecx, ebx; dwErrCode
0x1800063e3  call    cs:__imp_SetLastError
0x1800063e9  mov     qword ptr [rdi+10h], 0
0x1800063f1  mov     rcx, rdi; this
0x1800063f4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800063f9  mov     rcx, [rdi+68h]
0x1800063fd  test    rcx, rcx
0x180006400  jz      short loc_180006432
0x180006402  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006409  test    rax, rax
0x18000640c  jnz     short loc_18000641D
0x18000640e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006415  test    rdx, rdx
0x180006418  jz      short loc_180006430
0x18000641a  mov     rax, rdx
0x18000641d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006422  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006429  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006430  jmp     short loc_180006440
0x180006432  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006439  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006440  mov     rcx, [rdi+60h]
0x180006444  test    rcx, rcx
0x180006447  jz      short loc_18000645C
0x180006449  test    rax, rax
0x18000644c  jnz     short loc_180006456
0x18000644e  test    rdx, rdx
0x180006451  jz      short loc_18000645C
0x180006453  mov     rax, rdx
0x180006456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645b  nop
0x18000645c  mov     rbx, [rdi+58h]
0x180006460  mov     qword ptr [rdi+58h], 0
0x180006468  test    rbx, rbx
0x18000646b  jz      short loc_180006481
0x18000646d  call    cs:__imp_GetProcessHeap
0x180006473  mov     rcx, rax; hHeap
0x180006476  mov     r8, rbx; lpMem
0x180006479  xor     edx, edx; dwFlags
0x18000647b  call    cs:__imp_HeapFree
0x180006481  mov     rbx, [rdi+38h]
0x180006485  mov     qword ptr [rdi+38h], 0
0x18000648d  test    rbx, rbx
0x180006490  jz      short loc_1800064A6
0x180006492  call    cs:__imp_GetProcessHeap
0x180006498  mov     rcx, rax; hHeap
0x18000649b  mov     r8, rbx; lpMem
0x18000649e  xor     edx, edx; dwFlags
0x1800064a0  call    cs:__imp_HeapFree
0x1800064a6  mov     rbx, [rdi+10h]
0x1800064aa  test    rbx, rbx
0x1800064ad  jz      short loc_1800064D8
0x1800064af  xor     r9d, r9d; msWindowLength
0x1800064b2  xor     r8d, r8d; msPeriod
0x1800064b5  xor     edx, edx; pftDueTime
0x1800064b7  mov     rcx, rbx; pti
0x1800064ba  call    cs:__imp_SetThreadpoolTimer
0x1800064c0  mov     edx, 1; fCancelPendingCallbacks
0x1800064c5  mov     rcx, rbx; pti
0x1800064c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800064ce  mov     rcx, rbx; pti
0x1800064d1  call    cs:__imp_CloseThreadpoolTimer
0x1800064d7  nop
0x1800064d8  mov     rbx, [rsp+28h+arg_0]
0x1800064dd  mov     rsi, [rsp+28h+arg_8]
0x1800064e2  add     rsp, 20h
0x1800064e6  pop     rdi
0x1800064e7  retn
```
