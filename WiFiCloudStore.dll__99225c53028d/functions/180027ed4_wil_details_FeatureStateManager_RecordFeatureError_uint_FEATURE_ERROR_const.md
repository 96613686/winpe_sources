# wil::details::FeatureStateManager::RecordFeatureError(uint,FEATURE_ERROR const &)

- ea: `0x180027ed4`
- end: `0x180027fd5`
- name: `?RecordFeatureError@FeatureStateManager@details@wil@@QEAAXIAEBUFEATURE_ERROR@@@Z`
- size: `257`
- prototype: `void __fastcall(PVOID pv, unsigned int, const struct FEATURE_ERROR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002e1e0`

## callees

- `0x18000e17c`
- `0x18000e19c`
- `0x18000e5e0`
- `0x18000f7f0`
- `0x18001acd0`
- `0x180027ed4`
- `0x180027fdc`
- `0x180028800`
- `0x18002d89c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027f5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027f5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027f8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027f8d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureError(
        char *pv,
        unsigned int a2,
        const struct FEATURE_ERROR *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  char v8; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+78h] [rbp+20h] BYREF

  if ( *pv )
  {
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(a2, 0);
    if ( wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)pv)
      && wil::details_abi::FeatureStateData::RecordFeatureError(*((PSRWLOCK *)pv + 3), a2, a3)
      && !wil::ProcessShutdownInProgress(v6) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)pv + 4);
      v9 = (RTL_SRWLOCK *)(pv + 32);
      if ( !pv[65] )
      {
        if ( !*((_QWORD *)pv + 6) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            pv + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
        }
        wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 6, pv + 65, 300000);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    }
  }
}

```

## disassembly

```asm
0x180027ed4  mov     r11, rsp
0x180027ed7  mov     [r11+10h], rbx
0x180027edb  mov     [r11+18h], rsi
0x180027edf  push    rdi
0x180027ee0  sub     rsp, 50h
0x180027ee4  mov     rbx, r8
0x180027ee7  mov     esi, edx
0x180027ee9  mov     rdi, rcx
0x180027eec  cmp     byte ptr [rcx], 0
0x180027eef  jz      loc_180027FC5
0x180027ef5  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180027efc  test    rax, rax
0x180027eff  jz      short loc_180027F29
0x180027f01  mov     r9d, 1
0x180027f07  mov     [r11-20h], r9
0x180027f0b  mov     [rsp+58h+var_28], 0
0x180027f10  mov     qword ptr [r11-30h], 0
0x180027f18  mov     qword ptr [r11-38h], 0
0x180027f20  xor     edx, edx
0x180027f22  mov     ecx, esi
0x180027f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f29  mov     rcx, rdi; this
0x180027f2c  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180027f31  test    al, al
0x180027f33  jz      loc_180027FC5
0x180027f39  mov     r8, rbx; struct FEATURE_ERROR *
0x180027f3c  mov     edx, esi; unsigned int
0x180027f3e  mov     rcx, [rdi+18h]; SRWLock
0x180027f42  call    ?RecordFeatureError@FeatureStateData@details_abi@wil@@QEAA_NIAEBUFEATURE_ERROR@@@Z; wil::details_abi::FeatureStateData::RecordFeatureError(uint,FEATURE_ERROR const &)
0x180027f47  test    al, al
0x180027f49  jz      short loc_180027FC5
0x180027f4b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180027f50  test    al, al
0x180027f52  jnz     short loc_180027FC5
0x180027f54  lea     rbx, [rdi+20h]
0x180027f58  mov     rcx, rbx; SRWLock
0x180027f5b  call    cs:__imp_AcquireSRWLockExclusive
0x180027f61  mov     [rsp+58h+arg_18], rbx
0x180027f66  cmp     byte ptr [rdi+41h], 0
0x180027f6a  jnz     short loc_180027FBA
0x180027f6c  lea     rbx, [rdi+30h]
0x180027f70  cmp     qword ptr [rbx], 0
0x180027f74  jnz     short loc_180027FA8
0x180027f76  lea     rcx, [rsp+58h+arg_0]; this
0x180027f7b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180027f80  xor     r8d, r8d; pcbe
0x180027f83  mov     rdx, rdi; pv
0x180027f86  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180027f8d  call    cs:__imp_CreateThreadpoolTimer
0x180027f93  mov     rdx, rax
0x180027f96  mov     rcx, rbx
0x180027f99  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180027f9e  lea     rcx, [rsp+58h+arg_0]; this
0x180027fa3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180027fa8  mov     r8d, 493E0h
0x180027fae  lea     rdx, [rdi+41h]
0x180027fb2  mov     rcx, rbx
0x180027fb5  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180027fba  lea     rcx, [rsp+58h+arg_18]
0x180027fbf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027fc4  nop
0x180027fc5  mov     rbx, [rsp+58h+arg_8]
0x180027fca  mov     rsi, [rsp+58h+arg_10]
0x180027fcf  add     rsp, 50h
0x180027fd3  pop     rdi
0x180027fd4  retn
```
