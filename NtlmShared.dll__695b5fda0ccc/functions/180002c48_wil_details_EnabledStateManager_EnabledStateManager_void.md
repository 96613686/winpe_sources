# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180002c48`
- end: `0x180002d8e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c6e0`

## callees

- `0x180002c48`
- `0x18000555c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002c7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002c7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002c8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002d6f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002c8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002d6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002c93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002d78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002c93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002d78`

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
0x180002c48  mov     [rsp+arg_0], rbx
0x180002c4d  mov     [rsp+arg_8], rsi
0x180002c52  push    rdi
0x180002c53  sub     rsp, 20h
0x180002c57  mov     dword ptr [rcx], 0
0x180002c5d  mov     rdi, rcx
0x180002c60  mov     rsi, [rcx+10h]
0x180002c64  test    rsi, rsi
0x180002c67  jz      short loc_180002CA1
0x180002c69  call    cs:__imp_GetLastError
0x180002c6f  xor     r9d, r9d; msWindowLength
0x180002c72  xor     r8d, r8d; msPeriod
0x180002c75  xor     edx, edx; pftDueTime
0x180002c77  mov     rcx, rsi; pti
0x180002c7a  mov     ebx, eax
0x180002c7c  call    cs:__imp_SetThreadpoolTimer
0x180002c82  mov     edx, 1; fCancelPendingCallbacks
0x180002c87  mov     rcx, rsi; pti
0x180002c8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002c90  mov     rcx, rsi; pti
0x180002c93  call    cs:__imp_CloseThreadpoolTimer
0x180002c99  mov     ecx, ebx; dwErrCode
0x180002c9b  call    cs:__imp_SetLastError
0x180002ca1  mov     rcx, rdi; this
0x180002ca4  mov     qword ptr [rdi+10h], 0
0x180002cac  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180002cb1  mov     rcx, [rdi+68h]
0x180002cb5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180002cbc  test    rcx, rcx
0x180002cbf  jz      short loc_180002CE1
0x180002cc1  test    rax, rax
0x180002cc4  jnz     short loc_180002CD5
0x180002cc6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180002ccd  test    rdx, rdx
0x180002cd0  jz      short loc_180002CE8
0x180002cd2  mov     rax, rdx
0x180002cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cda  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180002ce1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180002ce8  mov     rcx, [rdi+60h]
0x180002cec  test    rcx, rcx
0x180002cef  jz      short loc_180002D03
0x180002cf1  test    rax, rax
0x180002cf4  jnz     short loc_180002CFE
0x180002cf6  test    rdx, rdx
0x180002cf9  jz      short loc_180002D03
0x180002cfb  mov     rax, rdx
0x180002cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d03  mov     rbx, [rdi+58h]
0x180002d07  mov     qword ptr [rdi+58h], 0
0x180002d0f  test    rbx, rbx
0x180002d12  jz      short loc_180002D28
0x180002d14  call    cs:__imp_GetProcessHeap
0x180002d1a  mov     r8, rbx; lpMem
0x180002d1d  xor     edx, edx; dwFlags
0x180002d1f  mov     rcx, rax; hHeap
0x180002d22  call    cs:__imp_HeapFree
0x180002d28  mov     rbx, [rdi+38h]
0x180002d2c  mov     qword ptr [rdi+38h], 0
0x180002d34  test    rbx, rbx
0x180002d37  jz      short loc_180002D4D
0x180002d39  call    cs:__imp_GetProcessHeap
0x180002d3f  mov     r8, rbx; lpMem
0x180002d42  xor     edx, edx; dwFlags
0x180002d44  mov     rcx, rax; hHeap
0x180002d47  call    cs:__imp_HeapFree
0x180002d4d  mov     rbx, [rdi+10h]
0x180002d51  test    rbx, rbx
0x180002d54  jz      short loc_180002D7E
0x180002d56  xor     r9d, r9d; msWindowLength
0x180002d59  xor     r8d, r8d; msPeriod
0x180002d5c  xor     edx, edx; pftDueTime
0x180002d5e  mov     rcx, rbx; pti
0x180002d61  call    cs:__imp_SetThreadpoolTimer
0x180002d67  mov     edx, 1; fCancelPendingCallbacks
0x180002d6c  mov     rcx, rbx; pti
0x180002d6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002d75  mov     rcx, rbx; pti
0x180002d78  call    cs:__imp_CloseThreadpoolTimer
0x180002d7e  mov     rbx, [rsp+28h+arg_0]
0x180002d83  mov     rsi, [rsp+28h+arg_8]
0x180002d88  add     rsp, 20h
0x180002d8c  pop     rdi
0x180002d8d  retn
```
