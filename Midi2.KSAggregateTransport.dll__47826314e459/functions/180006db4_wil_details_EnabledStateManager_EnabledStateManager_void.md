# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006db4`
- end: `0x180006f0c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005cd50`

## callees

- `0x180006db4`
- `0x180009f8c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ec4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dd5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006dff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006ef5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006dff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006ef5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006de8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ede`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006de8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ede`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006df6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006eec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006df6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006eec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006db4  mov     [rsp+arg_0], rbx
0x180006db9  mov     [rsp+arg_8], rsi
0x180006dbe  push    rdi
0x180006dbf  sub     rsp, 20h
0x180006dc3  mov     rdi, rcx
0x180006dc6  mov     dword ptr [rcx], 0
0x180006dcc  mov     rsi, [rcx+10h]
0x180006dd0  test    rsi, rsi
0x180006dd3  jz      short loc_180006E0D
0x180006dd5  call    cs:__imp_GetLastError
0x180006ddb  mov     ebx, eax
0x180006ddd  xor     r9d, r9d; msWindowLength
0x180006de0  xor     r8d, r8d; msPeriod
0x180006de3  xor     edx, edx; pftDueTime
0x180006de5  mov     rcx, rsi; pti
0x180006de8  call    cs:__imp_SetThreadpoolTimer
0x180006dee  mov     edx, 1; fCancelPendingCallbacks
0x180006df3  mov     rcx, rsi; pti
0x180006df6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006dfc  mov     rcx, rsi; pti
0x180006dff  call    cs:__imp_CloseThreadpoolTimer
0x180006e05  mov     ecx, ebx; dwErrCode
0x180006e07  call    cs:__imp_SetLastError
0x180006e0d  mov     qword ptr [rdi+10h], 0
0x180006e15  mov     rcx, rdi; this
0x180006e18  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180006e1d  mov     rcx, [rdi+68h]
0x180006e21  test    rcx, rcx
0x180006e24  jz      short loc_180006E56
0x180006e26  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006e2d  test    rax, rax
0x180006e30  jnz     short loc_180006E41
0x180006e32  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006e39  test    rdx, rdx
0x180006e3c  jz      short loc_180006E54
0x180006e3e  mov     rax, rdx
0x180006e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e46  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006e4d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006e54  jmp     short loc_180006E64
0x180006e56  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006e5d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006e64  mov     rcx, [rdi+60h]
0x180006e68  test    rcx, rcx
0x180006e6b  jz      short loc_180006E80
0x180006e6d  test    rax, rax
0x180006e70  jnz     short loc_180006E7A
0x180006e72  test    rdx, rdx
0x180006e75  jz      short loc_180006E80
0x180006e77  mov     rax, rdx
0x180006e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7f  nop
0x180006e80  mov     rbx, [rdi+58h]
0x180006e84  mov     qword ptr [rdi+58h], 0
0x180006e8c  test    rbx, rbx
0x180006e8f  jz      short loc_180006EA5
0x180006e91  call    cs:__imp_GetProcessHeap
0x180006e97  mov     rcx, rax; hHeap
0x180006e9a  mov     r8, rbx; lpMem
0x180006e9d  xor     edx, edx; dwFlags
0x180006e9f  call    cs:__imp_HeapFree
0x180006ea5  mov     rbx, [rdi+38h]
0x180006ea9  mov     qword ptr [rdi+38h], 0
0x180006eb1  test    rbx, rbx
0x180006eb4  jz      short loc_180006ECA
0x180006eb6  call    cs:__imp_GetProcessHeap
0x180006ebc  mov     rcx, rax; hHeap
0x180006ebf  mov     r8, rbx; lpMem
0x180006ec2  xor     edx, edx; dwFlags
0x180006ec4  call    cs:__imp_HeapFree
0x180006eca  mov     rbx, [rdi+10h]
0x180006ece  test    rbx, rbx
0x180006ed1  jz      short loc_180006EFC
0x180006ed3  xor     r9d, r9d; msWindowLength
0x180006ed6  xor     r8d, r8d; msPeriod
0x180006ed9  xor     edx, edx; pftDueTime
0x180006edb  mov     rcx, rbx; pti
0x180006ede  call    cs:__imp_SetThreadpoolTimer
0x180006ee4  mov     edx, 1; fCancelPendingCallbacks
0x180006ee9  mov     rcx, rbx; pti
0x180006eec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006ef2  mov     rcx, rbx; pti
0x180006ef5  call    cs:__imp_CloseThreadpoolTimer
0x180006efb  nop
0x180006efc  mov     rbx, [rsp+28h+arg_0]
0x180006f01  mov     rsi, [rsp+28h+arg_8]
0x180006f06  add     rsp, 20h
0x180006f0a  pop     rdi
0x180006f0b  retn
```
