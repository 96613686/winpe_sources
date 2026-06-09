# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140007ddc`
- end: `0x140007f34`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e9a0`

## callees

- `0x140007ddc`
- `0x14000a930`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007ec7`
- `KERNEL32!HeapFree` at `0x140007eec`
- `KERNEL32!HeapFree` at `0x140007ec7`
- `KERNEL32!HeapFree` at `0x140007eec`
- `KERNEL32!SetLastError` at `0x140007e2f`
- `KERNEL32!SetLastError` at `0x140007e2f`
- `KERNEL32!GetLastError` at `0x140007dfd`
- `KERNEL32!GetLastError` at `0x140007dfd`
- `KERNEL32!GetProcessHeap` at `0x140007eb9`
- `KERNEL32!GetProcessHeap` at `0x140007ede`
- `KERNEL32!GetProcessHeap` at `0x140007eb9`
- `KERNEL32!GetProcessHeap` at `0x140007ede`
- `KERNEL32!SetThreadpoolTimer` at `0x140007e10`
- `KERNEL32!SetThreadpoolTimer` at `0x140007f06`
- `KERNEL32!SetThreadpoolTimer` at `0x140007e10`
- `KERNEL32!SetThreadpoolTimer` at `0x140007f06`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007e1e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007f14`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007e1e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007f14`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007e27`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007f1d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007e27`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007f1d`

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
0x140007ddc  mov     [rsp+arg_0], rbx
0x140007de1  mov     [rsp+arg_8], rsi
0x140007de6  push    rdi
0x140007de7  sub     rsp, 20h
0x140007deb  mov     rdi, rcx
0x140007dee  mov     dword ptr [rcx], 0
0x140007df4  mov     rsi, [rcx+10h]
0x140007df8  test    rsi, rsi
0x140007dfb  jz      short loc_140007E35
0x140007dfd  call    cs:__imp_GetLastError
0x140007e03  mov     ebx, eax
0x140007e05  xor     r9d, r9d; msWindowLength
0x140007e08  xor     r8d, r8d; msPeriod
0x140007e0b  xor     edx, edx; pftDueTime
0x140007e0d  mov     rcx, rsi; pti
0x140007e10  call    cs:__imp_SetThreadpoolTimer
0x140007e16  mov     edx, 1; fCancelPendingCallbacks
0x140007e1b  mov     rcx, rsi; pti
0x140007e1e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007e24  mov     rcx, rsi; pti
0x140007e27  call    cs:__imp_CloseThreadpoolTimer
0x140007e2d  mov     ecx, ebx; dwErrCode
0x140007e2f  call    cs:__imp_SetLastError
0x140007e35  mov     qword ptr [rdi+10h], 0
0x140007e3d  mov     rcx, rdi; this
0x140007e40  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140007e45  mov     rcx, [rdi+68h]
0x140007e49  test    rcx, rcx
0x140007e4c  jz      short loc_140007E7E
0x140007e4e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140007e55  test    rax, rax
0x140007e58  jnz     short loc_140007E69
0x140007e5a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140007e61  test    rdx, rdx
0x140007e64  jz      short loc_140007E7C
0x140007e66  mov     rax, rdx
0x140007e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e6e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140007e75  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140007e7c  jmp     short loc_140007E8C
0x140007e7e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140007e85  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140007e8c  mov     rcx, [rdi+60h]
0x140007e90  test    rcx, rcx
0x140007e93  jz      short loc_140007EA8
0x140007e95  test    rax, rax
0x140007e98  jnz     short loc_140007EA2
0x140007e9a  test    rdx, rdx
0x140007e9d  jz      short loc_140007EA8
0x140007e9f  mov     rax, rdx
0x140007ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ea7  nop
0x140007ea8  mov     rbx, [rdi+58h]
0x140007eac  mov     qword ptr [rdi+58h], 0
0x140007eb4  test    rbx, rbx
0x140007eb7  jz      short loc_140007ECD
0x140007eb9  call    cs:__imp_GetProcessHeap
0x140007ebf  mov     rcx, rax; hHeap
0x140007ec2  mov     r8, rbx; lpMem
0x140007ec5  xor     edx, edx; dwFlags
0x140007ec7  call    cs:__imp_HeapFree
0x140007ecd  mov     rbx, [rdi+38h]
0x140007ed1  mov     qword ptr [rdi+38h], 0
0x140007ed9  test    rbx, rbx
0x140007edc  jz      short loc_140007EF2
0x140007ede  call    cs:__imp_GetProcessHeap
0x140007ee4  mov     rcx, rax; hHeap
0x140007ee7  mov     r8, rbx; lpMem
0x140007eea  xor     edx, edx; dwFlags
0x140007eec  call    cs:__imp_HeapFree
0x140007ef2  mov     rbx, [rdi+10h]
0x140007ef6  test    rbx, rbx
0x140007ef9  jz      short loc_140007F24
0x140007efb  xor     r9d, r9d; msWindowLength
0x140007efe  xor     r8d, r8d; msPeriod
0x140007f01  xor     edx, edx; pftDueTime
0x140007f03  mov     rcx, rbx; pti
0x140007f06  call    cs:__imp_SetThreadpoolTimer
0x140007f0c  mov     edx, 1; fCancelPendingCallbacks
0x140007f11  mov     rcx, rbx; pti
0x140007f14  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007f1a  mov     rcx, rbx; pti
0x140007f1d  call    cs:__imp_CloseThreadpoolTimer
0x140007f23  nop
0x140007f24  mov     rbx, [rsp+28h+arg_0]
0x140007f29  mov     rsi, [rsp+28h+arg_8]
0x140007f2e  add     rsp, 20h
0x140007f32  pop     rdi
0x140007f33  retn
```
