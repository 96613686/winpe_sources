# wil::details::FeatureStateManager::RecordFeatureError(uint,FEATURE_ERROR const &)

- ea: `0x18004491c`
- end: `0x180044a1d`
- name: `?RecordFeatureError@FeatureStateManager@details@wil@@QEAAXIAEBUFEATURE_ERROR@@@Z`
- size: `257`
- prototype: `void __fastcall(PVOID pv, unsigned int, const struct FEATURE_ERROR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180069c30`

## callees

- `0x18004491c`
- `0x180044a24`
- `0x180044a44`
- `0x180044a88`
- `0x180044aac`
- `0x180044c28`
- `0x180044cf4`
- `0x1800458e0`
- `0x180066774`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800449a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800449a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800449d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800449d5`

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
  char *v9; // [rsp+78h] [rbp+20h] BYREF

  if ( *pv )
  {
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(a2, 0);
    if ( wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)pv)
      && wil::details_abi::FeatureStateData::RecordFeatureError(*((PSRWLOCK *)pv + 3), a2, a3)
      && !wil::ProcessShutdownInProgress(v6) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)pv + 4);
      v9 = pv + 32;
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
0x18004491c  mov     r11, rsp
0x18004491f  mov     [r11+10h], rbx
0x180044923  mov     [r11+18h], rsi
0x180044927  push    rdi
0x180044928  sub     rsp, 50h
0x18004492c  mov     rbx, r8
0x18004492f  mov     esi, edx
0x180044931  mov     rdi, rcx
0x180044934  cmp     byte ptr [rcx], 0
0x180044937  jz      loc_180044A0D
0x18004493d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180044944  test    rax, rax
0x180044947  jz      short loc_180044971
0x180044949  mov     r9d, 1
0x18004494f  mov     [r11-20h], r9
0x180044953  mov     [rsp+58h+var_28], 0
0x180044958  mov     qword ptr [r11-30h], 0
0x180044960  mov     qword ptr [r11-38h], 0
0x180044968  xor     edx, edx
0x18004496a  mov     ecx, esi
0x18004496c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044971  mov     rcx, rdi; this
0x180044974  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180044979  test    al, al
0x18004497b  jz      loc_180044A0D
0x180044981  mov     r8, rbx; struct FEATURE_ERROR *
0x180044984  mov     edx, esi; unsigned int
0x180044986  mov     rcx, [rdi+18h]; SRWLock
0x18004498a  call    ?RecordFeatureError@FeatureStateData@details_abi@wil@@QEAA_NIAEBUFEATURE_ERROR@@@Z; wil::details_abi::FeatureStateData::RecordFeatureError(uint,FEATURE_ERROR const &)
0x18004498f  test    al, al
0x180044991  jz      short loc_180044A0D
0x180044993  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180044998  test    al, al
0x18004499a  jnz     short loc_180044A0D
0x18004499c  lea     rbx, [rdi+20h]
0x1800449a0  mov     rcx, rbx; SRWLock
0x1800449a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800449a9  mov     [rsp+58h+arg_18], rbx
0x1800449ae  cmp     byte ptr [rdi+41h], 0
0x1800449b2  jnz     short loc_180044A02
0x1800449b4  lea     rbx, [rdi+30h]
0x1800449b8  cmp     qword ptr [rbx], 0
0x1800449bc  jnz     short loc_1800449F0
0x1800449be  lea     rcx, [rsp+58h+arg_0]; this
0x1800449c3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800449c8  xor     r8d, r8d; pcbe
0x1800449cb  mov     rdx, rdi; pv
0x1800449ce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800449d5  call    cs:__imp_CreateThreadpoolTimer
0x1800449db  mov     rdx, rax
0x1800449de  mov     rcx, rbx
0x1800449e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800449e6  lea     rcx, [rsp+58h+arg_0]; this
0x1800449eb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800449f0  mov     r8d, 493E0h
0x1800449f6  lea     rdx, [rdi+41h]
0x1800449fa  mov     rcx, rbx
0x1800449fd  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180044a02  lea     rcx, [rsp+58h+arg_18]
0x180044a07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180044a0c  nop
0x180044a0d  mov     rbx, [rsp+58h+arg_8]
0x180044a12  mov     rsi, [rsp+58h+arg_10]
0x180044a17  add     rsp, 50h
0x180044a1b  pop     rdi
0x180044a1c  retn
```
