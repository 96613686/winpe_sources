# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140008838`
- end: `0x1400088ff`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140008f40`

## callees

- `0x140004604`
- `0x140008838`
- `0x1400089fc`
- `0x14000972c`
- `0x140020010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000886d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000886d`

## string_xrefs

- `0x140008898`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140008838  mov     [rsp+arg_8], rbx
0x14000883d  mov     [rsp+arg_10], rbp
0x140008842  push    rsi
0x140008843  push    rdi
0x140008844  push    r14
0x140008846  sub     rsp, 30h
0x14000884a  mov     qword ptr [rdx], 0
0x140008851  mov     rbp, r9
0x140008854  cmp     byte ptr [rcx], 0
0x140008857  mov     r14, r8
0x14000885a  mov     rsi, rdx
0x14000885d  mov     rdi, rcx
0x140008860  jz      loc_1400088EC
0x140008866  lea     rbx, [rcx+20h]
0x14000886a  mov     rcx, rbx; SRWLock
0x14000886d  call    cs:__imp_AcquireSRWLockExclusive
0x140008873  mov     [rsp+48h+arg_0], rbx
0x140008878  lea     rbx, [rdi+90h]
0x14000887f  cmp     qword ptr [rbx], 0
0x140008883  jnz     short loc_1400088D0
0x140008885  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000888c  mov     qword ptr [rbx], 0
0x140008893  test    rax, rax
0x140008896  jnz     short loc_1400088B7
0x140008898  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000889f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400088a4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400088ab  test    rax, rax
0x1400088ae  jnz     short loc_1400088B7
0x1400088b0  mov     eax, 0C0000139h
0x1400088b5  jmp     short loc_1400088CC
0x1400088b7  mov     r9, rbx
0x1400088ba  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400088c1  xor     r8d, r8d
0x1400088c4  mov     rdx, rdi
0x1400088c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088cc  test    eax, eax
0x1400088ce  jnz     short loc_1400088E2
0x1400088d0  lea     rcx, [rdi+48h]; this
0x1400088d4  mov     r9, rbp; void *
0x1400088d7  mov     r8, r14; void (*)(void *)
0x1400088da  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400088dd  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400088e2  lea     rcx, [rsp+48h+arg_0]
0x1400088e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400088ec  mov     rbx, [rsp+48h+arg_8]
0x1400088f1  mov     rbp, [rsp+48h+arg_10]
0x1400088f6  add     rsp, 30h
0x1400088fa  pop     r14
0x1400088fc  pop     rdi
0x1400088fd  pop     rsi
0x1400088fe  retn
```
