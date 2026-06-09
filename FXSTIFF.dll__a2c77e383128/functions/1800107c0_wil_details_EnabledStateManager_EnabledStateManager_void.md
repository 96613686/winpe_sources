# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800107c0`
- end: `0x18001091a`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `346`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018090`

## callees

- `0x1800107c0`
- `0x180013204`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800108ad`
- `KERNEL32!HeapFree` at `0x1800108d2`
- `KERNEL32!HeapFree` at `0x1800108ad`
- `KERNEL32!HeapFree` at `0x1800108d2`
- `KERNEL32!GetProcessHeap` at `0x18001089f`
- `KERNEL32!GetProcessHeap` at `0x1800108c4`
- `KERNEL32!GetProcessHeap` at `0x18001089f`
- `KERNEL32!GetProcessHeap` at `0x1800108c4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010802`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800108fa`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010802`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800108fa`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001080b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010903`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001080b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010903`
- `KERNEL32!SetThreadpoolTimer` at `0x1800107f4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800108ec`
- `KERNEL32!SetThreadpoolTimer` at `0x1800107f4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800108ec`
- `KERNEL32!GetLastError` at `0x1800107e1`
- `KERNEL32!GetLastError` at `0x1800107e1`
- `KERNEL32!SetLastError` at `0x180010814`
- `KERNEL32!SetLastError` at `0x180010814`

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
0x1800107c0  mov     [rsp+arg_0], rbx
0x1800107c5  mov     [rsp+arg_8], rsi
0x1800107ca  push    rdi
0x1800107cb  sub     rsp, 20h
0x1800107cf  mov     rdi, rcx
0x1800107d2  mov     dword ptr [rcx], 0
0x1800107d8  mov     rsi, [rcx+10h]
0x1800107dc  test    rsi, rsi
0x1800107df  jz      short loc_18001081B
0x1800107e1  call    cs:__imp_GetLastError
0x1800107e7  mov     ebx, eax
0x1800107e9  xor     r9d, r9d; msWindowLength
0x1800107ec  xor     r8d, r8d; msPeriod
0x1800107ef  xor     edx, edx; pftDueTime
0x1800107f1  mov     rcx, rsi; pti
0x1800107f4  call    cs:__imp_SetThreadpoolTimer
0x1800107fa  mov     edx, 1; fCancelPendingCallbacks
0x1800107ff  mov     rcx, rsi; pti
0x180010802  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010808  mov     rcx, rsi; pti
0x18001080b  call    cs:__imp_CloseThreadpoolTimer
0x180010811  nop
0x180010812  mov     ecx, ebx; dwErrCode
0x180010814  call    cs:__imp_SetLastError
0x18001081a  nop
0x18001081b  mov     qword ptr [rdi+10h], 0
0x180010823  mov     rcx, rdi; this
0x180010826  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001082b  mov     rcx, [rdi+68h]
0x18001082f  test    rcx, rcx
0x180010832  jz      short loc_180010864
0x180010834  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001083b  test    rax, rax
0x18001083e  jnz     short loc_18001084F
0x180010840  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010847  test    rdx, rdx
0x18001084a  jz      short loc_180010862
0x18001084c  mov     rax, rdx
0x18001084f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010854  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001085b  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010862  jmp     short loc_180010872
0x180010864  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001086b  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010872  mov     rcx, [rdi+60h]
0x180010876  test    rcx, rcx
0x180010879  jz      short loc_18001088E
0x18001087b  test    rax, rax
0x18001087e  jnz     short loc_180010888
0x180010880  test    rdx, rdx
0x180010883  jz      short loc_18001088E
0x180010885  mov     rax, rdx
0x180010888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088d  nop
0x18001088e  mov     rbx, [rdi+58h]
0x180010892  mov     qword ptr [rdi+58h], 0
0x18001089a  test    rbx, rbx
0x18001089d  jz      short loc_1800108B3
0x18001089f  call    cs:__imp_GetProcessHeap
0x1800108a5  mov     rcx, rax; hHeap
0x1800108a8  mov     r8, rbx; lpMem
0x1800108ab  xor     edx, edx; dwFlags
0x1800108ad  call    cs:__imp_HeapFree
0x1800108b3  mov     rbx, [rdi+38h]
0x1800108b7  mov     qword ptr [rdi+38h], 0
0x1800108bf  test    rbx, rbx
0x1800108c2  jz      short loc_1800108D8
0x1800108c4  call    cs:__imp_GetProcessHeap
0x1800108ca  mov     rcx, rax; hHeap
0x1800108cd  mov     r8, rbx; lpMem
0x1800108d0  xor     edx, edx; dwFlags
0x1800108d2  call    cs:__imp_HeapFree
0x1800108d8  mov     rbx, [rdi+10h]
0x1800108dc  test    rbx, rbx
0x1800108df  jz      short loc_18001090A
0x1800108e1  xor     r9d, r9d; msWindowLength
0x1800108e4  xor     r8d, r8d; msPeriod
0x1800108e7  xor     edx, edx; pftDueTime
0x1800108e9  mov     rcx, rbx; pti
0x1800108ec  call    cs:__imp_SetThreadpoolTimer
0x1800108f2  mov     edx, 1; fCancelPendingCallbacks
0x1800108f7  mov     rcx, rbx; pti
0x1800108fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010900  mov     rcx, rbx; pti
0x180010903  call    cs:__imp_CloseThreadpoolTimer
0x180010909  nop
0x18001090a  mov     rbx, [rsp+28h+arg_0]
0x18001090f  mov     rsi, [rsp+28h+arg_8]
0x180010914  add     rsp, 20h
0x180010918  pop     rdi
0x180010919  retn
```
