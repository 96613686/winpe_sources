# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000b158`
- end: `0x14000b1e8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e640`
- `0x14000e814`
- `0x14000e988`
- `0x14000eafc`
- `0x14000ec70`
- `0x14000ede4`
- `0x14000ef58`
- `0x14000f0cc`
- `0x14000f1ac`
- `0x14000f28c`
- `0x14000f36c`
- `0x14000f44c`
- `0x14000f52c`
- `0x14000f60c`
- `0x140016e6c`
- `0x140017040`
- `0x140017120`
- `0x14002edfc`
- `0x14003a794`
- `0x1400466fc`

## callees

- `0x14000b158`
- `0x14000c89c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b180`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b1d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b1d2`

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
      || a3 != dword_1400966A4
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1400966C8, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x14000b158  mov     [rsp+arg_0], rbx
0x14000b15d  mov     [rsp+arg_8], rsi
0x14000b162  push    rdi
0x14000b163  sub     rsp, 30h
0x14000b167  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000b16d  mov     esi, r8d
0x14000b170  mov     ebx, edx
0x14000b172  mov     rdi, rcx
0x14000b175  test    eax, eax
0x14000b177  jz      short loc_14000B1D8
0x14000b179  lea     rcx, SRWLock; SRWLock
0x14000b180  call    cs:__imp_AcquireSRWLockExclusive
0x14000b186  mov     eax, cs:dword_1400966A4
0x14000b18c  test    esi, esi
0x14000b18e  jz      short loc_14000B1BA
0x14000b190  cmp     esi, eax
0x14000b192  jnz     short loc_14000B1BA
0x14000b194  lea     rdx, [rsp+38h+var_18]; void *
0x14000b199  mov     [rsp+38h+var_14], 0
0x14000b1a1  lea     rcx, qword_1400966C8; this
0x14000b1a8  mov     [rsp+38h+var_18], ebx
0x14000b1ac  mov     [rsp+38h+var_10], rdi
0x14000b1b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000b1b6  test    al, al
0x14000b1b8  jnz     short loc_14000B1CB
0x14000b1ba  neg     ebx
0x14000b1bc  sbb     eax, eax
0x14000b1be  and     eax, 83Ah
0x14000b1c3  add     eax, 0FFFFF7C1h
0x14000b1c8  lock and [rdi], eax
0x14000b1cb  lea     rcx, SRWLock; SRWLock
0x14000b1d2  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b1d8  mov     rbx, [rsp+38h+arg_0]
0x14000b1dd  mov     rsi, [rsp+38h+arg_8]
0x14000b1e2  add     rsp, 30h
0x14000b1e6  pop     rdi
0x14000b1e7  retn
```
