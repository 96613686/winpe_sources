# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000d5e8`
- end: `0x18000d740`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020db0`

## callees

- `0x18000d5e8`
- `0x180010e04`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d63b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d63b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d62a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d720`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d62a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d720`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d61c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d712`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d61c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d712`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d633`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d729`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d633`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d729`

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
0x18000d5e8  mov     [rsp+arg_0], rbx
0x18000d5ed  mov     [rsp+arg_8], rsi
0x18000d5f2  push    rdi
0x18000d5f3  sub     rsp, 20h
0x18000d5f7  mov     rdi, rcx
0x18000d5fa  mov     dword ptr [rcx], 0
0x18000d600  mov     rsi, [rcx+10h]
0x18000d604  test    rsi, rsi
0x18000d607  jz      short loc_18000D641
0x18000d609  call    cs:__imp_GetLastError
0x18000d60f  mov     ebx, eax
0x18000d611  xor     r9d, r9d; msWindowLength
0x18000d614  xor     r8d, r8d; msPeriod
0x18000d617  xor     edx, edx; pftDueTime
0x18000d619  mov     rcx, rsi; pti
0x18000d61c  call    cs:__imp_SetThreadpoolTimer
0x18000d622  mov     edx, 1; fCancelPendingCallbacks
0x18000d627  mov     rcx, rsi; pti
0x18000d62a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d630  mov     rcx, rsi; pti
0x18000d633  call    cs:__imp_CloseThreadpoolTimer
0x18000d639  mov     ecx, ebx; dwErrCode
0x18000d63b  call    cs:__imp_SetLastError
0x18000d641  mov     qword ptr [rdi+10h], 0
0x18000d649  mov     rcx, rdi; this
0x18000d64c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000d651  mov     rcx, [rdi+68h]
0x18000d655  test    rcx, rcx
0x18000d658  jz      short loc_18000D68A
0x18000d65a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d661  test    rax, rax
0x18000d664  jnz     short loc_18000D675
0x18000d666  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d66d  test    rdx, rdx
0x18000d670  jz      short loc_18000D688
0x18000d672  mov     rax, rdx
0x18000d675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d67a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d681  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d688  jmp     short loc_18000D698
0x18000d68a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d691  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d698  mov     rcx, [rdi+60h]
0x18000d69c  test    rcx, rcx
0x18000d69f  jz      short loc_18000D6B4
0x18000d6a1  test    rax, rax
0x18000d6a4  jnz     short loc_18000D6AE
0x18000d6a6  test    rdx, rdx
0x18000d6a9  jz      short loc_18000D6B4
0x18000d6ab  mov     rax, rdx
0x18000d6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b3  nop
0x18000d6b4  mov     rbx, [rdi+58h]
0x18000d6b8  mov     qword ptr [rdi+58h], 0
0x18000d6c0  test    rbx, rbx
0x18000d6c3  jz      short loc_18000D6D9
0x18000d6c5  call    cs:__imp_GetProcessHeap
0x18000d6cb  mov     rcx, rax; hHeap
0x18000d6ce  mov     r8, rbx; lpMem
0x18000d6d1  xor     edx, edx; dwFlags
0x18000d6d3  call    cs:__imp_HeapFree
0x18000d6d9  mov     rbx, [rdi+38h]
0x18000d6dd  mov     qword ptr [rdi+38h], 0
0x18000d6e5  test    rbx, rbx
0x18000d6e8  jz      short loc_18000D6FE
0x18000d6ea  call    cs:__imp_GetProcessHeap
0x18000d6f0  mov     rcx, rax; hHeap
0x18000d6f3  mov     r8, rbx; lpMem
0x18000d6f6  xor     edx, edx; dwFlags
0x18000d6f8  call    cs:__imp_HeapFree
0x18000d6fe  mov     rbx, [rdi+10h]
0x18000d702  test    rbx, rbx
0x18000d705  jz      short loc_18000D730
0x18000d707  xor     r9d, r9d; msWindowLength
0x18000d70a  xor     r8d, r8d; msPeriod
0x18000d70d  xor     edx, edx; pftDueTime
0x18000d70f  mov     rcx, rbx; pti
0x18000d712  call    cs:__imp_SetThreadpoolTimer
0x18000d718  mov     edx, 1; fCancelPendingCallbacks
0x18000d71d  mov     rcx, rbx; pti
0x18000d720  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d726  mov     rcx, rbx; pti
0x18000d729  call    cs:__imp_CloseThreadpoolTimer
0x18000d72f  nop
0x18000d730  mov     rbx, [rsp+28h+arg_0]
0x18000d735  mov     rsi, [rsp+28h+arg_8]
0x18000d73a  add     rsp, 20h
0x18000d73e  pop     rdi
0x18000d73f  retn
```
