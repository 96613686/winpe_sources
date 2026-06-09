# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000d1b0`
- end: `0x14000d2ed`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `317`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140070170`

## callees

- `0x14000c300`
- `0x14000d1b0`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d1fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d1fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d27d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d29e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d27d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d29e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d2ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d2ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d1f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d2dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d1f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d2dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d1ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d2d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d1ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d2d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d1dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d2c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d1dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d2c6`

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
0x14000d1b0  push    rbx
0x14000d1b2  push    rbp
0x14000d1b3  push    rsi
0x14000d1b4  push    rdi
0x14000d1b5  sub     rsp, 28h
0x14000d1b9  mov     rdi, rcx
0x14000d1bc  xor     ebp, ebp
0x14000d1be  mov     [rcx], ebp
0x14000d1c0  mov     rsi, [rcx+10h]
0x14000d1c4  test    rsi, rsi
0x14000d1c7  jz      short loc_14000D201
0x14000d1c9  call    cs:__imp_GetLastError
0x14000d1cf  mov     ebx, eax
0x14000d1d1  xor     r9d, r9d; msWindowLength
0x14000d1d4  xor     r8d, r8d; msPeriod
0x14000d1d7  xor     edx, edx; pftDueTime
0x14000d1d9  mov     rcx, rsi; pti
0x14000d1dc  call    cs:__imp_SetThreadpoolTimer
0x14000d1e2  mov     edx, 1; fCancelPendingCallbacks
0x14000d1e7  mov     rcx, rsi; pti
0x14000d1ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d1f0  mov     rcx, rsi; pti
0x14000d1f3  call    cs:__imp_CloseThreadpoolTimer
0x14000d1f9  mov     ecx, ebx; dwErrCode
0x14000d1fb  call    cs:__imp_SetLastError
0x14000d201  mov     [rdi+10h], rbp
0x14000d205  mov     rcx, rdi; this
0x14000d208  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000d20d  mov     rcx, [rdi+68h]
0x14000d211  test    rcx, rcx
0x14000d214  jz      short loc_14000D246
0x14000d216  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d21d  test    rax, rax
0x14000d220  jnz     short loc_14000D231
0x14000d222  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d229  test    rdx, rdx
0x14000d22c  jz      short loc_14000D244
0x14000d22e  mov     rax, rdx
0x14000d231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d236  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d23d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d244  jmp     short loc_14000D254
0x14000d246  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d24d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d254  mov     rcx, [rdi+60h]
0x14000d258  test    rcx, rcx
0x14000d25b  jz      short loc_14000D270
0x14000d25d  test    rax, rax
0x14000d260  jnz     short loc_14000D26A
0x14000d262  test    rdx, rdx
0x14000d265  jz      short loc_14000D270
0x14000d267  mov     rax, rdx
0x14000d26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d26f  nop
0x14000d270  mov     rbx, [rdi+58h]
0x14000d274  mov     [rdi+58h], rbp
0x14000d278  test    rbx, rbx
0x14000d27b  jz      short loc_14000D291
0x14000d27d  call    cs:__imp_GetProcessHeap
0x14000d283  mov     rcx, rax; hHeap
0x14000d286  mov     r8, rbx; lpMem
0x14000d289  xor     edx, edx; dwFlags
0x14000d28b  call    cs:__imp_HeapFree
0x14000d291  mov     rbx, [rdi+38h]
0x14000d295  mov     [rdi+38h], rbp
0x14000d299  test    rbx, rbx
0x14000d29c  jz      short loc_14000D2B2
0x14000d29e  call    cs:__imp_GetProcessHeap
0x14000d2a4  mov     rcx, rax; hHeap
0x14000d2a7  mov     r8, rbx; lpMem
0x14000d2aa  xor     edx, edx; dwFlags
0x14000d2ac  call    cs:__imp_HeapFree
0x14000d2b2  mov     rbx, [rdi+10h]
0x14000d2b6  test    rbx, rbx
0x14000d2b9  jz      short loc_14000D2E4
0x14000d2bb  xor     r9d, r9d; msWindowLength
0x14000d2be  xor     r8d, r8d; msPeriod
0x14000d2c1  xor     edx, edx; pftDueTime
0x14000d2c3  mov     rcx, rbx; pti
0x14000d2c6  call    cs:__imp_SetThreadpoolTimer
0x14000d2cc  mov     edx, 1; fCancelPendingCallbacks
0x14000d2d1  mov     rcx, rbx; pti
0x14000d2d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d2da  mov     rcx, rbx; pti
0x14000d2dd  call    cs:__imp_CloseThreadpoolTimer
0x14000d2e3  nop
0x14000d2e4  add     rsp, 28h
0x14000d2e8  pop     rdi
0x14000d2e9  pop     rsi
0x14000d2ea  pop     rbp
0x14000d2eb  pop     rbx
0x14000d2ec  retn
```
