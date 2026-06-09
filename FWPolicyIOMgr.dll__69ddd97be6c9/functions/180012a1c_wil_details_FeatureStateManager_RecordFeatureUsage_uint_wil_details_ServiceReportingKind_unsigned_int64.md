# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180012a1c`
- end: `0x180012aea`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `206`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001ae50`

## callees

- `0x180012a1c`
- `0x180012af0`
- `0x180012b7c`
- `0x1800135d4`
- `0x1800135f4`
- `0x180013654`
- `0x180013678`
- `0x180013738`
- `0x18001dd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ac8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ac8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012a88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012a88`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-28h] BYREF
  RTL_SRWLOCK *v11; // [rsp+28h] [rbp-20h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v11 = (RTL_SRWLOCK *)(a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180012a1c  mov     [rsp+arg_18], rbx
0x180012a21  push    rbp
0x180012a22  push    rsi
0x180012a23  push    rdi
0x180012a24  sub     rsp, 30h
0x180012a28  mov     rbx, r9
0x180012a2b  mov     ebp, r8d
0x180012a2e  mov     esi, edx
0x180012a30  mov     rdi, rcx
0x180012a33  cmp     byte ptr [rcx], 0
0x180012a36  jz      short loc_180012A5A
0x180012a38  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180012a3d  test    al, al
0x180012a3f  jz      short loc_180012A5A
0x180012a41  mov     r9, rbx
0x180012a44  mov     r8d, ebp
0x180012a47  mov     edx, esi
0x180012a49  mov     rcx, [rdi+18h]
0x180012a4d  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180012a52  test    al, al
0x180012a54  jnz     loc_180012ADB
0x180012a5a  mov     rbx, [rsp+48h+arg_18]
0x180012a5f  add     rsp, 30h
0x180012a63  pop     rdi
0x180012a64  pop     rsi
0x180012a65  pop     rbp
0x180012a66  retn
0x180012a67  lea     rbx, [rdi+30h]
0x180012a6b  cmp     qword ptr [rbx], 0
0x180012a6f  jnz     short loc_180012AA3
0x180012a71  lea     rcx, [rsp+48h+var_28]; this
0x180012a76  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012a7b  xor     r8d, r8d; pcbe
0x180012a7e  mov     rdx, rdi; pv
0x180012a81  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012a88  call    cs:__imp_CreateThreadpoolTimer
0x180012a8e  mov     rdx, rax
0x180012a91  mov     rcx, rbx
0x180012a94  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012a99  lea     rcx, [rsp+48h+var_28]; this
0x180012a9e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012aa3  mov     r8d, 493E0h
0x180012aa9  lea     rdx, [rdi+41h]
0x180012aad  mov     rcx, rbx
0x180012ab0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180012ab5  lea     rcx, [rsp+48h+var_20]
0x180012aba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012abf  jmp     short loc_180012A5A
0x180012ac1  lea     rbx, [rdi+20h]
0x180012ac5  mov     rcx, rbx; SRWLock
0x180012ac8  call    cs:__imp_AcquireSRWLockExclusive
0x180012ace  mov     [rsp+48h+var_20], rbx
0x180012ad3  cmp     byte ptr [rdi+41h], 0
0x180012ad7  jnz     short loc_180012AB5
0x180012ad9  jmp     short loc_180012A67
0x180012adb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180012ae0  test    al, al
0x180012ae2  jnz     loc_180012A5A
0x180012ae8  jmp     short loc_180012AC1
```
