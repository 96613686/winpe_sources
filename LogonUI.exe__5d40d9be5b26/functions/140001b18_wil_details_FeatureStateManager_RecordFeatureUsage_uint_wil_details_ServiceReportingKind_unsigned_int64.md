# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140001b18`
- end: `0x140001bd9`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x140006c20`

## callees

- `0x140001650`
- `0x140001b18`
- `0x140001be0`
- `0x140001c00`
- `0x140001c44`
- `0x140001c64`
- `0x140001c88`
- `0x1400043a4`
- `0x140005bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001b67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001b67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001b99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001b99`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF
  char v12; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v9 = BYTE1(a1[8].Ptr) == 0;
    v11 = a1 + 4;
    if ( v9 )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x140001b18  push    rbx
0x140001b1a  push    rbp
0x140001b1b  push    rsi
0x140001b1c  push    rdi
0x140001b1d  sub     rsp, 38h
0x140001b21  cmp     byte ptr [rcx], 0
0x140001b24  mov     rbx, r9
0x140001b27  mov     esi, r8d
0x140001b2a  mov     ebp, edx
0x140001b2c  mov     rdi, rcx
0x140001b2f  jz      loc_140001BD0
0x140001b35  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140001b3a  test    al, al
0x140001b3c  jz      loc_140001BD0
0x140001b42  mov     rcx, [rdi+18h]
0x140001b46  mov     r9, rbx
0x140001b49  mov     r8d, esi
0x140001b4c  mov     edx, ebp
0x140001b4e  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140001b53  test    al, al
0x140001b55  jz      short loc_140001BD0
0x140001b57  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140001b5c  test    al, al
0x140001b5e  jnz     short loc_140001BD0
0x140001b60  lea     rbx, [rdi+20h]
0x140001b64  mov     rcx, rbx; SRWLock
0x140001b67  call    cs:__imp_AcquireSRWLockExclusive
0x140001b6d  cmp     byte ptr [rdi+41h], 0
0x140001b71  mov     [rsp+58h+var_38], rbx
0x140001b76  jnz     short loc_140001BC6
0x140001b78  lea     rbx, [rdi+30h]
0x140001b7c  cmp     qword ptr [rbx], 0
0x140001b80  jnz     short loc_140001BB4
0x140001b82  lea     rcx, [rsp+58h+arg_0]; this
0x140001b87  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140001b8c  xor     r8d, r8d; pcbe
0x140001b8f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140001b96  mov     rdx, rdi; pv
0x140001b99  call    cs:__imp_CreateThreadpoolTimer
0x140001b9f  mov     rdx, rax
0x140001ba2  mov     rcx, rbx
0x140001ba5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140001baa  lea     rcx, [rsp+58h+arg_0]; this
0x140001baf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140001bb4  mov     r8d, 493E0h
0x140001bba  lea     rdx, [rdi+41h]
0x140001bbe  mov     rcx, rbx
0x140001bc1  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140001bc6  lea     rcx, [rsp+58h+var_38]
0x140001bcb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140001bd0  add     rsp, 38h
0x140001bd4  pop     rdi
0x140001bd5  pop     rsi
0x140001bd6  pop     rbp
0x140001bd7  pop     rbx
0x140001bd8  retn
```
