# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14005279c`
- end: `0x140052869`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x14008c170`

## callees

- `0x1400215f0`
- `0x1400378e4`
- `0x14004f1c8`
- `0x14005279c`
- `0x140052870`
- `0x1400528b4`
- `0x140086c24`
- `0x14008a178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400527ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400527ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005283d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005283d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140052821`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140052821`

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
  DWORD dwErrCode; // [rsp+64h] [rbp+Ch]

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
        if ( !v11 )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x14005279c  push    rbx
0x14005279e  push    rbp
0x14005279f  push    rsi
0x1400527a0  push    rdi
0x1400527a1  sub     rsp, 38h
0x1400527a5  mov     rbx, r9
0x1400527a8  mov     esi, r8d
0x1400527ab  mov     ebp, edx
0x1400527ad  mov     rdi, rcx
0x1400527b0  cmp     byte ptr [rcx], 0
0x1400527b3  jz      loc_140052860
0x1400527b9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400527be  test    al, al
0x1400527c0  jz      loc_140052860
0x1400527c6  mov     r9, rbx
0x1400527c9  mov     r8d, esi
0x1400527cc  mov     edx, ebp
0x1400527ce  mov     rcx, [rdi+18h]
0x1400527d2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400527d7  test    al, al
0x1400527d9  jz      loc_140052860
0x1400527df  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400527e4  test    al, al
0x1400527e6  jnz     short loc_140052860
0x1400527e8  lea     rbx, [rdi+20h]
0x1400527ec  mov     rcx, rbx; SRWLock
0x1400527ef  call    cs:__imp_AcquireSRWLockExclusive
0x1400527f5  mov     [rsp+58h+var_38], rbx
0x1400527fa  cmp     byte ptr [rdi+41h], 0
0x1400527fe  jnz     short loc_140052855
0x140052800  lea     rbx, [rdi+30h]
0x140052804  cmp     qword ptr [rbx], 0
0x140052808  jnz     short loc_140052843
0x14005280a  lea     rcx, [rsp+58h+arg_0]; this
0x14005280f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140052814  xor     r8d, r8d; pcbe
0x140052817  mov     rdx, rdi; pv
0x14005281a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140052821  call    cs:__imp_CreateThreadpoolTimer
0x140052827  mov     rdx, rax
0x14005282a  mov     rcx, rbx
0x14005282d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140052832  cmp     [rsp+58h+arg_0], 0
0x140052837  jnz     short loc_140052843
0x140052839  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x14005283d  call    cs:__imp_SetLastError
0x140052843  mov     r8d, 493E0h
0x140052849  lea     rdx, [rdi+41h]
0x14005284d  mov     rcx, rbx
0x140052850  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140052855  lea     rcx, [rsp+58h+var_38]
0x14005285a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14005285f  nop
0x140052860  add     rsp, 38h
0x140052864  pop     rdi
0x140052865  pop     rsi
0x140052866  pop     rbp
0x140052867  pop     rbx
0x140052868  retn
```
