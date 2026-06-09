# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180012234`
- end: `0x18001238c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004eb70`

## callees

- `0x180012234`
- `0x1800136e4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001231f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001231f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012344`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012255`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012287`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001227f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012375`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001227f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012375`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001236c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001236c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001235e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001235e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180012234  mov     [rsp+arg_0], rbx
0x180012239  mov     [rsp+arg_8], rsi
0x18001223e  push    rdi
0x18001223f  sub     rsp, 20h
0x180012243  mov     rdi, rcx
0x180012246  mov     dword ptr [rcx], 0
0x18001224c  mov     rsi, [rcx+10h]
0x180012250  test    rsi, rsi
0x180012253  jz      short loc_18001228D
0x180012255  call    cs:__imp_GetLastError
0x18001225b  mov     ebx, eax
0x18001225d  xor     r9d, r9d; msWindowLength
0x180012260  xor     r8d, r8d; msPeriod
0x180012263  xor     edx, edx; pftDueTime
0x180012265  mov     rcx, rsi; pti
0x180012268  call    cs:__imp_SetThreadpoolTimer
0x18001226e  mov     edx, 1; fCancelPendingCallbacks
0x180012273  mov     rcx, rsi; pti
0x180012276  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001227c  mov     rcx, rsi; pti
0x18001227f  call    cs:__imp_CloseThreadpoolTimer
0x180012285  mov     ecx, ebx; dwErrCode
0x180012287  call    cs:__imp_SetLastError
0x18001228d  mov     qword ptr [rdi+10h], 0
0x180012295  mov     rcx, rdi; this
0x180012298  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001229d  mov     rcx, [rdi+68h]
0x1800122a1  test    rcx, rcx
0x1800122a4  jz      short loc_1800122D6
0x1800122a6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800122ad  test    rax, rax
0x1800122b0  jnz     short loc_1800122C1
0x1800122b2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800122b9  test    rdx, rdx
0x1800122bc  jz      short loc_1800122D4
0x1800122be  mov     rax, rdx
0x1800122c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800122cd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800122d4  jmp     short loc_1800122E4
0x1800122d6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800122dd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800122e4  mov     rcx, [rdi+60h]
0x1800122e8  test    rcx, rcx
0x1800122eb  jz      short loc_180012300
0x1800122ed  test    rax, rax
0x1800122f0  jnz     short loc_1800122FA
0x1800122f2  test    rdx, rdx
0x1800122f5  jz      short loc_180012300
0x1800122f7  mov     rax, rdx
0x1800122fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ff  nop
0x180012300  mov     rbx, [rdi+58h]
0x180012304  mov     qword ptr [rdi+58h], 0
0x18001230c  test    rbx, rbx
0x18001230f  jz      short loc_180012325
0x180012311  call    cs:__imp_GetProcessHeap
0x180012317  mov     rcx, rax; hHeap
0x18001231a  mov     r8, rbx; lpMem
0x18001231d  xor     edx, edx; dwFlags
0x18001231f  call    cs:__imp_HeapFree
0x180012325  mov     rbx, [rdi+38h]
0x180012329  mov     qword ptr [rdi+38h], 0
0x180012331  test    rbx, rbx
0x180012334  jz      short loc_18001234A
0x180012336  call    cs:__imp_GetProcessHeap
0x18001233c  mov     rcx, rax; hHeap
0x18001233f  mov     r8, rbx; lpMem
0x180012342  xor     edx, edx; dwFlags
0x180012344  call    cs:__imp_HeapFree
0x18001234a  mov     rbx, [rdi+10h]
0x18001234e  test    rbx, rbx
0x180012351  jz      short loc_18001237C
0x180012353  xor     r9d, r9d; msWindowLength
0x180012356  xor     r8d, r8d; msPeriod
0x180012359  xor     edx, edx; pftDueTime
0x18001235b  mov     rcx, rbx; pti
0x18001235e  call    cs:__imp_SetThreadpoolTimer
0x180012364  mov     edx, 1; fCancelPendingCallbacks
0x180012369  mov     rcx, rbx; pti
0x18001236c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012372  mov     rcx, rbx; pti
0x180012375  call    cs:__imp_CloseThreadpoolTimer
0x18001237b  nop
0x18001237c  mov     rbx, [rsp+28h+arg_0]
0x180012381  mov     rsi, [rsp+28h+arg_8]
0x180012386  add     rsp, 20h
0x18001238a  pop     rdi
0x18001238b  retn
```
