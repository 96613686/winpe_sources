# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140005dc0`
- end: `0x140005f06`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013770`

## callees

- `0x140005dc0`
- `0x14000fb7c`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ebf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ebf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005de1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e02`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005ee7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e02`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005ee7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005ef0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005ef0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005df4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005ed9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005df4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005ed9`

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
0x140005dc0  mov     [rsp+arg_0], rbx
0x140005dc5  mov     [rsp+arg_8], rsi
0x140005dca  push    rdi
0x140005dcb  sub     rsp, 20h
0x140005dcf  mov     dword ptr [rcx], 0
0x140005dd5  mov     rdi, rcx
0x140005dd8  mov     rsi, [rcx+10h]
0x140005ddc  test    rsi, rsi
0x140005ddf  jz      short loc_140005E19
0x140005de1  call    cs:__imp_GetLastError
0x140005de7  xor     r9d, r9d; msWindowLength
0x140005dea  xor     r8d, r8d; msPeriod
0x140005ded  xor     edx, edx; pftDueTime
0x140005def  mov     rcx, rsi; pti
0x140005df2  mov     ebx, eax
0x140005df4  call    cs:__imp_SetThreadpoolTimer
0x140005dfa  mov     edx, 1; fCancelPendingCallbacks
0x140005dff  mov     rcx, rsi; pti
0x140005e02  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e08  mov     rcx, rsi; pti
0x140005e0b  call    cs:__imp_CloseThreadpoolTimer
0x140005e11  mov     ecx, ebx; dwErrCode
0x140005e13  call    cs:__imp_SetLastError
0x140005e19  mov     rcx, rdi; this
0x140005e1c  mov     qword ptr [rdi+10h], 0
0x140005e24  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140005e29  mov     rcx, [rdi+68h]
0x140005e2d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005e34  test    rcx, rcx
0x140005e37  jz      short loc_140005E59
0x140005e39  test    rax, rax
0x140005e3c  jnz     short loc_140005E4D
0x140005e3e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005e45  test    rdx, rdx
0x140005e48  jz      short loc_140005E60
0x140005e4a  mov     rax, rdx
0x140005e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e52  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005e59  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005e60  mov     rcx, [rdi+60h]
0x140005e64  test    rcx, rcx
0x140005e67  jz      short loc_140005E7B
0x140005e69  test    rax, rax
0x140005e6c  jnz     short loc_140005E76
0x140005e6e  test    rdx, rdx
0x140005e71  jz      short loc_140005E7B
0x140005e73  mov     rax, rdx
0x140005e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e7b  mov     rbx, [rdi+58h]
0x140005e7f  mov     qword ptr [rdi+58h], 0
0x140005e87  test    rbx, rbx
0x140005e8a  jz      short loc_140005EA0
0x140005e8c  call    cs:__imp_GetProcessHeap
0x140005e92  mov     r8, rbx; lpMem
0x140005e95  xor     edx, edx; dwFlags
0x140005e97  mov     rcx, rax; hHeap
0x140005e9a  call    cs:__imp_HeapFree
0x140005ea0  mov     rbx, [rdi+38h]
0x140005ea4  mov     qword ptr [rdi+38h], 0
0x140005eac  test    rbx, rbx
0x140005eaf  jz      short loc_140005EC5
0x140005eb1  call    cs:__imp_GetProcessHeap
0x140005eb7  mov     r8, rbx; lpMem
0x140005eba  xor     edx, edx; dwFlags
0x140005ebc  mov     rcx, rax; hHeap
0x140005ebf  call    cs:__imp_HeapFree
0x140005ec5  mov     rbx, [rdi+10h]
0x140005ec9  test    rbx, rbx
0x140005ecc  jz      short loc_140005EF6
0x140005ece  xor     r9d, r9d; msWindowLength
0x140005ed1  xor     r8d, r8d; msPeriod
0x140005ed4  xor     edx, edx; pftDueTime
0x140005ed6  mov     rcx, rbx; pti
0x140005ed9  call    cs:__imp_SetThreadpoolTimer
0x140005edf  mov     edx, 1; fCancelPendingCallbacks
0x140005ee4  mov     rcx, rbx; pti
0x140005ee7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005eed  mov     rcx, rbx; pti
0x140005ef0  call    cs:__imp_CloseThreadpoolTimer
0x140005ef6  mov     rbx, [rsp+28h+arg_0]
0x140005efb  mov     rsi, [rsp+28h+arg_8]
0x140005f00  add     rsp, 20h
0x140005f04  pop     rdi
0x140005f05  retn
```
