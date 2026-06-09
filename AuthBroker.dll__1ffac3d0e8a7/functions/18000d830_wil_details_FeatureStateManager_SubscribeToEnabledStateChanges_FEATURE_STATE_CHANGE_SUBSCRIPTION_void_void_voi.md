# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000d830`
- end: `0x18000d8f7`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, FEATURE_STATE_CHANGE_SUBSCRIPTION__ **subscription, void (__fastcall *callback)(void *), void *context)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000de50`

## callees

- `0x1800066b4`
- `0x18000d830`
- `0x18000d9f4`
- `0x18000e430`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d865`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d865`

## string_xrefs

- `0x18000d890`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        wil::details::FeatureStateManager *this,
        FEATURE_STATE_CHANGE_SUBSCRIPTION__ **subscription,
        void (__fastcall *callback)(void *),
        void *context)
{
  wil::srwlock *p_m_lock; // rbx
  int (__fastcall *NtDllProcedureAddress)(void (__fastcall *)(void *), void *, unsigned __int64 *, void **); // rax
  int v10; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+50h] [rbp+8h] BYREF

  *subscription = 0;
  if ( this->m_fInitialized )
  {
    p_m_lock = &this->m_lock;
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    lock.m_ptr = &p_m_lock->m_lock;
    if ( this->m_featureConfigurationChangeSubscription.m_ptr
      || ((NtDllProcedureAddress = g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
           this->m_featureConfigurationChangeSubscription.m_ptr = 0,
           NtDllProcedureAddress)
       || (NtDllProcedureAddress = (int (__fastcall *)(void (__fastcall *)(void *), void *, unsigned __int64 *, void **))wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
           (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = NtDllProcedureAddress) != 0)
        ? (v10 = NtDllProcedureAddress(
                   _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                   this,
                   0,
                   &this->m_featureConfigurationChangeSubscription.m_ptr))
        : (v10 = -1073741511),
          !v10) )
    {
      wil::details_abi::SubscriptionList::SubscribeUnderLock(
        &this->m_stateChangeSubscriptions,
        subscription,
        callback,
        context);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x18000d830  mov     [rsp+arg_8], rbx
0x18000d835  mov     [rsp+arg_10], rbp
0x18000d83a  push    rsi
0x18000d83b  push    rdi
0x18000d83c  push    r14
0x18000d83e  sub     rsp, 30h
0x18000d842  mov     qword ptr [subscription], 0
0x18000d849  mov     rbp, context
0x18000d84c  cmp     byte ptr [this], 0
0x18000d84f  mov     r14, callback
0x18000d852  mov     rsi, subscription
0x18000d855  mov     rdi, this
0x18000d858  jz      loc_18000D8E4
0x18000d85e  lea     rbx, [this+20h]
0x18000d862  mov     this, rbx; SRWLock
0x18000d865  call    cs:__imp_AcquireSRWLockExclusive
0x18000d86b  mov     [rsp+48h+lock.m_ptr], rbx
0x18000d870  lea     rbx, [rdi+90h]
0x18000d877  cmp     qword ptr [rbx], 0
0x18000d87b  jnz     short loc_18000D8C8
0x18000d87d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d884  mov     qword ptr [rbx], 0
0x18000d88b  test    rax, rax
0x18000d88e  jnz     short loc_18000D8AF
0x18000d890  lea     this, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d897  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d89c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d8a3  test    rax, rax
0x18000d8a6  jnz     short loc_18000D8AF
0x18000d8a8  mov     eax, 0C0000139h
0x18000d8ad  jmp     short loc_18000D8C4
0x18000d8af  mov     context, rbx
0x18000d8b2  lea     this, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000d8b9  xor     r8d, r8d
0x18000d8bc  mov     subscription, rdi
0x18000d8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c4  test    eax, eax
0x18000d8c6  jnz     short loc_18000D8DA
0x18000d8c8  lea     this, [rdi+48h]; this
0x18000d8cc  mov     context, rbp; context
0x18000d8cf  mov     callback, r14; callback
0x18000d8d2  mov     subscription, rsi; subscription
0x18000d8d5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000d8da  lea     this, [rsp+48h+lock]; this
0x18000d8df  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d8e4  mov     rbx, [rsp+48h+arg_8]
0x18000d8e9  mov     rbp, [rsp+48h+arg_10]
0x18000d8ee  add     rsp, 30h
0x18000d8f2  pop     r14
0x18000d8f4  pop     rdi
0x18000d8f5  pop     rsi
0x18000d8f6  retn
```
