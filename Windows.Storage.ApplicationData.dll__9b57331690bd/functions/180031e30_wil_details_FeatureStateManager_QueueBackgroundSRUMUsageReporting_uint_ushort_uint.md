# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180031e30`
- end: `0x180031f1e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, unsigned __int16 serviceReportingKind, unsigned int addend)`
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
- `0x180031e30`
- `0x180033cc4`
- `0x180033dd0`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031e73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031e73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031ecf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031ecf`

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
0x180031e30  push    rbx
0x180031e32  push    rbp
0x180031e33  push    rsi
0x180031e34  push    rdi
0x180031e35  push    r14
0x180031e37  sub     rsp, 50h
0x180031e3b  mov     rax, cs:__security_cookie
0x180031e42  xor     rax, rsp
0x180031e45  mov     [rsp+78h+var_38], rax
0x180031e4a  cmp     byte ptr [this], 0
0x180031e4d  mov     r14d, addend
0x180031e50  movzx   ebp, serviceReportingKind
0x180031e54  mov     esi, featureId
0x180031e56  mov     rdi, this
0x180031e59  jz      loc_180031F06
0x180031e5f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180031e64  test    al, al
0x180031e66  jnz     loc_180031F06
0x180031e6c  lea     rbx, [rdi+28h]
0x180031e70  mov     this, rbx; SRWLock
0x180031e73  call    cs:__imp_AcquireSRWLockExclusive
0x180031e79  xor     eax, eax
0x180031e7b  mov     [rsp+78h+lock.m_ptr], rbx
0x180031e80  lea     this, [rdi+0E8h]; this
0x180031e87  mov     word ptr [rsp+78h+properties+6], ax
0x180031e8c  lea     rdx, [rsp+78h+properties]; data
0x180031e91  mov     [rsp+78h+properties.featureId], esi
0x180031e95  mov     [rsp+78h+properties.serviceReportingKind], bp
0x180031e9a  lea     r8d, [rax+0Ch]; appendSize
0x180031e9e  mov     [rsp+78h+properties.usageCount], r14d
0x180031ea3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180031ea8  cmp     byte ptr [rdi+40h], 0
0x180031eac  jnz     short loc_180031EFC
0x180031eae  lea     rbx, [rdi+38h]
0x180031eb2  cmp     qword ptr [rbx], 0
0x180031eb6  jnz     short loc_180031EEA
0x180031eb8  lea     this, [rsp+78h+var_58]; this
0x180031ebd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031ec2  xor     r8d, r8d; pcbe
0x180031ec5  lea     this, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180031ecc  mov     rdx, rdi; pv
0x180031ecf  call    cs:__imp_CreateThreadpoolTimer
0x180031ed5  mov     rdx, rax; ptr
0x180031ed8  mov     this, rbx; this
0x180031edb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180031ee0  lea     this, [rsp+78h+var_58]; this
0x180031ee5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180031eea  mov     r8d, 1388h; delay
0x180031ef0  lea     rdx, [rdi+40h]; timerSet
0x180031ef4  mov     this, rbx; timer
0x180031ef7  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180031efc  lea     this, [rsp+78h+lock]; this
0x180031f01  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031f06  mov     this, [rsp+78h+var_38]
0x180031f0b  xor     this, rsp; StackCookie
0x180031f0e  call    __security_check_cookie
0x180031f13  add     rsp, 50h
0x180031f17  pop     r14
0x180031f19  pop     rdi
0x180031f1a  pop     rsi
0x180031f1b  pop     rbp
0x180031f1c  pop     rbx
0x180031f1d  retn
```
