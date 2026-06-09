# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x1800419a0`
- end: `0x180041b06`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f590`
- `0x18000f670`
- `0x18003bed0`
- `0x1800419a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180041a1a`
- `KERNEL32!HeapFree` at `0x180041a45`
- `KERNEL32!HeapFree` at `0x180041a1a`
- `KERNEL32!HeapFree` at `0x180041a45`
- `KERNEL32!GetProcessHeap` at `0x180041a0c`
- `KERNEL32!GetProcessHeap` at `0x180041a37`
- `KERNEL32!GetProcessHeap` at `0x180041a0c`
- `KERNEL32!GetProcessHeap` at `0x180041a37`
- `KERNEL32!SetThreadpoolTimer` at `0x180041acd`
- `KERNEL32!SetThreadpoolTimer` at `0x180041acd`
- `KERNEL32!CloseThreadpoolTimer` at `0x180041ae4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180041ae4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180041adb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180041adb`

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
  v2 = qword_180058428;
  qword_180058428 = 0;
  if ( v2 )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 0, v2);
  }
  if ( !qword_180058408 )
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
  if ( !qword_180058400 )
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
0x1800419a0  push    rbx
0x1800419a2  sub     rsp, 20h
0x1800419a6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800419ad  jnz     loc_180041AEC
0x1800419b3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800419ba  test    rax, rax
0x1800419bd  jz      short loc_1800419CD
0x1800419bf  call    cs:__guard_dispatch_icall_fptr
0x1800419c5  test    al, al
0x1800419c7  jnz     loc_180041AEC
0x1800419cd  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800419d4  xor     edx, edx
0x1800419d6  lea     rcx, pti
0x1800419dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800419e2  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800419e9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800419f0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x1800419f5  mov     rbx, cs:lpMem
0x1800419fc  mov     cs:lpMem, 0
0x180041a07  test    rbx, rbx
0x180041a0a  jz      short loc_180041A20
0x180041a0c  call    cs:__imp_GetProcessHeap
0x180041a12  mov     rcx, rax; hHeap
0x180041a15  mov     r8, rbx; lpMem
0x180041a18  xor     edx, edx; dwFlags
0x180041a1a  call    cs:__imp_HeapFree
0x180041a20  mov     rbx, cs:qword_180058428
0x180041a27  mov     cs:qword_180058428, 0
0x180041a32  test    rbx, rbx
0x180041a35  jz      short loc_180041A4B
0x180041a37  call    cs:__imp_GetProcessHeap
0x180041a3d  mov     rcx, rax; hHeap
0x180041a40  mov     r8, rbx; lpMem
0x180041a43  xor     edx, edx; dwFlags
0x180041a45  call    cs:__imp_HeapFree
0x180041a4b  mov     rcx, cs:qword_180058408
0x180041a52  test    rcx, rcx
0x180041a55  jz      short loc_180041A88
0x180041a57  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180041a5e  test    rax, rax
0x180041a61  jnz     short loc_180041A72
0x180041a63  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180041a6a  test    rdx, rdx
0x180041a6d  jz      short loc_180041A86
0x180041a6f  mov     rax, rdx
0x180041a72  call    cs:__guard_dispatch_icall_fptr
0x180041a78  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180041a7f  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180041a86  jmp     short loc_180041A96
0x180041a88  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180041a8f  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180041a96  mov     rcx, cs:qword_180058400
0x180041a9d  test    rcx, rcx
0x180041aa0  jz      short loc_180041AB6
0x180041aa2  test    rax, rax
0x180041aa5  jnz     short loc_180041AAF
0x180041aa7  test    rdx, rdx
0x180041aaa  jz      short loc_180041AB6
0x180041aac  mov     rax, rdx
0x180041aaf  call    cs:__guard_dispatch_icall_fptr
0x180041ab5  nop
0x180041ab6  mov     rbx, cs:pti
0x180041abd  test    rbx, rbx
0x180041ac0  jz      short loc_180041B00
0x180041ac2  xor     r9d, r9d; msWindowLength
0x180041ac5  xor     r8d, r8d; msPeriod
0x180041ac8  xor     edx, edx; pftDueTime
0x180041aca  mov     rcx, rbx; pti
0x180041acd  call    cs:__imp_SetThreadpoolTimer
0x180041ad3  mov     edx, 1; fCancelPendingCallbacks
0x180041ad8  mov     rcx, rbx; pti
0x180041adb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180041ae1  mov     rcx, rbx; pti
0x180041ae4  call    cs:__imp_CloseThreadpoolTimer
0x180041aea  jmp     short loc_180041B00
0x180041aec  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180041af3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180041afa  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180041aff  nop
0x180041b00  add     rsp, 20h
0x180041b04  pop     rbx
0x180041b05  retn
```
