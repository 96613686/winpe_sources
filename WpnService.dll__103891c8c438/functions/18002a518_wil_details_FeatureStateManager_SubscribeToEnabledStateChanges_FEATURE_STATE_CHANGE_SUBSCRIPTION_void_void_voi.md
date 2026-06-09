# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002a518`
- end: `0x18002a5d3`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002aa50`

## callees

- `0x1800209c4`
- `0x1800247a0`
- `0x18002a518`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a548`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a548`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a5c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a5c0`

## string_xrefs

- `0x18002a56e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002a518  push    rbx
0x18002a51a  push    rbp
0x18002a51b  push    rsi
0x18002a51c  push    rdi
0x18002a51d  push    r14
0x18002a51f  push    r15
0x18002a521  sub     rsp, 38h
0x18002a525  mov     qword ptr [rdx], 0
0x18002a52c  mov     rbp, r9
0x18002a52f  cmp     byte ptr [rcx], 0
0x18002a532  mov     r15, r8
0x18002a535  mov     r14, rdx
0x18002a538  mov     rbx, rcx
0x18002a53b  jz      loc_18002A5C6
0x18002a541  lea     rdi, [rcx+20h]
0x18002a545  mov     rcx, rdi; SRWLock
0x18002a548  call    cs:__imp_AcquireSRWLockExclusive
0x18002a54e  lea     rsi, [rbx+90h]
0x18002a555  cmp     qword ptr [rsi], 0
0x18002a559  jnz     short loc_18002A5A6
0x18002a55b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002a562  mov     qword ptr [rsi], 0
0x18002a569  test    rax, rax
0x18002a56c  jnz     short loc_18002A58D
0x18002a56e  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002a575  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002a57a  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002a581  test    rax, rax
0x18002a584  jnz     short loc_18002A58D
0x18002a586  mov     eax, 0C0000139h
0x18002a58b  jmp     short loc_18002A5A2
0x18002a58d  mov     r9, rsi
0x18002a590  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002a597  xor     r8d, r8d
0x18002a59a  mov     rdx, rbx
0x18002a59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5a2  test    eax, eax
0x18002a5a4  jnz     short loc_18002A5B8
0x18002a5a6  lea     rcx, [rbx+48h]; this
0x18002a5aa  mov     r9, rbp; void *
0x18002a5ad  mov     r8, r15; void (*)(void *)
0x18002a5b0  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002a5b3  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002a5b8  test    rdi, rdi
0x18002a5bb  jz      short loc_18002A5C6
0x18002a5bd  mov     rcx, rdi; SRWLock
0x18002a5c0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a5c6  add     rsp, 38h
0x18002a5ca  pop     r15
0x18002a5cc  pop     r14
0x18002a5ce  pop     rdi
0x18002a5cf  pop     rsi
0x18002a5d0  pop     rbp
0x18002a5d1  pop     rbx
0x18002a5d2  retn
```
