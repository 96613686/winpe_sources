# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003738`
- end: `0x180003890`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010f40`

## callees

- `0x180003738`
- `0x180007190`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000383a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000383a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000378b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000378b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000376c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003862`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000376c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003862`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003879`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003879`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000377a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003870`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000377a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003870`

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
0x180003738  mov     [rsp+arg_0], rbx
0x18000373d  mov     [rsp+arg_8], rsi
0x180003742  push    rdi
0x180003743  sub     rsp, 20h
0x180003747  mov     rdi, rcx
0x18000374a  mov     dword ptr [rcx], 0
0x180003750  mov     rsi, [rcx+10h]
0x180003754  test    rsi, rsi
0x180003757  jz      short loc_180003791
0x180003759  call    cs:__imp_GetLastError
0x18000375f  mov     ebx, eax
0x180003761  xor     r9d, r9d; msWindowLength
0x180003764  xor     r8d, r8d; msPeriod
0x180003767  xor     edx, edx; pftDueTime
0x180003769  mov     rcx, rsi; pti
0x18000376c  call    cs:__imp_SetThreadpoolTimer
0x180003772  mov     edx, 1; fCancelPendingCallbacks
0x180003777  mov     rcx, rsi; pti
0x18000377a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003780  mov     rcx, rsi; pti
0x180003783  call    cs:__imp_CloseThreadpoolTimer
0x180003789  mov     ecx, ebx; dwErrCode
0x18000378b  call    cs:__imp_SetLastError
0x180003791  mov     qword ptr [rdi+10h], 0
0x180003799  mov     rcx, rdi; this
0x18000379c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800037a1  mov     rcx, [rdi+68h]
0x1800037a5  test    rcx, rcx
0x1800037a8  jz      short loc_1800037DA
0x1800037aa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800037b1  test    rax, rax
0x1800037b4  jnz     short loc_1800037C5
0x1800037b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800037bd  test    rdx, rdx
0x1800037c0  jz      short loc_1800037D8
0x1800037c2  mov     rax, rdx
0x1800037c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ca  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800037d1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800037d8  jmp     short loc_1800037E8
0x1800037da  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800037e1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800037e8  mov     rcx, [rdi+60h]
0x1800037ec  test    rcx, rcx
0x1800037ef  jz      short loc_180003804
0x1800037f1  test    rax, rax
0x1800037f4  jnz     short loc_1800037FE
0x1800037f6  test    rdx, rdx
0x1800037f9  jz      short loc_180003804
0x1800037fb  mov     rax, rdx
0x1800037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003803  nop
0x180003804  mov     rbx, [rdi+58h]
0x180003808  mov     qword ptr [rdi+58h], 0
0x180003810  test    rbx, rbx
0x180003813  jz      short loc_180003829
0x180003815  call    cs:__imp_GetProcessHeap
0x18000381b  mov     rcx, rax; hHeap
0x18000381e  mov     r8, rbx; lpMem
0x180003821  xor     edx, edx; dwFlags
0x180003823  call    cs:__imp_HeapFree
0x180003829  mov     rbx, [rdi+38h]
0x18000382d  mov     qword ptr [rdi+38h], 0
0x180003835  test    rbx, rbx
0x180003838  jz      short loc_18000384E
0x18000383a  call    cs:__imp_GetProcessHeap
0x180003840  mov     rcx, rax; hHeap
0x180003843  mov     r8, rbx; lpMem
0x180003846  xor     edx, edx; dwFlags
0x180003848  call    cs:__imp_HeapFree
0x18000384e  mov     rbx, [rdi+10h]
0x180003852  test    rbx, rbx
0x180003855  jz      short loc_180003880
0x180003857  xor     r9d, r9d; msWindowLength
0x18000385a  xor     r8d, r8d; msPeriod
0x18000385d  xor     edx, edx; pftDueTime
0x18000385f  mov     rcx, rbx; pti
0x180003862  call    cs:__imp_SetThreadpoolTimer
0x180003868  mov     edx, 1; fCancelPendingCallbacks
0x18000386d  mov     rcx, rbx; pti
0x180003870  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003876  mov     rcx, rbx; pti
0x180003879  call    cs:__imp_CloseThreadpoolTimer
0x18000387f  nop
0x180003880  mov     rbx, [rsp+28h+arg_0]
0x180003885  mov     rsi, [rsp+28h+arg_8]
0x18000388a  add     rsp, 20h
0x18000388e  pop     rdi
0x18000388f  retn
```
