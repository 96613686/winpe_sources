# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000a958`
- end: `0x18000aab0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ecc0`

## callees

- `0x18000a958`
- `0x18000c3f8`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a979`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aa99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aa99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a98c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa82`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a98c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a99a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aa90`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a99a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aa90`

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
0x18000a958  mov     [rsp+arg_0], rbx
0x18000a95d  mov     [rsp+arg_8], rsi
0x18000a962  push    rdi
0x18000a963  sub     rsp, 20h
0x18000a967  mov     rdi, rcx
0x18000a96a  mov     dword ptr [rcx], 0
0x18000a970  mov     rsi, [rcx+10h]
0x18000a974  test    rsi, rsi
0x18000a977  jz      short loc_18000A9B1
0x18000a979  call    cs:__imp_GetLastError
0x18000a97f  mov     ebx, eax
0x18000a981  xor     r9d, r9d; msWindowLength
0x18000a984  xor     r8d, r8d; msPeriod
0x18000a987  xor     edx, edx; pftDueTime
0x18000a989  mov     rcx, rsi; pti
0x18000a98c  call    cs:__imp_SetThreadpoolTimer
0x18000a992  mov     edx, 1; fCancelPendingCallbacks
0x18000a997  mov     rcx, rsi; pti
0x18000a99a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a9a0  mov     rcx, rsi; pti
0x18000a9a3  call    cs:__imp_CloseThreadpoolTimer
0x18000a9a9  mov     ecx, ebx; dwErrCode
0x18000a9ab  call    cs:__imp_SetLastError
0x18000a9b1  mov     qword ptr [rdi+10h], 0
0x18000a9b9  mov     rcx, rdi; this
0x18000a9bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000a9c1  mov     rcx, [rdi+68h]
0x18000a9c5  test    rcx, rcx
0x18000a9c8  jz      short loc_18000A9FA
0x18000a9ca  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a9d1  test    rax, rax
0x18000a9d4  jnz     short loc_18000A9E5
0x18000a9d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a9dd  test    rdx, rdx
0x18000a9e0  jz      short loc_18000A9F8
0x18000a9e2  mov     rax, rdx
0x18000a9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a9f1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a9f8  jmp     short loc_18000AA08
0x18000a9fa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000aa01  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000aa08  mov     rcx, [rdi+60h]
0x18000aa0c  test    rcx, rcx
0x18000aa0f  jz      short loc_18000AA24
0x18000aa11  test    rax, rax
0x18000aa14  jnz     short loc_18000AA1E
0x18000aa16  test    rdx, rdx
0x18000aa19  jz      short loc_18000AA24
0x18000aa1b  mov     rax, rdx
0x18000aa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa23  nop
0x18000aa24  mov     rbx, [rdi+58h]
0x18000aa28  mov     qword ptr [rdi+58h], 0
0x18000aa30  test    rbx, rbx
0x18000aa33  jz      short loc_18000AA49
0x18000aa35  call    cs:__imp_GetProcessHeap
0x18000aa3b  mov     rcx, rax; hHeap
0x18000aa3e  mov     r8, rbx; lpMem
0x18000aa41  xor     edx, edx; dwFlags
0x18000aa43  call    cs:__imp_HeapFree
0x18000aa49  mov     rbx, [rdi+38h]
0x18000aa4d  mov     qword ptr [rdi+38h], 0
0x18000aa55  test    rbx, rbx
0x18000aa58  jz      short loc_18000AA6E
0x18000aa5a  call    cs:__imp_GetProcessHeap
0x18000aa60  mov     rcx, rax; hHeap
0x18000aa63  mov     r8, rbx; lpMem
0x18000aa66  xor     edx, edx; dwFlags
0x18000aa68  call    cs:__imp_HeapFree
0x18000aa6e  mov     rbx, [rdi+10h]
0x18000aa72  test    rbx, rbx
0x18000aa75  jz      short loc_18000AAA0
0x18000aa77  xor     r9d, r9d; msWindowLength
0x18000aa7a  xor     r8d, r8d; msPeriod
0x18000aa7d  xor     edx, edx; pftDueTime
0x18000aa7f  mov     rcx, rbx; pti
0x18000aa82  call    cs:__imp_SetThreadpoolTimer
0x18000aa88  mov     edx, 1; fCancelPendingCallbacks
0x18000aa8d  mov     rcx, rbx; pti
0x18000aa90  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aa96  mov     rcx, rbx; pti
0x18000aa99  call    cs:__imp_CloseThreadpoolTimer
0x18000aa9f  nop
0x18000aaa0  mov     rbx, [rsp+28h+arg_0]
0x18000aaa5  mov     rsi, [rsp+28h+arg_8]
0x18000aaaa  add     rsp, 20h
0x18000aaae  pop     rdi
0x18000aaaf  retn
```
