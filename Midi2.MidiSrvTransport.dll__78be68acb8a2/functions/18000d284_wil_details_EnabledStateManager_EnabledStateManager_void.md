# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000d284`
- end: `0x18000d3dc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800145a0`

## callees

- `0x18000d284`
- `0x18000f8e8`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d386`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d386`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d36f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d394`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d36f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d394`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3ae`

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
0x18000d284  mov     [rsp+arg_0], rbx
0x18000d289  mov     [rsp+arg_8], rsi
0x18000d28e  push    rdi
0x18000d28f  sub     rsp, 20h
0x18000d293  mov     rdi, rcx
0x18000d296  mov     dword ptr [rcx], 0
0x18000d29c  mov     rsi, [rcx+10h]
0x18000d2a0  test    rsi, rsi
0x18000d2a3  jz      short loc_18000D2DD
0x18000d2a5  call    cs:__imp_GetLastError
0x18000d2ab  mov     ebx, eax
0x18000d2ad  xor     r9d, r9d; msWindowLength
0x18000d2b0  xor     r8d, r8d; msPeriod
0x18000d2b3  xor     edx, edx; pftDueTime
0x18000d2b5  mov     rcx, rsi; pti
0x18000d2b8  call    cs:__imp_SetThreadpoolTimer
0x18000d2be  mov     edx, 1; fCancelPendingCallbacks
0x18000d2c3  mov     rcx, rsi; pti
0x18000d2c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d2cc  mov     rcx, rsi; pti
0x18000d2cf  call    cs:__imp_CloseThreadpoolTimer
0x18000d2d5  mov     ecx, ebx; dwErrCode
0x18000d2d7  call    cs:__imp_SetLastError
0x18000d2dd  mov     qword ptr [rdi+10h], 0
0x18000d2e5  mov     rcx, rdi; this
0x18000d2e8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000d2ed  mov     rcx, [rdi+68h]
0x18000d2f1  test    rcx, rcx
0x18000d2f4  jz      short loc_18000D326
0x18000d2f6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d2fd  test    rax, rax
0x18000d300  jnz     short loc_18000D311
0x18000d302  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d309  test    rdx, rdx
0x18000d30c  jz      short loc_18000D324
0x18000d30e  mov     rax, rdx
0x18000d311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d316  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d31d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d324  jmp     short loc_18000D334
0x18000d326  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d32d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d334  mov     rcx, [rdi+60h]
0x18000d338  test    rcx, rcx
0x18000d33b  jz      short loc_18000D350
0x18000d33d  test    rax, rax
0x18000d340  jnz     short loc_18000D34A
0x18000d342  test    rdx, rdx
0x18000d345  jz      short loc_18000D350
0x18000d347  mov     rax, rdx
0x18000d34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34f  nop
0x18000d350  mov     rbx, [rdi+58h]
0x18000d354  mov     qword ptr [rdi+58h], 0
0x18000d35c  test    rbx, rbx
0x18000d35f  jz      short loc_18000D375
0x18000d361  call    cs:__imp_GetProcessHeap
0x18000d367  mov     rcx, rax; hHeap
0x18000d36a  mov     r8, rbx; lpMem
0x18000d36d  xor     edx, edx; dwFlags
0x18000d36f  call    cs:__imp_HeapFree
0x18000d375  mov     rbx, [rdi+38h]
0x18000d379  mov     qword ptr [rdi+38h], 0
0x18000d381  test    rbx, rbx
0x18000d384  jz      short loc_18000D39A
0x18000d386  call    cs:__imp_GetProcessHeap
0x18000d38c  mov     rcx, rax; hHeap
0x18000d38f  mov     r8, rbx; lpMem
0x18000d392  xor     edx, edx; dwFlags
0x18000d394  call    cs:__imp_HeapFree
0x18000d39a  mov     rbx, [rdi+10h]
0x18000d39e  test    rbx, rbx
0x18000d3a1  jz      short loc_18000D3CC
0x18000d3a3  xor     r9d, r9d; msWindowLength
0x18000d3a6  xor     r8d, r8d; msPeriod
0x18000d3a9  xor     edx, edx; pftDueTime
0x18000d3ab  mov     rcx, rbx; pti
0x18000d3ae  call    cs:__imp_SetThreadpoolTimer
0x18000d3b4  mov     edx, 1; fCancelPendingCallbacks
0x18000d3b9  mov     rcx, rbx; pti
0x18000d3bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d3c2  mov     rcx, rbx; pti
0x18000d3c5  call    cs:__imp_CloseThreadpoolTimer
0x18000d3cb  nop
0x18000d3cc  mov     rbx, [rsp+28h+arg_0]
0x18000d3d1  mov     rsi, [rsp+28h+arg_8]
0x18000d3d6  add     rsp, 20h
0x18000d3da  pop     rdi
0x18000d3db  retn
```
