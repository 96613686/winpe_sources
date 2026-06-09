# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180027634`
- end: `0x1800276fb`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180027ec0`

## callees

- `0x180018434`
- `0x180018e1c`
- `0x180027634`
- `0x1800277f8`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027669`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027669`

## string_xrefs

- `0x180027694`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180027634  mov     [rsp+arg_8], rbx
0x180027639  mov     [rsp+arg_10], rbp
0x18002763e  push    rsi
0x18002763f  push    rdi
0x180027640  push    r14
0x180027642  sub     rsp, 30h
0x180027646  mov     qword ptr [rdx], 0
0x18002764d  mov     rbp, r9
0x180027650  cmp     byte ptr [rcx], 0
0x180027653  mov     r14, r8
0x180027656  mov     rsi, rdx
0x180027659  mov     rdi, rcx
0x18002765c  jz      loc_1800276E8
0x180027662  lea     rbx, [rcx+20h]
0x180027666  mov     rcx, rbx; SRWLock
0x180027669  call    cs:__imp_AcquireSRWLockExclusive
0x18002766f  mov     [rsp+48h+arg_0], rbx
0x180027674  lea     rbx, [rdi+90h]
0x18002767b  cmp     qword ptr [rbx], 0
0x18002767f  jnz     short loc_1800276CC
0x180027681  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180027688  mov     qword ptr [rbx], 0
0x18002768f  test    rax, rax
0x180027692  jnz     short loc_1800276B3
0x180027694  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002769b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800276a0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800276a7  test    rax, rax
0x1800276aa  jnz     short loc_1800276B3
0x1800276ac  mov     eax, 0C0000139h
0x1800276b1  jmp     short loc_1800276C8
0x1800276b3  mov     r9, rbx
0x1800276b6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800276bd  xor     r8d, r8d
0x1800276c0  mov     rdx, rdi
0x1800276c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276c8  test    eax, eax
0x1800276ca  jnz     short loc_1800276DE
0x1800276cc  lea     rcx, [rdi+48h]; this
0x1800276d0  mov     r9, rbp; void *
0x1800276d3  mov     r8, r14; void (*)(void *)
0x1800276d6  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800276d9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800276de  lea     rcx, [rsp+48h+arg_0]
0x1800276e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800276e8  mov     rbx, [rsp+48h+arg_8]
0x1800276ed  mov     rbp, [rsp+48h+arg_10]
0x1800276f2  add     rsp, 30h
0x1800276f6  pop     r14
0x1800276f8  pop     rdi
0x1800276f9  pop     rsi
0x1800276fa  retn
```
