# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180004660`
- end: `0x1800047c2`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `354`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017c10`

## callees

- `0x180004660`
- `0x1800071a4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000477a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000477a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000468b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000468b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000469e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004794`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000469e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004794`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800046b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800046b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800046ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800046ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047a2`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  __int64 v4; // rcx
  void (__fastcall *v5)(__int64); // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  struct _TP_TIMER *v12; // rbx

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
  v4 = *((_QWORD *)this + 13);
  if ( !v4 )
  {
    v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v5 = (void (__fastcall *)(__int64))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v5(v4);
  v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  v7 = *((_QWORD *)this + 12);
  if ( !v7 )
    goto LABEL_15;
  if ( !v5 )
  {
    if ( !v6 )
      goto LABEL_15;
    v5 = (void (__fastcall *)(__int64))v6;
  }
  v5(v7);
LABEL_15:
  v8 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  v10 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
}

```

## disassembly

```asm
0x180004660  push    rdi
0x180004662  sub     rsp, 30h
0x180004666  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000466f  mov     [rsp+38h+arg_0], rbx
0x180004674  mov     [rsp+38h+arg_8], rsi
0x180004679  mov     rdi, rcx
0x18000467c  mov     dword ptr [rcx], 0
0x180004682  mov     rsi, [rcx+10h]
0x180004686  test    rsi, rsi
0x180004689  jz      short loc_1800046C3
0x18000468b  call    cs:__imp_GetLastError
0x180004691  mov     ebx, eax
0x180004693  xor     r9d, r9d; msWindowLength
0x180004696  xor     r8d, r8d; msPeriod
0x180004699  xor     edx, edx; pftDueTime
0x18000469b  mov     rcx, rsi; pti
0x18000469e  call    cs:__imp_SetThreadpoolTimer
0x1800046a4  mov     edx, 1; fCancelPendingCallbacks
0x1800046a9  mov     rcx, rsi; pti
0x1800046ac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800046b2  mov     rcx, rsi; pti
0x1800046b5  call    cs:__imp_CloseThreadpoolTimer
0x1800046bb  mov     ecx, ebx; dwErrCode
0x1800046bd  call    cs:__imp_SetLastError
0x1800046c3  mov     qword ptr [rdi+10h], 0
0x1800046cb  mov     rcx, rdi; this
0x1800046ce  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800046d3  mov     rcx, [rdi+68h]
0x1800046d7  test    rcx, rcx
0x1800046da  jz      short loc_18000470C
0x1800046dc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800046e3  test    rax, rax
0x1800046e6  jnz     short loc_1800046F7
0x1800046e8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800046ef  test    rdx, rdx
0x1800046f2  jz      short loc_18000470A
0x1800046f4  mov     rax, rdx
0x1800046f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004703  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000470a  jmp     short loc_18000471A
0x18000470c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004713  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000471a  mov     rcx, [rdi+60h]
0x18000471e  test    rcx, rcx
0x180004721  jz      short loc_180004736
0x180004723  test    rax, rax
0x180004726  jnz     short loc_180004730
0x180004728  test    rdx, rdx
0x18000472b  jz      short loc_180004736
0x18000472d  mov     rax, rdx
0x180004730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004735  nop
0x180004736  mov     rbx, [rdi+58h]
0x18000473a  mov     qword ptr [rdi+58h], 0
0x180004742  test    rbx, rbx
0x180004745  jz      short loc_18000475B
0x180004747  call    cs:__imp_GetProcessHeap
0x18000474d  mov     rcx, rax; hHeap
0x180004750  mov     r8, rbx; lpMem
0x180004753  xor     edx, edx; dwFlags
0x180004755  call    cs:__imp_HeapFree
0x18000475b  mov     rbx, [rdi+38h]
0x18000475f  mov     qword ptr [rdi+38h], 0
0x180004767  test    rbx, rbx
0x18000476a  jz      short loc_180004780
0x18000476c  call    cs:__imp_GetProcessHeap
0x180004772  mov     rcx, rax; hHeap
0x180004775  mov     r8, rbx; lpMem
0x180004778  xor     edx, edx; dwFlags
0x18000477a  call    cs:__imp_HeapFree
0x180004780  mov     rbx, [rdi+10h]
0x180004784  test    rbx, rbx
0x180004787  jz      short loc_1800047B2
0x180004789  xor     r9d, r9d; msWindowLength
0x18000478c  xor     r8d, r8d; msPeriod
0x18000478f  xor     edx, edx; pftDueTime
0x180004791  mov     rcx, rbx; pti
0x180004794  call    cs:__imp_SetThreadpoolTimer
0x18000479a  mov     edx, 1; fCancelPendingCallbacks
0x18000479f  mov     rcx, rbx; pti
0x1800047a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800047a8  mov     rcx, rbx; pti
0x1800047ab  call    cs:__imp_CloseThreadpoolTimer
0x1800047b1  nop
0x1800047b2  mov     rbx, [rsp+38h+arg_0]
0x1800047b7  mov     rsi, [rsp+38h+arg_8]
0x1800047bc  add     rsp, 30h
0x1800047c0  pop     rdi
0x1800047c1  retn
```
