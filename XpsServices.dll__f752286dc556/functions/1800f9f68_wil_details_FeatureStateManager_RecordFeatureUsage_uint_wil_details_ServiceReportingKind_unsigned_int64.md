# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800f9f68`
- end: `0x1800fa02a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18013a670`

## callees

- `0x1800f9f68`
- `0x1800fa030`
- `0x1800fa050`
- `0x1800fa094`
- `0x1800fa0b4`
- `0x1800fa0d8`
- `0x1800fa200`
- `0x1801370a0`
- `0x180139134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9fb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9fb7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f9fe9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f9fe9`

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
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v10 = a1 + 4;
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x1800f9f68  push    rbx
0x1800f9f6a  push    rbp
0x1800f9f6b  push    rsi
0x1800f9f6c  push    rdi
0x1800f9f6d  sub     rsp, 38h
0x1800f9f71  mov     rbx, r9
0x1800f9f74  mov     esi, r8d
0x1800f9f77  mov     ebp, edx
0x1800f9f79  mov     rdi, rcx
0x1800f9f7c  cmp     byte ptr [rcx], 0
0x1800f9f7f  jz      loc_1800FA021
0x1800f9f85  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800f9f8a  test    al, al
0x1800f9f8c  jz      loc_1800FA021
0x1800f9f92  mov     r9, rbx
0x1800f9f95  mov     r8d, esi
0x1800f9f98  mov     edx, ebp
0x1800f9f9a  mov     rcx, [rdi+18h]
0x1800f9f9e  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800f9fa3  test    al, al
0x1800f9fa5  jz      short loc_1800FA021
0x1800f9fa7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800f9fac  test    al, al
0x1800f9fae  jnz     short loc_1800FA021
0x1800f9fb0  lea     rbx, [rdi+20h]
0x1800f9fb4  mov     rcx, rbx; SRWLock
0x1800f9fb7  call    cs:__imp_AcquireSRWLockExclusive
0x1800f9fbd  mov     [rsp+58h+var_38], rbx
0x1800f9fc2  cmp     byte ptr [rdi+41h], 0
0x1800f9fc6  jnz     short loc_1800FA016
0x1800f9fc8  lea     rbx, [rdi+30h]
0x1800f9fcc  cmp     qword ptr [rbx], 0
0x1800f9fd0  jnz     short loc_1800FA004
0x1800f9fd2  lea     rcx, [rsp+58h+arg_0]; this
0x1800f9fd7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800f9fdc  xor     r8d, r8d; pcbe
0x1800f9fdf  mov     rdx, rdi; pv
0x1800f9fe2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800f9fe9  call    cs:__imp_CreateThreadpoolTimer
0x1800f9fef  mov     rdx, rax
0x1800f9ff2  mov     rcx, rbx
0x1800f9ff5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800f9ffa  lea     rcx, [rsp+58h+arg_0]; this
0x1800f9fff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800fa004  mov     r8d, 493E0h
0x1800fa00a  lea     rdx, [rdi+41h]
0x1800fa00e  mov     rcx, rbx
0x1800fa011  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800fa016  lea     rcx, [rsp+58h+var_38]
0x1800fa01b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fa020  nop
0x1800fa021  add     rsp, 38h
0x1800fa025  pop     rdi
0x1800fa026  pop     rsi
0x1800fa027  pop     rbp
0x1800fa028  pop     rbx
0x1800fa029  retn
```
