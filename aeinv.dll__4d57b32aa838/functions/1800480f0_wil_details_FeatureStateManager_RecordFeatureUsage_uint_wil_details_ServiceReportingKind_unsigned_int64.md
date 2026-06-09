# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800480f0`
- end: `0x1800481bb`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180113ee0`

## callees

- `0x1800480f0`
- `0x18004826c`
- `0x18004828c`
- `0x18004869c`
- `0x1800487ac`
- `0x1800487d0`
- `0x1800488f8`
- `0x1801122b8`
- `0x1801131a4`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18004817a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18004817a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048148`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048148`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  v10[1] = -2;
  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v10[0] = a1 + 4;
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x1800480f0  push    rbx
0x1800480f2  push    rbp
0x1800480f3  push    rsi
0x1800480f4  push    rdi
0x1800480f5  sub     rsp, 38h
0x1800480f9  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x180048102  mov     rbx, r9
0x180048105  mov     esi, r8d
0x180048108  mov     ebp, edx
0x18004810a  mov     rdi, rcx
0x18004810d  cmp     byte ptr [rcx], 0
0x180048110  jz      loc_1800481B2
0x180048116  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18004811b  test    al, al
0x18004811d  jz      loc_1800481B2
0x180048123  mov     r9, rbx
0x180048126  mov     r8d, esi
0x180048129  mov     edx, ebp
0x18004812b  mov     rcx, [rdi+18h]
0x18004812f  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180048134  test    al, al
0x180048136  jz      short loc_1800481B2
0x180048138  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004813d  test    al, al
0x18004813f  jnz     short loc_1800481B2
0x180048141  lea     rbx, [rdi+20h]
0x180048145  mov     rcx, rbx; SRWLock
0x180048148  call    cs:__imp_AcquireSRWLockExclusive
0x18004814e  mov     [rsp+58h+var_38], rbx
0x180048153  cmp     byte ptr [rdi+41h], 0
0x180048157  jnz     short loc_1800481A7
0x180048159  lea     rbx, [rdi+30h]
0x18004815d  cmp     qword ptr [rbx], 0
0x180048161  jnz     short loc_180048195
0x180048163  lea     rcx, [rsp+58h+arg_0]; this
0x180048168  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004816d  xor     r8d, r8d; pcbe
0x180048170  mov     rdx, rdi; pv
0x180048173  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004817a  call    cs:__imp_CreateThreadpoolTimer
0x180048180  mov     rdx, rax
0x180048183  mov     rcx, rbx
0x180048186  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004818b  lea     rcx, [rsp+58h+arg_0]; this
0x180048190  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180048195  mov     r8d, 493E0h
0x18004819b  lea     rdx, [rdi+41h]
0x18004819f  mov     rcx, rbx
0x1800481a2  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800481a7  lea     rcx, [rsp+58h+var_38]
0x1800481ac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800481b1  nop
0x1800481b2  add     rsp, 38h
0x1800481b6  pop     rdi
0x1800481b7  pop     rsi
0x1800481b8  pop     rbp
0x1800481b9  pop     rbx
0x1800481ba  retn
```
