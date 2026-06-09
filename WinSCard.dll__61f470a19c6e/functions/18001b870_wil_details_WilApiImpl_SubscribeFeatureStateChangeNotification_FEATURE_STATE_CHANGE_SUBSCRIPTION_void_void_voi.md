# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001b870`
- end: `0x18001b95c`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `236`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180018504`
- `0x18001b774`
- `0x18001b870`
- `0x18001b964`
- `0x180021c54`
- `0x180022af0`
- `0x180033010`

## string_xrefs

- `0x18001b8ec`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v8; // eax
  char v9; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      wil::srwlock::lock_exclusive(qword_180045A90, &v9);
      if ( qword_180045B00
        || ((qword_180045B00 = 0,
             (NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification) != 0)
         || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
             (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
          ? (v8 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))NtDllProcedureAddress)(
                    _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                    &wil::details::g_featureStateManager,
                    0,
                    &qword_180045B00))
          : (v8 = -1073741511),
            !v8) )
      {
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)qword_180045AB8,
          this,
          (void (*)(void *))a2,
          a3);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    }
  }
}

```

## disassembly

```asm
0x18001b870  mov     [rsp+arg_0], rbx
0x18001b875  mov     [rsp+arg_8], rsi
0x18001b87a  push    rdi
0x18001b87b  sub     rsp, 30h
0x18001b87f  mov     rdi, r8
0x18001b882  mov     rsi, rdx
0x18001b885  mov     rbx, rcx
0x18001b888  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001b88c  jnz     short loc_18001B8A5
0x18001b88e  mov     r8, rdx; void (*)(void *)
0x18001b891  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001b894  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001b89b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001b8a0  jmp     loc_18001B94C
0x18001b8a5  mov     qword ptr [rcx], 0
0x18001b8ac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001b8b3  jz      loc_18001B94C
0x18001b8b9  lea     rdx, [rsp+38h+arg_10]
0x18001b8be  lea     rcx, qword_180045A90
0x18001b8c5  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001b8ca  nop
0x18001b8cb  cmp     cs:qword_180045B00, 0
0x18001b8d3  jnz     short loc_18001B92C
0x18001b8d5  mov     cs:qword_180045B00, 0
0x18001b8e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001b8e7  test    rax, rax
0x18001b8ea  jnz     short loc_18001B90B
0x18001b8ec  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001b8f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b8f8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001b8ff  test    rax, rax
0x18001b902  jnz     short loc_18001B90B
0x18001b904  mov     eax, 0C0000139h
0x18001b909  jmp     short loc_18001B928
0x18001b90b  lea     r9, qword_180045B00
0x18001b912  xor     r8d, r8d
0x18001b915  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001b91c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001b923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b928  test    eax, eax
0x18001b92a  jnz     short loc_18001B942
0x18001b92c  mov     r9, rdi; void *
0x18001b92f  mov     r8, rsi; void (*)(void *)
0x18001b932  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001b935  lea     rcx, qword_180045AB8; this
0x18001b93c  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001b941  nop
0x18001b942  lea     rcx, [rsp+38h+arg_10]
0x18001b947  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b94c  mov     rbx, [rsp+38h+arg_0]
0x18001b951  mov     rsi, [rsp+38h+arg_8]
0x18001b956  add     rsp, 30h
0x18001b95a  pop     rdi
0x18001b95b  retn
```
