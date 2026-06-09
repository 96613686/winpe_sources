# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000a87c`
- end: `0x14000a943`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b0b0`

## callees

- `0x1400067e4`
- `0x14000a87c`
- `0x14000aa40`
- `0x14000c040`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8b1`

## string_xrefs

- `0x14000a8dc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000a87c  mov     [rsp+arg_8], rbx
0x14000a881  mov     [rsp+arg_10], rbp
0x14000a886  push    rsi
0x14000a887  push    rdi
0x14000a888  push    r14
0x14000a88a  sub     rsp, 30h
0x14000a88e  mov     qword ptr [rdx], 0
0x14000a895  mov     rbp, r9
0x14000a898  cmp     byte ptr [rcx], 0
0x14000a89b  mov     r14, r8
0x14000a89e  mov     rsi, rdx
0x14000a8a1  mov     rdi, rcx
0x14000a8a4  jz      loc_14000A930
0x14000a8aa  lea     rbx, [rcx+20h]
0x14000a8ae  mov     rcx, rbx; SRWLock
0x14000a8b1  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8b7  mov     [rsp+48h+arg_0], rbx
0x14000a8bc  lea     rbx, [rdi+90h]
0x14000a8c3  cmp     qword ptr [rbx], 0
0x14000a8c7  jnz     short loc_14000A914
0x14000a8c9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000a8d0  mov     qword ptr [rbx], 0
0x14000a8d7  test    rax, rax
0x14000a8da  jnz     short loc_14000A8FB
0x14000a8dc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000a8e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a8e8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000a8ef  test    rax, rax
0x14000a8f2  jnz     short loc_14000A8FB
0x14000a8f4  mov     eax, 0C0000139h
0x14000a8f9  jmp     short loc_14000A910
0x14000a8fb  mov     r9, rbx
0x14000a8fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000a905  xor     r8d, r8d
0x14000a908  mov     rdx, rdi
0x14000a90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a910  test    eax, eax
0x14000a912  jnz     short loc_14000A926
0x14000a914  lea     rcx, [rdi+48h]; this
0x14000a918  mov     r9, rbp; void *
0x14000a91b  mov     r8, r14; void (*)(void *)
0x14000a91e  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000a921  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000a926  lea     rcx, [rsp+48h+arg_0]
0x14000a92b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a930  mov     rbx, [rsp+48h+arg_8]
0x14000a935  mov     rbp, [rsp+48h+arg_10]
0x14000a93a  add     rsp, 30h
0x14000a93e  pop     r14
0x14000a940  pop     rdi
0x14000a941  pop     rsi
0x14000a942  retn
```
