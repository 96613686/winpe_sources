# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006234`
- end: `0x18000638c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180040760`

## callees

- `0x180006234`
- `0x18000940c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000631f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000631f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006344`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006336`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006255`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000635e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000635e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000627f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006375`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000627f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006375`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000636c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000636c`

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
0x180006234  mov     [rsp+arg_0], rbx
0x180006239  mov     [rsp+arg_8], rsi
0x18000623e  push    rdi
0x18000623f  sub     rsp, 20h
0x180006243  mov     rdi, rcx
0x180006246  mov     dword ptr [rcx], 0
0x18000624c  mov     rsi, [rcx+10h]
0x180006250  test    rsi, rsi
0x180006253  jz      short loc_18000628D
0x180006255  call    cs:__imp_GetLastError
0x18000625b  mov     ebx, eax
0x18000625d  xor     r9d, r9d; msWindowLength
0x180006260  xor     r8d, r8d; msPeriod
0x180006263  xor     edx, edx; pftDueTime
0x180006265  mov     rcx, rsi; pti
0x180006268  call    cs:__imp_SetThreadpoolTimer
0x18000626e  mov     edx, 1; fCancelPendingCallbacks
0x180006273  mov     rcx, rsi; pti
0x180006276  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000627c  mov     rcx, rsi; pti
0x18000627f  call    cs:__imp_CloseThreadpoolTimer
0x180006285  mov     ecx, ebx; dwErrCode
0x180006287  call    cs:__imp_SetLastError
0x18000628d  mov     qword ptr [rdi+10h], 0
0x180006295  mov     rcx, rdi; this
0x180006298  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000629d  mov     rcx, [rdi+68h]
0x1800062a1  test    rcx, rcx
0x1800062a4  jz      short loc_1800062D6
0x1800062a6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800062ad  test    rax, rax
0x1800062b0  jnz     short loc_1800062C1
0x1800062b2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800062b9  test    rdx, rdx
0x1800062bc  jz      short loc_1800062D4
0x1800062be  mov     rax, rdx
0x1800062c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800062cd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800062d4  jmp     short loc_1800062E4
0x1800062d6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800062dd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800062e4  mov     rcx, [rdi+60h]
0x1800062e8  test    rcx, rcx
0x1800062eb  jz      short loc_180006300
0x1800062ed  test    rax, rax
0x1800062f0  jnz     short loc_1800062FA
0x1800062f2  test    rdx, rdx
0x1800062f5  jz      short loc_180006300
0x1800062f7  mov     rax, rdx
0x1800062fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ff  nop
0x180006300  mov     rbx, [rdi+58h]
0x180006304  mov     qword ptr [rdi+58h], 0
0x18000630c  test    rbx, rbx
0x18000630f  jz      short loc_180006325
0x180006311  call    cs:__imp_GetProcessHeap
0x180006317  mov     rcx, rax; hHeap
0x18000631a  mov     r8, rbx; lpMem
0x18000631d  xor     edx, edx; dwFlags
0x18000631f  call    cs:__imp_HeapFree
0x180006325  mov     rbx, [rdi+38h]
0x180006329  mov     qword ptr [rdi+38h], 0
0x180006331  test    rbx, rbx
0x180006334  jz      short loc_18000634A
0x180006336  call    cs:__imp_GetProcessHeap
0x18000633c  mov     rcx, rax; hHeap
0x18000633f  mov     r8, rbx; lpMem
0x180006342  xor     edx, edx; dwFlags
0x180006344  call    cs:__imp_HeapFree
0x18000634a  mov     rbx, [rdi+10h]
0x18000634e  test    rbx, rbx
0x180006351  jz      short loc_18000637C
0x180006353  xor     r9d, r9d; msWindowLength
0x180006356  xor     r8d, r8d; msPeriod
0x180006359  xor     edx, edx; pftDueTime
0x18000635b  mov     rcx, rbx; pti
0x18000635e  call    cs:__imp_SetThreadpoolTimer
0x180006364  mov     edx, 1; fCancelPendingCallbacks
0x180006369  mov     rcx, rbx; pti
0x18000636c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006372  mov     rcx, rbx; pti
0x180006375  call    cs:__imp_CloseThreadpoolTimer
0x18000637b  nop
0x18000637c  mov     rbx, [rsp+28h+arg_0]
0x180006381  mov     rsi, [rsp+28h+arg_8]
0x180006386  add     rsp, 20h
0x18000638a  pop     rdi
0x18000638b  retn
```
