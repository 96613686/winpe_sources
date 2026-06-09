# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400066a8`
- end: `0x14000676f`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140006ca0`

## callees

- `0x140001c44`
- `0x1400066a8`
- `0x14000686c`
- `0x1400072ec`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400066dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400066dd`

## string_xrefs

- `0x140006708`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    v11 = v8;
    if ( this[18].Ptr
      || ((NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
           this[18].Ptr = 0,
           NtDllProcedureAddress)
       || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
           (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
        ? (v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))NtDllProcedureAddress)(
                   _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                   this,
                   0,
                   &this[18]))
        : (v10 = -1073741511),
          !v10) )
    {
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x1400066a8  mov     [rsp+arg_8], rbx
0x1400066ad  mov     [rsp+arg_10], rbp
0x1400066b2  push    rsi
0x1400066b3  push    rdi
0x1400066b4  push    r14
0x1400066b6  sub     rsp, 30h
0x1400066ba  mov     qword ptr [rdx], 0
0x1400066c1  mov     rbp, r9
0x1400066c4  cmp     byte ptr [rcx], 0
0x1400066c7  mov     r14, r8
0x1400066ca  mov     rsi, rdx
0x1400066cd  mov     rdi, rcx
0x1400066d0  jz      loc_14000675C
0x1400066d6  lea     rbx, [rcx+20h]
0x1400066da  mov     rcx, rbx; SRWLock
0x1400066dd  call    cs:__imp_AcquireSRWLockExclusive
0x1400066e3  mov     [rsp+48h+arg_0], rbx
0x1400066e8  lea     rbx, [rdi+90h]
0x1400066ef  cmp     qword ptr [rbx], 0
0x1400066f3  jnz     short loc_140006740
0x1400066f5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1400066fc  mov     qword ptr [rbx], 0
0x140006703  test    rax, rax
0x140006706  jnz     short loc_140006727
0x140006708  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000670f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140006714  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000671b  test    rax, rax
0x14000671e  jnz     short loc_140006727
0x140006720  mov     eax, 0C0000139h
0x140006725  jmp     short loc_14000673C
0x140006727  mov     r9, rbx
0x14000672a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140006731  xor     r8d, r8d
0x140006734  mov     rdx, rdi
0x140006737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000673c  test    eax, eax
0x14000673e  jnz     short loc_140006752
0x140006740  lea     rcx, [rdi+48h]; this
0x140006744  mov     r9, rbp; void *
0x140006747  mov     r8, r14; void (*)(void *)
0x14000674a  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000674d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140006752  lea     rcx, [rsp+48h+arg_0]
0x140006757  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000675c  mov     rbx, [rsp+48h+arg_8]
0x140006761  mov     rbp, [rsp+48h+arg_10]
0x140006766  add     rsp, 30h
0x14000676a  pop     r14
0x14000676c  pop     rdi
0x14000676d  pop     rsi
0x14000676e  retn
```
