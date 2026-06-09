# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x18025d660`
- end: `0x18025d7c6`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007430`
- `0x1800074c0`
- `0x180242120`
- `0x18025d660`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18025d6cc`
- `KERNEL32!GetProcessHeap` at `0x18025d6f7`
- `KERNEL32!GetProcessHeap` at `0x18025d6cc`
- `KERNEL32!GetProcessHeap` at `0x18025d6f7`
- `KERNEL32!HeapFree` at `0x18025d6da`
- `KERNEL32!HeapFree` at `0x18025d705`
- `KERNEL32!HeapFree` at `0x18025d6da`
- `KERNEL32!HeapFree` at `0x18025d705`
- `KERNEL32!SetThreadpoolTimer` at `0x18025d78d`
- `KERNEL32!SetThreadpoolTimer` at `0x18025d78d`
- `KERNEL32!CloseThreadpoolTimer` at `0x18025d7a4`
- `KERNEL32!CloseThreadpoolTimer` at `0x18025d7a4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18025d79b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18025d79b`

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
    wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
    return;
  }
  wil::details::g_enabledStateManager = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  wil::details::g_enabledStateManager = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  v0 = lpMem;
  lpMem = 0;
  if ( v0 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
  }
  v2 = qword_18033CC48;
  qword_18033CC48 = 0;
  if ( v2 )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 0, v2);
  }
  if ( !qword_18033CC28 )
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
  if ( !qword_18033CC20 )
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
0x18025d660  push    rbx
0x18025d662  sub     rsp, 20h
0x18025d666  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18025d66d  jnz     loc_18025D7AC
0x18025d673  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18025d67a  test    rax, rax
0x18025d67d  jz      short loc_18025D68D
0x18025d67f  call    cs:__guard_dispatch_icall_fptr
0x18025d685  test    al, al
0x18025d687  jnz     loc_18025D7AC
0x18025d68d  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18025d694  xor     edx, edx
0x18025d696  lea     rcx, pti
0x18025d69d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18025d6a2  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18025d6a9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18025d6b0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18025d6b5  mov     rbx, cs:lpMem
0x18025d6bc  mov     cs:lpMem, 0
0x18025d6c7  test    rbx, rbx
0x18025d6ca  jz      short loc_18025D6E0
0x18025d6cc  call    cs:__imp_GetProcessHeap
0x18025d6d2  mov     rcx, rax; hHeap
0x18025d6d5  mov     r8, rbx; lpMem
0x18025d6d8  xor     edx, edx; dwFlags
0x18025d6da  call    cs:__imp_HeapFree
0x18025d6e0  mov     rbx, cs:qword_18033CC48
0x18025d6e7  mov     cs:qword_18033CC48, 0
0x18025d6f2  test    rbx, rbx
0x18025d6f5  jz      short loc_18025D70B
0x18025d6f7  call    cs:__imp_GetProcessHeap
0x18025d6fd  mov     rcx, rax; hHeap
0x18025d700  mov     r8, rbx; lpMem
0x18025d703  xor     edx, edx; dwFlags
0x18025d705  call    cs:__imp_HeapFree
0x18025d70b  mov     rcx, cs:qword_18033CC28
0x18025d712  test    rcx, rcx
0x18025d715  jz      short loc_18025D748
0x18025d717  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18025d71e  test    rax, rax
0x18025d721  jnz     short loc_18025D732
0x18025d723  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18025d72a  test    rdx, rdx
0x18025d72d  jz      short loc_18025D746
0x18025d72f  mov     rax, rdx
0x18025d732  call    cs:__guard_dispatch_icall_fptr
0x18025d738  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18025d73f  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18025d746  jmp     short loc_18025D756
0x18025d748  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18025d74f  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18025d756  mov     rcx, cs:qword_18033CC20
0x18025d75d  test    rcx, rcx
0x18025d760  jz      short loc_18025D776
0x18025d762  test    rax, rax
0x18025d765  jnz     short loc_18025D76F
0x18025d767  test    rdx, rdx
0x18025d76a  jz      short loc_18025D776
0x18025d76c  mov     rax, rdx
0x18025d76f  call    cs:__guard_dispatch_icall_fptr
0x18025d775  nop
0x18025d776  mov     rbx, cs:pti
0x18025d77d  test    rbx, rbx
0x18025d780  jz      short loc_18025D7C0
0x18025d782  xor     r9d, r9d; msWindowLength
0x18025d785  xor     r8d, r8d; msPeriod
0x18025d788  xor     edx, edx; pftDueTime
0x18025d78a  mov     rcx, rbx; pti
0x18025d78d  call    cs:__imp_SetThreadpoolTimer
0x18025d793  mov     edx, 1; fCancelPendingCallbacks
0x18025d798  mov     rcx, rbx; pti
0x18025d79b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18025d7a1  mov     rcx, rbx; pti
0x18025d7a4  call    cs:__imp_CloseThreadpoolTimer
0x18025d7aa  jmp     short loc_18025D7C0
0x18025d7ac  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18025d7b3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18025d7ba  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18025d7bf  nop
0x18025d7c0  add     rsp, 20h
0x18025d7c4  pop     rbx
0x18025d7c5  retn
```
