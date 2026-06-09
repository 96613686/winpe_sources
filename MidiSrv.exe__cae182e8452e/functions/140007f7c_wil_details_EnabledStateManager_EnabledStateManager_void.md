# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140007f7c`
- end: `0x1400080d4`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140059270`

## callees

- `0x140007f7c`
- `0x140009b30`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000808c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000808c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000807e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000807e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007fcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007fc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400080bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007fc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400080bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007fb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400080a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007fb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400080a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007fbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400080b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007fbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400080b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x140007f7c  mov     [rsp+arg_0], rbx
0x140007f81  mov     [rsp+arg_8], rsi
0x140007f86  push    rdi
0x140007f87  sub     rsp, 20h
0x140007f8b  mov     rdi, rcx
0x140007f8e  mov     dword ptr [rcx], 0
0x140007f94  mov     rsi, [rcx+10h]
0x140007f98  test    rsi, rsi
0x140007f9b  jz      short loc_140007FD5
0x140007f9d  call    cs:__imp_GetLastError
0x140007fa3  mov     ebx, eax
0x140007fa5  xor     r9d, r9d; msWindowLength
0x140007fa8  xor     r8d, r8d; msPeriod
0x140007fab  xor     edx, edx; pftDueTime
0x140007fad  mov     rcx, rsi; pti
0x140007fb0  call    cs:__imp_SetThreadpoolTimer
0x140007fb6  mov     edx, 1; fCancelPendingCallbacks
0x140007fbb  mov     rcx, rsi; pti
0x140007fbe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007fc4  mov     rcx, rsi; pti
0x140007fc7  call    cs:__imp_CloseThreadpoolTimer
0x140007fcd  mov     ecx, ebx; dwErrCode
0x140007fcf  call    cs:__imp_SetLastError
0x140007fd5  mov     qword ptr [rdi+10h], 0
0x140007fdd  mov     rcx, rdi; this
0x140007fe0  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140007fe5  mov     rcx, [rdi+68h]
0x140007fe9  test    rcx, rcx
0x140007fec  jz      short loc_14000801E
0x140007fee  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140007ff5  test    rax, rax
0x140007ff8  jnz     short loc_140008009
0x140007ffa  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008001  test    rdx, rdx
0x140008004  jz      short loc_14000801C
0x140008006  mov     rax, rdx
0x140008009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000800e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008015  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000801c  jmp     short loc_14000802C
0x14000801e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140008025  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000802c  mov     rcx, [rdi+60h]
0x140008030  test    rcx, rcx
0x140008033  jz      short loc_140008048
0x140008035  test    rax, rax
0x140008038  jnz     short loc_140008042
0x14000803a  test    rdx, rdx
0x14000803d  jz      short loc_140008048
0x14000803f  mov     rax, rdx
0x140008042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008047  nop
0x140008048  mov     rbx, [rdi+58h]
0x14000804c  mov     qword ptr [rdi+58h], 0
0x140008054  test    rbx, rbx
0x140008057  jz      short loc_14000806D
0x140008059  call    cs:__imp_GetProcessHeap
0x14000805f  mov     rcx, rax; hHeap
0x140008062  mov     r8, rbx; lpMem
0x140008065  xor     edx, edx; dwFlags
0x140008067  call    cs:__imp_HeapFree
0x14000806d  mov     rbx, [rdi+38h]
0x140008071  mov     qword ptr [rdi+38h], 0
0x140008079  test    rbx, rbx
0x14000807c  jz      short loc_140008092
0x14000807e  call    cs:__imp_GetProcessHeap
0x140008084  mov     rcx, rax; hHeap
0x140008087  mov     r8, rbx; lpMem
0x14000808a  xor     edx, edx; dwFlags
0x14000808c  call    cs:__imp_HeapFree
0x140008092  mov     rbx, [rdi+10h]
0x140008096  test    rbx, rbx
0x140008099  jz      short loc_1400080C4
0x14000809b  xor     r9d, r9d; msWindowLength
0x14000809e  xor     r8d, r8d; msPeriod
0x1400080a1  xor     edx, edx; pftDueTime
0x1400080a3  mov     rcx, rbx; pti
0x1400080a6  call    cs:__imp_SetThreadpoolTimer
0x1400080ac  mov     edx, 1; fCancelPendingCallbacks
0x1400080b1  mov     rcx, rbx; pti
0x1400080b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400080ba  mov     rcx, rbx; pti
0x1400080bd  call    cs:__imp_CloseThreadpoolTimer
0x1400080c3  nop
0x1400080c4  mov     rbx, [rsp+28h+arg_0]
0x1400080c9  mov     rsi, [rsp+28h+arg_8]
0x1400080ce  add     rsp, 20h
0x1400080d2  pop     rdi
0x1400080d3  retn
```
