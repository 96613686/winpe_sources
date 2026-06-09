# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18003ba88`
- end: `0x18003bb4a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180089910`

## callees

- `0x18003ba88`
- `0x18003bb50`
- `0x18003bdc4`
- `0x18003bdf8`
- `0x18003be18`
- `0x1800629dc`
- `0x1800629fc`
- `0x180062a40`
- `0x18006bba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bad7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bad7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bb09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bb09`

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
    PendingRequestManager::~PendingRequestManager((PendingRequestManager *)&v10);
  }
}

```

## disassembly

```asm
0x18003ba88  push    rbx
0x18003ba8a  push    rbp
0x18003ba8b  push    rsi
0x18003ba8c  push    rdi
0x18003ba8d  sub     rsp, 38h
0x18003ba91  mov     rbx, r9
0x18003ba94  mov     esi, r8d
0x18003ba97  mov     ebp, edx
0x18003ba99  mov     rdi, rcx
0x18003ba9c  cmp     byte ptr [rcx], 0
0x18003ba9f  jz      loc_18003BB41
0x18003baa5  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18003baaa  test    al, al
0x18003baac  jz      loc_18003BB41
0x18003bab2  mov     r9, rbx
0x18003bab5  mov     r8d, esi
0x18003bab8  mov     edx, ebp
0x18003baba  mov     rcx, [rdi+18h]
0x18003babe  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18003bac3  test    al, al
0x18003bac5  jz      short loc_18003BB41
0x18003bac7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003bacc  test    al, al
0x18003bace  jnz     short loc_18003BB41
0x18003bad0  lea     rbx, [rdi+20h]
0x18003bad4  mov     rcx, rbx; SRWLock
0x18003bad7  call    cs:__imp_AcquireSRWLockExclusive
0x18003badd  mov     [rsp+58h+var_38], rbx
0x18003bae2  cmp     byte ptr [rdi+41h], 0
0x18003bae6  jnz     short loc_18003BB36
0x18003bae8  lea     rbx, [rdi+30h]
0x18003baec  cmp     qword ptr [rbx], 0
0x18003baf0  jnz     short loc_18003BB24
0x18003baf2  lea     rcx, [rsp+58h+arg_0]; this
0x18003baf7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003bafc  xor     r8d, r8d; pcbe
0x18003baff  mov     rdx, rdi; pv
0x18003bb02  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003bb09  call    cs:__imp_CreateThreadpoolTimer
0x18003bb0f  mov     rdx, rax
0x18003bb12  mov     rcx, rbx
0x18003bb15  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003bb1a  lea     rcx, [rsp+58h+arg_0]; this
0x18003bb1f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003bb24  mov     r8d, 493E0h
0x18003bb2a  lea     rdx, [rdi+41h]
0x18003bb2e  mov     rcx, rbx
0x18003bb31  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003bb36  lea     rcx, [rsp+58h+var_38]; this
0x18003bb3b  call    ??1PendingRequestManager@@QEAA@XZ; PendingRequestManager::~PendingRequestManager(void)
0x18003bb40  nop
0x18003bb41  add     rsp, 38h
0x18003bb45  pop     rdi
0x18003bb46  pop     rsi
0x18003bb47  pop     rbp
0x18003bb48  pop     rbx
0x18003bb49  retn
```
