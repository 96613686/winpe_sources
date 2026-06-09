# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000aedc`
- end: `0x18000af9e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000c750`

## callees

- `0x180008418`
- `0x180008700`
- `0x1800089f0`
- `0x180009084`
- `0x1800090c8`
- `0x18000aa9c`
- `0x18000ae34`
- `0x18000aedc`
- `0x18000ce38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000af2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000af2b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af5d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af5d`

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
0x18000aedc  push    rbx
0x18000aede  push    rbp
0x18000aedf  push    rsi
0x18000aee0  push    rdi
0x18000aee1  sub     rsp, 38h
0x18000aee5  mov     rbx, r9
0x18000aee8  mov     esi, r8d
0x18000aeeb  mov     ebp, edx
0x18000aeed  mov     rdi, rcx
0x18000aef0  cmp     byte ptr [rcx], 0
0x18000aef3  jz      loc_18000AF95
0x18000aef9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aefe  test    al, al
0x18000af00  jz      loc_18000AF95
0x18000af06  mov     r9, rbx
0x18000af09  mov     r8d, esi
0x18000af0c  mov     edx, ebp
0x18000af0e  mov     rcx, [rdi+18h]
0x18000af12  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000af17  test    al, al
0x18000af19  jz      short loc_18000AF95
0x18000af1b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000af20  test    al, al
0x18000af22  jnz     short loc_18000AF95
0x18000af24  lea     rbx, [rdi+20h]
0x18000af28  mov     rcx, rbx; SRWLock
0x18000af2b  call    cs:__imp_AcquireSRWLockExclusive
0x18000af31  mov     [rsp+58h+var_38], rbx
0x18000af36  cmp     byte ptr [rdi+41h], 0
0x18000af3a  jnz     short loc_18000AF8A
0x18000af3c  lea     rbx, [rdi+30h]
0x18000af40  cmp     qword ptr [rbx], 0
0x18000af44  jnz     short loc_18000AF78
0x18000af46  lea     rcx, [rsp+58h+arg_0]; this
0x18000af4b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000af50  xor     r8d, r8d; pcbe
0x18000af53  mov     rdx, rdi; pv
0x18000af56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000af5d  call    cs:__imp_CreateThreadpoolTimer
0x18000af63  mov     rdx, rax
0x18000af66  mov     rcx, rbx
0x18000af69  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000af6e  lea     rcx, [rsp+58h+arg_0]; this
0x18000af73  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000af78  mov     r8d, 493E0h
0x18000af7e  lea     rdx, [rdi+41h]
0x18000af82  mov     rcx, rbx
0x18000af85  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000af8a  lea     rcx, [rsp+58h+var_38]
0x18000af8f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000af94  nop
0x18000af95  add     rsp, 38h
0x18000af99  pop     rdi
0x18000af9a  pop     rsi
0x18000af9b  pop     rbp
0x18000af9c  pop     rbx
0x18000af9d  retn
```
