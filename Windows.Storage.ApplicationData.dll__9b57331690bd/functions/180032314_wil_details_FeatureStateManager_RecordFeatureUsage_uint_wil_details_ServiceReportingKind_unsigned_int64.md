# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180032314`
- end: `0x1800323d5`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180033740`

## callees

- `0x18001abe8`
- `0x18001ad68`
- `0x18001c6ac`
- `0x18002f910`
- `0x180030518`
- `0x180030638`
- `0x18003226c`
- `0x180032314`
- `0x180033dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032363`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032363`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032395`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032395`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        wil_details_ServiceReportingKind kind,
        unsigned __int64 addend)
{
  bool v8; // zf
  _TP_TIMER *ThreadpoolTimer; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+20h] [rbp-38h] BYREF
  wil::last_error_context v11; // [rsp+60h] [rbp+8h] BYREF

  if ( this->m_fInitialized
    && wil::details::FeatureStateManager::EnsureStateData(this)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(this->m_data, featureId, kind, addend)
    && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    v8 = !this->m_timerSet;
    lock.m_ptr = &this->m_lock.m_lock;
    if ( v8 )
    {
      if ( !this->m_timer.m_ptr )
      {
        wil::last_error_context::last_error_context(&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_timer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context(&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_timer, &this->m_timerSet, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x180032314  push    rbx
0x180032316  push    rbp
0x180032317  push    rsi
0x180032318  push    rdi
0x180032319  sub     rsp, 38h
0x18003231d  cmp     byte ptr [this], 0
0x180032320  mov     rbx, addend
0x180032323  mov     esi, kind
0x180032326  mov     ebp, featureId
0x180032328  mov     rdi, this
0x18003232b  jz      loc_1800323CC
0x180032331  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180032336  test    al, al
0x180032338  jz      loc_1800323CC
0x18003233e  mov     this, [rdi+18h]; this
0x180032342  mov     addend, rbx; addend
0x180032345  mov     kind, esi; kind
0x180032348  mov     featureId, ebp; featureId
0x18003234a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18003234f  test    al, al
0x180032351  jz      short loc_1800323CC
0x180032353  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180032358  test    al, al
0x18003235a  jnz     short loc_1800323CC
0x18003235c  lea     rbx, [rdi+20h]
0x180032360  mov     this, rbx; SRWLock
0x180032363  call    cs:__imp_AcquireSRWLockExclusive
0x180032369  cmp     byte ptr [rdi+41h], 0
0x18003236d  mov     [rsp+58h+lock.m_ptr], rbx
0x180032372  jnz     short loc_1800323C2
0x180032374  lea     rbx, [rdi+30h]
0x180032378  cmp     qword ptr [rbx], 0
0x18003237c  jnz     short loc_1800323B0
0x18003237e  lea     this, [rsp+58h+arg_0]; this
0x180032383  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032388  xor     kind, kind; pcbe
0x18003238b  lea     this, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032392  mov     rdx, rdi; pv
0x180032395  call    cs:__imp_CreateThreadpoolTimer
0x18003239b  mov     rdx, rax; ptr
0x18003239e  mov     this, rbx; this
0x1800323a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800323a6  lea     this, [rsp+58h+arg_0]; this
0x1800323ab  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800323b0  mov     kind, 493E0h; delay
0x1800323b6  lea     rdx, [rdi+41h]; timerSet
0x1800323ba  mov     this, rbx; timer
0x1800323bd  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800323c2  lea     this, [rsp+58h+lock]; this
0x1800323c7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800323cc  add     rsp, 38h
0x1800323d0  pop     rdi
0x1800323d1  pop     rsi
0x1800323d2  pop     rbp
0x1800323d3  pop     rbx
0x1800323d4  retn
```
