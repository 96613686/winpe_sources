# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180029700`
- end: `0x1800297e8`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `232`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18001298c`
- `0x1800135d4`
- `0x18001db3c`
- `0x180029278`
- `0x180029700`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029750`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029750`

## string_xrefs

- `0x18002977c`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC NtDllProcedureAddress; // rax
  int v8; // eax
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp-28h] BYREF

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&stru_18004EFC0);
      v9 = &stru_18004EFC0;
      if ( qword_18004F030
        || ((NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
             qword_18004F030 = 0,
             g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification)
         || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
             (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
          ? (v8 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))NtDllProcedureAddress)(
                    _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                    &wil::details::g_featureStateManager,
                    0,
                    &qword_18004F030))
          : (v8 = -1073741511),
            !v8) )
      {
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    }
  }
}

```

## disassembly

```asm
0x180029700  mov     [rsp+arg_18], rbx
0x180029705  push    rbp
0x180029706  push    rsi
0x180029707  push    rdi
0x180029708  sub     rsp, 40h
0x18002970c  mov     rsi, r8
0x18002970f  mov     rdi, rdx
0x180029712  mov     rbx, rcx
0x180029715  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180029719  jnz     short loc_180029732
0x18002971b  mov     r8, rdx; void (*)(void *)
0x18002971e  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180029721  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180029728  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18002972d  jmp     loc_1800297DB
0x180029732  mov     qword ptr [rcx], 0
0x180029739  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180029740  jz      loc_1800297DB
0x180029746  lea     rbp, stru_18004EFC0
0x18002974d  mov     rcx, rbp; SRWLock
0x180029750  call    cs:__imp_AcquireSRWLockExclusive
0x180029756  cmp     cs:qword_18004F030, 0
0x18002975e  mov     [rsp+58h+var_28], rbp
0x180029763  jnz     short loc_1800297BC
0x180029765  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002976c  mov     cs:qword_18004F030, 0
0x180029777  test    rax, rax
0x18002977a  jnz     short loc_18002979B
0x18002977c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180029783  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180029788  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002978f  test    rax, rax
0x180029792  jnz     short loc_18002979B
0x180029794  mov     eax, 0C0000139h
0x180029799  jmp     short loc_1800297B8
0x18002979b  lea     r9, qword_18004F030
0x1800297a2  xor     r8d, r8d
0x1800297a5  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800297ac  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800297b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297b8  test    eax, eax
0x1800297ba  jnz     short loc_1800297D1
0x1800297bc  mov     r9, rsi; void *
0x1800297bf  lea     rcx, CriticalSection; this
0x1800297c6  mov     r8, rdi; void (*)(void *)
0x1800297c9  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800297cc  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800297d1  lea     rcx, [rsp+58h+var_28]
0x1800297d6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800297db  mov     rbx, [rsp+58h+arg_18]
0x1800297e0  add     rsp, 40h
0x1800297e4  pop     rdi
0x1800297e5  pop     rsi
0x1800297e6  pop     rbp
0x1800297e7  retn
```
