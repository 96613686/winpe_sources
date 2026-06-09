# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000c780`
- end: `0x14000c8d8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14005c0e0`

## callees

- `0x14000c780`
- `0x140014740`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c86b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c890`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c86b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c890`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c85d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c882`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c85d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c7d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c7cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c8c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c7cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c8c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c7b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c8aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c7b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c8aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c7c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c8b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c7c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c8b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x14000c780  mov     [rsp+arg_0], rbx
0x14000c785  mov     [rsp+arg_8], rsi
0x14000c78a  push    rdi
0x14000c78b  sub     rsp, 20h
0x14000c78f  mov     rdi, rcx
0x14000c792  mov     dword ptr [rcx], 0
0x14000c798  mov     rsi, [rcx+10h]
0x14000c79c  test    rsi, rsi
0x14000c79f  jz      short loc_14000C7D9
0x14000c7a1  call    cs:__imp_GetLastError
0x14000c7a7  mov     ebx, eax
0x14000c7a9  xor     r9d, r9d; msWindowLength
0x14000c7ac  xor     r8d, r8d; msPeriod
0x14000c7af  xor     edx, edx; pftDueTime
0x14000c7b1  mov     rcx, rsi; pti
0x14000c7b4  call    cs:__imp_SetThreadpoolTimer
0x14000c7ba  mov     edx, 1; fCancelPendingCallbacks
0x14000c7bf  mov     rcx, rsi; pti
0x14000c7c2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000c7c8  mov     rcx, rsi; pti
0x14000c7cb  call    cs:__imp_CloseThreadpoolTimer
0x14000c7d1  mov     ecx, ebx; dwErrCode
0x14000c7d3  call    cs:__imp_SetLastError
0x14000c7d9  mov     qword ptr [rdi+10h], 0
0x14000c7e1  mov     rcx, rdi; this
0x14000c7e4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000c7e9  mov     rcx, [rdi+68h]
0x14000c7ed  test    rcx, rcx
0x14000c7f0  jz      short loc_14000C822
0x14000c7f2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000c7f9  test    rax, rax
0x14000c7fc  jnz     short loc_14000C80D
0x14000c7fe  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000c805  test    rdx, rdx
0x14000c808  jz      short loc_14000C820
0x14000c80a  mov     rax, rdx
0x14000c80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c812  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000c819  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000c820  jmp     short loc_14000C830
0x14000c822  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000c829  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000c830  mov     rcx, [rdi+60h]
0x14000c834  test    rcx, rcx
0x14000c837  jz      short loc_14000C84C
0x14000c839  test    rax, rax
0x14000c83c  jnz     short loc_14000C846
0x14000c83e  test    rdx, rdx
0x14000c841  jz      short loc_14000C84C
0x14000c843  mov     rax, rdx
0x14000c846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c84b  nop
0x14000c84c  mov     rbx, [rdi+58h]
0x14000c850  mov     qword ptr [rdi+58h], 0
0x14000c858  test    rbx, rbx
0x14000c85b  jz      short loc_14000C871
0x14000c85d  call    cs:__imp_GetProcessHeap
0x14000c863  mov     rcx, rax; hHeap
0x14000c866  mov     r8, rbx; lpMem
0x14000c869  xor     edx, edx; dwFlags
0x14000c86b  call    cs:__imp_HeapFree
0x14000c871  mov     rbx, [rdi+38h]
0x14000c875  mov     qword ptr [rdi+38h], 0
0x14000c87d  test    rbx, rbx
0x14000c880  jz      short loc_14000C896
0x14000c882  call    cs:__imp_GetProcessHeap
0x14000c888  mov     rcx, rax; hHeap
0x14000c88b  mov     r8, rbx; lpMem
0x14000c88e  xor     edx, edx; dwFlags
0x14000c890  call    cs:__imp_HeapFree
0x14000c896  mov     rbx, [rdi+10h]
0x14000c89a  test    rbx, rbx
0x14000c89d  jz      short loc_14000C8C8
0x14000c89f  xor     r9d, r9d; msWindowLength
0x14000c8a2  xor     r8d, r8d; msPeriod
0x14000c8a5  xor     edx, edx; pftDueTime
0x14000c8a7  mov     rcx, rbx; pti
0x14000c8aa  call    cs:__imp_SetThreadpoolTimer
0x14000c8b0  mov     edx, 1; fCancelPendingCallbacks
0x14000c8b5  mov     rcx, rbx; pti
0x14000c8b8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000c8be  mov     rcx, rbx; pti
0x14000c8c1  call    cs:__imp_CloseThreadpoolTimer
0x14000c8c7  nop
0x14000c8c8  mov     rbx, [rsp+28h+arg_0]
0x14000c8cd  mov     rsi, [rsp+28h+arg_8]
0x14000c8d2  add     rsp, 20h
0x14000c8d6  pop     rdi
0x14000c8d7  retn
```
