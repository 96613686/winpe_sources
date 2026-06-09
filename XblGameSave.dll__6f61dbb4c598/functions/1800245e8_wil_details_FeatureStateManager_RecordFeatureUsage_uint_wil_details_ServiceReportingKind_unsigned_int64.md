# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800245e8`
- end: `0x1800246aa`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180025d90`

## callees

- `0x180007df8`
- `0x180008434`
- `0x18000a840`
- `0x1800212c4`
- `0x180022a3c`
- `0x180022a80`
- `0x180024540`
- `0x1800245e8`
- `0x1800265f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024637`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024637`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024669`

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
0x1800245e8  push    rbx
0x1800245ea  push    rbp
0x1800245eb  push    rsi
0x1800245ec  push    rdi
0x1800245ed  sub     rsp, 38h
0x1800245f1  mov     rbx, r9
0x1800245f4  mov     esi, r8d
0x1800245f7  mov     ebp, edx
0x1800245f9  mov     rdi, rcx
0x1800245fc  cmp     byte ptr [rcx], 0
0x1800245ff  jz      loc_1800246A1
0x180024605  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002460a  test    al, al
0x18002460c  jz      loc_1800246A1
0x180024612  mov     r9, rbx
0x180024615  mov     r8d, esi
0x180024618  mov     edx, ebp
0x18002461a  mov     rcx, [rdi+18h]
0x18002461e  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180024623  test    al, al
0x180024625  jz      short loc_1800246A1
0x180024627  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002462c  test    al, al
0x18002462e  jnz     short loc_1800246A1
0x180024630  lea     rbx, [rdi+20h]
0x180024634  mov     rcx, rbx; SRWLock
0x180024637  call    cs:__imp_AcquireSRWLockExclusive
0x18002463d  mov     [rsp+58h+var_38], rbx
0x180024642  cmp     byte ptr [rdi+41h], 0
0x180024646  jnz     short loc_180024696
0x180024648  lea     rbx, [rdi+30h]
0x18002464c  cmp     qword ptr [rbx], 0
0x180024650  jnz     short loc_180024684
0x180024652  lea     rcx, [rsp+58h+arg_0]; this
0x180024657  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002465c  xor     r8d, r8d; pcbe
0x18002465f  mov     rdx, rdi; pv
0x180024662  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180024669  call    cs:__imp_CreateThreadpoolTimer
0x18002466f  mov     rdx, rax
0x180024672  mov     rcx, rbx
0x180024675  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002467a  lea     rcx, [rsp+58h+arg_0]; this
0x18002467f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180024684  mov     r8d, 493E0h
0x18002468a  lea     rdx, [rdi+41h]
0x18002468e  mov     rcx, rbx
0x180024691  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180024696  lea     rcx, [rsp+58h+var_38]
0x18002469b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800246a0  nop
0x1800246a1  add     rsp, 38h
0x1800246a5  pop     rdi
0x1800246a6  pop     rsi
0x1800246a7  pop     rbp
0x1800246a8  pop     rbx
0x1800246a9  retn
```
