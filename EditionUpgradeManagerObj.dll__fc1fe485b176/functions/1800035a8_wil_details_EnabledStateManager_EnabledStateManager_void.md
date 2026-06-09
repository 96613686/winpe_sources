# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800035a8`
- end: `0x1800036ee`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022b20`

## callees

- `0x1800035a8`
- `0x180005f4c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003682`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003682`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003699`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800035dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800035dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036c1`

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
0x1800035a8  mov     [rsp+arg_0], rbx
0x1800035ad  mov     [rsp+arg_8], rsi
0x1800035b2  push    rdi
0x1800035b3  sub     rsp, 20h
0x1800035b7  mov     dword ptr [rcx], 0
0x1800035bd  mov     rdi, rcx
0x1800035c0  mov     rsi, [rcx+10h]
0x1800035c4  test    rsi, rsi
0x1800035c7  jz      short loc_180003601
0x1800035c9  call    cs:__imp_GetLastError
0x1800035cf  xor     r9d, r9d; msWindowLength
0x1800035d2  xor     r8d, r8d; msPeriod
0x1800035d5  xor     edx, edx; pftDueTime
0x1800035d7  mov     rcx, rsi; pti
0x1800035da  mov     ebx, eax
0x1800035dc  call    cs:__imp_SetThreadpoolTimer
0x1800035e2  mov     edx, 1; fCancelPendingCallbacks
0x1800035e7  mov     rcx, rsi; pti
0x1800035ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800035f0  mov     rcx, rsi; pti
0x1800035f3  call    cs:__imp_CloseThreadpoolTimer
0x1800035f9  mov     ecx, ebx; dwErrCode
0x1800035fb  call    cs:__imp_SetLastError
0x180003601  mov     rcx, rdi; this
0x180003604  mov     qword ptr [rdi+10h], 0
0x18000360c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003611  mov     rcx, [rdi+68h]
0x180003615  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000361c  test    rcx, rcx
0x18000361f  jz      short loc_180003641
0x180003621  test    rax, rax
0x180003624  jnz     short loc_180003635
0x180003626  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000362d  test    rdx, rdx
0x180003630  jz      short loc_180003648
0x180003632  mov     rax, rdx
0x180003635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003641  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003648  mov     rcx, [rdi+60h]
0x18000364c  test    rcx, rcx
0x18000364f  jz      short loc_180003663
0x180003651  test    rax, rax
0x180003654  jnz     short loc_18000365E
0x180003656  test    rdx, rdx
0x180003659  jz      short loc_180003663
0x18000365b  mov     rax, rdx
0x18000365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003663  mov     rbx, [rdi+58h]
0x180003667  mov     qword ptr [rdi+58h], 0
0x18000366f  test    rbx, rbx
0x180003672  jz      short loc_180003688
0x180003674  call    cs:__imp_GetProcessHeap
0x18000367a  mov     r8, rbx; lpMem
0x18000367d  xor     edx, edx; dwFlags
0x18000367f  mov     rcx, rax; hHeap
0x180003682  call    cs:__imp_HeapFree
0x180003688  mov     rbx, [rdi+38h]
0x18000368c  mov     qword ptr [rdi+38h], 0
0x180003694  test    rbx, rbx
0x180003697  jz      short loc_1800036AD
0x180003699  call    cs:__imp_GetProcessHeap
0x18000369f  mov     r8, rbx; lpMem
0x1800036a2  xor     edx, edx; dwFlags
0x1800036a4  mov     rcx, rax; hHeap
0x1800036a7  call    cs:__imp_HeapFree
0x1800036ad  mov     rbx, [rdi+10h]
0x1800036b1  test    rbx, rbx
0x1800036b4  jz      short loc_1800036DE
0x1800036b6  xor     r9d, r9d; msWindowLength
0x1800036b9  xor     r8d, r8d; msPeriod
0x1800036bc  xor     edx, edx; pftDueTime
0x1800036be  mov     rcx, rbx; pti
0x1800036c1  call    cs:__imp_SetThreadpoolTimer
0x1800036c7  mov     edx, 1; fCancelPendingCallbacks
0x1800036cc  mov     rcx, rbx; pti
0x1800036cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036d5  mov     rcx, rbx; pti
0x1800036d8  call    cs:__imp_CloseThreadpoolTimer
0x1800036de  mov     rbx, [rsp+28h+arg_0]
0x1800036e3  mov     rsi, [rsp+28h+arg_8]
0x1800036e8  add     rsp, 20h
0x1800036ec  pop     rdi
0x1800036ed  retn
```
