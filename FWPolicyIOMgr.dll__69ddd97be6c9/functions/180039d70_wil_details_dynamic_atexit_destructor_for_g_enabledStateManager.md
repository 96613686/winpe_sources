# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x180039d70`
- end: `0x180039f0e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800136ac`
- `0x180039d70`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ea7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039db9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039dda`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039ee0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039dda`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039ee0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039dcc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039ed2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039dcc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039ed2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039de3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039ee9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039de3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__()
{
  struct _TP_TIMER *v0; // rdi
  DWORD LastError; // ebx
  void (*v2)(void); // rax
  __int64 v3; // rdx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  struct _TP_TIMER *v8; // rbx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
    return;
  }
  wil::details::g_enabledStateManager = 0;
  v0 = pti;
  if ( pti )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
    SetLastError(LastError);
  }
  pti = 0;
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  if ( !qword_180053448 )
  {
    v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_13;
  }
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_13;
    v2 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v2();
  v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_13:
  if ( qword_180053440 )
  {
    if ( v2 )
    {
LABEL_17:
      v2();
      goto LABEL_18;
    }
    if ( v3 )
    {
      v2 = (void (*)(void))v3;
      goto LABEL_17;
    }
  }
LABEL_18:
  v4 = lpMem;
  lpMem = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = qword_180053418;
  qword_180053418 = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  v8 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
}

```

## disassembly

```asm
0x180039d70  mov     [rsp+arg_0], rbx
0x180039d75  mov     [rsp+arg_8], rsi
0x180039d7a  push    rdi
0x180039d7b  sub     rsp, 20h
0x180039d7f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180039d86  jnz     loc_180039EF1
0x180039d8c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180039d93  test    rax, rax
0x180039d96  jz      short loc_180039DA5
0x180039d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d9d  test    al, al
0x180039d9f  jnz     loc_180039EF1
0x180039da5  xor     esi, esi
0x180039da7  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, esi; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180039dad  mov     rdi, cs:pti
0x180039db4  test    rdi, rdi
0x180039db7  jz      short loc_180039DF1
0x180039db9  call    cs:__imp_GetLastError
0x180039dbf  mov     ebx, eax
0x180039dc1  xor     r9d, r9d; msWindowLength
0x180039dc4  xor     r8d, r8d; msPeriod
0x180039dc7  xor     edx, edx; pftDueTime
0x180039dc9  mov     rcx, rdi; pti
0x180039dcc  call    cs:__imp_SetThreadpoolTimer
0x180039dd2  mov     edx, 1; fCancelPendingCallbacks
0x180039dd7  mov     rcx, rdi; pti
0x180039dda  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180039de0  mov     rcx, rdi; pti
0x180039de3  call    cs:__imp_CloseThreadpoolTimer
0x180039de9  mov     ecx, ebx; dwErrCode
0x180039deb  call    cs:__imp_SetLastError
0x180039df1  mov     cs:pti, rsi
0x180039df8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180039dff  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180039e04  mov     rcx, cs:qword_180053448
0x180039e0b  test    rcx, rcx
0x180039e0e  jz      short loc_180039E40
0x180039e10  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180039e17  test    rax, rax
0x180039e1a  jnz     short loc_180039E2B
0x180039e1c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180039e23  test    rdx, rdx
0x180039e26  jz      short loc_180039E3E
0x180039e28  mov     rax, rdx
0x180039e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e30  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180039e37  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180039e3e  jmp     short loc_180039E4E
0x180039e40  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180039e47  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180039e4e  mov     rcx, cs:qword_180053440
0x180039e55  test    rcx, rcx
0x180039e58  jz      short loc_180039E6D
0x180039e5a  test    rax, rax
0x180039e5d  jnz     short loc_180039E67
0x180039e5f  test    rdx, rdx
0x180039e62  jz      short loc_180039E6D
0x180039e64  mov     rax, rdx
0x180039e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e6c  nop
0x180039e6d  mov     rbx, cs:lpMem
0x180039e74  mov     cs:lpMem, rsi
0x180039e7b  test    rbx, rbx
0x180039e7e  jz      short loc_180039E94
0x180039e80  call    cs:__imp_GetProcessHeap
0x180039e86  mov     rcx, rax; hHeap
0x180039e89  mov     r8, rbx; lpMem
0x180039e8c  xor     edx, edx; dwFlags
0x180039e8e  call    cs:__imp_HeapFree
0x180039e94  mov     rbx, cs:qword_180053418
0x180039e9b  mov     cs:qword_180053418, rsi
0x180039ea2  test    rbx, rbx
0x180039ea5  jz      short loc_180039EBB
0x180039ea7  call    cs:__imp_GetProcessHeap
0x180039ead  mov     rcx, rax; hHeap
0x180039eb0  mov     r8, rbx; lpMem
0x180039eb3  xor     edx, edx; dwFlags
0x180039eb5  call    cs:__imp_HeapFree
0x180039ebb  mov     rbx, cs:pti
0x180039ec2  test    rbx, rbx
0x180039ec5  jz      short loc_180039EFE
0x180039ec7  xor     r9d, r9d; msWindowLength
0x180039eca  xor     r8d, r8d; msPeriod
0x180039ecd  xor     edx, edx; pftDueTime
0x180039ecf  mov     rcx, rbx; pti
0x180039ed2  call    cs:__imp_SetThreadpoolTimer
0x180039ed8  mov     edx, 1; fCancelPendingCallbacks
0x180039edd  mov     rcx, rbx; pti
0x180039ee0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180039ee6  mov     rcx, rbx; pti
0x180039ee9  call    cs:__imp_CloseThreadpoolTimer
0x180039eef  jmp     short loc_180039EFE
0x180039ef1  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180039ef8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180039efd  nop
0x180039efe  mov     rbx, [rsp+28h+arg_0]
0x180039f03  mov     rsi, [rsp+28h+arg_8]
0x180039f08  add     rsp, 20h
0x180039f0c  pop     rdi
0x180039f0d  retn
```
