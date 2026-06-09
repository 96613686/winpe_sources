# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009144`
- end: `0x18000920b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800098d0`

## callees

- `0x180004e64`
- `0x180009144`
- `0x180009308`
- `0x18000a360`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009179`

## string_xrefs

- `0x1800091a4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180009144  mov     [rsp+arg_8], rbx
0x180009149  mov     [rsp+arg_10], rbp
0x18000914e  push    rsi
0x18000914f  push    rdi
0x180009150  push    r14
0x180009152  sub     rsp, 30h
0x180009156  mov     qword ptr [rdx], 0
0x18000915d  mov     rbp, r9
0x180009160  cmp     byte ptr [rcx], 0
0x180009163  mov     r14, r8
0x180009166  mov     rsi, rdx
0x180009169  mov     rdi, rcx
0x18000916c  jz      loc_1800091F8
0x180009172  lea     rbx, [rcx+20h]
0x180009176  mov     rcx, rbx; SRWLock
0x180009179  call    cs:__imp_AcquireSRWLockExclusive
0x18000917f  mov     [rsp+48h+arg_0], rbx
0x180009184  lea     rbx, [rdi+90h]
0x18000918b  cmp     qword ptr [rbx], 0
0x18000918f  jnz     short loc_1800091DC
0x180009191  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009198  mov     qword ptr [rbx], 0
0x18000919f  test    rax, rax
0x1800091a2  jnz     short loc_1800091C3
0x1800091a4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800091ab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800091b0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800091b7  test    rax, rax
0x1800091ba  jnz     short loc_1800091C3
0x1800091bc  mov     eax, 0C0000139h
0x1800091c1  jmp     short loc_1800091D8
0x1800091c3  mov     r9, rbx
0x1800091c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800091cd  xor     r8d, r8d
0x1800091d0  mov     rdx, rdi
0x1800091d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d8  test    eax, eax
0x1800091da  jnz     short loc_1800091EE
0x1800091dc  lea     rcx, [rdi+48h]; this
0x1800091e0  mov     r9, rbp; void *
0x1800091e3  mov     r8, r14; void (*)(void *)
0x1800091e6  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800091e9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800091ee  lea     rcx, [rsp+48h+arg_0]
0x1800091f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800091f8  mov     rbx, [rsp+48h+arg_8]
0x1800091fd  mov     rbp, [rsp+48h+arg_10]
0x180009202  add     rsp, 30h
0x180009206  pop     r14
0x180009208  pop     rdi
0x180009209  pop     rsi
0x18000920a  retn
```
