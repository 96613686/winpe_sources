# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000cc88`
- end: `0x18000cde0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180088450`

## callees

- `0x18000cc88`
- `0x18000ed54`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cca9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ccca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ccca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdc0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ccd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ccd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ccbc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cdb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ccbc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cdb2`

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
0x18000cc88  mov     [rsp+arg_0], rbx
0x18000cc8d  mov     [rsp+arg_8], rsi
0x18000cc92  push    rdi
0x18000cc93  sub     rsp, 20h
0x18000cc97  mov     rdi, rcx
0x18000cc9a  mov     dword ptr [rcx], 0
0x18000cca0  mov     rsi, [rcx+10h]
0x18000cca4  test    rsi, rsi
0x18000cca7  jz      short loc_18000CCE1
0x18000cca9  call    cs:__imp_GetLastError
0x18000ccaf  mov     ebx, eax
0x18000ccb1  xor     r9d, r9d; msWindowLength
0x18000ccb4  xor     r8d, r8d; msPeriod
0x18000ccb7  xor     edx, edx; pftDueTime
0x18000ccb9  mov     rcx, rsi; pti
0x18000ccbc  call    cs:__imp_SetThreadpoolTimer
0x18000ccc2  mov     edx, 1; fCancelPendingCallbacks
0x18000ccc7  mov     rcx, rsi; pti
0x18000ccca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ccd0  mov     rcx, rsi; pti
0x18000ccd3  call    cs:__imp_CloseThreadpoolTimer
0x18000ccd9  mov     ecx, ebx; dwErrCode
0x18000ccdb  call    cs:__imp_SetLastError
0x18000cce1  mov     qword ptr [rdi+10h], 0
0x18000cce9  mov     rcx, rdi; this
0x18000ccec  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000ccf1  mov     rcx, [rdi+68h]
0x18000ccf5  test    rcx, rcx
0x18000ccf8  jz      short loc_18000CD2A
0x18000ccfa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000cd01  test    rax, rax
0x18000cd04  jnz     short loc_18000CD15
0x18000cd06  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000cd0d  test    rdx, rdx
0x18000cd10  jz      short loc_18000CD28
0x18000cd12  mov     rax, rdx
0x18000cd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd1a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000cd21  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000cd28  jmp     short loc_18000CD38
0x18000cd2a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000cd31  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000cd38  mov     rcx, [rdi+60h]
0x18000cd3c  test    rcx, rcx
0x18000cd3f  jz      short loc_18000CD54
0x18000cd41  test    rax, rax
0x18000cd44  jnz     short loc_18000CD4E
0x18000cd46  test    rdx, rdx
0x18000cd49  jz      short loc_18000CD54
0x18000cd4b  mov     rax, rdx
0x18000cd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd53  nop
0x18000cd54  mov     rbx, [rdi+58h]
0x18000cd58  mov     qword ptr [rdi+58h], 0
0x18000cd60  test    rbx, rbx
0x18000cd63  jz      short loc_18000CD79
0x18000cd65  call    cs:__imp_GetProcessHeap
0x18000cd6b  mov     rcx, rax; hHeap
0x18000cd6e  mov     r8, rbx; lpMem
0x18000cd71  xor     edx, edx; dwFlags
0x18000cd73  call    cs:__imp_HeapFree
0x18000cd79  mov     rbx, [rdi+38h]
0x18000cd7d  mov     qword ptr [rdi+38h], 0
0x18000cd85  test    rbx, rbx
0x18000cd88  jz      short loc_18000CD9E
0x18000cd8a  call    cs:__imp_GetProcessHeap
0x18000cd90  mov     rcx, rax; hHeap
0x18000cd93  mov     r8, rbx; lpMem
0x18000cd96  xor     edx, edx; dwFlags
0x18000cd98  call    cs:__imp_HeapFree
0x18000cd9e  mov     rbx, [rdi+10h]
0x18000cda2  test    rbx, rbx
0x18000cda5  jz      short loc_18000CDD0
0x18000cda7  xor     r9d, r9d; msWindowLength
0x18000cdaa  xor     r8d, r8d; msPeriod
0x18000cdad  xor     edx, edx; pftDueTime
0x18000cdaf  mov     rcx, rbx; pti
0x18000cdb2  call    cs:__imp_SetThreadpoolTimer
0x18000cdb8  mov     edx, 1; fCancelPendingCallbacks
0x18000cdbd  mov     rcx, rbx; pti
0x18000cdc0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cdc6  mov     rcx, rbx; pti
0x18000cdc9  call    cs:__imp_CloseThreadpoolTimer
0x18000cdcf  nop
0x18000cdd0  mov     rbx, [rsp+28h+arg_0]
0x18000cdd5  mov     rsi, [rsp+28h+arg_8]
0x18000cdda  add     rsp, 20h
0x18000cdde  pop     rdi
0x18000cddf  retn
```
