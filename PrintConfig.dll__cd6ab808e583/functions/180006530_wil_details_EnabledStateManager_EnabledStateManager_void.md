# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006530`
- end: `0x180006692`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `354`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801c1df0`

## callees

- `0x180006530`
- `0x180009994`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180006585`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000667b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180006585`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000667b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000657c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006672`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000657c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006672`
- `KERNEL32!SetThreadpoolTimer` at `0x18000656e`
- `KERNEL32!SetThreadpoolTimer` at `0x180006664`
- `KERNEL32!SetThreadpoolTimer` at `0x18000656e`
- `KERNEL32!SetThreadpoolTimer` at `0x180006664`
- `KERNEL32!GetProcessHeap` at `0x180006617`
- `KERNEL32!GetProcessHeap` at `0x18000663c`
- `KERNEL32!GetProcessHeap` at `0x180006617`
- `KERNEL32!GetProcessHeap` at `0x18000663c`
- `KERNEL32!HeapFree` at `0x180006625`
- `KERNEL32!HeapFree` at `0x18000664a`
- `KERNEL32!HeapFree` at `0x180006625`
- `KERNEL32!HeapFree` at `0x18000664a`
- `KERNEL32!SetLastError` at `0x18000658d`
- `KERNEL32!SetLastError` at `0x18000658d`
- `KERNEL32!GetLastError` at `0x18000655b`
- `KERNEL32!GetLastError` at `0x18000655b`

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
0x180006530  push    rdi
0x180006532  sub     rsp, 30h
0x180006536  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000653f  mov     [rsp+38h+arg_0], rbx
0x180006544  mov     [rsp+38h+arg_8], rsi
0x180006549  mov     rdi, rcx
0x18000654c  mov     dword ptr [rcx], 0
0x180006552  mov     rsi, [rcx+10h]
0x180006556  test    rsi, rsi
0x180006559  jz      short loc_180006593
0x18000655b  call    cs:__imp_GetLastError
0x180006561  mov     ebx, eax
0x180006563  xor     r9d, r9d; msWindowLength
0x180006566  xor     r8d, r8d; msPeriod
0x180006569  xor     edx, edx; pftDueTime
0x18000656b  mov     rcx, rsi; pti
0x18000656e  call    cs:__imp_SetThreadpoolTimer
0x180006574  mov     edx, 1; fCancelPendingCallbacks
0x180006579  mov     rcx, rsi; pti
0x18000657c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006582  mov     rcx, rsi; pti
0x180006585  call    cs:__imp_CloseThreadpoolTimer
0x18000658b  mov     ecx, ebx; dwErrCode
0x18000658d  call    cs:__imp_SetLastError
0x180006593  mov     qword ptr [rdi+10h], 0
0x18000659b  mov     rcx, rdi; this
0x18000659e  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800065a3  mov     rcx, [rdi+68h]
0x1800065a7  test    rcx, rcx
0x1800065aa  jz      short loc_1800065DC
0x1800065ac  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800065b3  test    rax, rax
0x1800065b6  jnz     short loc_1800065C7
0x1800065b8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800065bf  test    rdx, rdx
0x1800065c2  jz      short loc_1800065DA
0x1800065c4  mov     rax, rdx
0x1800065c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065cc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800065d3  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800065da  jmp     short loc_1800065EA
0x1800065dc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800065e3  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800065ea  mov     rcx, [rdi+60h]
0x1800065ee  test    rcx, rcx
0x1800065f1  jz      short loc_180006606
0x1800065f3  test    rax, rax
0x1800065f6  jnz     short loc_180006600
0x1800065f8  test    rdx, rdx
0x1800065fb  jz      short loc_180006606
0x1800065fd  mov     rax, rdx
0x180006600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006605  nop
0x180006606  mov     rbx, [rdi+58h]
0x18000660a  mov     qword ptr [rdi+58h], 0
0x180006612  test    rbx, rbx
0x180006615  jz      short loc_18000662B
0x180006617  call    cs:__imp_GetProcessHeap
0x18000661d  mov     rcx, rax; hHeap
0x180006620  mov     r8, rbx; lpMem
0x180006623  xor     edx, edx; dwFlags
0x180006625  call    cs:__imp_HeapFree
0x18000662b  mov     rbx, [rdi+38h]
0x18000662f  mov     qword ptr [rdi+38h], 0
0x180006637  test    rbx, rbx
0x18000663a  jz      short loc_180006650
0x18000663c  call    cs:__imp_GetProcessHeap
0x180006642  mov     rcx, rax; hHeap
0x180006645  mov     r8, rbx; lpMem
0x180006648  xor     edx, edx; dwFlags
0x18000664a  call    cs:__imp_HeapFree
0x180006650  mov     rbx, [rdi+10h]
0x180006654  test    rbx, rbx
0x180006657  jz      short loc_180006682
0x180006659  xor     r9d, r9d; msWindowLength
0x18000665c  xor     r8d, r8d; msPeriod
0x18000665f  xor     edx, edx; pftDueTime
0x180006661  mov     rcx, rbx; pti
0x180006664  call    cs:__imp_SetThreadpoolTimer
0x18000666a  mov     edx, 1; fCancelPendingCallbacks
0x18000666f  mov     rcx, rbx; pti
0x180006672  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006678  mov     rcx, rbx; pti
0x18000667b  call    cs:__imp_CloseThreadpoolTimer
0x180006681  nop
0x180006682  mov     rbx, [rsp+38h+arg_0]
0x180006687  mov     rsi, [rsp+38h+arg_8]
0x18000668c  add     rsp, 30h
0x180006690  pop     rdi
0x180006691  retn
```
