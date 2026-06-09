# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000db80`
- end: `0x18000dc3b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011e60`

## callees

- `0x18000c9e4`
- `0x18000db80`
- `0x18000dc44`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dbb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dbb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc28`

## string_xrefs

- `0x18000dbd6`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000db80  push    rbx
0x18000db82  push    rbp
0x18000db83  push    rsi
0x18000db84  push    rdi
0x18000db85  push    r14
0x18000db87  push    r15
0x18000db89  sub     rsp, 38h
0x18000db8d  mov     qword ptr [rdx], 0
0x18000db94  mov     rbp, r9
0x18000db97  cmp     byte ptr [rcx], 0
0x18000db9a  mov     r15, r8
0x18000db9d  mov     r14, rdx
0x18000dba0  mov     rbx, rcx
0x18000dba3  jz      loc_18000DC2E
0x18000dba9  lea     rdi, [rcx+20h]
0x18000dbad  mov     rcx, rdi; SRWLock
0x18000dbb0  call    cs:__imp_AcquireSRWLockExclusive
0x18000dbb6  lea     rsi, [rbx+90h]
0x18000dbbd  cmp     qword ptr [rsi], 0
0x18000dbc1  jnz     short loc_18000DC0E
0x18000dbc3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000dbca  mov     qword ptr [rsi], 0
0x18000dbd1  test    rax, rax
0x18000dbd4  jnz     short loc_18000DBF5
0x18000dbd6  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000dbdd  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000dbe2  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000dbe9  test    rax, rax
0x18000dbec  jnz     short loc_18000DBF5
0x18000dbee  mov     eax, 0C0000139h
0x18000dbf3  jmp     short loc_18000DC0A
0x18000dbf5  mov     r9, rsi
0x18000dbf8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000dbff  xor     r8d, r8d
0x18000dc02  mov     rdx, rbx
0x18000dc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0a  test    eax, eax
0x18000dc0c  jnz     short loc_18000DC20
0x18000dc0e  lea     rcx, [rbx+48h]; this
0x18000dc12  mov     r9, rbp; void *
0x18000dc15  mov     r8, r15; void (*)(void *)
0x18000dc18  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000dc1b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000dc20  test    rdi, rdi
0x18000dc23  jz      short loc_18000DC2E
0x18000dc25  mov     rcx, rdi; SRWLock
0x18000dc28  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dc2e  add     rsp, 38h
0x18000dc32  pop     r15
0x18000dc34  pop     r14
0x18000dc36  pop     rdi
0x18000dc37  pop     rsi
0x18000dc38  pop     rbp
0x18000dc39  pop     rbx
0x18000dc3a  retn
```
