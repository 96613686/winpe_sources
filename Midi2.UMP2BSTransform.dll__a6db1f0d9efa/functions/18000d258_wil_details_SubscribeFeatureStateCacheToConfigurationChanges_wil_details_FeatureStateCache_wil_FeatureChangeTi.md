# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000d258`
- end: `0x18000d2e8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ac3c`
- `0x18000ae10`
- `0x18000af84`
- `0x18000b0f8`
- `0x18000b26c`
- `0x18000b3e0`
- `0x18000b554`
- `0x18000b634`
- `0x18000b714`
- `0x18000b7f4`
- `0x18000b8d4`
- `0x18000b9b4`

## callees

- `0x18000d258`
- `0x18000e124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d280`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d280`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d2d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d2d2`

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
      || a3 != dword_180015374
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180015398, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000d258  mov     [rsp+arg_0], rbx
0x18000d25d  mov     [rsp+arg_8], rsi
0x18000d262  push    rdi
0x18000d263  sub     rsp, 30h
0x18000d267  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000d26d  mov     esi, r8d
0x18000d270  mov     ebx, edx
0x18000d272  mov     rdi, rcx
0x18000d275  test    eax, eax
0x18000d277  jz      short loc_18000D2D8
0x18000d279  lea     rcx, SRWLock; SRWLock
0x18000d280  call    cs:__imp_AcquireSRWLockExclusive
0x18000d286  mov     eax, cs:dword_180015374
0x18000d28c  test    esi, esi
0x18000d28e  jz      short loc_18000D2BA
0x18000d290  cmp     esi, eax
0x18000d292  jnz     short loc_18000D2BA
0x18000d294  lea     rdx, [rsp+38h+var_18]; void *
0x18000d299  mov     [rsp+38h+var_14], 0
0x18000d2a1  lea     rcx, qword_180015398; this
0x18000d2a8  mov     [rsp+38h+var_18], ebx
0x18000d2ac  mov     [rsp+38h+var_10], rdi
0x18000d2b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000d2b6  test    al, al
0x18000d2b8  jnz     short loc_18000D2CB
0x18000d2ba  neg     ebx
0x18000d2bc  sbb     eax, eax
0x18000d2be  and     eax, 83Ah
0x18000d2c3  add     eax, 0FFFFF7C1h
0x18000d2c8  lock and [rdi], eax
0x18000d2cb  lea     rcx, SRWLock; SRWLock
0x18000d2d2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d2d8  mov     rbx, [rsp+38h+arg_0]
0x18000d2dd  mov     rsi, [rsp+38h+arg_8]
0x18000d2e2  add     rsp, 30h
0x18000d2e6  pop     rdi
0x18000d2e7  retn
```
