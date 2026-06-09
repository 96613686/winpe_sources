# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001abbc`
- end: `0x18001ac88`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180011f50`

## callees

- `0x18000debc`
- `0x180010490`
- `0x180011e58`
- `0x18001a7e8`
- `0x18001abbc`
- `0x18001ac90`
- `0x18001adc8`
- `0x1800246e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ac0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ac0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac5d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ac41`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ac41`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF
  char v12; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+64h] [rbp+Ch]

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v9 = a1[65] == 0;
    v11 = (RTL_SRWLOCK *)(a1 + 32);
    if ( v9 )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        if ( !v12 )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18001abbc  push    rbx
0x18001abbe  push    rbp
0x18001abbf  push    rsi
0x18001abc0  push    rdi
0x18001abc1  sub     rsp, 38h
0x18001abc5  cmp     byte ptr [rcx], 0
0x18001abc8  mov     rbx, r9
0x18001abcb  mov     esi, r8d
0x18001abce  mov     ebp, edx
0x18001abd0  mov     rdi, rcx
0x18001abd3  jz      loc_18001AC7F
0x18001abd9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001abde  test    al, al
0x18001abe0  jz      loc_18001AC7F
0x18001abe6  mov     rcx, [rdi+18h]
0x18001abea  mov     r9, rbx
0x18001abed  mov     r8d, esi
0x18001abf0  mov     edx, ebp
0x18001abf2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001abf7  test    al, al
0x18001abf9  jz      loc_18001AC7F
0x18001abff  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ac04  test    al, al
0x18001ac06  jnz     short loc_18001AC7F
0x18001ac08  lea     rbx, [rdi+20h]
0x18001ac0c  mov     rcx, rbx; SRWLock
0x18001ac0f  call    cs:__imp_AcquireSRWLockExclusive
0x18001ac15  cmp     byte ptr [rdi+41h], 0
0x18001ac19  mov     [rsp+58h+var_38], rbx
0x18001ac1e  jnz     short loc_18001AC75
0x18001ac20  lea     rbx, [rdi+30h]
0x18001ac24  cmp     qword ptr [rbx], 0
0x18001ac28  jnz     short loc_18001AC63
0x18001ac2a  lea     rcx, [rsp+58h+arg_0]; this
0x18001ac2f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ac34  xor     r8d, r8d; pcbe
0x18001ac37  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ac3e  mov     rdx, rdi; pv
0x18001ac41  call    cs:__imp_CreateThreadpoolTimer
0x18001ac47  mov     rdx, rax
0x18001ac4a  mov     rcx, rbx
0x18001ac4d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ac52  cmp     [rsp+58h+arg_0], 0
0x18001ac57  jnz     short loc_18001AC63
0x18001ac59  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18001ac5d  call    cs:__imp_SetLastError
0x18001ac63  mov     r8d, 493E0h
0x18001ac69  lea     rdx, [rdi+41h]
0x18001ac6d  mov     rcx, rbx
0x18001ac70  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001ac75  lea     rcx, [rsp+58h+var_38]
0x18001ac7a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ac7f  add     rsp, 38h
0x18001ac83  pop     rdi
0x18001ac84  pop     rsi
0x18001ac85  pop     rbp
0x18001ac86  pop     rbx
0x18001ac87  retn
```
