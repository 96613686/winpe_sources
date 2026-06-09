# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003778`
- end: `0x1800038d0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029b20`

## callees

- `0x180003778`
- `0x18000629c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003855`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000387a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003855`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000387a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003799`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800038b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800038b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800038b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800038b0`

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
0x180003778  mov     [rsp+arg_0], rbx
0x18000377d  mov     [rsp+arg_8], rsi
0x180003782  push    rdi
0x180003783  sub     rsp, 20h
0x180003787  mov     rdi, rcx
0x18000378a  mov     dword ptr [rcx], 0
0x180003790  mov     rsi, [rcx+10h]
0x180003794  test    rsi, rsi
0x180003797  jz      short loc_1800037D1
0x180003799  call    cs:__imp_GetLastError
0x18000379f  mov     ebx, eax
0x1800037a1  xor     r9d, r9d; msWindowLength
0x1800037a4  xor     r8d, r8d; msPeriod
0x1800037a7  xor     edx, edx; pftDueTime
0x1800037a9  mov     rcx, rsi; pti
0x1800037ac  call    cs:__imp_SetThreadpoolTimer
0x1800037b2  mov     edx, 1; fCancelPendingCallbacks
0x1800037b7  mov     rcx, rsi; pti
0x1800037ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037c0  mov     rcx, rsi; pti
0x1800037c3  call    cs:__imp_CloseThreadpoolTimer
0x1800037c9  mov     ecx, ebx; dwErrCode
0x1800037cb  call    cs:__imp_SetLastError
0x1800037d1  mov     qword ptr [rdi+10h], 0
0x1800037d9  mov     rcx, rdi; this
0x1800037dc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800037e1  mov     rcx, [rdi+68h]
0x1800037e5  test    rcx, rcx
0x1800037e8  jz      short loc_18000381A
0x1800037ea  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800037f1  test    rax, rax
0x1800037f4  jnz     short loc_180003805
0x1800037f6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800037fd  test    rdx, rdx
0x180003800  jz      short loc_180003818
0x180003802  mov     rax, rdx
0x180003805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003811  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003818  jmp     short loc_180003828
0x18000381a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003821  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003828  mov     rcx, [rdi+60h]
0x18000382c  test    rcx, rcx
0x18000382f  jz      short loc_180003844
0x180003831  test    rax, rax
0x180003834  jnz     short loc_18000383E
0x180003836  test    rdx, rdx
0x180003839  jz      short loc_180003844
0x18000383b  mov     rax, rdx
0x18000383e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003843  nop
0x180003844  mov     rbx, [rdi+58h]
0x180003848  mov     qword ptr [rdi+58h], 0
0x180003850  test    rbx, rbx
0x180003853  jz      short loc_180003869
0x180003855  call    cs:__imp_GetProcessHeap
0x18000385b  mov     rcx, rax; hHeap
0x18000385e  mov     r8, rbx; lpMem
0x180003861  xor     edx, edx; dwFlags
0x180003863  call    cs:__imp_HeapFree
0x180003869  mov     rbx, [rdi+38h]
0x18000386d  mov     qword ptr [rdi+38h], 0
0x180003875  test    rbx, rbx
0x180003878  jz      short loc_18000388E
0x18000387a  call    cs:__imp_GetProcessHeap
0x180003880  mov     rcx, rax; hHeap
0x180003883  mov     r8, rbx; lpMem
0x180003886  xor     edx, edx; dwFlags
0x180003888  call    cs:__imp_HeapFree
0x18000388e  mov     rbx, [rdi+10h]
0x180003892  test    rbx, rbx
0x180003895  jz      short loc_1800038C0
0x180003897  xor     r9d, r9d; msWindowLength
0x18000389a  xor     r8d, r8d; msPeriod
0x18000389d  xor     edx, edx; pftDueTime
0x18000389f  mov     rcx, rbx; pti
0x1800038a2  call    cs:__imp_SetThreadpoolTimer
0x1800038a8  mov     edx, 1; fCancelPendingCallbacks
0x1800038ad  mov     rcx, rbx; pti
0x1800038b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800038b6  mov     rcx, rbx; pti
0x1800038b9  call    cs:__imp_CloseThreadpoolTimer
0x1800038bf  nop
0x1800038c0  mov     rbx, [rsp+28h+arg_0]
0x1800038c5  mov     rsi, [rsp+28h+arg_8]
0x1800038ca  add     rsp, 20h
0x1800038ce  pop     rdi
0x1800038cf  retn
```
