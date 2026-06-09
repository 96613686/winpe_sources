# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800031c8`
- end: `0x180003320`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cc50`

## callees

- `0x1800031c8`
- `0x1800070a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000321b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000321b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000320a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003300`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000320a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003300`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003213`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003309`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003213`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003309`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800031fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800031fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032f2`

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
0x1800031c8  mov     [rsp+arg_0], rbx
0x1800031cd  mov     [rsp+arg_8], rsi
0x1800031d2  push    rdi
0x1800031d3  sub     rsp, 20h
0x1800031d7  mov     rdi, rcx
0x1800031da  mov     dword ptr [rcx], 0
0x1800031e0  mov     rsi, [rcx+10h]
0x1800031e4  test    rsi, rsi
0x1800031e7  jz      short loc_180003221
0x1800031e9  call    cs:__imp_GetLastError
0x1800031ef  mov     ebx, eax
0x1800031f1  xor     r9d, r9d; msWindowLength
0x1800031f4  xor     r8d, r8d; msPeriod
0x1800031f7  xor     edx, edx; pftDueTime
0x1800031f9  mov     rcx, rsi; pti
0x1800031fc  call    cs:__imp_SetThreadpoolTimer
0x180003202  mov     edx, 1; fCancelPendingCallbacks
0x180003207  mov     rcx, rsi; pti
0x18000320a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003210  mov     rcx, rsi; pti
0x180003213  call    cs:__imp_CloseThreadpoolTimer
0x180003219  mov     ecx, ebx; dwErrCode
0x18000321b  call    cs:__imp_SetLastError
0x180003221  mov     qword ptr [rdi+10h], 0
0x180003229  mov     rcx, rdi; this
0x18000322c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003231  mov     rcx, [rdi+68h]
0x180003235  test    rcx, rcx
0x180003238  jz      short loc_18000326A
0x18000323a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003241  test    rax, rax
0x180003244  jnz     short loc_180003255
0x180003246  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000324d  test    rdx, rdx
0x180003250  jz      short loc_180003268
0x180003252  mov     rax, rdx
0x180003255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003261  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003268  jmp     short loc_180003278
0x18000326a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003271  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003278  mov     rcx, [rdi+60h]
0x18000327c  test    rcx, rcx
0x18000327f  jz      short loc_180003294
0x180003281  test    rax, rax
0x180003284  jnz     short loc_18000328E
0x180003286  test    rdx, rdx
0x180003289  jz      short loc_180003294
0x18000328b  mov     rax, rdx
0x18000328e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003293  nop
0x180003294  mov     rbx, [rdi+58h]
0x180003298  mov     qword ptr [rdi+58h], 0
0x1800032a0  test    rbx, rbx
0x1800032a3  jz      short loc_1800032B9
0x1800032a5  call    cs:__imp_GetProcessHeap
0x1800032ab  mov     rcx, rax; hHeap
0x1800032ae  mov     r8, rbx; lpMem
0x1800032b1  xor     edx, edx; dwFlags
0x1800032b3  call    cs:__imp_HeapFree
0x1800032b9  mov     rbx, [rdi+38h]
0x1800032bd  mov     qword ptr [rdi+38h], 0
0x1800032c5  test    rbx, rbx
0x1800032c8  jz      short loc_1800032DE
0x1800032ca  call    cs:__imp_GetProcessHeap
0x1800032d0  mov     rcx, rax; hHeap
0x1800032d3  mov     r8, rbx; lpMem
0x1800032d6  xor     edx, edx; dwFlags
0x1800032d8  call    cs:__imp_HeapFree
0x1800032de  mov     rbx, [rdi+10h]
0x1800032e2  test    rbx, rbx
0x1800032e5  jz      short loc_180003310
0x1800032e7  xor     r9d, r9d; msWindowLength
0x1800032ea  xor     r8d, r8d; msPeriod
0x1800032ed  xor     edx, edx; pftDueTime
0x1800032ef  mov     rcx, rbx; pti
0x1800032f2  call    cs:__imp_SetThreadpoolTimer
0x1800032f8  mov     edx, 1; fCancelPendingCallbacks
0x1800032fd  mov     rcx, rbx; pti
0x180003300  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003306  mov     rcx, rbx; pti
0x180003309  call    cs:__imp_CloseThreadpoolTimer
0x18000330f  nop
0x180003310  mov     rbx, [rsp+28h+arg_0]
0x180003315  mov     rsi, [rsp+28h+arg_8]
0x18000331a  add     rsp, 20h
0x18000331e  pop     rdi
0x18000331f  retn
```
