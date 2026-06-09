# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006588`
- end: `0x180006649`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000ddd0`

## callees

- `0x180004520`
- `0x180006588`
- `0x180006650`
- `0x180006670`
- `0x1800066b4`
- `0x1800066d4`
- `0x1800066f8`
- `0x18000ac64`
- `0x18000cba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800065d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800065d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006609`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006609`

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
0x180006588  push    rbx
0x18000658a  push    rbp
0x18000658b  push    rsi
0x18000658c  push    rdi
0x18000658d  sub     rsp, 38h
0x180006591  cmp     byte ptr [this], 0
0x180006594  mov     rbx, addend
0x180006597  mov     esi, kind
0x18000659a  mov     ebp, featureId
0x18000659c  mov     rdi, this
0x18000659f  jz      loc_180006640
0x1800065a5  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800065aa  test    al, al
0x1800065ac  jz      loc_180006640
0x1800065b2  mov     this, [rdi+18h]; this
0x1800065b6  mov     addend, rbx; addend
0x1800065b9  mov     kind, esi; kind
0x1800065bc  mov     featureId, ebp; featureId
0x1800065be  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800065c3  test    al, al
0x1800065c5  jz      short loc_180006640
0x1800065c7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800065cc  test    al, al
0x1800065ce  jnz     short loc_180006640
0x1800065d0  lea     rbx, [rdi+20h]
0x1800065d4  mov     this, rbx; SRWLock
0x1800065d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800065dd  cmp     byte ptr [rdi+41h], 0
0x1800065e1  mov     [rsp+58h+lock.m_ptr], rbx
0x1800065e6  jnz     short loc_180006636
0x1800065e8  lea     rbx, [rdi+30h]
0x1800065ec  cmp     qword ptr [rbx], 0
0x1800065f0  jnz     short loc_180006624
0x1800065f2  lea     this, [rsp+58h+arg_0]; this
0x1800065f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800065fc  xor     kind, kind; pcbe
0x1800065ff  lea     this, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006606  mov     rdx, rdi; pv
0x180006609  call    cs:__imp_CreateThreadpoolTimer
0x18000660f  mov     rdx, rax; ptr
0x180006612  mov     this, rbx; this
0x180006615  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000661a  lea     this, [rsp+58h+arg_0]; this
0x18000661f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006624  mov     kind, 493E0h; delay
0x18000662a  lea     rdx, [rdi+41h]; timerSet
0x18000662e  mov     this, rbx; timer
0x180006631  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180006636  lea     this, [rsp+58h+lock]; this
0x18000663b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006640  add     rsp, 38h
0x180006644  pop     rdi
0x180006645  pop     rsi
0x180006646  pop     rbp
0x180006647  pop     rbx
0x180006648  retn
```
