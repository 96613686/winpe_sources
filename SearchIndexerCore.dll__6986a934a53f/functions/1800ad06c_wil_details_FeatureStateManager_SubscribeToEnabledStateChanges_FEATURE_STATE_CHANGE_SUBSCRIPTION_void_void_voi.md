# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800ad06c`
- end: `0x1800ad133`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ad730`

## callees

- `0x18006966c`
- `0x1800ad06c`
- `0x1800ad230`
- `0x1800ae300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad0a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad0a1`

## string_xrefs

- `0x1800ad0cc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800ad06c  mov     [rsp+arg_8], rbx
0x1800ad071  mov     [rsp+arg_10], rbp
0x1800ad076  push    rsi
0x1800ad077  push    rdi
0x1800ad078  push    r14
0x1800ad07a  sub     rsp, 30h
0x1800ad07e  mov     qword ptr [rdx], 0
0x1800ad085  mov     rbp, r9
0x1800ad088  cmp     byte ptr [rcx], 0
0x1800ad08b  mov     r14, r8
0x1800ad08e  mov     rsi, rdx
0x1800ad091  mov     rdi, rcx
0x1800ad094  jz      loc_1800AD120
0x1800ad09a  lea     rbx, [rcx+20h]
0x1800ad09e  mov     rcx, rbx; SRWLock
0x1800ad0a1  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad0a7  mov     [rsp+48h+arg_0], rbx
0x1800ad0ac  lea     rbx, [rdi+90h]
0x1800ad0b3  cmp     qword ptr [rbx], 0
0x1800ad0b7  jnz     short loc_1800AD104
0x1800ad0b9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800ad0c0  mov     qword ptr [rbx], 0
0x1800ad0c7  test    rax, rax
0x1800ad0ca  jnz     short loc_1800AD0EB
0x1800ad0cc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800ad0d3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800ad0d8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800ad0df  test    rax, rax
0x1800ad0e2  jnz     short loc_1800AD0EB
0x1800ad0e4  mov     eax, 0C0000139h
0x1800ad0e9  jmp     short loc_1800AD100
0x1800ad0eb  mov     r9, rbx
0x1800ad0ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800ad0f5  xor     r8d, r8d
0x1800ad0f8  mov     rdx, rdi
0x1800ad0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad100  test    eax, eax
0x1800ad102  jnz     short loc_1800AD116
0x1800ad104  lea     rcx, [rdi+48h]; this
0x1800ad108  mov     r9, rbp; void *
0x1800ad10b  mov     r8, r14; void (*)(void *)
0x1800ad10e  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800ad111  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800ad116  lea     rcx, [rsp+48h+arg_0]
0x1800ad11b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ad120  mov     rbx, [rsp+48h+arg_8]
0x1800ad125  mov     rbp, [rsp+48h+arg_10]
0x1800ad12a  add     rsp, 30h
0x1800ad12e  pop     r14
0x1800ad130  pop     rdi
0x1800ad131  pop     rsi
0x1800ad132  retn
```
