# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180005e64`
- end: `0x180005fbc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011160`

## callees

- `0x180005e64`
- `0x180009d70`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005eb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005eaf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005fa5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005eaf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005fa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ea6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ea6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f9c`

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
0x180005e64  mov     [rsp+arg_0], rbx
0x180005e69  mov     [rsp+arg_8], rsi
0x180005e6e  push    rdi
0x180005e6f  sub     rsp, 20h
0x180005e73  mov     rdi, rcx
0x180005e76  mov     dword ptr [rcx], 0
0x180005e7c  mov     rsi, [rcx+10h]
0x180005e80  test    rsi, rsi
0x180005e83  jz      short loc_180005EBD
0x180005e85  call    cs:__imp_GetLastError
0x180005e8b  mov     ebx, eax
0x180005e8d  xor     r9d, r9d; msWindowLength
0x180005e90  xor     r8d, r8d; msPeriod
0x180005e93  xor     edx, edx; pftDueTime
0x180005e95  mov     rcx, rsi; pti
0x180005e98  call    cs:__imp_SetThreadpoolTimer
0x180005e9e  mov     edx, 1; fCancelPendingCallbacks
0x180005ea3  mov     rcx, rsi; pti
0x180005ea6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005eac  mov     rcx, rsi; pti
0x180005eaf  call    cs:__imp_CloseThreadpoolTimer
0x180005eb5  mov     ecx, ebx; dwErrCode
0x180005eb7  call    cs:__imp_SetLastError
0x180005ebd  mov     qword ptr [rdi+10h], 0
0x180005ec5  mov     rcx, rdi; this
0x180005ec8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180005ecd  mov     rcx, [rdi+68h]
0x180005ed1  test    rcx, rcx
0x180005ed4  jz      short loc_180005F06
0x180005ed6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005edd  test    rax, rax
0x180005ee0  jnz     short loc_180005EF1
0x180005ee2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005ee9  test    rdx, rdx
0x180005eec  jz      short loc_180005F04
0x180005eee  mov     rax, rdx
0x180005ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005efd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005f04  jmp     short loc_180005F14
0x180005f06  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005f0d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005f14  mov     rcx, [rdi+60h]
0x180005f18  test    rcx, rcx
0x180005f1b  jz      short loc_180005F30
0x180005f1d  test    rax, rax
0x180005f20  jnz     short loc_180005F2A
0x180005f22  test    rdx, rdx
0x180005f25  jz      short loc_180005F30
0x180005f27  mov     rax, rdx
0x180005f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2f  nop
0x180005f30  mov     rbx, [rdi+58h]
0x180005f34  mov     qword ptr [rdi+58h], 0
0x180005f3c  test    rbx, rbx
0x180005f3f  jz      short loc_180005F55
0x180005f41  call    cs:__imp_GetProcessHeap
0x180005f47  mov     rcx, rax; hHeap
0x180005f4a  mov     r8, rbx; lpMem
0x180005f4d  xor     edx, edx; dwFlags
0x180005f4f  call    cs:__imp_HeapFree
0x180005f55  mov     rbx, [rdi+38h]
0x180005f59  mov     qword ptr [rdi+38h], 0
0x180005f61  test    rbx, rbx
0x180005f64  jz      short loc_180005F7A
0x180005f66  call    cs:__imp_GetProcessHeap
0x180005f6c  mov     rcx, rax; hHeap
0x180005f6f  mov     r8, rbx; lpMem
0x180005f72  xor     edx, edx; dwFlags
0x180005f74  call    cs:__imp_HeapFree
0x180005f7a  mov     rbx, [rdi+10h]
0x180005f7e  test    rbx, rbx
0x180005f81  jz      short loc_180005FAC
0x180005f83  xor     r9d, r9d; msWindowLength
0x180005f86  xor     r8d, r8d; msPeriod
0x180005f89  xor     edx, edx; pftDueTime
0x180005f8b  mov     rcx, rbx; pti
0x180005f8e  call    cs:__imp_SetThreadpoolTimer
0x180005f94  mov     edx, 1; fCancelPendingCallbacks
0x180005f99  mov     rcx, rbx; pti
0x180005f9c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005fa2  mov     rcx, rbx; pti
0x180005fa5  call    cs:__imp_CloseThreadpoolTimer
0x180005fab  nop
0x180005fac  mov     rbx, [rsp+28h+arg_0]
0x180005fb1  mov     rsi, [rsp+28h+arg_8]
0x180005fb6  add     rsp, 20h
0x180005fba  pop     rdi
0x180005fbb  retn
```
