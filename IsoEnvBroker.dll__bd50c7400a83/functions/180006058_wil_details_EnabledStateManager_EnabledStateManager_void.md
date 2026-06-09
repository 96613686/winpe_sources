# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006058`
- end: `0x1800061b0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180067080`

## callees

- `0x180006058`
- `0x180008d3c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006143`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006143`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006079`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800060ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800060ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000608c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006182`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000608c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006182`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800060a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006199`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800060a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006199`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000609a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006190`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000609a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006190`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180006058  mov     [rsp+arg_0], rbx
0x18000605d  mov     [rsp+arg_8], rsi
0x180006062  push    rdi
0x180006063  sub     rsp, 20h
0x180006067  mov     rdi, rcx
0x18000606a  mov     dword ptr [rcx], 0
0x180006070  mov     rsi, [rcx+10h]
0x180006074  test    rsi, rsi
0x180006077  jz      short loc_1800060B1
0x180006079  call    cs:__imp_GetLastError
0x18000607f  mov     ebx, eax
0x180006081  xor     r9d, r9d; msWindowLength
0x180006084  xor     r8d, r8d; msPeriod
0x180006087  xor     edx, edx; pftDueTime
0x180006089  mov     rcx, rsi; pti
0x18000608c  call    cs:__imp_SetThreadpoolTimer
0x180006092  mov     edx, 1; fCancelPendingCallbacks
0x180006097  mov     rcx, rsi; pti
0x18000609a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800060a0  mov     rcx, rsi; pti
0x1800060a3  call    cs:__imp_CloseThreadpoolTimer
0x1800060a9  mov     ecx, ebx; dwErrCode
0x1800060ab  call    cs:__imp_SetLastError
0x1800060b1  mov     qword ptr [rdi+10h], 0
0x1800060b9  mov     rcx, rdi; this
0x1800060bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800060c1  mov     rcx, [rdi+68h]
0x1800060c5  test    rcx, rcx
0x1800060c8  jz      short loc_1800060FA
0x1800060ca  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800060d1  test    rax, rax
0x1800060d4  jnz     short loc_1800060E5
0x1800060d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800060dd  test    rdx, rdx
0x1800060e0  jz      short loc_1800060F8
0x1800060e2  mov     rax, rdx
0x1800060e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800060f1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800060f8  jmp     short loc_180006108
0x1800060fa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006101  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006108  mov     rcx, [rdi+60h]
0x18000610c  test    rcx, rcx
0x18000610f  jz      short loc_180006124
0x180006111  test    rax, rax
0x180006114  jnz     short loc_18000611E
0x180006116  test    rdx, rdx
0x180006119  jz      short loc_180006124
0x18000611b  mov     rax, rdx
0x18000611e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006123  nop
0x180006124  mov     rbx, [rdi+58h]
0x180006128  mov     qword ptr [rdi+58h], 0
0x180006130  test    rbx, rbx
0x180006133  jz      short loc_180006149
0x180006135  call    cs:__imp_GetProcessHeap
0x18000613b  mov     rcx, rax; hHeap
0x18000613e  mov     r8, rbx; lpMem
0x180006141  xor     edx, edx; dwFlags
0x180006143  call    cs:__imp_HeapFree
0x180006149  mov     rbx, [rdi+38h]
0x18000614d  mov     qword ptr [rdi+38h], 0
0x180006155  test    rbx, rbx
0x180006158  jz      short loc_18000616E
0x18000615a  call    cs:__imp_GetProcessHeap
0x180006160  mov     rcx, rax; hHeap
0x180006163  mov     r8, rbx; lpMem
0x180006166  xor     edx, edx; dwFlags
0x180006168  call    cs:__imp_HeapFree
0x18000616e  mov     rbx, [rdi+10h]
0x180006172  test    rbx, rbx
0x180006175  jz      short loc_1800061A0
0x180006177  xor     r9d, r9d; msWindowLength
0x18000617a  xor     r8d, r8d; msPeriod
0x18000617d  xor     edx, edx; pftDueTime
0x18000617f  mov     rcx, rbx; pti
0x180006182  call    cs:__imp_SetThreadpoolTimer
0x180006188  mov     edx, 1; fCancelPendingCallbacks
0x18000618d  mov     rcx, rbx; pti
0x180006190  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006196  mov     rcx, rbx; pti
0x180006199  call    cs:__imp_CloseThreadpoolTimer
0x18000619f  nop
0x1800061a0  mov     rbx, [rsp+28h+arg_0]
0x1800061a5  mov     rsi, [rsp+28h+arg_8]
0x1800061aa  add     rsp, 20h
0x1800061ae  pop     rdi
0x1800061af  retn
```
