# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009da4`
- end: `0x180009efc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180069bf0`

## callees

- `0x180009da4`
- `0x18000b900`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ea6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009def`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009ee5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009def`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009ee5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dd8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ece`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dd8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ece`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009de6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009edc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009de6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009edc`

## pseudocode

```c
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
0x180009da4  mov     [rsp+arg_0], rbx
0x180009da9  mov     [rsp+arg_8], rsi
0x180009dae  push    rdi
0x180009daf  sub     rsp, 20h
0x180009db3  mov     rdi, rcx
0x180009db6  mov     dword ptr [rcx], 0
0x180009dbc  mov     rsi, [rcx+10h]
0x180009dc0  test    rsi, rsi
0x180009dc3  jz      short loc_180009DFD
0x180009dc5  call    cs:__imp_GetLastError
0x180009dcb  mov     ebx, eax
0x180009dcd  xor     r9d, r9d; msWindowLength
0x180009dd0  xor     r8d, r8d; msPeriod
0x180009dd3  xor     edx, edx; pftDueTime
0x180009dd5  mov     rcx, rsi; pti
0x180009dd8  call    cs:__imp_SetThreadpoolTimer
0x180009dde  mov     edx, 1; fCancelPendingCallbacks
0x180009de3  mov     rcx, rsi; pti
0x180009de6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009dec  mov     rcx, rsi; pti
0x180009def  call    cs:__imp_CloseThreadpoolTimer
0x180009df5  mov     ecx, ebx; dwErrCode
0x180009df7  call    cs:__imp_SetLastError
0x180009dfd  mov     qword ptr [rdi+10h], 0
0x180009e05  mov     rcx, rdi; this
0x180009e08  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180009e0d  mov     rcx, [rdi+68h]
0x180009e11  test    rcx, rcx
0x180009e14  jz      short loc_180009E46
0x180009e16  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009e1d  test    rax, rax
0x180009e20  jnz     short loc_180009E31
0x180009e22  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009e29  test    rdx, rdx
0x180009e2c  jz      short loc_180009E44
0x180009e2e  mov     rax, rdx
0x180009e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e36  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009e3d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009e44  jmp     short loc_180009E54
0x180009e46  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009e4d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009e54  mov     rcx, [rdi+60h]
0x180009e58  test    rcx, rcx
0x180009e5b  jz      short loc_180009E70
0x180009e5d  test    rax, rax
0x180009e60  jnz     short loc_180009E6A
0x180009e62  test    rdx, rdx
0x180009e65  jz      short loc_180009E70
0x180009e67  mov     rax, rdx
0x180009e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e6f  nop
0x180009e70  mov     rbx, [rdi+58h]
0x180009e74  mov     qword ptr [rdi+58h], 0
0x180009e7c  test    rbx, rbx
0x180009e7f  jz      short loc_180009E95
0x180009e81  call    cs:__imp_GetProcessHeap
0x180009e87  mov     rcx, rax; hHeap
0x180009e8a  mov     r8, rbx; lpMem
0x180009e8d  xor     edx, edx; dwFlags
0x180009e8f  call    cs:__imp_HeapFree
0x180009e95  mov     rbx, [rdi+38h]
0x180009e99  mov     qword ptr [rdi+38h], 0
0x180009ea1  test    rbx, rbx
0x180009ea4  jz      short loc_180009EBA
0x180009ea6  call    cs:__imp_GetProcessHeap
0x180009eac  mov     rcx, rax; hHeap
0x180009eaf  mov     r8, rbx; lpMem
0x180009eb2  xor     edx, edx; dwFlags
0x180009eb4  call    cs:__imp_HeapFree
0x180009eba  mov     rbx, [rdi+10h]
0x180009ebe  test    rbx, rbx
0x180009ec1  jz      short loc_180009EEC
0x180009ec3  xor     r9d, r9d; msWindowLength
0x180009ec6  xor     r8d, r8d; msPeriod
0x180009ec9  xor     edx, edx; pftDueTime
0x180009ecb  mov     rcx, rbx; pti
0x180009ece  call    cs:__imp_SetThreadpoolTimer
0x180009ed4  mov     edx, 1; fCancelPendingCallbacks
0x180009ed9  mov     rcx, rbx; pti
0x180009edc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ee2  mov     rcx, rbx; pti
0x180009ee5  call    cs:__imp_CloseThreadpoolTimer
0x180009eeb  nop
0x180009eec  mov     rbx, [rsp+28h+arg_0]
0x180009ef1  mov     rsi, [rsp+28h+arg_8]
0x180009ef6  add     rsp, 20h
0x180009efa  pop     rdi
0x180009efb  retn
```
