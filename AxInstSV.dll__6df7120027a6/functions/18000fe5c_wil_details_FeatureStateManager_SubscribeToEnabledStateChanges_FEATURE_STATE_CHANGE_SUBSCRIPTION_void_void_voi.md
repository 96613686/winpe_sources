# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000fe5c`
- end: `0x18000ff23`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180010b60`

## callees

- `0x180008720`
- `0x18000fe5c`
- `0x180010020`
- `0x180011540`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fe91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fe91`

## string_xrefs

- `0x18000febc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000fe5c  mov     [rsp+arg_8], rbx
0x18000fe61  mov     [rsp+arg_10], rbp
0x18000fe66  push    rsi
0x18000fe67  push    rdi
0x18000fe68  push    r14
0x18000fe6a  sub     rsp, 30h
0x18000fe6e  mov     qword ptr [rdx], 0
0x18000fe75  mov     rbp, r9
0x18000fe78  cmp     byte ptr [rcx], 0
0x18000fe7b  mov     r14, r8
0x18000fe7e  mov     rsi, rdx
0x18000fe81  mov     rdi, rcx
0x18000fe84  jz      loc_18000FF10
0x18000fe8a  lea     rbx, [rcx+20h]
0x18000fe8e  mov     rcx, rbx; SRWLock
0x18000fe91  call    cs:__imp_AcquireSRWLockExclusive
0x18000fe97  mov     [rsp+48h+arg_0], rbx
0x18000fe9c  lea     rbx, [rdi+90h]
0x18000fea3  cmp     qword ptr [rbx], 0
0x18000fea7  jnz     short loc_18000FEF4
0x18000fea9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000feb0  mov     qword ptr [rbx], 0
0x18000feb7  test    rax, rax
0x18000feba  jnz     short loc_18000FEDB
0x18000febc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000fec3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000fec8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000fecf  test    rax, rax
0x18000fed2  jnz     short loc_18000FEDB
0x18000fed4  mov     eax, 0C0000139h
0x18000fed9  jmp     short loc_18000FEF0
0x18000fedb  mov     r9, rbx
0x18000fede  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000fee5  xor     r8d, r8d
0x18000fee8  mov     rdx, rdi
0x18000feeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fef0  test    eax, eax
0x18000fef2  jnz     short loc_18000FF06
0x18000fef4  lea     rcx, [rdi+48h]; this
0x18000fef8  mov     r9, rbp; void *
0x18000fefb  mov     r8, r14; void (*)(void *)
0x18000fefe  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ff01  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ff06  lea     rcx, [rsp+48h+arg_0]
0x18000ff0b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ff10  mov     rbx, [rsp+48h+arg_8]
0x18000ff15  mov     rbp, [rsp+48h+arg_10]
0x18000ff1a  add     rsp, 30h
0x18000ff1e  pop     r14
0x18000ff20  pop     rdi
0x18000ff21  pop     rsi
0x18000ff22  retn
```
