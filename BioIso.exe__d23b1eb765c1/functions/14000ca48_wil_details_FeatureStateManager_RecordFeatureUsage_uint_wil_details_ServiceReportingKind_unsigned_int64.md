# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000ca48`
- end: `0x14000cb1b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1400292b0`

## callees

- `0x14000bd48`
- `0x14000c604`
- `0x14000c628`
- `0x14000c670`
- `0x14000c69c`
- `0x14000ca48`
- `0x140013958`
- `0x140026138`
- `0x140027b04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000cad3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000cad3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v10 = (RTL_SRWLOCK *)(a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v10);
  }
}

```

## disassembly

```asm
0x14000ca48  push    rbx
0x14000ca4a  push    rbp
0x14000ca4b  push    rsi
0x14000ca4c  push    rdi
0x14000ca4d  sub     rsp, 38h
0x14000ca51  mov     rbx, r9
0x14000ca54  mov     esi, r8d
0x14000ca57  mov     ebp, edx
0x14000ca59  mov     rdi, rcx
0x14000ca5c  cmp     byte ptr [rcx], 0
0x14000ca5f  jz      loc_14000CB11
0x14000ca65  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000ca6a  test    al, al
0x14000ca6c  jz      loc_14000CB11
0x14000ca72  mov     r9, rbx
0x14000ca75  mov     r8d, esi
0x14000ca78  mov     edx, ebp
0x14000ca7a  mov     rcx, [rdi+18h]
0x14000ca7e  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000ca83  test    al, al
0x14000ca85  jz      loc_14000CB11
0x14000ca8b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000ca90  test    al, al
0x14000ca92  jnz     short loc_14000CB11
0x14000ca94  lea     rbx, [rdi+20h]
0x14000ca98  mov     rcx, rbx; SRWLock
0x14000ca9b  call    cs:__imp_AcquireSRWLockExclusive
0x14000caa2  nop     dword ptr [rax+rax+00h]
0x14000caa7  mov     [rsp+58h+var_38], rbx
0x14000caac  cmp     byte ptr [rdi+41h], 0
0x14000cab0  jnz     short loc_14000CB06
0x14000cab2  lea     rbx, [rdi+30h]
0x14000cab6  cmp     qword ptr [rbx], 0
0x14000caba  jnz     short loc_14000CAF4
0x14000cabc  lea     rcx, [rsp+58h+arg_0]; this
0x14000cac1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000cac6  xor     r8d, r8d; pcbe
0x14000cac9  mov     rdx, rdi; pv
0x14000cacc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000cad3  call    cs:__imp_CreateThreadpoolTimer
0x14000cada  nop     dword ptr [rax+rax+00h]
0x14000cadf  mov     rdx, rax
0x14000cae2  mov     rcx, rbx
0x14000cae5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000caea  lea     rcx, [rsp+58h+arg_0]; this
0x14000caef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000caf4  mov     r8d, 493E0h
0x14000cafa  lea     rdx, [rdi+41h]
0x14000cafe  mov     rcx, rbx
0x14000cb01  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000cb06  lea     rcx, [rsp+58h+var_38]
0x14000cb0b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14000cb10  nop
0x14000cb11  add     rsp, 38h
0x14000cb15  pop     rdi
0x14000cb16  pop     rsi
0x14000cb17  pop     rbp
0x14000cb18  pop     rbx
0x14000cb19  retn
```
