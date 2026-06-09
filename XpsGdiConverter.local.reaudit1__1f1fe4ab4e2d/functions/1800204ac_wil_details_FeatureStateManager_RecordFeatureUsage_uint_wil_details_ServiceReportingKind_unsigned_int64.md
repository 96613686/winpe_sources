# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800204ac`
- end: `0x18002056e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180022030`

## callees

- `0x18000a894`
- `0x18000ab7c`
- `0x18000c11c`
- `0x18001da5c`
- `0x18001e628`
- `0x18001e66c`
- `0x180020404`
- `0x1800204ac`
- `0x18002308c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18002052d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002052d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800204fb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800204fb`

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
0x1800204ac  push    rbx
0x1800204ae  push    rbp
0x1800204af  push    rsi
0x1800204b0  push    rdi
0x1800204b1  sub     rsp, 38h
0x1800204b5  mov     rbx, r9
0x1800204b8  mov     esi, r8d
0x1800204bb  mov     ebp, edx
0x1800204bd  mov     rdi, rcx
0x1800204c0  cmp     byte ptr [rcx], 0
0x1800204c3  jz      loc_180020565
0x1800204c9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800204ce  test    al, al
0x1800204d0  jz      loc_180020565
0x1800204d6  mov     r9, rbx
0x1800204d9  mov     r8d, esi
0x1800204dc  mov     edx, ebp
0x1800204de  mov     rcx, [rdi+18h]
0x1800204e2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800204e7  test    al, al
0x1800204e9  jz      short loc_180020565
0x1800204eb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800204f0  test    al, al
0x1800204f2  jnz     short loc_180020565
0x1800204f4  lea     rbx, [rdi+20h]
0x1800204f8  mov     rcx, rbx; SRWLock
0x1800204fb  call    cs:__imp_AcquireSRWLockExclusive
0x180020501  mov     [rsp+58h+var_38], rbx
0x180020506  cmp     byte ptr [rdi+41h], 0
0x18002050a  jnz     short loc_18002055A
0x18002050c  lea     rbx, [rdi+30h]
0x180020510  cmp     qword ptr [rbx], 0
0x180020514  jnz     short loc_180020548
0x180020516  lea     rcx, [rsp+58h+arg_0]; this
0x18002051b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020520  xor     r8d, r8d; pcbe
0x180020523  mov     rdx, rdi; pv
0x180020526  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002052d  call    cs:__imp_CreateThreadpoolTimer
0x180020533  mov     rdx, rax
0x180020536  mov     rcx, rbx
0x180020539  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002053e  lea     rcx, [rsp+58h+arg_0]; this
0x180020543  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020548  mov     r8d, 493E0h
0x18002054e  lea     rdx, [rdi+41h]
0x180020552  mov     rcx, rbx
0x180020555  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002055a  lea     rcx, [rsp+58h+var_38]
0x18002055f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020564  nop
0x180020565  add     rsp, 38h
0x180020569  pop     rdi
0x18002056a  pop     rsi
0x18002056b  pop     rbp
0x18002056c  pop     rbx
0x18002056d  retn
```
