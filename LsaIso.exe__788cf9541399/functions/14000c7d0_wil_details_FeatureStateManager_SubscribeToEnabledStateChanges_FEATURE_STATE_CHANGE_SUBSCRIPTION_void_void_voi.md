# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000c7d0`
- end: `0x14000c897`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d050`

## callees

- `0x140002cec`
- `0x140002d0c`
- `0x14000c7d0`
- `0x14000c994`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c805`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c805`

## string_xrefs

- `0x14000c830`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000c7d0  mov     [rsp+arg_8], rbx
0x14000c7d5  mov     [rsp+arg_10], rbp
0x14000c7da  push    rsi
0x14000c7db  push    rdi
0x14000c7dc  push    r14
0x14000c7de  sub     rsp, 30h
0x14000c7e2  mov     qword ptr [rdx], 0
0x14000c7e9  mov     rbp, r9
0x14000c7ec  cmp     byte ptr [rcx], 0
0x14000c7ef  mov     r14, r8
0x14000c7f2  mov     rsi, rdx
0x14000c7f5  mov     rdi, rcx
0x14000c7f8  jz      loc_14000C884
0x14000c7fe  lea     rbx, [rcx+20h]
0x14000c802  mov     rcx, rbx; SRWLock
0x14000c805  call    cs:__imp_AcquireSRWLockExclusive
0x14000c80b  mov     [rsp+48h+arg_0], rbx
0x14000c810  lea     rbx, [rdi+90h]
0x14000c817  cmp     qword ptr [rbx], 0
0x14000c81b  jnz     short loc_14000C868
0x14000c81d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c824  mov     qword ptr [rbx], 0
0x14000c82b  test    rax, rax
0x14000c82e  jnz     short loc_14000C84F
0x14000c830  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c837  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c83c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c843  test    rax, rax
0x14000c846  jnz     short loc_14000C84F
0x14000c848  mov     eax, 0C0000139h
0x14000c84d  jmp     short loc_14000C864
0x14000c84f  mov     r9, rbx
0x14000c852  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000c859  xor     r8d, r8d
0x14000c85c  mov     rdx, rdi
0x14000c85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c864  test    eax, eax
0x14000c866  jnz     short loc_14000C87A
0x14000c868  lea     rcx, [rdi+48h]; this
0x14000c86c  mov     r9, rbp; void *
0x14000c86f  mov     r8, r14; void (*)(void *)
0x14000c872  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000c875  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000c87a  lea     rcx, [rsp+48h+arg_0]
0x14000c87f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c884  mov     rbx, [rsp+48h+arg_8]
0x14000c889  mov     rbp, [rsp+48h+arg_10]
0x14000c88e  add     rsp, 30h
0x14000c892  pop     r14
0x14000c894  pop     rdi
0x14000c895  pop     rsi
0x14000c896  retn
```
