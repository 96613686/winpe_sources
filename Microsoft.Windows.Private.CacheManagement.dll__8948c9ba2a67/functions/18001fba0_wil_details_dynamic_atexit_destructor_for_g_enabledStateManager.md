# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x18001fba0`
- end: `0x18001fd06`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004650`
- `0x180012de0`
- `0x18001cdf0`
- `0x18001fba0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001fc1a`
- `KERNEL32!HeapFree` at `0x18001fc45`
- `KERNEL32!HeapFree` at `0x18001fc1a`
- `KERNEL32!HeapFree` at `0x18001fc45`
- `KERNEL32!GetProcessHeap` at `0x18001fc0c`
- `KERNEL32!GetProcessHeap` at `0x18001fc37`
- `KERNEL32!GetProcessHeap` at `0x18001fc0c`
- `KERNEL32!GetProcessHeap` at `0x18001fc37`
- `KERNEL32!SetThreadpoolTimer` at `0x18001fccd`
- `KERNEL32!SetThreadpoolTimer` at `0x18001fccd`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001fce4`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001fce4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001fcdb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001fcdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__()
{
  void *v0; // rbx
  HANDLE ProcessHeap; // rax
  void *v2; // rbx
  HANDLE v3; // rax
  void (*v4)(void); // rax
  __int64 v5; // rdx
  struct _TP_TIMER *v6; // rbx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::g_enabledStateManager = 0;
    wil::details::EnabledStateManager::RecordCachedUsageUnderLock((int **)&wil::details::g_enabledStateManager);
    return;
  }
  wil::details::g_enabledStateManager = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  wil::details::g_enabledStateManager = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock((int **)&wil::details::g_enabledStateManager);
  v0 = lpMem;
  lpMem = 0;
  if ( v0 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
  }
  v2 = qword_18002D368;
  qword_18002D368 = 0;
  if ( v2 )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 0, v2);
  }
  if ( !qword_18002D348 )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_15;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_15;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_15:
  if ( !qword_18002D340 )
    goto LABEL_20;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_20;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_20:
  v6 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v6, 1);
    CloseThreadpoolTimer(v6);
  }
}

```

## disassembly

```asm
0x18001fba0  push    rbx
0x18001fba2  sub     rsp, 20h
0x18001fba6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001fbad  jnz     loc_18001FCEC
0x18001fbb3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001fbba  test    rax, rax
0x18001fbbd  jz      short loc_18001FBCD
0x18001fbbf  call    cs:__guard_dispatch_icall_fptr
0x18001fbc5  test    al, al
0x18001fbc7  jnz     loc_18001FCEC
0x18001fbcd  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001fbd4  xor     edx, edx
0x18001fbd6  lea     rcx, pti
0x18001fbdd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001fbe2  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001fbe9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001fbf0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18001fbf5  mov     rbx, cs:lpMem
0x18001fbfc  mov     cs:lpMem, 0
0x18001fc07  test    rbx, rbx
0x18001fc0a  jz      short loc_18001FC20
0x18001fc0c  call    cs:__imp_GetProcessHeap
0x18001fc12  mov     rcx, rax; hHeap
0x18001fc15  mov     r8, rbx; lpMem
0x18001fc18  xor     edx, edx; dwFlags
0x18001fc1a  call    cs:__imp_HeapFree
0x18001fc20  mov     rbx, cs:qword_18002D368
0x18001fc27  mov     cs:qword_18002D368, 0
0x18001fc32  test    rbx, rbx
0x18001fc35  jz      short loc_18001FC4B
0x18001fc37  call    cs:__imp_GetProcessHeap
0x18001fc3d  mov     rcx, rax; hHeap
0x18001fc40  mov     r8, rbx; lpMem
0x18001fc43  xor     edx, edx; dwFlags
0x18001fc45  call    cs:__imp_HeapFree
0x18001fc4b  mov     rcx, cs:qword_18002D348
0x18001fc52  test    rcx, rcx
0x18001fc55  jz      short loc_18001FC88
0x18001fc57  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001fc5e  test    rax, rax
0x18001fc61  jnz     short loc_18001FC72
0x18001fc63  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001fc6a  test    rdx, rdx
0x18001fc6d  jz      short loc_18001FC86
0x18001fc6f  mov     rax, rdx
0x18001fc72  call    cs:__guard_dispatch_icall_fptr
0x18001fc78  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001fc7f  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001fc86  jmp     short loc_18001FC96
0x18001fc88  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001fc8f  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001fc96  mov     rcx, cs:qword_18002D340
0x18001fc9d  test    rcx, rcx
0x18001fca0  jz      short loc_18001FCB6
0x18001fca2  test    rax, rax
0x18001fca5  jnz     short loc_18001FCAF
0x18001fca7  test    rdx, rdx
0x18001fcaa  jz      short loc_18001FCB6
0x18001fcac  mov     rax, rdx
0x18001fcaf  call    cs:__guard_dispatch_icall_fptr
0x18001fcb5  nop
0x18001fcb6  mov     rbx, cs:pti
0x18001fcbd  test    rbx, rbx
0x18001fcc0  jz      short loc_18001FD00
0x18001fcc2  xor     r9d, r9d; msWindowLength
0x18001fcc5  xor     r8d, r8d; msPeriod
0x18001fcc8  xor     edx, edx; pftDueTime
0x18001fcca  mov     rcx, rbx; pti
0x18001fccd  call    cs:__imp_SetThreadpoolTimer
0x18001fcd3  mov     edx, 1; fCancelPendingCallbacks
0x18001fcd8  mov     rcx, rbx; pti
0x18001fcdb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fce1  mov     rcx, rbx; pti
0x18001fce4  call    cs:__imp_CloseThreadpoolTimer
0x18001fcea  jmp     short loc_18001FD00
0x18001fcec  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001fcf3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001fcfa  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18001fcff  nop
0x18001fd00  add     rsp, 20h
0x18001fd04  pop     rbx
0x18001fd05  retn
```
