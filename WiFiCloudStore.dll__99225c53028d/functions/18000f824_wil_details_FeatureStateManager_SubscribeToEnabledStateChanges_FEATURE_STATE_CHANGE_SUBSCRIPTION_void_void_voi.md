# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000f824`
- end: `0x18000f8db`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `183`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ee30`

## callees

- `0x18000f268`
- `0x18000f824`
- `0x180010864`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f850`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f850`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f8a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f8a9`

## string_xrefs

- `0x18000f8bc`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
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
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000f824  push    rbx
0x18000f826  push    rbp
0x18000f827  push    rsi
0x18000f828  push    rdi
0x18000f829  push    r14
0x18000f82b  push    r15
0x18000f82d  sub     rsp, 38h
0x18000f831  mov     qword ptr [rdx], 0
0x18000f838  mov     rbp, r9
0x18000f83b  cmp     byte ptr [rcx], 0
0x18000f83e  mov     r15, r8
0x18000f841  mov     r14, rdx
0x18000f844  mov     rbx, rcx
0x18000f847  jz      short loc_18000F8AF
0x18000f849  lea     rdi, [rcx+20h]
0x18000f84d  mov     rcx, rdi; SRWLock
0x18000f850  call    cs:__imp_AcquireSRWLockExclusive
0x18000f856  lea     rsi, [rbx+90h]
0x18000f85d  cmp     qword ptr [rsi], 0
0x18000f861  jnz     short loc_18000F88F
0x18000f863  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000f86a  mov     qword ptr [rsi], 0
0x18000f871  test    rax, rax
0x18000f874  jz      short loc_18000F8BC
0x18000f876  mov     r9, rsi
0x18000f879  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000f880  xor     r8d, r8d
0x18000f883  mov     rdx, rbx
0x18000f886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88b  test    eax, eax
0x18000f88d  jnz     short loc_18000F8A1
0x18000f88f  lea     rcx, [rbx+48h]; this
0x18000f893  mov     r9, rbp; void *
0x18000f896  mov     r8, r15; void (*)(void *)
0x18000f899  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000f89c  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000f8a1  test    rdi, rdi
0x18000f8a4  jz      short loc_18000F8AF
0x18000f8a6  mov     rcx, rdi; SRWLock
0x18000f8a9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f8af  add     rsp, 38h
0x18000f8b3  pop     r15
0x18000f8b5  pop     r14
0x18000f8b7  pop     rdi
0x18000f8b8  pop     rsi
0x18000f8b9  pop     rbp
0x18000f8ba  pop     rbx
0x18000f8bb  retn
0x18000f8bc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000f8c3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f8c8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000f8cf  test    rax, rax
0x18000f8d2  jnz     short loc_18000F876
0x18000f8d4  mov     eax, 0C0000139h
0x18000f8d9  jmp     short loc_18000F88B
```
