# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800058e4`
- end: `0x180005a46`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `354`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032e10`

## callees

- `0x1800058e4`
- `0x180008990`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005941`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005922`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005922`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005939`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005939`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005930`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005930`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a26`

## pseudocode

```c
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
0x1800058e4  push    rdi
0x1800058e6  sub     rsp, 30h
0x1800058ea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800058f3  mov     [rsp+38h+arg_0], rbx
0x1800058f8  mov     [rsp+38h+arg_8], rsi
0x1800058fd  mov     rdi, rcx
0x180005900  mov     dword ptr [rcx], 0
0x180005906  mov     rsi, [rcx+10h]
0x18000590a  test    rsi, rsi
0x18000590d  jz      short loc_180005947
0x18000590f  call    cs:__imp_GetLastError
0x180005915  mov     ebx, eax
0x180005917  xor     r9d, r9d; msWindowLength
0x18000591a  xor     r8d, r8d; msPeriod
0x18000591d  xor     edx, edx; pftDueTime
0x18000591f  mov     rcx, rsi; pti
0x180005922  call    cs:__imp_SetThreadpoolTimer
0x180005928  mov     edx, 1; fCancelPendingCallbacks
0x18000592d  mov     rcx, rsi; pti
0x180005930  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005936  mov     rcx, rsi; pti
0x180005939  call    cs:__imp_CloseThreadpoolTimer
0x18000593f  mov     ecx, ebx; dwErrCode
0x180005941  call    cs:__imp_SetLastError
0x180005947  mov     qword ptr [rdi+10h], 0
0x18000594f  mov     rcx, rdi; this
0x180005952  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180005957  mov     rcx, [rdi+68h]
0x18000595b  test    rcx, rcx
0x18000595e  jz      short loc_180005990
0x180005960  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005967  test    rax, rax
0x18000596a  jnz     short loc_18000597B
0x18000596c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005973  test    rdx, rdx
0x180005976  jz      short loc_18000598E
0x180005978  mov     rax, rdx
0x18000597b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005980  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005987  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000598e  jmp     short loc_18000599E
0x180005990  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005997  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000599e  mov     rcx, [rdi+60h]
0x1800059a2  test    rcx, rcx
0x1800059a5  jz      short loc_1800059BA
0x1800059a7  test    rax, rax
0x1800059aa  jnz     short loc_1800059B4
0x1800059ac  test    rdx, rdx
0x1800059af  jz      short loc_1800059BA
0x1800059b1  mov     rax, rdx
0x1800059b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b9  nop
0x1800059ba  mov     rbx, [rdi+58h]
0x1800059be  mov     qword ptr [rdi+58h], 0
0x1800059c6  test    rbx, rbx
0x1800059c9  jz      short loc_1800059DF
0x1800059cb  call    cs:__imp_GetProcessHeap
0x1800059d1  mov     rcx, rax; hHeap
0x1800059d4  mov     r8, rbx; lpMem
0x1800059d7  xor     edx, edx; dwFlags
0x1800059d9  call    cs:__imp_HeapFree
0x1800059df  mov     rbx, [rdi+38h]
0x1800059e3  mov     qword ptr [rdi+38h], 0
0x1800059eb  test    rbx, rbx
0x1800059ee  jz      short loc_180005A04
0x1800059f0  call    cs:__imp_GetProcessHeap
0x1800059f6  mov     rcx, rax; hHeap
0x1800059f9  mov     r8, rbx; lpMem
0x1800059fc  xor     edx, edx; dwFlags
0x1800059fe  call    cs:__imp_HeapFree
0x180005a04  mov     rbx, [rdi+10h]
0x180005a08  test    rbx, rbx
0x180005a0b  jz      short loc_180005A36
0x180005a0d  xor     r9d, r9d; msWindowLength
0x180005a10  xor     r8d, r8d; msPeriod
0x180005a13  xor     edx, edx; pftDueTime
0x180005a15  mov     rcx, rbx; pti
0x180005a18  call    cs:__imp_SetThreadpoolTimer
0x180005a1e  mov     edx, 1; fCancelPendingCallbacks
0x180005a23  mov     rcx, rbx; pti
0x180005a26  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a2c  mov     rcx, rbx; pti
0x180005a2f  call    cs:__imp_CloseThreadpoolTimer
0x180005a35  nop
0x180005a36  mov     rbx, [rsp+38h+arg_0]
0x180005a3b  mov     rsi, [rsp+38h+arg_8]
0x180005a40  add     rsp, 30h
0x180005a44  pop     rdi
0x180005a45  retn
```
