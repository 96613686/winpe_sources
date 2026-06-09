# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800041a8`
- end: `0x180004300`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800188e0`

## callees

- `0x1800041a8`
- `0x180006cdc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800041ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800042e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800041ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800042e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800041f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800042e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800041f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800042e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800041dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800041dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042d2`

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
0x1800041a8  mov     [rsp+arg_0], rbx
0x1800041ad  mov     [rsp+arg_8], rsi
0x1800041b2  push    rdi
0x1800041b3  sub     rsp, 20h
0x1800041b7  mov     rdi, rcx
0x1800041ba  mov     dword ptr [rcx], 0
0x1800041c0  mov     rsi, [rcx+10h]
0x1800041c4  test    rsi, rsi
0x1800041c7  jz      short loc_180004201
0x1800041c9  call    cs:__imp_GetLastError
0x1800041cf  mov     ebx, eax
0x1800041d1  xor     r9d, r9d; msWindowLength
0x1800041d4  xor     r8d, r8d; msPeriod
0x1800041d7  xor     edx, edx; pftDueTime
0x1800041d9  mov     rcx, rsi; pti
0x1800041dc  call    cs:__imp_SetThreadpoolTimer
0x1800041e2  mov     edx, 1; fCancelPendingCallbacks
0x1800041e7  mov     rcx, rsi; pti
0x1800041ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800041f0  mov     rcx, rsi; pti
0x1800041f3  call    cs:__imp_CloseThreadpoolTimer
0x1800041f9  mov     ecx, ebx; dwErrCode
0x1800041fb  call    cs:__imp_SetLastError
0x180004201  mov     qword ptr [rdi+10h], 0
0x180004209  mov     rcx, rdi; this
0x18000420c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180004211  mov     rcx, [rdi+68h]
0x180004215  test    rcx, rcx
0x180004218  jz      short loc_18000424A
0x18000421a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004221  test    rax, rax
0x180004224  jnz     short loc_180004235
0x180004226  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000422d  test    rdx, rdx
0x180004230  jz      short loc_180004248
0x180004232  mov     rax, rdx
0x180004235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000423a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004241  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004248  jmp     short loc_180004258
0x18000424a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004251  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004258  mov     rcx, [rdi+60h]
0x18000425c  test    rcx, rcx
0x18000425f  jz      short loc_180004274
0x180004261  test    rax, rax
0x180004264  jnz     short loc_18000426E
0x180004266  test    rdx, rdx
0x180004269  jz      short loc_180004274
0x18000426b  mov     rax, rdx
0x18000426e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004273  nop
0x180004274  mov     rbx, [rdi+58h]
0x180004278  mov     qword ptr [rdi+58h], 0
0x180004280  test    rbx, rbx
0x180004283  jz      short loc_180004299
0x180004285  call    cs:__imp_GetProcessHeap
0x18000428b  mov     rcx, rax; hHeap
0x18000428e  mov     r8, rbx; lpMem
0x180004291  xor     edx, edx; dwFlags
0x180004293  call    cs:__imp_HeapFree
0x180004299  mov     rbx, [rdi+38h]
0x18000429d  mov     qword ptr [rdi+38h], 0
0x1800042a5  test    rbx, rbx
0x1800042a8  jz      short loc_1800042BE
0x1800042aa  call    cs:__imp_GetProcessHeap
0x1800042b0  mov     rcx, rax; hHeap
0x1800042b3  mov     r8, rbx; lpMem
0x1800042b6  xor     edx, edx; dwFlags
0x1800042b8  call    cs:__imp_HeapFree
0x1800042be  mov     rbx, [rdi+10h]
0x1800042c2  test    rbx, rbx
0x1800042c5  jz      short loc_1800042F0
0x1800042c7  xor     r9d, r9d; msWindowLength
0x1800042ca  xor     r8d, r8d; msPeriod
0x1800042cd  xor     edx, edx; pftDueTime
0x1800042cf  mov     rcx, rbx; pti
0x1800042d2  call    cs:__imp_SetThreadpoolTimer
0x1800042d8  mov     edx, 1; fCancelPendingCallbacks
0x1800042dd  mov     rcx, rbx; pti
0x1800042e0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800042e6  mov     rcx, rbx; pti
0x1800042e9  call    cs:__imp_CloseThreadpoolTimer
0x1800042ef  nop
0x1800042f0  mov     rbx, [rsp+28h+arg_0]
0x1800042f5  mov     rsi, [rsp+28h+arg_8]
0x1800042fa  add     rsp, 20h
0x1800042fe  pop     rdi
0x1800042ff  retn
```
