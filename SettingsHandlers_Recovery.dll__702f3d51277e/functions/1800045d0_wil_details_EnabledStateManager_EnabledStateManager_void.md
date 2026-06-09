# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800045d0`
- end: `0x180004728`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002aac0`

## callees

- `0x1800045d0`
- `0x1800073fc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004623`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000461b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004711`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000461b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004711`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004604`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800046fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004604`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800046fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004612`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004708`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004612`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004708`

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
0x1800045d0  mov     [rsp+arg_0], rbx
0x1800045d5  mov     [rsp+arg_8], rsi
0x1800045da  push    rdi
0x1800045db  sub     rsp, 20h
0x1800045df  mov     rdi, rcx
0x1800045e2  mov     dword ptr [rcx], 0
0x1800045e8  mov     rsi, [rcx+10h]
0x1800045ec  test    rsi, rsi
0x1800045ef  jz      short loc_180004629
0x1800045f1  call    cs:__imp_GetLastError
0x1800045f7  mov     ebx, eax
0x1800045f9  xor     r9d, r9d; msWindowLength
0x1800045fc  xor     r8d, r8d; msPeriod
0x1800045ff  xor     edx, edx; pftDueTime
0x180004601  mov     rcx, rsi; pti
0x180004604  call    cs:__imp_SetThreadpoolTimer
0x18000460a  mov     edx, 1; fCancelPendingCallbacks
0x18000460f  mov     rcx, rsi; pti
0x180004612  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004618  mov     rcx, rsi; pti
0x18000461b  call    cs:__imp_CloseThreadpoolTimer
0x180004621  mov     ecx, ebx; dwErrCode
0x180004623  call    cs:__imp_SetLastError
0x180004629  mov     qword ptr [rdi+10h], 0
0x180004631  mov     rcx, rdi; this
0x180004634  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180004639  mov     rcx, [rdi+68h]
0x18000463d  test    rcx, rcx
0x180004640  jz      short loc_180004672
0x180004642  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004649  test    rax, rax
0x18000464c  jnz     short loc_18000465D
0x18000464e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004655  test    rdx, rdx
0x180004658  jz      short loc_180004670
0x18000465a  mov     rax, rdx
0x18000465d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004662  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004669  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004670  jmp     short loc_180004680
0x180004672  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004679  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004680  mov     rcx, [rdi+60h]
0x180004684  test    rcx, rcx
0x180004687  jz      short loc_18000469C
0x180004689  test    rax, rax
0x18000468c  jnz     short loc_180004696
0x18000468e  test    rdx, rdx
0x180004691  jz      short loc_18000469C
0x180004693  mov     rax, rdx
0x180004696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469b  nop
0x18000469c  mov     rbx, [rdi+58h]
0x1800046a0  mov     qword ptr [rdi+58h], 0
0x1800046a8  test    rbx, rbx
0x1800046ab  jz      short loc_1800046C1
0x1800046ad  call    cs:__imp_GetProcessHeap
0x1800046b3  mov     rcx, rax; hHeap
0x1800046b6  mov     r8, rbx; lpMem
0x1800046b9  xor     edx, edx; dwFlags
0x1800046bb  call    cs:__imp_HeapFree
0x1800046c1  mov     rbx, [rdi+38h]
0x1800046c5  mov     qword ptr [rdi+38h], 0
0x1800046cd  test    rbx, rbx
0x1800046d0  jz      short loc_1800046E6
0x1800046d2  call    cs:__imp_GetProcessHeap
0x1800046d8  mov     rcx, rax; hHeap
0x1800046db  mov     r8, rbx; lpMem
0x1800046de  xor     edx, edx; dwFlags
0x1800046e0  call    cs:__imp_HeapFree
0x1800046e6  mov     rbx, [rdi+10h]
0x1800046ea  test    rbx, rbx
0x1800046ed  jz      short loc_180004718
0x1800046ef  xor     r9d, r9d; msWindowLength
0x1800046f2  xor     r8d, r8d; msPeriod
0x1800046f5  xor     edx, edx; pftDueTime
0x1800046f7  mov     rcx, rbx; pti
0x1800046fa  call    cs:__imp_SetThreadpoolTimer
0x180004700  mov     edx, 1; fCancelPendingCallbacks
0x180004705  mov     rcx, rbx; pti
0x180004708  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000470e  mov     rcx, rbx; pti
0x180004711  call    cs:__imp_CloseThreadpoolTimer
0x180004717  nop
0x180004718  mov     rbx, [rsp+28h+arg_0]
0x18000471d  mov     rsi, [rsp+28h+arg_8]
0x180004722  add     rsp, 20h
0x180004726  pop     rdi
0x180004727  retn
```
