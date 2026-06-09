# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010704`
- end: `0x18001085c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006e850`

## callees

- `0x180010704`
- `0x18001624c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010757`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001074f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010845`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001074f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010845`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010738`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001082e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010738`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001082e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010746`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001083c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010746`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001083c`

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
0x180010704  mov     [rsp+arg_0], rbx
0x180010709  mov     [rsp+arg_8], rsi
0x18001070e  push    rdi
0x18001070f  sub     rsp, 20h
0x180010713  mov     rdi, rcx
0x180010716  mov     dword ptr [rcx], 0
0x18001071c  mov     rsi, [rcx+10h]
0x180010720  test    rsi, rsi
0x180010723  jz      short loc_18001075D
0x180010725  call    cs:__imp_GetLastError
0x18001072b  mov     ebx, eax
0x18001072d  xor     r9d, r9d; msWindowLength
0x180010730  xor     r8d, r8d; msPeriod
0x180010733  xor     edx, edx; pftDueTime
0x180010735  mov     rcx, rsi; pti
0x180010738  call    cs:__imp_SetThreadpoolTimer
0x18001073e  mov     edx, 1; fCancelPendingCallbacks
0x180010743  mov     rcx, rsi; pti
0x180010746  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001074c  mov     rcx, rsi; pti
0x18001074f  call    cs:__imp_CloseThreadpoolTimer
0x180010755  mov     ecx, ebx; dwErrCode
0x180010757  call    cs:__imp_SetLastError
0x18001075d  mov     qword ptr [rdi+10h], 0
0x180010765  mov     rcx, rdi; this
0x180010768  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001076d  mov     rcx, [rdi+68h]
0x180010771  test    rcx, rcx
0x180010774  jz      short loc_1800107A6
0x180010776  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001077d  test    rax, rax
0x180010780  jnz     short loc_180010791
0x180010782  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010789  test    rdx, rdx
0x18001078c  jz      short loc_1800107A4
0x18001078e  mov     rax, rdx
0x180010791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010796  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001079d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800107a4  jmp     short loc_1800107B4
0x1800107a6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800107ad  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800107b4  mov     rcx, [rdi+60h]
0x1800107b8  test    rcx, rcx
0x1800107bb  jz      short loc_1800107D0
0x1800107bd  test    rax, rax
0x1800107c0  jnz     short loc_1800107CA
0x1800107c2  test    rdx, rdx
0x1800107c5  jz      short loc_1800107D0
0x1800107c7  mov     rax, rdx
0x1800107ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107cf  nop
0x1800107d0  mov     rbx, [rdi+58h]
0x1800107d4  mov     qword ptr [rdi+58h], 0
0x1800107dc  test    rbx, rbx
0x1800107df  jz      short loc_1800107F5
0x1800107e1  call    cs:__imp_GetProcessHeap
0x1800107e7  mov     rcx, rax; hHeap
0x1800107ea  mov     r8, rbx; lpMem
0x1800107ed  xor     edx, edx; dwFlags
0x1800107ef  call    cs:__imp_HeapFree
0x1800107f5  mov     rbx, [rdi+38h]
0x1800107f9  mov     qword ptr [rdi+38h], 0
0x180010801  test    rbx, rbx
0x180010804  jz      short loc_18001081A
0x180010806  call    cs:__imp_GetProcessHeap
0x18001080c  mov     rcx, rax; hHeap
0x18001080f  mov     r8, rbx; lpMem
0x180010812  xor     edx, edx; dwFlags
0x180010814  call    cs:__imp_HeapFree
0x18001081a  mov     rbx, [rdi+10h]
0x18001081e  test    rbx, rbx
0x180010821  jz      short loc_18001084C
0x180010823  xor     r9d, r9d; msWindowLength
0x180010826  xor     r8d, r8d; msPeriod
0x180010829  xor     edx, edx; pftDueTime
0x18001082b  mov     rcx, rbx; pti
0x18001082e  call    cs:__imp_SetThreadpoolTimer
0x180010834  mov     edx, 1; fCancelPendingCallbacks
0x180010839  mov     rcx, rbx; pti
0x18001083c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010842  mov     rcx, rbx; pti
0x180010845  call    cs:__imp_CloseThreadpoolTimer
0x18001084b  nop
0x18001084c  mov     rbx, [rsp+28h+arg_0]
0x180010851  mov     rsi, [rsp+28h+arg_8]
0x180010856  add     rsp, 20h
0x18001085a  pop     rdi
0x18001085b  retn
```
