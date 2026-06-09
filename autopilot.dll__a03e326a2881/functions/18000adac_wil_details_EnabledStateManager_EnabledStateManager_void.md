# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000adac`
- end: `0x18000af04`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d280`

## callees

- `0x18000adac`
- `0x18000e760`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aeae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aeae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000adee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aee4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000adee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aee4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000adf7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aeed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000adf7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aeed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ade0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aed6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ade0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aed6`

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
0x18000adac  mov     [rsp+arg_0], rbx
0x18000adb1  mov     [rsp+arg_8], rsi
0x18000adb6  push    rdi
0x18000adb7  sub     rsp, 20h
0x18000adbb  mov     rdi, rcx
0x18000adbe  mov     dword ptr [rcx], 0
0x18000adc4  mov     rsi, [rcx+10h]
0x18000adc8  test    rsi, rsi
0x18000adcb  jz      short loc_18000AE05
0x18000adcd  call    cs:__imp_GetLastError
0x18000add3  mov     ebx, eax
0x18000add5  xor     r9d, r9d; msWindowLength
0x18000add8  xor     r8d, r8d; msPeriod
0x18000addb  xor     edx, edx; pftDueTime
0x18000addd  mov     rcx, rsi; pti
0x18000ade0  call    cs:__imp_SetThreadpoolTimer
0x18000ade6  mov     edx, 1; fCancelPendingCallbacks
0x18000adeb  mov     rcx, rsi; pti
0x18000adee  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000adf4  mov     rcx, rsi; pti
0x18000adf7  call    cs:__imp_CloseThreadpoolTimer
0x18000adfd  mov     ecx, ebx; dwErrCode
0x18000adff  call    cs:__imp_SetLastError
0x18000ae05  mov     qword ptr [rdi+10h], 0
0x18000ae0d  mov     rcx, rdi; this
0x18000ae10  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000ae15  mov     rcx, [rdi+68h]
0x18000ae19  test    rcx, rcx
0x18000ae1c  jz      short loc_18000AE4E
0x18000ae1e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ae25  test    rax, rax
0x18000ae28  jnz     short loc_18000AE39
0x18000ae2a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ae31  test    rdx, rdx
0x18000ae34  jz      short loc_18000AE4C
0x18000ae36  mov     rax, rdx
0x18000ae39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ae45  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ae4c  jmp     short loc_18000AE5C
0x18000ae4e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ae55  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ae5c  mov     rcx, [rdi+60h]
0x18000ae60  test    rcx, rcx
0x18000ae63  jz      short loc_18000AE78
0x18000ae65  test    rax, rax
0x18000ae68  jnz     short loc_18000AE72
0x18000ae6a  test    rdx, rdx
0x18000ae6d  jz      short loc_18000AE78
0x18000ae6f  mov     rax, rdx
0x18000ae72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae77  nop
0x18000ae78  mov     rbx, [rdi+58h]
0x18000ae7c  mov     qword ptr [rdi+58h], 0
0x18000ae84  test    rbx, rbx
0x18000ae87  jz      short loc_18000AE9D
0x18000ae89  call    cs:__imp_GetProcessHeap
0x18000ae8f  mov     rcx, rax; hHeap
0x18000ae92  mov     r8, rbx; lpMem
0x18000ae95  xor     edx, edx; dwFlags
0x18000ae97  call    cs:__imp_HeapFree
0x18000ae9d  mov     rbx, [rdi+38h]
0x18000aea1  mov     qword ptr [rdi+38h], 0
0x18000aea9  test    rbx, rbx
0x18000aeac  jz      short loc_18000AEC2
0x18000aeae  call    cs:__imp_GetProcessHeap
0x18000aeb4  mov     rcx, rax; hHeap
0x18000aeb7  mov     r8, rbx; lpMem
0x18000aeba  xor     edx, edx; dwFlags
0x18000aebc  call    cs:__imp_HeapFree
0x18000aec2  mov     rbx, [rdi+10h]
0x18000aec6  test    rbx, rbx
0x18000aec9  jz      short loc_18000AEF4
0x18000aecb  xor     r9d, r9d; msWindowLength
0x18000aece  xor     r8d, r8d; msPeriod
0x18000aed1  xor     edx, edx; pftDueTime
0x18000aed3  mov     rcx, rbx; pti
0x18000aed6  call    cs:__imp_SetThreadpoolTimer
0x18000aedc  mov     edx, 1; fCancelPendingCallbacks
0x18000aee1  mov     rcx, rbx; pti
0x18000aee4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aeea  mov     rcx, rbx; pti
0x18000aeed  call    cs:__imp_CloseThreadpoolTimer
0x18000aef3  nop
0x18000aef4  mov     rbx, [rsp+28h+arg_0]
0x18000aef9  mov     rsi, [rsp+28h+arg_8]
0x18000aefe  add     rsp, 20h
0x18000af02  pop     rdi
0x18000af03  retn
```
