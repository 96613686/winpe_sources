# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003324`
- end: `0x18000347c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800139b0`

## callees

- `0x180003324`
- `0x18000600c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003345`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003377`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000340f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003434`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000340f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003434`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003426`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000336f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003465`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000336f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003465`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003366`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000345c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003366`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000345c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003358`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000344e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003358`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000344e`

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
0x180003324  mov     [rsp+arg_0], rbx
0x180003329  mov     [rsp+arg_8], rsi
0x18000332e  push    rdi
0x18000332f  sub     rsp, 20h
0x180003333  mov     rdi, rcx
0x180003336  mov     dword ptr [rcx], 0
0x18000333c  mov     rsi, [rcx+10h]
0x180003340  test    rsi, rsi
0x180003343  jz      short loc_18000337D
0x180003345  call    cs:__imp_GetLastError
0x18000334b  mov     ebx, eax
0x18000334d  xor     r9d, r9d; msWindowLength
0x180003350  xor     r8d, r8d; msPeriod
0x180003353  xor     edx, edx; pftDueTime
0x180003355  mov     rcx, rsi; pti
0x180003358  call    cs:__imp_SetThreadpoolTimer
0x18000335e  mov     edx, 1; fCancelPendingCallbacks
0x180003363  mov     rcx, rsi; pti
0x180003366  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000336c  mov     rcx, rsi; pti
0x18000336f  call    cs:__imp_CloseThreadpoolTimer
0x180003375  mov     ecx, ebx; dwErrCode
0x180003377  call    cs:__imp_SetLastError
0x18000337d  mov     qword ptr [rdi+10h], 0
0x180003385  mov     rcx, rdi; this
0x180003388  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000338d  mov     rcx, [rdi+68h]
0x180003391  test    rcx, rcx
0x180003394  jz      short loc_1800033C6
0x180003396  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000339d  test    rax, rax
0x1800033a0  jnz     short loc_1800033B1
0x1800033a2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800033a9  test    rdx, rdx
0x1800033ac  jz      short loc_1800033C4
0x1800033ae  mov     rax, rdx
0x1800033b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800033bd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800033c4  jmp     short loc_1800033D4
0x1800033c6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800033cd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800033d4  mov     rcx, [rdi+60h]
0x1800033d8  test    rcx, rcx
0x1800033db  jz      short loc_1800033F0
0x1800033dd  test    rax, rax
0x1800033e0  jnz     short loc_1800033EA
0x1800033e2  test    rdx, rdx
0x1800033e5  jz      short loc_1800033F0
0x1800033e7  mov     rax, rdx
0x1800033ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ef  nop
0x1800033f0  mov     rbx, [rdi+58h]
0x1800033f4  mov     qword ptr [rdi+58h], 0
0x1800033fc  test    rbx, rbx
0x1800033ff  jz      short loc_180003415
0x180003401  call    cs:__imp_GetProcessHeap
0x180003407  mov     rcx, rax; hHeap
0x18000340a  mov     r8, rbx; lpMem
0x18000340d  xor     edx, edx; dwFlags
0x18000340f  call    cs:__imp_HeapFree
0x180003415  mov     rbx, [rdi+38h]
0x180003419  mov     qword ptr [rdi+38h], 0
0x180003421  test    rbx, rbx
0x180003424  jz      short loc_18000343A
0x180003426  call    cs:__imp_GetProcessHeap
0x18000342c  mov     rcx, rax; hHeap
0x18000342f  mov     r8, rbx; lpMem
0x180003432  xor     edx, edx; dwFlags
0x180003434  call    cs:__imp_HeapFree
0x18000343a  mov     rbx, [rdi+10h]
0x18000343e  test    rbx, rbx
0x180003441  jz      short loc_18000346C
0x180003443  xor     r9d, r9d; msWindowLength
0x180003446  xor     r8d, r8d; msPeriod
0x180003449  xor     edx, edx; pftDueTime
0x18000344b  mov     rcx, rbx; pti
0x18000344e  call    cs:__imp_SetThreadpoolTimer
0x180003454  mov     edx, 1; fCancelPendingCallbacks
0x180003459  mov     rcx, rbx; pti
0x18000345c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003462  mov     rcx, rbx; pti
0x180003465  call    cs:__imp_CloseThreadpoolTimer
0x18000346b  nop
0x18000346c  mov     rbx, [rsp+28h+arg_0]
0x180003471  mov     rsi, [rsp+28h+arg_8]
0x180003476  add     rsp, 20h
0x18000347a  pop     rdi
0x18000347b  retn
```
