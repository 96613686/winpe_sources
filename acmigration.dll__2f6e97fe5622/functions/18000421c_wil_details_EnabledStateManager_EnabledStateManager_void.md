# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000421c`
- end: `0x18000437e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `354`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180068fb0`

## callees

- `0x18000421c`
- `0x180006e64`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004303`
- `KERNEL32!GetProcessHeap` at `0x180004328`
- `KERNEL32!GetProcessHeap` at `0x180004303`
- `KERNEL32!GetProcessHeap` at `0x180004328`
- `KERNEL32!SetThreadpoolTimer` at `0x18000425a`
- `KERNEL32!SetThreadpoolTimer` at `0x180004350`
- `KERNEL32!SetThreadpoolTimer` at `0x18000425a`
- `KERNEL32!SetThreadpoolTimer` at `0x180004350`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004271`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004367`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004271`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004367`
- `KERNEL32!GetLastError` at `0x180004247`
- `KERNEL32!GetLastError` at `0x180004247`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004268`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000435e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004268`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000435e`
- `KERNEL32!SetLastError` at `0x180004279`
- `KERNEL32!SetLastError` at `0x180004279`
- `KERNEL32!HeapFree` at `0x180004311`
- `KERNEL32!HeapFree` at `0x180004336`
- `KERNEL32!HeapFree` at `0x180004311`
- `KERNEL32!HeapFree` at `0x180004336`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  __int64 v4; // rcx
  void (__fastcall *v5)(__int64); // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  struct _TP_TIMER *v12; // rbx

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
  v4 = *((_QWORD *)this + 13);
  if ( !v4 )
  {
    v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v5 = (void (__fastcall *)(__int64))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v5(v4);
  v6 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v5 = (void (__fastcall *)(__int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  v7 = *((_QWORD *)this + 12);
  if ( !v7 )
    goto LABEL_15;
  if ( !v5 )
  {
    if ( !v6 )
      goto LABEL_15;
    v5 = (void (__fastcall *)(__int64))v6;
  }
  v5(v7);
LABEL_15:
  v8 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  v10 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
}

```

## disassembly

```asm
0x18000421c  push    rdi
0x18000421e  sub     rsp, 30h
0x180004222  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000422b  mov     [rsp+38h+arg_0], rbx
0x180004230  mov     [rsp+38h+arg_8], rsi
0x180004235  mov     rdi, rcx
0x180004238  mov     dword ptr [rcx], 0
0x18000423e  mov     rsi, [rcx+10h]
0x180004242  test    rsi, rsi
0x180004245  jz      short loc_18000427F
0x180004247  call    cs:__imp_GetLastError
0x18000424d  mov     ebx, eax
0x18000424f  xor     r9d, r9d; msWindowLength
0x180004252  xor     r8d, r8d; msPeriod
0x180004255  xor     edx, edx; pftDueTime
0x180004257  mov     rcx, rsi; pti
0x18000425a  call    cs:__imp_SetThreadpoolTimer
0x180004260  mov     edx, 1; fCancelPendingCallbacks
0x180004265  mov     rcx, rsi; pti
0x180004268  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000426e  mov     rcx, rsi; pti
0x180004271  call    cs:__imp_CloseThreadpoolTimer
0x180004277  mov     ecx, ebx; dwErrCode
0x180004279  call    cs:__imp_SetLastError
0x18000427f  mov     qword ptr [rdi+10h], 0
0x180004287  mov     rcx, rdi; this
0x18000428a  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000428f  mov     rcx, [rdi+68h]
0x180004293  test    rcx, rcx
0x180004296  jz      short loc_1800042C8
0x180004298  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000429f  test    rax, rax
0x1800042a2  jnz     short loc_1800042B3
0x1800042a4  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800042ab  test    rdx, rdx
0x1800042ae  jz      short loc_1800042C6
0x1800042b0  mov     rax, rdx
0x1800042b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800042bf  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800042c6  jmp     short loc_1800042D6
0x1800042c8  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800042cf  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800042d6  mov     rcx, [rdi+60h]
0x1800042da  test    rcx, rcx
0x1800042dd  jz      short loc_1800042F2
0x1800042df  test    rax, rax
0x1800042e2  jnz     short loc_1800042EC
0x1800042e4  test    rdx, rdx
0x1800042e7  jz      short loc_1800042F2
0x1800042e9  mov     rax, rdx
0x1800042ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f1  nop
0x1800042f2  mov     rbx, [rdi+58h]
0x1800042f6  mov     qword ptr [rdi+58h], 0
0x1800042fe  test    rbx, rbx
0x180004301  jz      short loc_180004317
0x180004303  call    cs:__imp_GetProcessHeap
0x180004309  mov     rcx, rax; hHeap
0x18000430c  mov     r8, rbx; lpMem
0x18000430f  xor     edx, edx; dwFlags
0x180004311  call    cs:__imp_HeapFree
0x180004317  mov     rbx, [rdi+38h]
0x18000431b  mov     qword ptr [rdi+38h], 0
0x180004323  test    rbx, rbx
0x180004326  jz      short loc_18000433C
0x180004328  call    cs:__imp_GetProcessHeap
0x18000432e  mov     rcx, rax; hHeap
0x180004331  mov     r8, rbx; lpMem
0x180004334  xor     edx, edx; dwFlags
0x180004336  call    cs:__imp_HeapFree
0x18000433c  mov     rbx, [rdi+10h]
0x180004340  test    rbx, rbx
0x180004343  jz      short loc_18000436E
0x180004345  xor     r9d, r9d; msWindowLength
0x180004348  xor     r8d, r8d; msPeriod
0x18000434b  xor     edx, edx; pftDueTime
0x18000434d  mov     rcx, rbx; pti
0x180004350  call    cs:__imp_SetThreadpoolTimer
0x180004356  mov     edx, 1; fCancelPendingCallbacks
0x18000435b  mov     rcx, rbx; pti
0x18000435e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004364  mov     rcx, rbx; pti
0x180004367  call    cs:__imp_CloseThreadpoolTimer
0x18000436d  nop
0x18000436e  mov     rbx, [rsp+38h+arg_0]
0x180004373  mov     rsi, [rsp+38h+arg_8]
0x180004378  add     rsp, 30h
0x18000437c  pop     rdi
0x18000437d  retn
```
