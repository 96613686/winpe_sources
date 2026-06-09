# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009934`
- end: `0x180009a8c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029120`

## callees

- `0x180009934`
- `0x18000cb64`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009955`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009968`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009968`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a5e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000997f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009a75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000997f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009a75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009976`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009a6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009976`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009a6c`

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
0x180009934  mov     [rsp+arg_0], rbx
0x180009939  mov     [rsp+arg_8], rsi
0x18000993e  push    rdi
0x18000993f  sub     rsp, 20h
0x180009943  mov     rdi, rcx
0x180009946  mov     dword ptr [rcx], 0
0x18000994c  mov     rsi, [rcx+10h]
0x180009950  test    rsi, rsi
0x180009953  jz      short loc_18000998D
0x180009955  call    cs:__imp_GetLastError
0x18000995b  mov     ebx, eax
0x18000995d  xor     r9d, r9d; msWindowLength
0x180009960  xor     r8d, r8d; msPeriod
0x180009963  xor     edx, edx; pftDueTime
0x180009965  mov     rcx, rsi; pti
0x180009968  call    cs:__imp_SetThreadpoolTimer
0x18000996e  mov     edx, 1; fCancelPendingCallbacks
0x180009973  mov     rcx, rsi; pti
0x180009976  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000997c  mov     rcx, rsi; pti
0x18000997f  call    cs:__imp_CloseThreadpoolTimer
0x180009985  mov     ecx, ebx; dwErrCode
0x180009987  call    cs:__imp_SetLastError
0x18000998d  mov     qword ptr [rdi+10h], 0
0x180009995  mov     rcx, rdi; this
0x180009998  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000999d  mov     rcx, [rdi+68h]
0x1800099a1  test    rcx, rcx
0x1800099a4  jz      short loc_1800099D6
0x1800099a6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800099ad  test    rax, rax
0x1800099b0  jnz     short loc_1800099C1
0x1800099b2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800099b9  test    rdx, rdx
0x1800099bc  jz      short loc_1800099D4
0x1800099be  mov     rax, rdx
0x1800099c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800099cd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800099d4  jmp     short loc_1800099E4
0x1800099d6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800099dd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800099e4  mov     rcx, [rdi+60h]
0x1800099e8  test    rcx, rcx
0x1800099eb  jz      short loc_180009A00
0x1800099ed  test    rax, rax
0x1800099f0  jnz     short loc_1800099FA
0x1800099f2  test    rdx, rdx
0x1800099f5  jz      short loc_180009A00
0x1800099f7  mov     rax, rdx
0x1800099fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ff  nop
0x180009a00  mov     rbx, [rdi+58h]
0x180009a04  mov     qword ptr [rdi+58h], 0
0x180009a0c  test    rbx, rbx
0x180009a0f  jz      short loc_180009A25
0x180009a11  call    cs:__imp_GetProcessHeap
0x180009a17  mov     rcx, rax; hHeap
0x180009a1a  mov     r8, rbx; lpMem
0x180009a1d  xor     edx, edx; dwFlags
0x180009a1f  call    cs:__imp_HeapFree
0x180009a25  mov     rbx, [rdi+38h]
0x180009a29  mov     qword ptr [rdi+38h], 0
0x180009a31  test    rbx, rbx
0x180009a34  jz      short loc_180009A4A
0x180009a36  call    cs:__imp_GetProcessHeap
0x180009a3c  mov     rcx, rax; hHeap
0x180009a3f  mov     r8, rbx; lpMem
0x180009a42  xor     edx, edx; dwFlags
0x180009a44  call    cs:__imp_HeapFree
0x180009a4a  mov     rbx, [rdi+10h]
0x180009a4e  test    rbx, rbx
0x180009a51  jz      short loc_180009A7C
0x180009a53  xor     r9d, r9d; msWindowLength
0x180009a56  xor     r8d, r8d; msPeriod
0x180009a59  xor     edx, edx; pftDueTime
0x180009a5b  mov     rcx, rbx; pti
0x180009a5e  call    cs:__imp_SetThreadpoolTimer
0x180009a64  mov     edx, 1; fCancelPendingCallbacks
0x180009a69  mov     rcx, rbx; pti
0x180009a6c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009a72  mov     rcx, rbx; pti
0x180009a75  call    cs:__imp_CloseThreadpoolTimer
0x180009a7b  nop
0x180009a7c  mov     rbx, [rsp+28h+arg_0]
0x180009a81  mov     rsi, [rsp+28h+arg_8]
0x180009a86  add     rsp, 20h
0x180009a8a  pop     rdi
0x180009a8b  retn
```
