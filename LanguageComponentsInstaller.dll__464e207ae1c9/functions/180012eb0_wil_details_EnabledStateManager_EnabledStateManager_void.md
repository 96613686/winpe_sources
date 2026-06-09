# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180012eb0`
- end: `0x180013008`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029950`

## callees

- `0x180012eb0`
- `0x18001947c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012fc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012fc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ed1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012efb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012ff1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012efb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012ff1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ee4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012fda`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ee4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012fda`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012ef2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012fe8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012ef2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012fe8`

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
0x180012eb0  mov     [rsp+arg_0], rbx
0x180012eb5  mov     [rsp+arg_8], rsi
0x180012eba  push    rdi
0x180012ebb  sub     rsp, 20h
0x180012ebf  mov     rdi, rcx
0x180012ec2  mov     dword ptr [rcx], 0
0x180012ec8  mov     rsi, [rcx+10h]
0x180012ecc  test    rsi, rsi
0x180012ecf  jz      short loc_180012F09
0x180012ed1  call    cs:__imp_GetLastError
0x180012ed7  mov     ebx, eax
0x180012ed9  xor     r9d, r9d; msWindowLength
0x180012edc  xor     r8d, r8d; msPeriod
0x180012edf  xor     edx, edx; pftDueTime
0x180012ee1  mov     rcx, rsi; pti
0x180012ee4  call    cs:__imp_SetThreadpoolTimer
0x180012eea  mov     edx, 1; fCancelPendingCallbacks
0x180012eef  mov     rcx, rsi; pti
0x180012ef2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012ef8  mov     rcx, rsi; pti
0x180012efb  call    cs:__imp_CloseThreadpoolTimer
0x180012f01  mov     ecx, ebx; dwErrCode
0x180012f03  call    cs:__imp_SetLastError
0x180012f09  mov     qword ptr [rdi+10h], 0
0x180012f11  mov     rcx, rdi; this
0x180012f14  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180012f19  mov     rcx, [rdi+68h]
0x180012f1d  test    rcx, rcx
0x180012f20  jz      short loc_180012F52
0x180012f22  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180012f29  test    rax, rax
0x180012f2c  jnz     short loc_180012F3D
0x180012f2e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180012f35  test    rdx, rdx
0x180012f38  jz      short loc_180012F50
0x180012f3a  mov     rax, rdx
0x180012f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f42  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180012f49  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180012f50  jmp     short loc_180012F60
0x180012f52  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180012f59  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180012f60  mov     rcx, [rdi+60h]
0x180012f64  test    rcx, rcx
0x180012f67  jz      short loc_180012F7C
0x180012f69  test    rax, rax
0x180012f6c  jnz     short loc_180012F76
0x180012f6e  test    rdx, rdx
0x180012f71  jz      short loc_180012F7C
0x180012f73  mov     rax, rdx
0x180012f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7b  nop
0x180012f7c  mov     rbx, [rdi+58h]
0x180012f80  mov     qword ptr [rdi+58h], 0
0x180012f88  test    rbx, rbx
0x180012f8b  jz      short loc_180012FA1
0x180012f8d  call    cs:__imp_GetProcessHeap
0x180012f93  mov     rcx, rax; hHeap
0x180012f96  mov     r8, rbx; lpMem
0x180012f99  xor     edx, edx; dwFlags
0x180012f9b  call    cs:__imp_HeapFree
0x180012fa1  mov     rbx, [rdi+38h]
0x180012fa5  mov     qword ptr [rdi+38h], 0
0x180012fad  test    rbx, rbx
0x180012fb0  jz      short loc_180012FC6
0x180012fb2  call    cs:__imp_GetProcessHeap
0x180012fb8  mov     rcx, rax; hHeap
0x180012fbb  mov     r8, rbx; lpMem
0x180012fbe  xor     edx, edx; dwFlags
0x180012fc0  call    cs:__imp_HeapFree
0x180012fc6  mov     rbx, [rdi+10h]
0x180012fca  test    rbx, rbx
0x180012fcd  jz      short loc_180012FF8
0x180012fcf  xor     r9d, r9d; msWindowLength
0x180012fd2  xor     r8d, r8d; msPeriod
0x180012fd5  xor     edx, edx; pftDueTime
0x180012fd7  mov     rcx, rbx; pti
0x180012fda  call    cs:__imp_SetThreadpoolTimer
0x180012fe0  mov     edx, 1; fCancelPendingCallbacks
0x180012fe5  mov     rcx, rbx; pti
0x180012fe8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012fee  mov     rcx, rbx; pti
0x180012ff1  call    cs:__imp_CloseThreadpoolTimer
0x180012ff7  nop
0x180012ff8  mov     rbx, [rsp+28h+arg_0]
0x180012ffd  mov     rsi, [rsp+28h+arg_8]
0x180013002  add     rsp, 20h
0x180013006  pop     rdi
0x180013007  retn
```
