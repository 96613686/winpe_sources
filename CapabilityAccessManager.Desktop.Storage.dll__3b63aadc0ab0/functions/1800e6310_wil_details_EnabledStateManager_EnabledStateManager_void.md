# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800e6310`
- end: `0x1800e6468`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18010c450`

## callees

- `0x1800e6310`
- `0x1800e9154`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e63ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e63ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e63fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e63fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e6363`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e6363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6331`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6352`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6448`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6352`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6448`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e635b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6451`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e635b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6451`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e6344`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e643a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e6344`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e643a`

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
0x1800e6310  mov     [rsp+arg_0], rbx
0x1800e6315  mov     [rsp+arg_8], rsi
0x1800e631a  push    rdi
0x1800e631b  sub     rsp, 20h
0x1800e631f  mov     rdi, rcx
0x1800e6322  mov     dword ptr [rcx], 0
0x1800e6328  mov     rsi, [rcx+10h]
0x1800e632c  test    rsi, rsi
0x1800e632f  jz      short loc_1800E6369
0x1800e6331  call    cs:__imp_GetLastError
0x1800e6337  mov     ebx, eax
0x1800e6339  xor     r9d, r9d; msWindowLength
0x1800e633c  xor     r8d, r8d; msPeriod
0x1800e633f  xor     edx, edx; pftDueTime
0x1800e6341  mov     rcx, rsi; pti
0x1800e6344  call    cs:__imp_SetThreadpoolTimer
0x1800e634a  mov     edx, 1; fCancelPendingCallbacks
0x1800e634f  mov     rcx, rsi; pti
0x1800e6352  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e6358  mov     rcx, rsi; pti
0x1800e635b  call    cs:__imp_CloseThreadpoolTimer
0x1800e6361  mov     ecx, ebx; dwErrCode
0x1800e6363  call    cs:__imp_SetLastError
0x1800e6369  mov     qword ptr [rdi+10h], 0
0x1800e6371  mov     rcx, rdi; this
0x1800e6374  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800e6379  mov     rcx, [rdi+68h]
0x1800e637d  test    rcx, rcx
0x1800e6380  jz      short loc_1800E63B2
0x1800e6382  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800e6389  test    rax, rax
0x1800e638c  jnz     short loc_1800E639D
0x1800e638e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800e6395  test    rdx, rdx
0x1800e6398  jz      short loc_1800E63B0
0x1800e639a  mov     rax, rdx
0x1800e639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e63a2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800e63a9  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800e63b0  jmp     short loc_1800E63C0
0x1800e63b2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800e63b9  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800e63c0  mov     rcx, [rdi+60h]
0x1800e63c4  test    rcx, rcx
0x1800e63c7  jz      short loc_1800E63DC
0x1800e63c9  test    rax, rax
0x1800e63cc  jnz     short loc_1800E63D6
0x1800e63ce  test    rdx, rdx
0x1800e63d1  jz      short loc_1800E63DC
0x1800e63d3  mov     rax, rdx
0x1800e63d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e63db  nop
0x1800e63dc  mov     rbx, [rdi+58h]
0x1800e63e0  mov     qword ptr [rdi+58h], 0
0x1800e63e8  test    rbx, rbx
0x1800e63eb  jz      short loc_1800E6401
0x1800e63ed  call    cs:__imp_GetProcessHeap
0x1800e63f3  mov     rcx, rax; hHeap
0x1800e63f6  mov     r8, rbx; lpMem
0x1800e63f9  xor     edx, edx; dwFlags
0x1800e63fb  call    cs:__imp_HeapFree
0x1800e6401  mov     rbx, [rdi+38h]
0x1800e6405  mov     qword ptr [rdi+38h], 0
0x1800e640d  test    rbx, rbx
0x1800e6410  jz      short loc_1800E6426
0x1800e6412  call    cs:__imp_GetProcessHeap
0x1800e6418  mov     rcx, rax; hHeap
0x1800e641b  mov     r8, rbx; lpMem
0x1800e641e  xor     edx, edx; dwFlags
0x1800e6420  call    cs:__imp_HeapFree
0x1800e6426  mov     rbx, [rdi+10h]
0x1800e642a  test    rbx, rbx
0x1800e642d  jz      short loc_1800E6458
0x1800e642f  xor     r9d, r9d; msWindowLength
0x1800e6432  xor     r8d, r8d; msPeriod
0x1800e6435  xor     edx, edx; pftDueTime
0x1800e6437  mov     rcx, rbx; pti
0x1800e643a  call    cs:__imp_SetThreadpoolTimer
0x1800e6440  mov     edx, 1; fCancelPendingCallbacks
0x1800e6445  mov     rcx, rbx; pti
0x1800e6448  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e644e  mov     rcx, rbx; pti
0x1800e6451  call    cs:__imp_CloseThreadpoolTimer
0x1800e6457  nop
0x1800e6458  mov     rbx, [rsp+28h+arg_0]
0x1800e645d  mov     rsi, [rsp+28h+arg_8]
0x1800e6462  add     rsp, 20h
0x1800e6466  pop     rdi
0x1800e6467  retn
```
