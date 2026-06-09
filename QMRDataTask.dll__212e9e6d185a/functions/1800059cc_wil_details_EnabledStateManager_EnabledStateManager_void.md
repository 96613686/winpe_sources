# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800059cc`
- end: `0x180005b24`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014990`

## callees

- `0x1800059cc`
- `0x18000c1bc`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800059ed`
- `KERNEL32!GetLastError` at `0x1800059ed`
- `KERNEL32!GetProcessHeap` at `0x180005aa9`
- `KERNEL32!GetProcessHeap` at `0x180005ace`
- `KERNEL32!GetProcessHeap` at `0x180005aa9`
- `KERNEL32!GetProcessHeap` at `0x180005ace`
- `KERNEL32!SetThreadpoolTimer` at `0x180005a00`
- `KERNEL32!SetThreadpoolTimer` at `0x180005af6`
- `KERNEL32!SetThreadpoolTimer` at `0x180005a00`
- `KERNEL32!SetThreadpoolTimer` at `0x180005af6`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005a17`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005b0d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005a17`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005b0d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005a0e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005b04`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005a0e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005b04`
- `KERNEL32!HeapFree` at `0x180005ab7`
- `KERNEL32!HeapFree` at `0x180005adc`
- `KERNEL32!HeapFree` at `0x180005ab7`
- `KERNEL32!HeapFree` at `0x180005adc`
- `KERNEL32!SetLastError` at `0x180005a1f`
- `KERNEL32!SetLastError` at `0x180005a1f`

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
0x1800059cc  mov     [rsp+arg_0], rbx
0x1800059d1  mov     [rsp+arg_8], rsi
0x1800059d6  push    rdi
0x1800059d7  sub     rsp, 20h
0x1800059db  mov     rdi, rcx
0x1800059de  mov     dword ptr [rcx], 0
0x1800059e4  mov     rsi, [rcx+10h]
0x1800059e8  test    rsi, rsi
0x1800059eb  jz      short loc_180005A25
0x1800059ed  call    cs:__imp_GetLastError
0x1800059f3  mov     ebx, eax
0x1800059f5  xor     r9d, r9d; msWindowLength
0x1800059f8  xor     r8d, r8d; msPeriod
0x1800059fb  xor     edx, edx; pftDueTime
0x1800059fd  mov     rcx, rsi; pti
0x180005a00  call    cs:__imp_SetThreadpoolTimer
0x180005a06  mov     edx, 1; fCancelPendingCallbacks
0x180005a0b  mov     rcx, rsi; pti
0x180005a0e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a14  mov     rcx, rsi; pti
0x180005a17  call    cs:__imp_CloseThreadpoolTimer
0x180005a1d  mov     ecx, ebx; dwErrCode
0x180005a1f  call    cs:__imp_SetLastError
0x180005a25  mov     qword ptr [rdi+10h], 0
0x180005a2d  mov     rcx, rdi; this
0x180005a30  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180005a35  mov     rcx, [rdi+68h]
0x180005a39  test    rcx, rcx
0x180005a3c  jz      short loc_180005A6E
0x180005a3e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005a45  test    rax, rax
0x180005a48  jnz     short loc_180005A59
0x180005a4a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005a51  test    rdx, rdx
0x180005a54  jz      short loc_180005A6C
0x180005a56  mov     rax, rdx
0x180005a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005a65  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005a6c  jmp     short loc_180005A7C
0x180005a6e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005a75  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005a7c  mov     rcx, [rdi+60h]
0x180005a80  test    rcx, rcx
0x180005a83  jz      short loc_180005A98
0x180005a85  test    rax, rax
0x180005a88  jnz     short loc_180005A92
0x180005a8a  test    rdx, rdx
0x180005a8d  jz      short loc_180005A98
0x180005a8f  mov     rax, rdx
0x180005a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a97  nop
0x180005a98  mov     rbx, [rdi+58h]
0x180005a9c  mov     qword ptr [rdi+58h], 0
0x180005aa4  test    rbx, rbx
0x180005aa7  jz      short loc_180005ABD
0x180005aa9  call    cs:__imp_GetProcessHeap
0x180005aaf  mov     rcx, rax; hHeap
0x180005ab2  mov     r8, rbx; lpMem
0x180005ab5  xor     edx, edx; dwFlags
0x180005ab7  call    cs:__imp_HeapFree
0x180005abd  mov     rbx, [rdi+38h]
0x180005ac1  mov     qword ptr [rdi+38h], 0
0x180005ac9  test    rbx, rbx
0x180005acc  jz      short loc_180005AE2
0x180005ace  call    cs:__imp_GetProcessHeap
0x180005ad4  mov     rcx, rax; hHeap
0x180005ad7  mov     r8, rbx; lpMem
0x180005ada  xor     edx, edx; dwFlags
0x180005adc  call    cs:__imp_HeapFree
0x180005ae2  mov     rbx, [rdi+10h]
0x180005ae6  test    rbx, rbx
0x180005ae9  jz      short loc_180005B14
0x180005aeb  xor     r9d, r9d; msWindowLength
0x180005aee  xor     r8d, r8d; msPeriod
0x180005af1  xor     edx, edx; pftDueTime
0x180005af3  mov     rcx, rbx; pti
0x180005af6  call    cs:__imp_SetThreadpoolTimer
0x180005afc  mov     edx, 1; fCancelPendingCallbacks
0x180005b01  mov     rcx, rbx; pti
0x180005b04  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005b0a  mov     rcx, rbx; pti
0x180005b0d  call    cs:__imp_CloseThreadpoolTimer
0x180005b13  nop
0x180005b14  mov     rbx, [rsp+28h+arg_0]
0x180005b19  mov     rsi, [rsp+28h+arg_8]
0x180005b1e  add     rsp, 20h
0x180005b22  pop     rdi
0x180005b23  retn
```
