# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003290`
- end: `0x1400033e8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b9a0`

## callees

- `0x140003290`
- `0x140005dbc`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000336d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003392`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000336d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000337b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400033a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000337b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400033a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400032db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400033d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400032db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400033d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400032c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400033ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400032c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400033ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400032d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400033c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400032d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400033c8`

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
0x140003290  mov     [rsp+arg_0], rbx
0x140003295  mov     [rsp+arg_8], rsi
0x14000329a  push    rdi
0x14000329b  sub     rsp, 20h
0x14000329f  mov     rdi, rcx
0x1400032a2  mov     dword ptr [rcx], 0
0x1400032a8  mov     rsi, [rcx+10h]
0x1400032ac  test    rsi, rsi
0x1400032af  jz      short loc_1400032E9
0x1400032b1  call    cs:__imp_GetLastError
0x1400032b7  mov     ebx, eax
0x1400032b9  xor     r9d, r9d; msWindowLength
0x1400032bc  xor     r8d, r8d; msPeriod
0x1400032bf  xor     edx, edx; pftDueTime
0x1400032c1  mov     rcx, rsi; pti
0x1400032c4  call    cs:__imp_SetThreadpoolTimer
0x1400032ca  mov     edx, 1; fCancelPendingCallbacks
0x1400032cf  mov     rcx, rsi; pti
0x1400032d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400032d8  mov     rcx, rsi; pti
0x1400032db  call    cs:__imp_CloseThreadpoolTimer
0x1400032e1  mov     ecx, ebx; dwErrCode
0x1400032e3  call    cs:__imp_SetLastError
0x1400032e9  mov     qword ptr [rdi+10h], 0
0x1400032f1  mov     rcx, rdi; this
0x1400032f4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1400032f9  mov     rcx, [rdi+68h]
0x1400032fd  test    rcx, rcx
0x140003300  jz      short loc_140003332
0x140003302  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003309  test    rax, rax
0x14000330c  jnz     short loc_14000331D
0x14000330e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003315  test    rdx, rdx
0x140003318  jz      short loc_140003330
0x14000331a  mov     rax, rdx
0x14000331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003322  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003329  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003330  jmp     short loc_140003340
0x140003332  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003339  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003340  mov     rcx, [rdi+60h]
0x140003344  test    rcx, rcx
0x140003347  jz      short loc_14000335C
0x140003349  test    rax, rax
0x14000334c  jnz     short loc_140003356
0x14000334e  test    rdx, rdx
0x140003351  jz      short loc_14000335C
0x140003353  mov     rax, rdx
0x140003356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000335b  nop
0x14000335c  mov     rbx, [rdi+58h]
0x140003360  mov     qword ptr [rdi+58h], 0
0x140003368  test    rbx, rbx
0x14000336b  jz      short loc_140003381
0x14000336d  call    cs:__imp_GetProcessHeap
0x140003373  mov     rcx, rax; hHeap
0x140003376  mov     r8, rbx; lpMem
0x140003379  xor     edx, edx; dwFlags
0x14000337b  call    cs:__imp_HeapFree
0x140003381  mov     rbx, [rdi+38h]
0x140003385  mov     qword ptr [rdi+38h], 0
0x14000338d  test    rbx, rbx
0x140003390  jz      short loc_1400033A6
0x140003392  call    cs:__imp_GetProcessHeap
0x140003398  mov     rcx, rax; hHeap
0x14000339b  mov     r8, rbx; lpMem
0x14000339e  xor     edx, edx; dwFlags
0x1400033a0  call    cs:__imp_HeapFree
0x1400033a6  mov     rbx, [rdi+10h]
0x1400033aa  test    rbx, rbx
0x1400033ad  jz      short loc_1400033D8
0x1400033af  xor     r9d, r9d; msWindowLength
0x1400033b2  xor     r8d, r8d; msPeriod
0x1400033b5  xor     edx, edx; pftDueTime
0x1400033b7  mov     rcx, rbx; pti
0x1400033ba  call    cs:__imp_SetThreadpoolTimer
0x1400033c0  mov     edx, 1; fCancelPendingCallbacks
0x1400033c5  mov     rcx, rbx; pti
0x1400033c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400033ce  mov     rcx, rbx; pti
0x1400033d1  call    cs:__imp_CloseThreadpoolTimer
0x1400033d7  nop
0x1400033d8  mov     rbx, [rsp+28h+arg_0]
0x1400033dd  mov     rsi, [rsp+28h+arg_8]
0x1400033e2  add     rsp, 20h
0x1400033e6  pop     rdi
0x1400033e7  retn
```
