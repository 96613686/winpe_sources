# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a13c`
- end: `0x18000a203`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a9d0`

## callees

- `0x18000460c`
- `0x18000a13c`
- `0x18000a300`
- `0x18000b670`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a171`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a171`

## string_xrefs

- `0x18000a19c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000a13c  mov     [rsp+arg_8], rbx
0x18000a141  mov     [rsp+arg_10], rbp
0x18000a146  push    rsi
0x18000a147  push    rdi
0x18000a148  push    r14
0x18000a14a  sub     rsp, 30h
0x18000a14e  mov     qword ptr [rdx], 0
0x18000a155  mov     rbp, r9
0x18000a158  cmp     byte ptr [rcx], 0
0x18000a15b  mov     r14, r8
0x18000a15e  mov     rsi, rdx
0x18000a161  mov     rdi, rcx
0x18000a164  jz      loc_18000A1F0
0x18000a16a  lea     rbx, [rcx+20h]
0x18000a16e  mov     rcx, rbx; SRWLock
0x18000a171  call    cs:__imp_AcquireSRWLockExclusive
0x18000a177  mov     [rsp+48h+arg_0], rbx
0x18000a17c  lea     rbx, [rdi+90h]
0x18000a183  cmp     qword ptr [rbx], 0
0x18000a187  jnz     short loc_18000A1D4
0x18000a189  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a190  mov     qword ptr [rbx], 0
0x18000a197  test    rax, rax
0x18000a19a  jnz     short loc_18000A1BB
0x18000a19c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a1a3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a1a8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a1af  test    rax, rax
0x18000a1b2  jnz     short loc_18000A1BB
0x18000a1b4  mov     eax, 0C0000139h
0x18000a1b9  jmp     short loc_18000A1D0
0x18000a1bb  mov     r9, rbx
0x18000a1be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a1c5  xor     r8d, r8d
0x18000a1c8  mov     rdx, rdi
0x18000a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d0  test    eax, eax
0x18000a1d2  jnz     short loc_18000A1E6
0x18000a1d4  lea     rcx, [rdi+48h]; this
0x18000a1d8  mov     r9, rbp; void *
0x18000a1db  mov     r8, r14; void (*)(void *)
0x18000a1de  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a1e1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a1e6  lea     rcx, [rsp+48h+arg_0]
0x18000a1eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a1f0  mov     rbx, [rsp+48h+arg_8]
0x18000a1f5  mov     rbp, [rsp+48h+arg_10]
0x18000a1fa  add     rsp, 30h
0x18000a1fe  pop     r14
0x18000a200  pop     rdi
0x18000a201  pop     rsi
0x18000a202  retn
```
