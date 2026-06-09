# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180008024`
- end: `0x18000817c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009c0a0`

## callees

- `0x180008024`
- `0x18000b09c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008101`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008126`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008101`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008126`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000810f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008134`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000810f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008077`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008077`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008066`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000815c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008066`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000815c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008058`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000814e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008058`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000814e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000806f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008165`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000806f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008165`

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
0x180008024  mov     [rsp+arg_0], rbx
0x180008029  mov     [rsp+arg_8], rsi
0x18000802e  push    rdi
0x18000802f  sub     rsp, 20h
0x180008033  mov     rdi, rcx
0x180008036  mov     dword ptr [rcx], 0
0x18000803c  mov     rsi, [rcx+10h]
0x180008040  test    rsi, rsi
0x180008043  jz      short loc_18000807D
0x180008045  call    cs:__imp_GetLastError
0x18000804b  mov     ebx, eax
0x18000804d  xor     r9d, r9d; msWindowLength
0x180008050  xor     r8d, r8d; msPeriod
0x180008053  xor     edx, edx; pftDueTime
0x180008055  mov     rcx, rsi; pti
0x180008058  call    cs:__imp_SetThreadpoolTimer
0x18000805e  mov     edx, 1; fCancelPendingCallbacks
0x180008063  mov     rcx, rsi; pti
0x180008066  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000806c  mov     rcx, rsi; pti
0x18000806f  call    cs:__imp_CloseThreadpoolTimer
0x180008075  mov     ecx, ebx; dwErrCode
0x180008077  call    cs:__imp_SetLastError
0x18000807d  mov     qword ptr [rdi+10h], 0
0x180008085  mov     rcx, rdi; this
0x180008088  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000808d  mov     rcx, [rdi+68h]
0x180008091  test    rcx, rcx
0x180008094  jz      short loc_1800080C6
0x180008096  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000809d  test    rax, rax
0x1800080a0  jnz     short loc_1800080B1
0x1800080a2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800080a9  test    rdx, rdx
0x1800080ac  jz      short loc_1800080C4
0x1800080ae  mov     rax, rdx
0x1800080b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800080bd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800080c4  jmp     short loc_1800080D4
0x1800080c6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800080cd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800080d4  mov     rcx, [rdi+60h]
0x1800080d8  test    rcx, rcx
0x1800080db  jz      short loc_1800080F0
0x1800080dd  test    rax, rax
0x1800080e0  jnz     short loc_1800080EA
0x1800080e2  test    rdx, rdx
0x1800080e5  jz      short loc_1800080F0
0x1800080e7  mov     rax, rdx
0x1800080ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ef  nop
0x1800080f0  mov     rbx, [rdi+58h]
0x1800080f4  mov     qword ptr [rdi+58h], 0
0x1800080fc  test    rbx, rbx
0x1800080ff  jz      short loc_180008115
0x180008101  call    cs:__imp_GetProcessHeap
0x180008107  mov     rcx, rax; hHeap
0x18000810a  mov     r8, rbx; lpMem
0x18000810d  xor     edx, edx; dwFlags
0x18000810f  call    cs:__imp_HeapFree
0x180008115  mov     rbx, [rdi+38h]
0x180008119  mov     qword ptr [rdi+38h], 0
0x180008121  test    rbx, rbx
0x180008124  jz      short loc_18000813A
0x180008126  call    cs:__imp_GetProcessHeap
0x18000812c  mov     rcx, rax; hHeap
0x18000812f  mov     r8, rbx; lpMem
0x180008132  xor     edx, edx; dwFlags
0x180008134  call    cs:__imp_HeapFree
0x18000813a  mov     rbx, [rdi+10h]
0x18000813e  test    rbx, rbx
0x180008141  jz      short loc_18000816C
0x180008143  xor     r9d, r9d; msWindowLength
0x180008146  xor     r8d, r8d; msPeriod
0x180008149  xor     edx, edx; pftDueTime
0x18000814b  mov     rcx, rbx; pti
0x18000814e  call    cs:__imp_SetThreadpoolTimer
0x180008154  mov     edx, 1; fCancelPendingCallbacks
0x180008159  mov     rcx, rbx; pti
0x18000815c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008162  mov     rcx, rbx; pti
0x180008165  call    cs:__imp_CloseThreadpoolTimer
0x18000816b  nop
0x18000816c  mov     rbx, [rsp+28h+arg_0]
0x180008171  mov     rsi, [rsp+28h+arg_8]
0x180008176  add     rsp, 20h
0x18000817a  pop     rdi
0x18000817b  retn
```
