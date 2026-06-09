# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1400032b0`
- end: `0x140003408`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140050940`

## callees

- `0x1400032b0`
- `0x140003498`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000335d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000335d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000332a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000334f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000332a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000334f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003300`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400032f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400033f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400032f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400033f1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400032ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400033e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400032ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400033e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400032e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400033da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400032e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400033da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x1400032b0  mov     [rsp+arg_0], rbx
0x1400032b5  mov     [rsp+arg_8], rsi
0x1400032ba  push    rdi
0x1400032bb  sub     rsp, 20h
0x1400032bf  mov     rdi, rcx
0x1400032c2  mov     byte ptr [rcx], 0
0x1400032c5  mov     rsi, [rcx+10h]
0x1400032c9  test    rsi, rsi
0x1400032cc  jz      short loc_140003306
0x1400032ce  call    cs:__imp_GetLastError
0x1400032d4  mov     ebx, eax
0x1400032d6  xor     r9d, r9d; msWindowLength
0x1400032d9  xor     r8d, r8d; msPeriod
0x1400032dc  xor     edx, edx; pftDueTime
0x1400032de  mov     rcx, rsi; pti
0x1400032e1  call    cs:__imp_SetThreadpoolTimer
0x1400032e7  mov     edx, 1; fCancelPendingCallbacks
0x1400032ec  mov     rcx, rsi; pti
0x1400032ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400032f5  mov     rcx, rsi; pti
0x1400032f8  call    cs:__imp_CloseThreadpoolTimer
0x1400032fe  mov     ecx, ebx; dwErrCode
0x140003300  call    cs:__imp_SetLastError
0x140003306  mov     qword ptr [rdi+10h], 0
0x14000330e  mov     byte ptr [rdi], 0
0x140003311  mov     rcx, rdi; this
0x140003314  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x140003319  mov     rbx, [rdi+68h]
0x14000331d  mov     qword ptr [rdi+68h], 0
0x140003325  test    rbx, rbx
0x140003328  jz      short loc_14000333E
0x14000332a  call    cs:__imp_GetProcessHeap
0x140003330  mov     rcx, rax; hHeap
0x140003333  mov     r8, rbx; lpMem
0x140003336  xor     edx, edx; dwFlags
0x140003338  call    cs:__imp_HeapFree
0x14000333e  mov     rbx, [rdi+48h]
0x140003342  mov     qword ptr [rdi+48h], 0
0x14000334a  test    rbx, rbx
0x14000334d  jz      short loc_140003363
0x14000334f  call    cs:__imp_GetProcessHeap
0x140003355  mov     rcx, rax; hHeap
0x140003358  mov     r8, rbx; lpMem
0x14000335b  xor     edx, edx; dwFlags
0x14000335d  call    cs:__imp_HeapFree
0x140003363  mov     rcx, [rdi+28h]
0x140003367  test    rcx, rcx
0x14000336a  jz      short loc_14000339C
0x14000336c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003373  test    rax, rax
0x140003376  jnz     short loc_140003387
0x140003378  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000337f  test    rdx, rdx
0x140003382  jz      short loc_14000339A
0x140003384  mov     rax, rdx
0x140003387  call    _guard_dispatch_icall
0x14000338c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003393  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000339a  jmp     short loc_1400033AA
0x14000339c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400033a3  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400033aa  mov     rcx, [rdi+20h]
0x1400033ae  test    rcx, rcx
0x1400033b1  jz      short loc_1400033C6
0x1400033b3  test    rax, rax
0x1400033b6  jnz     short loc_1400033C0
0x1400033b8  test    rdx, rdx
0x1400033bb  jz      short loc_1400033C6
0x1400033bd  mov     rax, rdx
0x1400033c0  call    _guard_dispatch_icall
0x1400033c5  nop
0x1400033c6  mov     rbx, [rdi+10h]
0x1400033ca  test    rbx, rbx
0x1400033cd  jz      short loc_1400033F8
0x1400033cf  xor     r9d, r9d; msWindowLength
0x1400033d2  xor     r8d, r8d; msPeriod
0x1400033d5  xor     edx, edx; pftDueTime
0x1400033d7  mov     rcx, rbx; pti
0x1400033da  call    cs:__imp_SetThreadpoolTimer
0x1400033e0  mov     edx, 1; fCancelPendingCallbacks
0x1400033e5  mov     rcx, rbx; pti
0x1400033e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400033ee  mov     rcx, rbx; pti
0x1400033f1  call    cs:__imp_CloseThreadpoolTimer
0x1400033f7  nop
0x1400033f8  mov     rbx, [rsp+28h+arg_0]
0x1400033fd  mov     rsi, [rsp+28h+arg_8]
0x140003402  add     rsp, 20h
0x140003406  pop     rdi
0x140003407  retn
```
