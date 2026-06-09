# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000c9d0`
- end: `0x18000cb28`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800125b0`

## callees

- `0x18000c9d0`
- `0x18000f7d4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000caad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000caad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cad2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cabb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cae0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cabb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cae0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ca1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cb11`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ca1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cb11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cb08`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cb08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cafa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cafa`

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
0x18000c9d0  mov     [rsp+arg_0], rbx
0x18000c9d5  mov     [rsp+arg_8], rsi
0x18000c9da  push    rdi
0x18000c9db  sub     rsp, 20h
0x18000c9df  mov     rdi, rcx
0x18000c9e2  mov     dword ptr [rcx], 0
0x18000c9e8  mov     rsi, [rcx+10h]
0x18000c9ec  test    rsi, rsi
0x18000c9ef  jz      short loc_18000CA29
0x18000c9f1  call    cs:__imp_GetLastError
0x18000c9f7  mov     ebx, eax
0x18000c9f9  xor     r9d, r9d; msWindowLength
0x18000c9fc  xor     r8d, r8d; msPeriod
0x18000c9ff  xor     edx, edx; pftDueTime
0x18000ca01  mov     rcx, rsi; pti
0x18000ca04  call    cs:__imp_SetThreadpoolTimer
0x18000ca0a  mov     edx, 1; fCancelPendingCallbacks
0x18000ca0f  mov     rcx, rsi; pti
0x18000ca12  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ca18  mov     rcx, rsi; pti
0x18000ca1b  call    cs:__imp_CloseThreadpoolTimer
0x18000ca21  mov     ecx, ebx; dwErrCode
0x18000ca23  call    cs:__imp_SetLastError
0x18000ca29  mov     qword ptr [rdi+10h], 0
0x18000ca31  mov     rcx, rdi; this
0x18000ca34  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000ca39  mov     rcx, [rdi+68h]
0x18000ca3d  test    rcx, rcx
0x18000ca40  jz      short loc_18000CA72
0x18000ca42  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ca49  test    rax, rax
0x18000ca4c  jnz     short loc_18000CA5D
0x18000ca4e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ca55  test    rdx, rdx
0x18000ca58  jz      short loc_18000CA70
0x18000ca5a  mov     rax, rdx
0x18000ca5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca62  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ca69  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ca70  jmp     short loc_18000CA80
0x18000ca72  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ca79  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ca80  mov     rcx, [rdi+60h]
0x18000ca84  test    rcx, rcx
0x18000ca87  jz      short loc_18000CA9C
0x18000ca89  test    rax, rax
0x18000ca8c  jnz     short loc_18000CA96
0x18000ca8e  test    rdx, rdx
0x18000ca91  jz      short loc_18000CA9C
0x18000ca93  mov     rax, rdx
0x18000ca96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9b  nop
0x18000ca9c  mov     rbx, [rdi+58h]
0x18000caa0  mov     qword ptr [rdi+58h], 0
0x18000caa8  test    rbx, rbx
0x18000caab  jz      short loc_18000CAC1
0x18000caad  call    cs:__imp_GetProcessHeap
0x18000cab3  mov     rcx, rax; hHeap
0x18000cab6  mov     r8, rbx; lpMem
0x18000cab9  xor     edx, edx; dwFlags
0x18000cabb  call    cs:__imp_HeapFree
0x18000cac1  mov     rbx, [rdi+38h]
0x18000cac5  mov     qword ptr [rdi+38h], 0
0x18000cacd  test    rbx, rbx
0x18000cad0  jz      short loc_18000CAE6
0x18000cad2  call    cs:__imp_GetProcessHeap
0x18000cad8  mov     rcx, rax; hHeap
0x18000cadb  mov     r8, rbx; lpMem
0x18000cade  xor     edx, edx; dwFlags
0x18000cae0  call    cs:__imp_HeapFree
0x18000cae6  mov     rbx, [rdi+10h]
0x18000caea  test    rbx, rbx
0x18000caed  jz      short loc_18000CB18
0x18000caef  xor     r9d, r9d; msWindowLength
0x18000caf2  xor     r8d, r8d; msPeriod
0x18000caf5  xor     edx, edx; pftDueTime
0x18000caf7  mov     rcx, rbx; pti
0x18000cafa  call    cs:__imp_SetThreadpoolTimer
0x18000cb00  mov     edx, 1; fCancelPendingCallbacks
0x18000cb05  mov     rcx, rbx; pti
0x18000cb08  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cb0e  mov     rcx, rbx; pti
0x18000cb11  call    cs:__imp_CloseThreadpoolTimer
0x18000cb17  nop
0x18000cb18  mov     rbx, [rsp+28h+arg_0]
0x18000cb1d  mov     rsi, [rsp+28h+arg_8]
0x18000cb22  add     rsp, 20h
0x18000cb26  pop     rdi
0x18000cb27  retn
```
