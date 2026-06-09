# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006494`
- end: `0x180006582`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, unsigned __int16 serviceReportingKind, unsigned int addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000ddd0`

## callees

- `0x180004520`
- `0x180006494`
- `0x180006650`
- `0x180006670`
- `0x1800066b4`
- `0x1800066d4`
- `0x1800066f8`
- `0x18000e29c`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006533`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006533`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        unsigned __int16 serviceReportingKind,
        unsigned int addend)
{
  _TP_TIMER *ThreadpoolTimer; // rax
  wil::last_error_context v9; // [rsp+20h] [rbp-58h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+28h] [rbp-50h] BYREF
  wil_details_FeatureUsageSRUM properties; // [rsp+30h] [rbp-48h] BYREF

  if ( this->m_fInitialized && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_SRUMlock.m_lock);
    lock.m_ptr = &this->m_SRUMlock.m_lock;
    *(&properties.serviceReportingKind + 1) = 0;
    properties.featureId = featureId;
    properties.serviceReportingKind = serviceReportingKind;
    properties.usageCount = addend;
    wil::details_abi::heap_buffer::push_back(&this->m_cachedSRUMUsageTrackingData.m_data, &properties, 0xCu);
    if ( !this->m_SRUMtimerSet )
    {
      if ( !this->m_SRUMtimer.m_ptr )
      {
        wil::last_error_context::last_error_context(&v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_SRUMtimer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context(&v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_SRUMtimer, &this->m_SRUMtimerSet, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x180006494  push    rbx
0x180006496  push    rbp
0x180006497  push    rsi
0x180006498  push    rdi
0x180006499  push    r14
0x18000649b  sub     rsp, 50h
0x18000649f  mov     rax, cs:__security_cookie
0x1800064a6  xor     rax, rsp
0x1800064a9  mov     [rsp+78h+var_38], rax
0x1800064ae  cmp     byte ptr [this], 0
0x1800064b1  mov     r14d, addend
0x1800064b4  movzx   ebp, serviceReportingKind
0x1800064b8  mov     esi, featureId
0x1800064ba  mov     rdi, this
0x1800064bd  jz      loc_18000656A
0x1800064c3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800064c8  test    al, al
0x1800064ca  jnz     loc_18000656A
0x1800064d0  lea     rbx, [rdi+28h]
0x1800064d4  mov     this, rbx; SRWLock
0x1800064d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800064dd  xor     eax, eax
0x1800064df  mov     [rsp+78h+lock.m_ptr], rbx
0x1800064e4  lea     this, [rdi+0E8h]; this
0x1800064eb  mov     word ptr [rsp+78h+properties+6], ax
0x1800064f0  lea     rdx, [rsp+78h+properties]; data
0x1800064f5  mov     [rsp+78h+properties.featureId], esi
0x1800064f9  mov     [rsp+78h+properties.serviceReportingKind], bp
0x1800064fe  lea     r8d, [rax+0Ch]; appendSize
0x180006502  mov     [rsp+78h+properties.usageCount], r14d
0x180006507  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000650c  cmp     byte ptr [rdi+40h], 0
0x180006510  jnz     short loc_180006560
0x180006512  lea     rbx, [rdi+38h]
0x180006516  cmp     qword ptr [rbx], 0
0x18000651a  jnz     short loc_18000654E
0x18000651c  lea     this, [rsp+78h+var_58]; this
0x180006521  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006526  xor     r8d, r8d; pcbe
0x180006529  lea     this, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006530  mov     rdx, rdi; pv
0x180006533  call    cs:__imp_CreateThreadpoolTimer
0x180006539  mov     rdx, rax; ptr
0x18000653c  mov     this, rbx; this
0x18000653f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006544  lea     this, [rsp+78h+var_58]; this
0x180006549  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000654e  mov     r8d, 1388h; delay
0x180006554  lea     rdx, [rdi+40h]; timerSet
0x180006558  mov     this, rbx; timer
0x18000655b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180006560  lea     this, [rsp+78h+lock]; this
0x180006565  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000656a  mov     this, [rsp+78h+var_38]
0x18000656f  xor     this, rsp; StackCookie
0x180006572  call    __security_check_cookie
0x180006577  add     rsp, 50h
0x18000657b  pop     r14
0x18000657d  pop     rdi
0x18000657e  pop     rsi
0x18000657f  pop     rbp
0x180006580  pop     rbx
0x180006581  retn
```
