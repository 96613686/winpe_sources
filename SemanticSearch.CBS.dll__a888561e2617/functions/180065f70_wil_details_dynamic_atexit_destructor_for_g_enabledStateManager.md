# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x180065f70`
- end: `0x1800660d6`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x1800068a0`
- `0x18005e260`
- `0x180065f70`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180065fdc`
- `KERNEL32!GetProcessHeap` at `0x180066007`
- `KERNEL32!GetProcessHeap` at `0x180065fdc`
- `KERNEL32!GetProcessHeap` at `0x180066007`
- `KERNEL32!HeapFree` at `0x180065fea`
- `KERNEL32!HeapFree` at `0x180066015`
- `KERNEL32!HeapFree` at `0x180065fea`
- `KERNEL32!HeapFree` at `0x180066015`
- `KERNEL32!SetThreadpoolTimer` at `0x18006609d`
- `KERNEL32!SetThreadpoolTimer` at `0x18006609d`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800660b4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800660b4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800660ab`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800660ab`

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
  v2 = qword_180085368;
  qword_180085368 = 0;
  if ( v2 )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 0, v2);
  }
  if ( !qword_180085348 )
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
  if ( !qword_180085340 )
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
0x180065f70  push    rbx
0x180065f72  sub     rsp, 20h
0x180065f76  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180065f7d  jnz     loc_1800660BC
0x180065f83  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180065f8a  test    rax, rax
0x180065f8d  jz      short loc_180065F9D
0x180065f8f  call    cs:__guard_dispatch_icall_fptr
0x180065f95  test    al, al
0x180065f97  jnz     loc_1800660BC
0x180065f9d  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180065fa4  xor     edx, edx
0x180065fa6  lea     rcx, pti
0x180065fad  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180065fb2  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180065fb9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180065fc0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180065fc5  mov     rbx, cs:lpMem
0x180065fcc  mov     cs:lpMem, 0
0x180065fd7  test    rbx, rbx
0x180065fda  jz      short loc_180065FF0
0x180065fdc  call    cs:__imp_GetProcessHeap
0x180065fe2  mov     rcx, rax; hHeap
0x180065fe5  mov     r8, rbx; lpMem
0x180065fe8  xor     edx, edx; dwFlags
0x180065fea  call    cs:__imp_HeapFree
0x180065ff0  mov     rbx, cs:qword_180085368
0x180065ff7  mov     cs:qword_180085368, 0
0x180066002  test    rbx, rbx
0x180066005  jz      short loc_18006601B
0x180066007  call    cs:__imp_GetProcessHeap
0x18006600d  mov     rcx, rax; hHeap
0x180066010  mov     r8, rbx; lpMem
0x180066013  xor     edx, edx; dwFlags
0x180066015  call    cs:__imp_HeapFree
0x18006601b  mov     rcx, cs:qword_180085348
0x180066022  test    rcx, rcx
0x180066025  jz      short loc_180066058
0x180066027  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006602e  test    rax, rax
0x180066031  jnz     short loc_180066042
0x180066033  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006603a  test    rdx, rdx
0x18006603d  jz      short loc_180066056
0x18006603f  mov     rax, rdx
0x180066042  call    cs:__guard_dispatch_icall_fptr
0x180066048  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006604f  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180066056  jmp     short loc_180066066
0x180066058  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006605f  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180066066  mov     rcx, cs:qword_180085340
0x18006606d  test    rcx, rcx
0x180066070  jz      short loc_180066086
0x180066072  test    rax, rax
0x180066075  jnz     short loc_18006607F
0x180066077  test    rdx, rdx
0x18006607a  jz      short loc_180066086
0x18006607c  mov     rax, rdx
0x18006607f  call    cs:__guard_dispatch_icall_fptr
0x180066085  nop
0x180066086  mov     rbx, cs:pti
0x18006608d  test    rbx, rbx
0x180066090  jz      short loc_1800660D0
0x180066092  xor     r9d, r9d; msWindowLength
0x180066095  xor     r8d, r8d; msPeriod
0x180066098  xor     edx, edx; pftDueTime
0x18006609a  mov     rcx, rbx; pti
0x18006609d  call    cs:__imp_SetThreadpoolTimer
0x1800660a3  mov     edx, 1; fCancelPendingCallbacks
0x1800660a8  mov     rcx, rbx; pti
0x1800660ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800660b1  mov     rcx, rbx; pti
0x1800660b4  call    cs:__imp_CloseThreadpoolTimer
0x1800660ba  jmp     short loc_1800660D0
0x1800660bc  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800660c3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800660ca  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x1800660cf  nop
0x1800660d0  add     rsp, 20h
0x1800660d4  pop     rbx
0x1800660d5  retn
```
