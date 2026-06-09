# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800085ac`
- end: `0x180008704`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c95e0`

## callees

- `0x1800085ac`
- `0x1800096c8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008697`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008697`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800085e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800085e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800086e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800086e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800086ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800086ed`

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
0x1800085ac  mov     [rsp+arg_0], rbx
0x1800085b1  mov     [rsp+arg_8], rsi
0x1800085b6  push    rdi
0x1800085b7  sub     rsp, 20h
0x1800085bb  mov     rdi, rcx
0x1800085be  mov     dword ptr [rcx], 0
0x1800085c4  mov     rsi, [rcx+10h]
0x1800085c8  test    rsi, rsi
0x1800085cb  jz      short loc_180008605
0x1800085cd  call    cs:__imp_GetLastError
0x1800085d3  mov     ebx, eax
0x1800085d5  xor     r9d, r9d; msWindowLength
0x1800085d8  xor     r8d, r8d; msPeriod
0x1800085db  xor     edx, edx; pftDueTime
0x1800085dd  mov     rcx, rsi; pti
0x1800085e0  call    cs:__imp_SetThreadpoolTimer
0x1800085e6  mov     edx, 1; fCancelPendingCallbacks
0x1800085eb  mov     rcx, rsi; pti
0x1800085ee  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800085f4  mov     rcx, rsi; pti
0x1800085f7  call    cs:__imp_CloseThreadpoolTimer
0x1800085fd  mov     ecx, ebx; dwErrCode
0x1800085ff  call    cs:__imp_SetLastError
0x180008605  mov     qword ptr [rdi+10h], 0
0x18000860d  mov     rcx, rdi; this
0x180008610  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180008615  mov     rcx, [rdi+68h]
0x180008619  test    rcx, rcx
0x18000861c  jz      short loc_18000864E
0x18000861e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008625  test    rax, rax
0x180008628  jnz     short loc_180008639
0x18000862a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008631  test    rdx, rdx
0x180008634  jz      short loc_18000864C
0x180008636  mov     rax, rdx
0x180008639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008645  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000864c  jmp     short loc_18000865C
0x18000864e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008655  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000865c  mov     rcx, [rdi+60h]
0x180008660  test    rcx, rcx
0x180008663  jz      short loc_180008678
0x180008665  test    rax, rax
0x180008668  jnz     short loc_180008672
0x18000866a  test    rdx, rdx
0x18000866d  jz      short loc_180008678
0x18000866f  mov     rax, rdx
0x180008672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008677  nop
0x180008678  mov     rbx, [rdi+58h]
0x18000867c  mov     qword ptr [rdi+58h], 0
0x180008684  test    rbx, rbx
0x180008687  jz      short loc_18000869D
0x180008689  call    cs:__imp_GetProcessHeap
0x18000868f  mov     rcx, rax; hHeap
0x180008692  mov     r8, rbx; lpMem
0x180008695  xor     edx, edx; dwFlags
0x180008697  call    cs:__imp_HeapFree
0x18000869d  mov     rbx, [rdi+38h]
0x1800086a1  mov     qword ptr [rdi+38h], 0
0x1800086a9  test    rbx, rbx
0x1800086ac  jz      short loc_1800086C2
0x1800086ae  call    cs:__imp_GetProcessHeap
0x1800086b4  mov     rcx, rax; hHeap
0x1800086b7  mov     r8, rbx; lpMem
0x1800086ba  xor     edx, edx; dwFlags
0x1800086bc  call    cs:__imp_HeapFree
0x1800086c2  mov     rbx, [rdi+10h]
0x1800086c6  test    rbx, rbx
0x1800086c9  jz      short loc_1800086F4
0x1800086cb  xor     r9d, r9d; msWindowLength
0x1800086ce  xor     r8d, r8d; msPeriod
0x1800086d1  xor     edx, edx; pftDueTime
0x1800086d3  mov     rcx, rbx; pti
0x1800086d6  call    cs:__imp_SetThreadpoolTimer
0x1800086dc  mov     edx, 1; fCancelPendingCallbacks
0x1800086e1  mov     rcx, rbx; pti
0x1800086e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800086ea  mov     rcx, rbx; pti
0x1800086ed  call    cs:__imp_CloseThreadpoolTimer
0x1800086f3  nop
0x1800086f4  mov     rbx, [rsp+28h+arg_0]
0x1800086f9  mov     rsi, [rsp+28h+arg_8]
0x1800086fe  add     rsp, 20h
0x180008702  pop     rdi
0x180008703  retn
```
