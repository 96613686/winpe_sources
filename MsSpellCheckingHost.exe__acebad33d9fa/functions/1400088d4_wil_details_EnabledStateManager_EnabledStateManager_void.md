# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1400088d4`
- end: `0x140008a2c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400126d0`

## callees

- `0x1400088d4`
- `0x14000bd34`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400088f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400088f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008927`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008908`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400089fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008908`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400089fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008916`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008916`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000891f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000891f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a15`

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
0x1400088d4  mov     [rsp+arg_0], rbx
0x1400088d9  mov     [rsp+arg_8], rsi
0x1400088de  push    rdi
0x1400088df  sub     rsp, 20h
0x1400088e3  mov     rdi, rcx
0x1400088e6  mov     dword ptr [rcx], 0
0x1400088ec  mov     rsi, [rcx+10h]
0x1400088f0  test    rsi, rsi
0x1400088f3  jz      short loc_14000892D
0x1400088f5  call    cs:__imp_GetLastError
0x1400088fb  mov     ebx, eax
0x1400088fd  xor     r9d, r9d; msWindowLength
0x140008900  xor     r8d, r8d; msPeriod
0x140008903  xor     edx, edx; pftDueTime
0x140008905  mov     rcx, rsi; pti
0x140008908  call    cs:__imp_SetThreadpoolTimer
0x14000890e  mov     edx, 1; fCancelPendingCallbacks
0x140008913  mov     rcx, rsi; pti
0x140008916  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000891c  mov     rcx, rsi; pti
0x14000891f  call    cs:__imp_CloseThreadpoolTimer
0x140008925  mov     ecx, ebx; dwErrCode
0x140008927  call    cs:__imp_SetLastError
0x14000892d  mov     qword ptr [rdi+10h], 0
0x140008935  mov     rcx, rdi; this
0x140008938  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000893d  mov     rcx, [rdi+68h]
0x140008941  test    rcx, rcx
0x140008944  jz      short loc_140008976
0x140008946  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000894d  test    rax, rax
0x140008950  jnz     short loc_140008961
0x140008952  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008959  test    rdx, rdx
0x14000895c  jz      short loc_140008974
0x14000895e  mov     rax, rdx
0x140008961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008966  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000896d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140008974  jmp     short loc_140008984
0x140008976  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000897d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008984  mov     rcx, [rdi+60h]
0x140008988  test    rcx, rcx
0x14000898b  jz      short loc_1400089A0
0x14000898d  test    rax, rax
0x140008990  jnz     short loc_14000899A
0x140008992  test    rdx, rdx
0x140008995  jz      short loc_1400089A0
0x140008997  mov     rax, rdx
0x14000899a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000899f  nop
0x1400089a0  mov     rbx, [rdi+58h]
0x1400089a4  mov     qword ptr [rdi+58h], 0
0x1400089ac  test    rbx, rbx
0x1400089af  jz      short loc_1400089C5
0x1400089b1  call    cs:__imp_GetProcessHeap
0x1400089b7  mov     rcx, rax; hHeap
0x1400089ba  mov     r8, rbx; lpMem
0x1400089bd  xor     edx, edx; dwFlags
0x1400089bf  call    cs:__imp_HeapFree
0x1400089c5  mov     rbx, [rdi+38h]
0x1400089c9  mov     qword ptr [rdi+38h], 0
0x1400089d1  test    rbx, rbx
0x1400089d4  jz      short loc_1400089EA
0x1400089d6  call    cs:__imp_GetProcessHeap
0x1400089dc  mov     rcx, rax; hHeap
0x1400089df  mov     r8, rbx; lpMem
0x1400089e2  xor     edx, edx; dwFlags
0x1400089e4  call    cs:__imp_HeapFree
0x1400089ea  mov     rbx, [rdi+10h]
0x1400089ee  test    rbx, rbx
0x1400089f1  jz      short loc_140008A1C
0x1400089f3  xor     r9d, r9d; msWindowLength
0x1400089f6  xor     r8d, r8d; msPeriod
0x1400089f9  xor     edx, edx; pftDueTime
0x1400089fb  mov     rcx, rbx; pti
0x1400089fe  call    cs:__imp_SetThreadpoolTimer
0x140008a04  mov     edx, 1; fCancelPendingCallbacks
0x140008a09  mov     rcx, rbx; pti
0x140008a0c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a12  mov     rcx, rbx; pti
0x140008a15  call    cs:__imp_CloseThreadpoolTimer
0x140008a1b  nop
0x140008a1c  mov     rbx, [rsp+28h+arg_0]
0x140008a21  mov     rsi, [rsp+28h+arg_8]
0x140008a26  add     rsp, 20h
0x140008a2a  pop     rdi
0x140008a2b  retn
```
