# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180007f14`
- end: `0x18000806c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006bc30`

## callees

- `0x180007f14`
- `0x180008108`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008055`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008055`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000803e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000803e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000804c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000804c`

## pseudocode

```c
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
0x180007f14  mov     [rsp+arg_0], rbx
0x180007f19  mov     [rsp+arg_8], rsi
0x180007f1e  push    rdi
0x180007f1f  sub     rsp, 20h
0x180007f23  mov     rdi, rcx
0x180007f26  mov     byte ptr [rcx], 0
0x180007f29  mov     rsi, [rcx+10h]
0x180007f2d  test    rsi, rsi
0x180007f30  jz      short loc_180007F6A
0x180007f32  call    cs:__imp_GetLastError
0x180007f38  mov     ebx, eax
0x180007f3a  xor     r9d, r9d; msWindowLength
0x180007f3d  xor     r8d, r8d; msPeriod
0x180007f40  xor     edx, edx; pftDueTime
0x180007f42  mov     rcx, rsi; pti
0x180007f45  call    cs:__imp_SetThreadpoolTimer
0x180007f4b  mov     edx, 1; fCancelPendingCallbacks
0x180007f50  mov     rcx, rsi; pti
0x180007f53  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007f59  mov     rcx, rsi; pti
0x180007f5c  call    cs:__imp_CloseThreadpoolTimer
0x180007f62  mov     ecx, ebx; dwErrCode
0x180007f64  call    cs:__imp_SetLastError
0x180007f6a  mov     qword ptr [rdi+10h], 0
0x180007f72  mov     byte ptr [rdi], 0
0x180007f75  mov     rcx, rdi; this
0x180007f78  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180007f7d  mov     rbx, [rdi+68h]
0x180007f81  mov     qword ptr [rdi+68h], 0
0x180007f89  test    rbx, rbx
0x180007f8c  jz      short loc_180007FA2
0x180007f8e  call    cs:__imp_GetProcessHeap
0x180007f94  mov     rcx, rax; hHeap
0x180007f97  mov     r8, rbx; lpMem
0x180007f9a  xor     edx, edx; dwFlags
0x180007f9c  call    cs:__imp_HeapFree
0x180007fa2  mov     rbx, [rdi+48h]
0x180007fa6  mov     qword ptr [rdi+48h], 0
0x180007fae  test    rbx, rbx
0x180007fb1  jz      short loc_180007FC7
0x180007fb3  call    cs:__imp_GetProcessHeap
0x180007fb9  mov     rcx, rax; hHeap
0x180007fbc  mov     r8, rbx; lpMem
0x180007fbf  xor     edx, edx; dwFlags
0x180007fc1  call    cs:__imp_HeapFree
0x180007fc7  mov     rcx, [rdi+28h]
0x180007fcb  test    rcx, rcx
0x180007fce  jz      short loc_180008000
0x180007fd0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007fd7  test    rax, rax
0x180007fda  jnz     short loc_180007FEB
0x180007fdc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007fe3  test    rdx, rdx
0x180007fe6  jz      short loc_180007FFE
0x180007fe8  mov     rax, rdx
0x180007feb  call    _guard_dispatch_icall
0x180007ff0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007ff7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007ffe  jmp     short loc_18000800E
0x180008000  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008007  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000800e  mov     rcx, [rdi+20h]
0x180008012  test    rcx, rcx
0x180008015  jz      short loc_18000802A
0x180008017  test    rax, rax
0x18000801a  jnz     short loc_180008024
0x18000801c  test    rdx, rdx
0x18000801f  jz      short loc_18000802A
0x180008021  mov     rax, rdx
0x180008024  call    _guard_dispatch_icall
0x180008029  nop
0x18000802a  mov     rbx, [rdi+10h]
0x18000802e  test    rbx, rbx
0x180008031  jz      short loc_18000805C
0x180008033  xor     r9d, r9d; msWindowLength
0x180008036  xor     r8d, r8d; msPeriod
0x180008039  xor     edx, edx; pftDueTime
0x18000803b  mov     rcx, rbx; pti
0x18000803e  call    cs:__imp_SetThreadpoolTimer
0x180008044  mov     edx, 1; fCancelPendingCallbacks
0x180008049  mov     rcx, rbx; pti
0x18000804c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008052  mov     rcx, rbx; pti
0x180008055  call    cs:__imp_CloseThreadpoolTimer
0x18000805b  nop
0x18000805c  mov     rbx, [rsp+28h+arg_0]
0x180008061  mov     rsi, [rsp+28h+arg_8]
0x180008066  add     rsp, 20h
0x18000806a  pop     rdi
0x18000806b  retn
```
