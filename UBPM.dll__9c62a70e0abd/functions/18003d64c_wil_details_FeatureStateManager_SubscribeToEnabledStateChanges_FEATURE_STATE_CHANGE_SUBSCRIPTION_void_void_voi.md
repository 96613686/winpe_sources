# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18003d64c`
- end: `0x18003d71a`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003dd00`

## callees

- `0x180032040`
- `0x180036c34`
- `0x18003d64c`
- `0x18003d820`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d681`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d681`

## string_xrefs

- `0x18003d6b2`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18003d64c  mov     [rsp+arg_8], rbx
0x18003d651  mov     [rsp+arg_10], rbp
0x18003d656  push    rsi
0x18003d657  push    rdi
0x18003d658  push    r14
0x18003d65a  sub     rsp, 30h
0x18003d65e  mov     qword ptr [rdx], 0
0x18003d665  mov     rbp, r9
0x18003d668  cmp     byte ptr [rcx], 0
0x18003d66b  mov     r14, r8
0x18003d66e  mov     rsi, rdx
0x18003d671  mov     rdi, rcx
0x18003d674  jz      loc_18003D706
0x18003d67a  lea     rbx, [rcx+20h]
0x18003d67e  mov     rcx, rbx; SRWLock
0x18003d681  call    cs:__imp_AcquireSRWLockExclusive
0x18003d688  nop     dword ptr [rax+rax+00h]
0x18003d68d  mov     [rsp+48h+arg_0], rbx
0x18003d692  lea     rbx, [rdi+90h]
0x18003d699  cmp     qword ptr [rbx], 0
0x18003d69d  jnz     short loc_18003D6EA
0x18003d69f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18003d6a6  mov     qword ptr [rbx], 0
0x18003d6ad  test    rax, rax
0x18003d6b0  jnz     short loc_18003D6D1
0x18003d6b2  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003d6b9  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003d6be  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18003d6c5  test    rax, rax
0x18003d6c8  jnz     short loc_18003D6D1
0x18003d6ca  mov     eax, 0C0000139h
0x18003d6cf  jmp     short loc_18003D6E6
0x18003d6d1  mov     r9, rbx
0x18003d6d4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18003d6db  xor     r8d, r8d
0x18003d6de  mov     rdx, rdi
0x18003d6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6e6  test    eax, eax
0x18003d6e8  jnz     short loc_18003D6FC
0x18003d6ea  lea     rcx, [rdi+48h]; this
0x18003d6ee  mov     r9, rbp; void *
0x18003d6f1  mov     r8, r14; void (*)(void *)
0x18003d6f4  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18003d6f7  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18003d6fc  lea     rcx, [rsp+48h+arg_0]
0x18003d701  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d706  mov     rbx, [rsp+48h+arg_8]
0x18003d70b  mov     rbp, [rsp+48h+arg_10]
0x18003d710  add     rsp, 30h
0x18003d714  pop     r14
0x18003d716  pop     rdi
0x18003d717  pop     rsi
0x18003d718  retn
```
