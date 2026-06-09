# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180031f24`
- end: `0x180031ffc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(wil::details::EnabledStateManager *this, unsigned int id, wil_details_FeatureReportingCache *reporting)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032d64`

## callees

- `0x18001abe8`
- `0x18001ad68`
- `0x18001c6ac`
- `0x18002f910`
- `0x180030518`
- `0x180031f24`
- `0x180033cc4`
- `0x180033dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031f56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031f56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031fb8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031fb8`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        unsigned int id,
        wil_details_FeatureReportingCache *reporting)
{
  volatile int m_fInitialized; // eax
  _TP_TIMER *ThreadpoolTimer; // rax
  _DWORD data[2]; // [rsp+20h] [rbp-28h] BYREF
  wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  wil::last_error_context v10; // [rsp+50h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+68h] [rbp+20h] BYREF

  if ( this->m_fInitialized && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    m_fInitialized = this->m_fInitialized;
    lock.m_ptr = &this->m_lock.m_lock;
    if ( m_fInitialized )
    {
      if ( !wil::ProcessShutdownInProgress() )
      {
        data[0] = id;
        data[1] = 0;
        v9 = reporting;
        wil::details_abi::heap_buffer::push_back(&this->m_cachedUsageTrackingData.m_data, data, 0x10u);
        if ( !this->m_timerSet )
        {
          if ( !this->m_timer.m_ptr )
          {
            wil::last_error_context::last_error_context(&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                this,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &this->m_timer,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context(&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&this->m_timer, &this->m_timerSet, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x180031f24  mov     [rsp+arg_8], rbx
0x180031f29  push    rbp
0x180031f2a  push    rsi
0x180031f2b  push    rdi
0x180031f2c  sub     rsp, 30h
0x180031f30  mov     eax, [this]
0x180031f32  mov     rsi, reporting
0x180031f35  mov     ebp, id
0x180031f37  mov     rdi, this
0x180031f3a  test    eax, eax
0x180031f3c  jz      loc_180031FEF
0x180031f42  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180031f47  test    al, al
0x180031f49  jnz     loc_180031FEF
0x180031f4f  lea     rbx, [rdi+8]
0x180031f53  mov     this, rbx; SRWLock
0x180031f56  call    cs:__imp_AcquireSRWLockExclusive
0x180031f5c  mov     eax, [rdi]
0x180031f5e  mov     [rsp+48h+lock.m_ptr], rbx
0x180031f63  test    eax, eax
0x180031f65  jz      short loc_180031FE5
0x180031f67  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180031f6c  test    al, al
0x180031f6e  jnz     short loc_180031FE5
0x180031f70  xor     eax, eax
0x180031f72  mov     [rsp+48h+data], ebp
0x180031f76  lea     this, [rdi+20h]; this
0x180031f7a  mov     [rsp+48h+var_24], eax
0x180031f7e  lea     rdx, [rsp+48h+data]; data
0x180031f83  mov     [rsp+48h+var_20], rsi
0x180031f88  lea     r8d, [rax+10h]; appendSize
0x180031f8c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180031f91  cmp     byte ptr [rdi+18h], 0
0x180031f95  jnz     short loc_180031FE5
0x180031f97  lea     rbx, [rdi+10h]
0x180031f9b  cmp     qword ptr [rbx], 0
0x180031f9f  jnz     short loc_180031FD3
0x180031fa1  lea     this, [rsp+48h+arg_0]; this
0x180031fa6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031fab  xor     r8d, r8d; pcbe
0x180031fae  lea     this, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180031fb5  mov     rdx, rdi; pv
0x180031fb8  call    cs:__imp_CreateThreadpoolTimer
0x180031fbe  mov     rdx, rax; ptr
0x180031fc1  mov     this, rbx; this
0x180031fc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180031fc9  lea     this, [rsp+48h+arg_0]; this
0x180031fce  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180031fd3  mov     r8d, 493E0h; delay
0x180031fd9  lea     rdx, [rdi+18h]; timerSet
0x180031fdd  mov     this, rbx; timer
0x180031fe0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180031fe5  lea     this, [rsp+48h+lock]; this
0x180031fea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031fef  mov     rbx, [rsp+48h+arg_8]
0x180031ff4  add     rsp, 30h
0x180031ff8  pop     rdi
0x180031ff9  pop     rsi
0x180031ffa  pop     rbp
0x180031ffb  retn
```
