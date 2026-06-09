# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000bf90`
- end: `0x18000c0f2`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `354`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18021bb70`

## callees

- `0x18000bf90`
- `0x18000f2a4`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000c077`
- `KERNEL32!GetProcessHeap` at `0x18000c09c`
- `KERNEL32!GetProcessHeap` at `0x18000c077`
- `KERNEL32!GetProcessHeap` at `0x18000c09c`
- `KERNEL32!SetThreadpoolTimer` at `0x18000bfce`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c0c4`
- `KERNEL32!SetThreadpoolTimer` at `0x18000bfce`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c0c4`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000bfe5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c0db`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000bfe5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c0db`
- `KERNEL32!GetLastError` at `0x18000bfbb`
- `KERNEL32!GetLastError` at `0x18000bfbb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000bfdc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c0d2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000bfdc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c0d2`
- `KERNEL32!SetLastError` at `0x18000bfed`
- `KERNEL32!SetLastError` at `0x18000bfed`
- `KERNEL32!HeapFree` at `0x18000c085`
- `KERNEL32!HeapFree` at `0x18000c0aa`
- `KERNEL32!HeapFree` at `0x18000c085`
- `KERNEL32!HeapFree` at `0x18000c0aa`

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
0x18000bf90  push    rdi
0x18000bf92  sub     rsp, 30h
0x18000bf96  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000bf9f  mov     [rsp+38h+arg_0], rbx
0x18000bfa4  mov     [rsp+38h+arg_8], rsi
0x18000bfa9  mov     rdi, rcx
0x18000bfac  mov     dword ptr [rcx], 0
0x18000bfb2  mov     rsi, [rcx+10h]
0x18000bfb6  test    rsi, rsi
0x18000bfb9  jz      short loc_18000BFF3
0x18000bfbb  call    cs:__imp_GetLastError
0x18000bfc1  mov     ebx, eax
0x18000bfc3  xor     r9d, r9d; msWindowLength
0x18000bfc6  xor     r8d, r8d; msPeriod
0x18000bfc9  xor     edx, edx; pftDueTime
0x18000bfcb  mov     rcx, rsi; pti
0x18000bfce  call    cs:__imp_SetThreadpoolTimer
0x18000bfd4  mov     edx, 1; fCancelPendingCallbacks
0x18000bfd9  mov     rcx, rsi; pti
0x18000bfdc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bfe2  mov     rcx, rsi; pti
0x18000bfe5  call    cs:__imp_CloseThreadpoolTimer
0x18000bfeb  mov     ecx, ebx; dwErrCode
0x18000bfed  call    cs:__imp_SetLastError
0x18000bff3  mov     qword ptr [rdi+10h], 0
0x18000bffb  mov     rcx, rdi; this
0x18000bffe  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000c003  mov     rcx, [rdi+68h]
0x18000c007  test    rcx, rcx
0x18000c00a  jz      short loc_18000C03C
0x18000c00c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c013  test    rax, rax
0x18000c016  jnz     short loc_18000C027
0x18000c018  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c01f  test    rdx, rdx
0x18000c022  jz      short loc_18000C03A
0x18000c024  mov     rax, rdx
0x18000c027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c02c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c033  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c03a  jmp     short loc_18000C04A
0x18000c03c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c043  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c04a  mov     rcx, [rdi+60h]
0x18000c04e  test    rcx, rcx
0x18000c051  jz      short loc_18000C066
0x18000c053  test    rax, rax
0x18000c056  jnz     short loc_18000C060
0x18000c058  test    rdx, rdx
0x18000c05b  jz      short loc_18000C066
0x18000c05d  mov     rax, rdx
0x18000c060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c065  nop
0x18000c066  mov     rbx, [rdi+58h]
0x18000c06a  mov     qword ptr [rdi+58h], 0
0x18000c072  test    rbx, rbx
0x18000c075  jz      short loc_18000C08B
0x18000c077  call    cs:__imp_GetProcessHeap
0x18000c07d  mov     rcx, rax; hHeap
0x18000c080  mov     r8, rbx; lpMem
0x18000c083  xor     edx, edx; dwFlags
0x18000c085  call    cs:__imp_HeapFree
0x18000c08b  mov     rbx, [rdi+38h]
0x18000c08f  mov     qword ptr [rdi+38h], 0
0x18000c097  test    rbx, rbx
0x18000c09a  jz      short loc_18000C0B0
0x18000c09c  call    cs:__imp_GetProcessHeap
0x18000c0a2  mov     rcx, rax; hHeap
0x18000c0a5  mov     r8, rbx; lpMem
0x18000c0a8  xor     edx, edx; dwFlags
0x18000c0aa  call    cs:__imp_HeapFree
0x18000c0b0  mov     rbx, [rdi+10h]
0x18000c0b4  test    rbx, rbx
0x18000c0b7  jz      short loc_18000C0E2
0x18000c0b9  xor     r9d, r9d; msWindowLength
0x18000c0bc  xor     r8d, r8d; msPeriod
0x18000c0bf  xor     edx, edx; pftDueTime
0x18000c0c1  mov     rcx, rbx; pti
0x18000c0c4  call    cs:__imp_SetThreadpoolTimer
0x18000c0ca  mov     edx, 1; fCancelPendingCallbacks
0x18000c0cf  mov     rcx, rbx; pti
0x18000c0d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c0d8  mov     rcx, rbx; pti
0x18000c0db  call    cs:__imp_CloseThreadpoolTimer
0x18000c0e1  nop
0x18000c0e2  mov     rbx, [rsp+38h+arg_0]
0x18000c0e7  mov     rsi, [rsp+38h+arg_8]
0x18000c0ec  add     rsp, 30h
0x18000c0f0  pop     rdi
0x18000c0f1  retn
```
