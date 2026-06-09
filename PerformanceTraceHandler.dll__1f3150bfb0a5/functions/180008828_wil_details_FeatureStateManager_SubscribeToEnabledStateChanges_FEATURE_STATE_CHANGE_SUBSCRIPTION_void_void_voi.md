# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008828`
- end: `0x1800088ef`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180008fb0`

## callees

- `0x18000490c`
- `0x180008828`
- `0x1800089ec`
- `0x180009e80`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000885d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000885d`

## string_xrefs

- `0x180008888`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180008828  mov     [rsp+arg_8], rbx
0x18000882d  mov     [rsp+arg_10], rbp
0x180008832  push    rsi
0x180008833  push    rdi
0x180008834  push    r14
0x180008836  sub     rsp, 30h
0x18000883a  mov     qword ptr [rdx], 0
0x180008841  mov     rbp, r9
0x180008844  cmp     byte ptr [rcx], 0
0x180008847  mov     r14, r8
0x18000884a  mov     rsi, rdx
0x18000884d  mov     rdi, rcx
0x180008850  jz      loc_1800088DC
0x180008856  lea     rbx, [rcx+20h]
0x18000885a  mov     rcx, rbx; SRWLock
0x18000885d  call    cs:__imp_AcquireSRWLockExclusive
0x180008863  mov     [rsp+48h+arg_0], rbx
0x180008868  lea     rbx, [rdi+90h]
0x18000886f  cmp     qword ptr [rbx], 0
0x180008873  jnz     short loc_1800088C0
0x180008875  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000887c  mov     qword ptr [rbx], 0
0x180008883  test    rax, rax
0x180008886  jnz     short loc_1800088A7
0x180008888  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000888f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008894  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000889b  test    rax, rax
0x18000889e  jnz     short loc_1800088A7
0x1800088a0  mov     eax, 0C0000139h
0x1800088a5  jmp     short loc_1800088BC
0x1800088a7  mov     r9, rbx
0x1800088aa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800088b1  xor     r8d, r8d
0x1800088b4  mov     rdx, rdi
0x1800088b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088bc  test    eax, eax
0x1800088be  jnz     short loc_1800088D2
0x1800088c0  lea     rcx, [rdi+48h]; this
0x1800088c4  mov     r9, rbp; void *
0x1800088c7  mov     r8, r14; void (*)(void *)
0x1800088ca  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800088cd  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800088d2  lea     rcx, [rsp+48h+arg_0]
0x1800088d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800088dc  mov     rbx, [rsp+48h+arg_8]
0x1800088e1  mov     rbp, [rsp+48h+arg_10]
0x1800088e6  add     rsp, 30h
0x1800088ea  pop     r14
0x1800088ec  pop     rdi
0x1800088ed  pop     rsi
0x1800088ee  retn
```
