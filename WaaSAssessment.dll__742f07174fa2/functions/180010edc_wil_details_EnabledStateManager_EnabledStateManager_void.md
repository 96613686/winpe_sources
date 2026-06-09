# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010edc`
- end: `0x180011034`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a0f0`

## callees

- `0x180010edc`
- `0x180013dd4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010efd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011014`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011014`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010f27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001101d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010f27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001101d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011006`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011006`

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
0x180010edc  mov     [rsp+arg_0], rbx
0x180010ee1  mov     [rsp+arg_8], rsi
0x180010ee6  push    rdi
0x180010ee7  sub     rsp, 20h
0x180010eeb  mov     rdi, rcx
0x180010eee  mov     dword ptr [rcx], 0
0x180010ef4  mov     rsi, [rcx+10h]
0x180010ef8  test    rsi, rsi
0x180010efb  jz      short loc_180010F35
0x180010efd  call    cs:__imp_GetLastError
0x180010f03  mov     ebx, eax
0x180010f05  xor     r9d, r9d; msWindowLength
0x180010f08  xor     r8d, r8d; msPeriod
0x180010f0b  xor     edx, edx; pftDueTime
0x180010f0d  mov     rcx, rsi; pti
0x180010f10  call    cs:__imp_SetThreadpoolTimer
0x180010f16  mov     edx, 1; fCancelPendingCallbacks
0x180010f1b  mov     rcx, rsi; pti
0x180010f1e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010f24  mov     rcx, rsi; pti
0x180010f27  call    cs:__imp_CloseThreadpoolTimer
0x180010f2d  mov     ecx, ebx; dwErrCode
0x180010f2f  call    cs:__imp_SetLastError
0x180010f35  mov     qword ptr [rdi+10h], 0
0x180010f3d  mov     rcx, rdi; this
0x180010f40  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180010f45  mov     rcx, [rdi+68h]
0x180010f49  test    rcx, rcx
0x180010f4c  jz      short loc_180010F7E
0x180010f4e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f55  test    rax, rax
0x180010f58  jnz     short loc_180010F69
0x180010f5a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f61  test    rdx, rdx
0x180010f64  jz      short loc_180010F7C
0x180010f66  mov     rax, rdx
0x180010f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f75  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f7c  jmp     short loc_180010F8C
0x180010f7e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f85  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f8c  mov     rcx, [rdi+60h]
0x180010f90  test    rcx, rcx
0x180010f93  jz      short loc_180010FA8
0x180010f95  test    rax, rax
0x180010f98  jnz     short loc_180010FA2
0x180010f9a  test    rdx, rdx
0x180010f9d  jz      short loc_180010FA8
0x180010f9f  mov     rax, rdx
0x180010fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fa7  nop
0x180010fa8  mov     rbx, [rdi+58h]
0x180010fac  mov     qword ptr [rdi+58h], 0
0x180010fb4  test    rbx, rbx
0x180010fb7  jz      short loc_180010FCD
0x180010fb9  call    cs:__imp_GetProcessHeap
0x180010fbf  mov     rcx, rax; hHeap
0x180010fc2  mov     r8, rbx; lpMem
0x180010fc5  xor     edx, edx; dwFlags
0x180010fc7  call    cs:__imp_HeapFree
0x180010fcd  mov     rbx, [rdi+38h]
0x180010fd1  mov     qword ptr [rdi+38h], 0
0x180010fd9  test    rbx, rbx
0x180010fdc  jz      short loc_180010FF2
0x180010fde  call    cs:__imp_GetProcessHeap
0x180010fe4  mov     rcx, rax; hHeap
0x180010fe7  mov     r8, rbx; lpMem
0x180010fea  xor     edx, edx; dwFlags
0x180010fec  call    cs:__imp_HeapFree
0x180010ff2  mov     rbx, [rdi+10h]
0x180010ff6  test    rbx, rbx
0x180010ff9  jz      short loc_180011024
0x180010ffb  xor     r9d, r9d; msWindowLength
0x180010ffe  xor     r8d, r8d; msPeriod
0x180011001  xor     edx, edx; pftDueTime
0x180011003  mov     rcx, rbx; pti
0x180011006  call    cs:__imp_SetThreadpoolTimer
0x18001100c  mov     edx, 1; fCancelPendingCallbacks
0x180011011  mov     rcx, rbx; pti
0x180011014  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001101a  mov     rcx, rbx; pti
0x18001101d  call    cs:__imp_CloseThreadpoolTimer
0x180011023  nop
0x180011024  mov     rbx, [rsp+28h+arg_0]
0x180011029  mov     rsi, [rsp+28h+arg_8]
0x18001102e  add     rsp, 20h
0x180011032  pop     rdi
0x180011033  retn
```
