# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010458`
- end: `0x18001059e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d600`

## callees

- `0x180010458`
- `0x180014cf0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010549`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010532`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010532`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010557`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800104ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800104ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010479`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800104a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010588`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800104a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010588`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001049a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001057f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001049a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001057f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001048c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010571`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001048c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010571`

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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x180010458  mov     [rsp+arg_0], rbx
0x18001045d  mov     [rsp+arg_8], rsi
0x180010462  push    rdi
0x180010463  sub     rsp, 20h
0x180010467  mov     dword ptr [rcx], 0
0x18001046d  mov     rdi, rcx
0x180010470  mov     rsi, [rcx+10h]
0x180010474  test    rsi, rsi
0x180010477  jz      short loc_1800104B1
0x180010479  call    cs:__imp_GetLastError
0x18001047f  xor     r9d, r9d; msWindowLength
0x180010482  xor     r8d, r8d; msPeriod
0x180010485  xor     edx, edx; pftDueTime
0x180010487  mov     rcx, rsi; pti
0x18001048a  mov     ebx, eax
0x18001048c  call    cs:__imp_SetThreadpoolTimer
0x180010492  mov     edx, 1; fCancelPendingCallbacks
0x180010497  mov     rcx, rsi; pti
0x18001049a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800104a0  mov     rcx, rsi; pti
0x1800104a3  call    cs:__imp_CloseThreadpoolTimer
0x1800104a9  mov     ecx, ebx; dwErrCode
0x1800104ab  call    cs:__imp_SetLastError
0x1800104b1  mov     rcx, rdi; this
0x1800104b4  mov     qword ptr [rdi+10h], 0
0x1800104bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800104c1  mov     rcx, [rdi+68h]
0x1800104c5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800104cc  test    rcx, rcx
0x1800104cf  jz      short loc_1800104F1
0x1800104d1  test    rax, rax
0x1800104d4  jnz     short loc_1800104E5
0x1800104d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800104dd  test    rdx, rdx
0x1800104e0  jz      short loc_1800104F8
0x1800104e2  mov     rax, rdx
0x1800104e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ea  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800104f1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800104f8  mov     rcx, [rdi+60h]
0x1800104fc  test    rcx, rcx
0x1800104ff  jz      short loc_180010513
0x180010501  test    rax, rax
0x180010504  jnz     short loc_18001050E
0x180010506  test    rdx, rdx
0x180010509  jz      short loc_180010513
0x18001050b  mov     rax, rdx
0x18001050e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010513  mov     rbx, [rdi+58h]
0x180010517  mov     qword ptr [rdi+58h], 0
0x18001051f  test    rbx, rbx
0x180010522  jz      short loc_180010538
0x180010524  call    cs:__imp_GetProcessHeap
0x18001052a  mov     r8, rbx; lpMem
0x18001052d  xor     edx, edx; dwFlags
0x18001052f  mov     rcx, rax; hHeap
0x180010532  call    cs:__imp_HeapFree
0x180010538  mov     rbx, [rdi+38h]
0x18001053c  mov     qword ptr [rdi+38h], 0
0x180010544  test    rbx, rbx
0x180010547  jz      short loc_18001055D
0x180010549  call    cs:__imp_GetProcessHeap
0x18001054f  mov     r8, rbx; lpMem
0x180010552  xor     edx, edx; dwFlags
0x180010554  mov     rcx, rax; hHeap
0x180010557  call    cs:__imp_HeapFree
0x18001055d  mov     rbx, [rdi+10h]
0x180010561  test    rbx, rbx
0x180010564  jz      short loc_18001058E
0x180010566  xor     r9d, r9d; msWindowLength
0x180010569  xor     r8d, r8d; msPeriod
0x18001056c  xor     edx, edx; pftDueTime
0x18001056e  mov     rcx, rbx; pti
0x180010571  call    cs:__imp_SetThreadpoolTimer
0x180010577  mov     edx, 1; fCancelPendingCallbacks
0x18001057c  mov     rcx, rbx; pti
0x18001057f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010585  mov     rcx, rbx; pti
0x180010588  call    cs:__imp_CloseThreadpoolTimer
0x18001058e  mov     rbx, [rsp+28h+arg_0]
0x180010593  mov     rsi, [rsp+28h+arg_8]
0x180010598  add     rsp, 20h
0x18001059c  pop     rdi
0x18001059d  retn
```
