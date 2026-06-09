# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800aef28`
- end: `0x1800aefef`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800af590`

## callees

- `0x18009ebc0`
- `0x1800aef28`
- `0x1800af0ec`
- `0x1800afd30`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aef5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aef5d`

## string_xrefs

- `0x1800aef88`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800aef28  mov     [rsp+arg_8], rbx
0x1800aef2d  mov     [rsp+arg_10], rbp
0x1800aef32  push    rsi
0x1800aef33  push    rdi
0x1800aef34  push    r14
0x1800aef36  sub     rsp, 30h
0x1800aef3a  mov     qword ptr [rdx], 0
0x1800aef41  mov     rbp, r9
0x1800aef44  cmp     byte ptr [rcx], 0
0x1800aef47  mov     r14, r8
0x1800aef4a  mov     rsi, rdx
0x1800aef4d  mov     rdi, rcx
0x1800aef50  jz      loc_1800AEFDC
0x1800aef56  lea     rbx, [rcx+20h]
0x1800aef5a  mov     rcx, rbx; SRWLock
0x1800aef5d  call    cs:__imp_AcquireSRWLockExclusive
0x1800aef63  mov     [rsp+48h+arg_0], rbx
0x1800aef68  lea     rbx, [rdi+90h]
0x1800aef6f  cmp     qword ptr [rbx], 0
0x1800aef73  jnz     short loc_1800AEFC0
0x1800aef75  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800aef7c  mov     qword ptr [rbx], 0
0x1800aef83  test    rax, rax
0x1800aef86  jnz     short loc_1800AEFA7
0x1800aef88  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800aef8f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800aef94  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800aef9b  test    rax, rax
0x1800aef9e  jnz     short loc_1800AEFA7
0x1800aefa0  mov     eax, 0C0000139h
0x1800aefa5  jmp     short loc_1800AEFBC
0x1800aefa7  mov     r9, rbx
0x1800aefaa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800aefb1  xor     r8d, r8d
0x1800aefb4  mov     rdx, rdi
0x1800aefb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aefbc  test    eax, eax
0x1800aefbe  jnz     short loc_1800AEFD2
0x1800aefc0  lea     rcx, [rdi+48h]; this
0x1800aefc4  mov     r9, rbp; void *
0x1800aefc7  mov     r8, r14; void (*)(void *)
0x1800aefca  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800aefcd  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800aefd2  lea     rcx, [rsp+48h+arg_0]
0x1800aefd7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800aefdc  mov     rbx, [rsp+48h+arg_8]
0x1800aefe1  mov     rbp, [rsp+48h+arg_10]
0x1800aefe6  add     rsp, 30h
0x1800aefea  pop     r14
0x1800aefec  pop     rdi
0x1800aefed  pop     rsi
0x1800aefee  retn
```
