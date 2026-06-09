# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x18005c390`
- end: `0x18005c52e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ad60`
- `0x18005c390`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c40b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c40b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c3ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c4f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c3ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c4f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005c403`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005c509`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005c403`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005c509`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005c3fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005c500`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005c3fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005c500`

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
  if ( !qword_180097DC8 )
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
  if ( qword_180097DC0 )
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
  v6 = qword_180097D98;
  qword_180097D98 = 0;
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
0x18005c390  mov     [rsp+arg_0], rbx
0x18005c395  mov     [rsp+arg_8], rsi
0x18005c39a  push    rdi
0x18005c39b  sub     rsp, 20h
0x18005c39f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18005c3a6  jnz     loc_18005C511
0x18005c3ac  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18005c3b3  test    rax, rax
0x18005c3b6  jz      short loc_18005C3C5
0x18005c3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3bd  test    al, al
0x18005c3bf  jnz     loc_18005C511
0x18005c3c5  xor     esi, esi
0x18005c3c7  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, esi; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005c3cd  mov     rdi, cs:pti
0x18005c3d4  test    rdi, rdi
0x18005c3d7  jz      short loc_18005C411
0x18005c3d9  call    cs:__imp_GetLastError
0x18005c3df  mov     ebx, eax
0x18005c3e1  xor     r9d, r9d; msWindowLength
0x18005c3e4  xor     r8d, r8d; msPeriod
0x18005c3e7  xor     edx, edx; pftDueTime
0x18005c3e9  mov     rcx, rdi; pti
0x18005c3ec  call    cs:__imp_SetThreadpoolTimer
0x18005c3f2  mov     edx, 1; fCancelPendingCallbacks
0x18005c3f7  mov     rcx, rdi; pti
0x18005c3fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005c400  mov     rcx, rdi; pti
0x18005c403  call    cs:__imp_CloseThreadpoolTimer
0x18005c409  mov     ecx, ebx; dwErrCode
0x18005c40b  call    cs:__imp_SetLastError
0x18005c411  mov     cs:pti, rsi
0x18005c418  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18005c41f  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18005c424  mov     rcx, cs:qword_180097DC8
0x18005c42b  test    rcx, rcx
0x18005c42e  jz      short loc_18005C460
0x18005c430  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18005c437  test    rax, rax
0x18005c43a  jnz     short loc_18005C44B
0x18005c43c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18005c443  test    rdx, rdx
0x18005c446  jz      short loc_18005C45E
0x18005c448  mov     rax, rdx
0x18005c44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c450  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18005c457  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18005c45e  jmp     short loc_18005C46E
0x18005c460  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18005c467  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18005c46e  mov     rcx, cs:qword_180097DC0
0x18005c475  test    rcx, rcx
0x18005c478  jz      short loc_18005C48D
0x18005c47a  test    rax, rax
0x18005c47d  jnz     short loc_18005C487
0x18005c47f  test    rdx, rdx
0x18005c482  jz      short loc_18005C48D
0x18005c484  mov     rax, rdx
0x18005c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c48c  nop
0x18005c48d  mov     rbx, cs:lpMem
0x18005c494  mov     cs:lpMem, rsi
0x18005c49b  test    rbx, rbx
0x18005c49e  jz      short loc_18005C4B4
0x18005c4a0  call    cs:__imp_GetProcessHeap
0x18005c4a6  mov     rcx, rax; hHeap
0x18005c4a9  mov     r8, rbx; lpMem
0x18005c4ac  xor     edx, edx; dwFlags
0x18005c4ae  call    cs:__imp_HeapFree
0x18005c4b4  mov     rbx, cs:qword_180097D98
0x18005c4bb  mov     cs:qword_180097D98, rsi
0x18005c4c2  test    rbx, rbx
0x18005c4c5  jz      short loc_18005C4DB
0x18005c4c7  call    cs:__imp_GetProcessHeap
0x18005c4cd  mov     rcx, rax; hHeap
0x18005c4d0  mov     r8, rbx; lpMem
0x18005c4d3  xor     edx, edx; dwFlags
0x18005c4d5  call    cs:__imp_HeapFree
0x18005c4db  mov     rbx, cs:pti
0x18005c4e2  test    rbx, rbx
0x18005c4e5  jz      short loc_18005C51E
0x18005c4e7  xor     r9d, r9d; msWindowLength
0x18005c4ea  xor     r8d, r8d; msPeriod
0x18005c4ed  xor     edx, edx; pftDueTime
0x18005c4ef  mov     rcx, rbx; pti
0x18005c4f2  call    cs:__imp_SetThreadpoolTimer
0x18005c4f8  mov     edx, 1; fCancelPendingCallbacks
0x18005c4fd  mov     rcx, rbx; pti
0x18005c500  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005c506  mov     rcx, rbx; pti
0x18005c509  call    cs:__imp_CloseThreadpoolTimer
0x18005c50f  jmp     short loc_18005C51E
0x18005c511  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18005c518  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18005c51d  nop
0x18005c51e  mov     rbx, [rsp+28h+arg_0]
0x18005c523  mov     rsi, [rsp+28h+arg_8]
0x18005c528  add     rsp, 20h
0x18005c52c  pop     rdi
0x18005c52d  retn
```
