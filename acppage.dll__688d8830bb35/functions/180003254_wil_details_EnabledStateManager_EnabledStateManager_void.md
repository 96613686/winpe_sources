# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003254`
- end: `0x18000339a`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800167f0`

## callees

- `0x180003254`
- `0x180005dfc`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000332e`
- `KERNEL32!HeapFree` at `0x180003353`
- `KERNEL32!HeapFree` at `0x18000332e`
- `KERNEL32!HeapFree` at `0x180003353`
- `KERNEL32!SetLastError` at `0x1800032a7`
- `KERNEL32!SetLastError` at `0x1800032a7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003296`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000337b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003296`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000337b`
- `KERNEL32!GetLastError` at `0x180003275`
- `KERNEL32!GetLastError` at `0x180003275`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000329f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003384`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000329f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003384`
- `KERNEL32!SetThreadpoolTimer` at `0x180003288`
- `KERNEL32!SetThreadpoolTimer` at `0x18000336d`
- `KERNEL32!SetThreadpoolTimer` at `0x180003288`
- `KERNEL32!SetThreadpoolTimer` at `0x18000336d`
- `KERNEL32!GetProcessHeap` at `0x180003320`
- `KERNEL32!GetProcessHeap` at `0x180003345`
- `KERNEL32!GetProcessHeap` at `0x180003320`
- `KERNEL32!GetProcessHeap` at `0x180003345`

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
0x180003254  mov     [rsp+arg_0], rbx
0x180003259  mov     [rsp+arg_8], rsi
0x18000325e  push    rdi
0x18000325f  sub     rsp, 20h
0x180003263  mov     dword ptr [rcx], 0
0x180003269  mov     rdi, rcx
0x18000326c  mov     rsi, [rcx+10h]
0x180003270  test    rsi, rsi
0x180003273  jz      short loc_1800032AD
0x180003275  call    cs:__imp_GetLastError
0x18000327b  xor     r9d, r9d; msWindowLength
0x18000327e  xor     r8d, r8d; msPeriod
0x180003281  xor     edx, edx; pftDueTime
0x180003283  mov     rcx, rsi; pti
0x180003286  mov     ebx, eax
0x180003288  call    cs:__imp_SetThreadpoolTimer
0x18000328e  mov     edx, 1; fCancelPendingCallbacks
0x180003293  mov     rcx, rsi; pti
0x180003296  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000329c  mov     rcx, rsi; pti
0x18000329f  call    cs:__imp_CloseThreadpoolTimer
0x1800032a5  mov     ecx, ebx; dwErrCode
0x1800032a7  call    cs:__imp_SetLastError
0x1800032ad  mov     rcx, rdi; this
0x1800032b0  mov     qword ptr [rdi+10h], 0
0x1800032b8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800032bd  mov     rcx, [rdi+68h]
0x1800032c1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800032c8  test    rcx, rcx
0x1800032cb  jz      short loc_1800032ED
0x1800032cd  test    rax, rax
0x1800032d0  jnz     short loc_1800032E1
0x1800032d2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800032d9  test    rdx, rdx
0x1800032dc  jz      short loc_1800032F4
0x1800032de  mov     rax, rdx
0x1800032e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800032ed  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800032f4  mov     rcx, [rdi+60h]
0x1800032f8  test    rcx, rcx
0x1800032fb  jz      short loc_18000330F
0x1800032fd  test    rax, rax
0x180003300  jnz     short loc_18000330A
0x180003302  test    rdx, rdx
0x180003305  jz      short loc_18000330F
0x180003307  mov     rax, rdx
0x18000330a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330f  mov     rbx, [rdi+58h]
0x180003313  mov     qword ptr [rdi+58h], 0
0x18000331b  test    rbx, rbx
0x18000331e  jz      short loc_180003334
0x180003320  call    cs:__imp_GetProcessHeap
0x180003326  mov     r8, rbx; lpMem
0x180003329  xor     edx, edx; dwFlags
0x18000332b  mov     rcx, rax; hHeap
0x18000332e  call    cs:__imp_HeapFree
0x180003334  mov     rbx, [rdi+38h]
0x180003338  mov     qword ptr [rdi+38h], 0
0x180003340  test    rbx, rbx
0x180003343  jz      short loc_180003359
0x180003345  call    cs:__imp_GetProcessHeap
0x18000334b  mov     r8, rbx; lpMem
0x18000334e  xor     edx, edx; dwFlags
0x180003350  mov     rcx, rax; hHeap
0x180003353  call    cs:__imp_HeapFree
0x180003359  mov     rbx, [rdi+10h]
0x18000335d  test    rbx, rbx
0x180003360  jz      short loc_18000338A
0x180003362  xor     r9d, r9d; msWindowLength
0x180003365  xor     r8d, r8d; msPeriod
0x180003368  xor     edx, edx; pftDueTime
0x18000336a  mov     rcx, rbx; pti
0x18000336d  call    cs:__imp_SetThreadpoolTimer
0x180003373  mov     edx, 1; fCancelPendingCallbacks
0x180003378  mov     rcx, rbx; pti
0x18000337b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003381  mov     rcx, rbx; pti
0x180003384  call    cs:__imp_CloseThreadpoolTimer
0x18000338a  mov     rbx, [rsp+28h+arg_0]
0x18000338f  mov     rsi, [rsp+28h+arg_8]
0x180003394  add     rsp, 20h
0x180003398  pop     rdi
0x180003399  retn
```
