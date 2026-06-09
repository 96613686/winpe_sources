# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b2e0`
- end: `0x18000b370`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019068`
- `0x18001923c`
- `0x180019410`
- `0x180019584`
- `0x1800196f8`
- `0x18001986c`
- `0x1800199e0`
- `0x180019b54`
- `0x180019cc8`
- `0x180019da8`
- `0x180019e88`
- `0x180019f68`
- `0x18001a048`
- `0x18001a128`
- `0x18001a208`
- `0x1800261c8`
- `0x18002639c`
- `0x18002647c`
- `0x18002caf8`
- `0x18003c8e8`

## callees

- `0x18000b2e0`
- `0x18000bbec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b35a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b35a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b308`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b308`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  unsigned __int64 v6; // r8
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180071894
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800718B8, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000b2e0  mov     [rsp+arg_0], rbx
0x18000b2e5  mov     [rsp+arg_8], rsi
0x18000b2ea  push    rdi
0x18000b2eb  sub     rsp, 30h
0x18000b2ef  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b2f5  mov     esi, r8d
0x18000b2f8  mov     ebx, edx
0x18000b2fa  mov     rdi, rcx
0x18000b2fd  test    eax, eax
0x18000b2ff  jz      short loc_18000B360
0x18000b301  lea     rcx, SRWLock; SRWLock
0x18000b308  call    cs:__imp_AcquireSRWLockExclusive
0x18000b30e  mov     eax, cs:dword_180071894
0x18000b314  test    esi, esi
0x18000b316  jz      short loc_18000B342
0x18000b318  cmp     esi, eax
0x18000b31a  jnz     short loc_18000B342
0x18000b31c  lea     rdx, [rsp+38h+var_18]; void *
0x18000b321  mov     [rsp+38h+var_14], 0
0x18000b329  lea     rcx, qword_1800718B8; this
0x18000b330  mov     [rsp+38h+var_18], ebx
0x18000b334  mov     [rsp+38h+var_10], rdi
0x18000b339  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b33e  test    al, al
0x18000b340  jnz     short loc_18000B353
0x18000b342  neg     ebx
0x18000b344  sbb     eax, eax
0x18000b346  and     eax, 83Ah
0x18000b34b  add     eax, 0FFFFF7C1h
0x18000b350  lock and [rdi], eax
0x18000b353  lea     rcx, SRWLock; SRWLock
0x18000b35a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b360  mov     rbx, [rsp+38h+arg_0]
0x18000b365  mov     rsi, [rsp+38h+arg_8]
0x18000b36a  add     rsp, 30h
0x18000b36e  pop     rdi
0x18000b36f  retn
```
