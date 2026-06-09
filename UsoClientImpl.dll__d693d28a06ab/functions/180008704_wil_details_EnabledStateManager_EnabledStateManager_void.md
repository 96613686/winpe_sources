# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180008704`
- end: `0x18000885c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180062b20`

## callees

- `0x180008704`
- `0x1800088f8`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000877e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000877e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000878c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000878c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008754`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008754`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008735`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000882e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008735`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000882e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008743`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000883c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008743`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000883c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000874c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008845`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000874c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008845`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x180008704  mov     [rsp+arg_0], rbx
0x180008709  mov     [rsp+arg_8], rsi
0x18000870e  push    rdi
0x18000870f  sub     rsp, 20h
0x180008713  mov     rdi, rcx
0x180008716  mov     byte ptr [rcx], 0
0x180008719  mov     rsi, [rcx+10h]
0x18000871d  test    rsi, rsi
0x180008720  jz      short loc_18000875A
0x180008722  call    cs:__imp_GetLastError
0x180008728  mov     ebx, eax
0x18000872a  xor     r9d, r9d; msWindowLength
0x18000872d  xor     r8d, r8d; msPeriod
0x180008730  xor     edx, edx; pftDueTime
0x180008732  mov     rcx, rsi; pti
0x180008735  call    cs:__imp_SetThreadpoolTimer
0x18000873b  mov     edx, 1; fCancelPendingCallbacks
0x180008740  mov     rcx, rsi; pti
0x180008743  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008749  mov     rcx, rsi; pti
0x18000874c  call    cs:__imp_CloseThreadpoolTimer
0x180008752  mov     ecx, ebx; dwErrCode
0x180008754  call    cs:__imp_SetLastError
0x18000875a  mov     qword ptr [rdi+10h], 0
0x180008762  mov     byte ptr [rdi], 0
0x180008765  mov     rcx, rdi; this
0x180008768  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18000876d  mov     rbx, [rdi+68h]
0x180008771  mov     qword ptr [rdi+68h], 0
0x180008779  test    rbx, rbx
0x18000877c  jz      short loc_180008792
0x18000877e  call    cs:__imp_GetProcessHeap
0x180008784  mov     rcx, rax; hHeap
0x180008787  mov     r8, rbx; lpMem
0x18000878a  xor     edx, edx; dwFlags
0x18000878c  call    cs:__imp_HeapFree
0x180008792  mov     rbx, [rdi+48h]
0x180008796  mov     qword ptr [rdi+48h], 0
0x18000879e  test    rbx, rbx
0x1800087a1  jz      short loc_1800087B7
0x1800087a3  call    cs:__imp_GetProcessHeap
0x1800087a9  mov     rcx, rax; hHeap
0x1800087ac  mov     r8, rbx; lpMem
0x1800087af  xor     edx, edx; dwFlags
0x1800087b1  call    cs:__imp_HeapFree
0x1800087b7  mov     rcx, [rdi+28h]
0x1800087bb  test    rcx, rcx
0x1800087be  jz      short loc_1800087F0
0x1800087c0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800087c7  test    rax, rax
0x1800087ca  jnz     short loc_1800087DB
0x1800087cc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800087d3  test    rdx, rdx
0x1800087d6  jz      short loc_1800087EE
0x1800087d8  mov     rax, rdx
0x1800087db  call    _guard_dispatch_icall
0x1800087e0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800087e7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800087ee  jmp     short loc_1800087FE
0x1800087f0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800087f7  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800087fe  mov     rcx, [rdi+20h]
0x180008802  test    rcx, rcx
0x180008805  jz      short loc_18000881A
0x180008807  test    rax, rax
0x18000880a  jnz     short loc_180008814
0x18000880c  test    rdx, rdx
0x18000880f  jz      short loc_18000881A
0x180008811  mov     rax, rdx
0x180008814  call    _guard_dispatch_icall
0x180008819  nop
0x18000881a  mov     rbx, [rdi+10h]
0x18000881e  test    rbx, rbx
0x180008821  jz      short loc_18000884C
0x180008823  xor     r9d, r9d; msWindowLength
0x180008826  xor     r8d, r8d; msPeriod
0x180008829  xor     edx, edx; pftDueTime
0x18000882b  mov     rcx, rbx; pti
0x18000882e  call    cs:__imp_SetThreadpoolTimer
0x180008834  mov     edx, 1; fCancelPendingCallbacks
0x180008839  mov     rcx, rbx; pti
0x18000883c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008842  mov     rcx, rbx; pti
0x180008845  call    cs:__imp_CloseThreadpoolTimer
0x18000884b  nop
0x18000884c  mov     rbx, [rsp+28h+arg_0]
0x180008851  mov     rsi, [rsp+28h+arg_8]
0x180008856  add     rsp, 20h
0x18000885a  pop     rdi
0x18000885b  retn
```
