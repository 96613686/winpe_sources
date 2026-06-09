# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180004fe4`
- end: `0x18000513c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032030`

## callees

- `0x180004fe4`
- `0x1800088d0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005037`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005005`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005026`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000511c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005026`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000511c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000502f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005125`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000502f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005125`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005018`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000510e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005018`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000510e`

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
0x180004fe4  mov     [rsp+arg_0], rbx
0x180004fe9  mov     [rsp+arg_8], rsi
0x180004fee  push    rdi
0x180004fef  sub     rsp, 20h
0x180004ff3  mov     rdi, rcx
0x180004ff6  mov     dword ptr [rcx], 0
0x180004ffc  mov     rsi, [rcx+10h]
0x180005000  test    rsi, rsi
0x180005003  jz      short loc_18000503D
0x180005005  call    cs:__imp_GetLastError
0x18000500b  mov     ebx, eax
0x18000500d  xor     r9d, r9d; msWindowLength
0x180005010  xor     r8d, r8d; msPeriod
0x180005013  xor     edx, edx; pftDueTime
0x180005015  mov     rcx, rsi; pti
0x180005018  call    cs:__imp_SetThreadpoolTimer
0x18000501e  mov     edx, 1; fCancelPendingCallbacks
0x180005023  mov     rcx, rsi; pti
0x180005026  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000502c  mov     rcx, rsi; pti
0x18000502f  call    cs:__imp_CloseThreadpoolTimer
0x180005035  mov     ecx, ebx; dwErrCode
0x180005037  call    cs:__imp_SetLastError
0x18000503d  mov     qword ptr [rdi+10h], 0
0x180005045  mov     rcx, rdi; this
0x180005048  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000504d  mov     rcx, [rdi+68h]
0x180005051  test    rcx, rcx
0x180005054  jz      short loc_180005086
0x180005056  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000505d  test    rax, rax
0x180005060  jnz     short loc_180005071
0x180005062  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005069  test    rdx, rdx
0x18000506c  jz      short loc_180005084
0x18000506e  mov     rax, rdx
0x180005071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005076  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000507d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005084  jmp     short loc_180005094
0x180005086  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000508d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005094  mov     rcx, [rdi+60h]
0x180005098  test    rcx, rcx
0x18000509b  jz      short loc_1800050B0
0x18000509d  test    rax, rax
0x1800050a0  jnz     short loc_1800050AA
0x1800050a2  test    rdx, rdx
0x1800050a5  jz      short loc_1800050B0
0x1800050a7  mov     rax, rdx
0x1800050aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050af  nop
0x1800050b0  mov     rbx, [rdi+58h]
0x1800050b4  mov     qword ptr [rdi+58h], 0
0x1800050bc  test    rbx, rbx
0x1800050bf  jz      short loc_1800050D5
0x1800050c1  call    cs:__imp_GetProcessHeap
0x1800050c7  mov     rcx, rax; hHeap
0x1800050ca  mov     r8, rbx; lpMem
0x1800050cd  xor     edx, edx; dwFlags
0x1800050cf  call    cs:__imp_HeapFree
0x1800050d5  mov     rbx, [rdi+38h]
0x1800050d9  mov     qword ptr [rdi+38h], 0
0x1800050e1  test    rbx, rbx
0x1800050e4  jz      short loc_1800050FA
0x1800050e6  call    cs:__imp_GetProcessHeap
0x1800050ec  mov     rcx, rax; hHeap
0x1800050ef  mov     r8, rbx; lpMem
0x1800050f2  xor     edx, edx; dwFlags
0x1800050f4  call    cs:__imp_HeapFree
0x1800050fa  mov     rbx, [rdi+10h]
0x1800050fe  test    rbx, rbx
0x180005101  jz      short loc_18000512C
0x180005103  xor     r9d, r9d; msWindowLength
0x180005106  xor     r8d, r8d; msPeriod
0x180005109  xor     edx, edx; pftDueTime
0x18000510b  mov     rcx, rbx; pti
0x18000510e  call    cs:__imp_SetThreadpoolTimer
0x180005114  mov     edx, 1; fCancelPendingCallbacks
0x180005119  mov     rcx, rbx; pti
0x18000511c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005122  mov     rcx, rbx; pti
0x180005125  call    cs:__imp_CloseThreadpoolTimer
0x18000512b  nop
0x18000512c  mov     rbx, [rsp+28h+arg_0]
0x180005131  mov     rsi, [rsp+28h+arg_8]
0x180005136  add     rsp, 20h
0x18000513a  pop     rdi
0x18000513b  retn
```
