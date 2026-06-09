# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003958`
- end: `0x180003ab0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180033b40`

## callees

- `0x180003958`
- `0x18000651c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003979`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000398c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a82`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000398c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800039a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800039a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000399a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a90`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000399a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a90`

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
0x180003958  mov     [rsp+arg_0], rbx
0x18000395d  mov     [rsp+arg_8], rsi
0x180003962  push    rdi
0x180003963  sub     rsp, 20h
0x180003967  mov     rdi, rcx
0x18000396a  mov     dword ptr [rcx], 0
0x180003970  mov     rsi, [rcx+10h]
0x180003974  test    rsi, rsi
0x180003977  jz      short loc_1800039B1
0x180003979  call    cs:__imp_GetLastError
0x18000397f  mov     ebx, eax
0x180003981  xor     r9d, r9d; msWindowLength
0x180003984  xor     r8d, r8d; msPeriod
0x180003987  xor     edx, edx; pftDueTime
0x180003989  mov     rcx, rsi; pti
0x18000398c  call    cs:__imp_SetThreadpoolTimer
0x180003992  mov     edx, 1; fCancelPendingCallbacks
0x180003997  mov     rcx, rsi; pti
0x18000399a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800039a0  mov     rcx, rsi; pti
0x1800039a3  call    cs:__imp_CloseThreadpoolTimer
0x1800039a9  mov     ecx, ebx; dwErrCode
0x1800039ab  call    cs:__imp_SetLastError
0x1800039b1  mov     qword ptr [rdi+10h], 0
0x1800039b9  mov     rcx, rdi; this
0x1800039bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800039c1  mov     rcx, [rdi+68h]
0x1800039c5  test    rcx, rcx
0x1800039c8  jz      short loc_1800039FA
0x1800039ca  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800039d1  test    rax, rax
0x1800039d4  jnz     short loc_1800039E5
0x1800039d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800039dd  test    rdx, rdx
0x1800039e0  jz      short loc_1800039F8
0x1800039e2  mov     rax, rdx
0x1800039e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800039f1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800039f8  jmp     short loc_180003A08
0x1800039fa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a01  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a08  mov     rcx, [rdi+60h]
0x180003a0c  test    rcx, rcx
0x180003a0f  jz      short loc_180003A24
0x180003a11  test    rax, rax
0x180003a14  jnz     short loc_180003A1E
0x180003a16  test    rdx, rdx
0x180003a19  jz      short loc_180003A24
0x180003a1b  mov     rax, rdx
0x180003a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a23  nop
0x180003a24  mov     rbx, [rdi+58h]
0x180003a28  mov     qword ptr [rdi+58h], 0
0x180003a30  test    rbx, rbx
0x180003a33  jz      short loc_180003A49
0x180003a35  call    cs:__imp_GetProcessHeap
0x180003a3b  mov     rcx, rax; hHeap
0x180003a3e  mov     r8, rbx; lpMem
0x180003a41  xor     edx, edx; dwFlags
0x180003a43  call    cs:__imp_HeapFree
0x180003a49  mov     rbx, [rdi+38h]
0x180003a4d  mov     qword ptr [rdi+38h], 0
0x180003a55  test    rbx, rbx
0x180003a58  jz      short loc_180003A6E
0x180003a5a  call    cs:__imp_GetProcessHeap
0x180003a60  mov     rcx, rax; hHeap
0x180003a63  mov     r8, rbx; lpMem
0x180003a66  xor     edx, edx; dwFlags
0x180003a68  call    cs:__imp_HeapFree
0x180003a6e  mov     rbx, [rdi+10h]
0x180003a72  test    rbx, rbx
0x180003a75  jz      short loc_180003AA0
0x180003a77  xor     r9d, r9d; msWindowLength
0x180003a7a  xor     r8d, r8d; msPeriod
0x180003a7d  xor     edx, edx; pftDueTime
0x180003a7f  mov     rcx, rbx; pti
0x180003a82  call    cs:__imp_SetThreadpoolTimer
0x180003a88  mov     edx, 1; fCancelPendingCallbacks
0x180003a8d  mov     rcx, rbx; pti
0x180003a90  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a96  mov     rcx, rbx; pti
0x180003a99  call    cs:__imp_CloseThreadpoolTimer
0x180003a9f  nop
0x180003aa0  mov     rbx, [rsp+28h+arg_0]
0x180003aa5  mov     rsi, [rsp+28h+arg_8]
0x180003aaa  add     rsp, 20h
0x180003aae  pop     rdi
0x180003aaf  retn
```
