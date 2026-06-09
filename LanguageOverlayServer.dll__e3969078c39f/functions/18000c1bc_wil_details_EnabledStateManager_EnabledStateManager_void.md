# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000c1bc`
- end: `0x18000c314`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800697c0`

## callees

- `0x18000c1bc`
- `0x18000e768`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c20f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c20f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c1f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c1f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c207`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c207`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c1fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c1fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
0x18000c1bc  mov     [rsp+arg_0], rbx
0x18000c1c1  mov     [rsp+arg_8], rsi
0x18000c1c6  push    rdi
0x18000c1c7  sub     rsp, 20h
0x18000c1cb  mov     rdi, rcx
0x18000c1ce  mov     dword ptr [rcx], 0
0x18000c1d4  mov     rsi, [rcx+10h]
0x18000c1d8  test    rsi, rsi
0x18000c1db  jz      short loc_18000C215
0x18000c1dd  call    cs:__imp_GetLastError
0x18000c1e3  mov     ebx, eax
0x18000c1e5  xor     r9d, r9d; msWindowLength
0x18000c1e8  xor     r8d, r8d; msPeriod
0x18000c1eb  xor     edx, edx; pftDueTime
0x18000c1ed  mov     rcx, rsi; pti
0x18000c1f0  call    cs:__imp_SetThreadpoolTimer
0x18000c1f6  mov     edx, 1; fCancelPendingCallbacks
0x18000c1fb  mov     rcx, rsi; pti
0x18000c1fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c204  mov     rcx, rsi; pti
0x18000c207  call    cs:__imp_CloseThreadpoolTimer
0x18000c20d  mov     ecx, ebx; dwErrCode
0x18000c20f  call    cs:__imp_SetLastError
0x18000c215  mov     qword ptr [rdi+10h], 0
0x18000c21d  mov     rcx, rdi; this
0x18000c220  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000c225  mov     rcx, [rdi+68h]
0x18000c229  test    rcx, rcx
0x18000c22c  jz      short loc_18000C25E
0x18000c22e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c235  test    rax, rax
0x18000c238  jnz     short loc_18000C249
0x18000c23a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c241  test    rdx, rdx
0x18000c244  jz      short loc_18000C25C
0x18000c246  mov     rax, rdx
0x18000c249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c255  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c25c  jmp     short loc_18000C26C
0x18000c25e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c265  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c26c  mov     rcx, [rdi+60h]
0x18000c270  test    rcx, rcx
0x18000c273  jz      short loc_18000C288
0x18000c275  test    rax, rax
0x18000c278  jnz     short loc_18000C282
0x18000c27a  test    rdx, rdx
0x18000c27d  jz      short loc_18000C288
0x18000c27f  mov     rax, rdx
0x18000c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c287  nop
0x18000c288  mov     rbx, [rdi+58h]
0x18000c28c  mov     qword ptr [rdi+58h], 0
0x18000c294  test    rbx, rbx
0x18000c297  jz      short loc_18000C2AD
0x18000c299  call    cs:__imp_GetProcessHeap
0x18000c29f  mov     rcx, rax; hHeap
0x18000c2a2  mov     r8, rbx; lpMem
0x18000c2a5  xor     edx, edx; dwFlags
0x18000c2a7  call    cs:__imp_HeapFree
0x18000c2ad  mov     rbx, [rdi+38h]
0x18000c2b1  mov     qword ptr [rdi+38h], 0
0x18000c2b9  test    rbx, rbx
0x18000c2bc  jz      short loc_18000C2D2
0x18000c2be  call    cs:__imp_GetProcessHeap
0x18000c2c4  mov     rcx, rax; hHeap
0x18000c2c7  mov     r8, rbx; lpMem
0x18000c2ca  xor     edx, edx; dwFlags
0x18000c2cc  call    cs:__imp_HeapFree
0x18000c2d2  mov     rbx, [rdi+10h]
0x18000c2d6  test    rbx, rbx
0x18000c2d9  jz      short loc_18000C304
0x18000c2db  xor     r9d, r9d; msWindowLength
0x18000c2de  xor     r8d, r8d; msPeriod
0x18000c2e1  xor     edx, edx; pftDueTime
0x18000c2e3  mov     rcx, rbx; pti
0x18000c2e6  call    cs:__imp_SetThreadpoolTimer
0x18000c2ec  mov     edx, 1; fCancelPendingCallbacks
0x18000c2f1  mov     rcx, rbx; pti
0x18000c2f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c2fa  mov     rcx, rbx; pti
0x18000c2fd  call    cs:__imp_CloseThreadpoolTimer
0x18000c303  nop
0x18000c304  mov     rbx, [rsp+28h+arg_0]
0x18000c309  mov     rsi, [rsp+28h+arg_8]
0x18000c30e  add     rsp, 20h
0x18000c312  pop     rdi
0x18000c313  retn
```
