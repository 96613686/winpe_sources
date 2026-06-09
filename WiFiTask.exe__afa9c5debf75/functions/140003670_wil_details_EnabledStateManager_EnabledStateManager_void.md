# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003670`
- end: `0x1400037c8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011380`

## callees

- `0x140003670`
- `0x140007dd0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400036b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400037a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400036b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400037a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400036a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000379a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400036a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000379a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400036bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400037b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400036bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400037b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000375b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000375b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000374d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000374d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003772`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003691`

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
0x140003670  mov     [rsp+arg_0], rbx
0x140003675  mov     [rsp+arg_8], rsi
0x14000367a  push    rdi
0x14000367b  sub     rsp, 20h
0x14000367f  mov     rdi, rcx
0x140003682  mov     dword ptr [rcx], 0
0x140003688  mov     rsi, [rcx+10h]
0x14000368c  test    rsi, rsi
0x14000368f  jz      short loc_1400036C9
0x140003691  call    cs:__imp_GetLastError
0x140003697  mov     ebx, eax
0x140003699  xor     r9d, r9d; msWindowLength
0x14000369c  xor     r8d, r8d; msPeriod
0x14000369f  xor     edx, edx; pftDueTime
0x1400036a1  mov     rcx, rsi; pti
0x1400036a4  call    cs:__imp_SetThreadpoolTimer
0x1400036aa  mov     edx, 1; fCancelPendingCallbacks
0x1400036af  mov     rcx, rsi; pti
0x1400036b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400036b8  mov     rcx, rsi; pti
0x1400036bb  call    cs:__imp_CloseThreadpoolTimer
0x1400036c1  mov     ecx, ebx; dwErrCode
0x1400036c3  call    cs:__imp_SetLastError
0x1400036c9  mov     qword ptr [rdi+10h], 0
0x1400036d1  mov     rcx, rdi; this
0x1400036d4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1400036d9  mov     rcx, [rdi+68h]
0x1400036dd  test    rcx, rcx
0x1400036e0  jz      short loc_140003712
0x1400036e2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400036e9  test    rax, rax
0x1400036ec  jnz     short loc_1400036FD
0x1400036ee  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400036f5  test    rdx, rdx
0x1400036f8  jz      short loc_140003710
0x1400036fa  mov     rax, rdx
0x1400036fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003702  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003709  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003710  jmp     short loc_140003720
0x140003712  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003719  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003720  mov     rcx, [rdi+60h]
0x140003724  test    rcx, rcx
0x140003727  jz      short loc_14000373C
0x140003729  test    rax, rax
0x14000372c  jnz     short loc_140003736
0x14000372e  test    rdx, rdx
0x140003731  jz      short loc_14000373C
0x140003733  mov     rax, rdx
0x140003736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000373b  nop
0x14000373c  mov     rbx, [rdi+58h]
0x140003740  mov     qword ptr [rdi+58h], 0
0x140003748  test    rbx, rbx
0x14000374b  jz      short loc_140003761
0x14000374d  call    cs:__imp_GetProcessHeap
0x140003753  mov     rcx, rax; hHeap
0x140003756  mov     r8, rbx; lpMem
0x140003759  xor     edx, edx; dwFlags
0x14000375b  call    cs:__imp_HeapFree
0x140003761  mov     rbx, [rdi+38h]
0x140003765  mov     qword ptr [rdi+38h], 0
0x14000376d  test    rbx, rbx
0x140003770  jz      short loc_140003786
0x140003772  call    cs:__imp_GetProcessHeap
0x140003778  mov     rcx, rax; hHeap
0x14000377b  mov     r8, rbx; lpMem
0x14000377e  xor     edx, edx; dwFlags
0x140003780  call    cs:__imp_HeapFree
0x140003786  mov     rbx, [rdi+10h]
0x14000378a  test    rbx, rbx
0x14000378d  jz      short loc_1400037B8
0x14000378f  xor     r9d, r9d; msWindowLength
0x140003792  xor     r8d, r8d; msPeriod
0x140003795  xor     edx, edx; pftDueTime
0x140003797  mov     rcx, rbx; pti
0x14000379a  call    cs:__imp_SetThreadpoolTimer
0x1400037a0  mov     edx, 1; fCancelPendingCallbacks
0x1400037a5  mov     rcx, rbx; pti
0x1400037a8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400037ae  mov     rcx, rbx; pti
0x1400037b1  call    cs:__imp_CloseThreadpoolTimer
0x1400037b7  nop
0x1400037b8  mov     rbx, [rsp+28h+arg_0]
0x1400037bd  mov     rsi, [rsp+28h+arg_8]
0x1400037c2  add     rsp, 20h
0x1400037c6  pop     rdi
0x1400037c7  retn
```
