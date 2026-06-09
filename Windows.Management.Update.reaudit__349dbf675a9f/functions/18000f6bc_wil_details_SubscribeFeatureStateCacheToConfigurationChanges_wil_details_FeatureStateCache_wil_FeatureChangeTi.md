# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000f6bc`
- end: `0x18000f75c`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c928`
- `0x18001cbdc`
- `0x18001cd7c`
- `0x18001ce64`

## callees

- `0x18000f6bc`
- `0x1800105e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f73f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f73f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f6e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f6e4`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_18003CA64
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003CA88, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000f6bc  mov     [rsp+arg_0], rbx
0x18000f6c1  mov     [rsp+arg_8], rsi
0x18000f6c6  push    rdi
0x18000f6c7  sub     rsp, 30h
0x18000f6cb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f6d1  mov     esi, r8d
0x18000f6d4  mov     ebx, edx
0x18000f6d6  mov     rdi, rcx
0x18000f6d9  test    eax, eax
0x18000f6db  jz      short loc_18000F74B
0x18000f6dd  lea     rcx, SRWLock; SRWLock
0x18000f6e4  call    cs:__imp_AcquireSRWLockExclusive
0x18000f6eb  nop     dword ptr [rax+rax+00h]
0x18000f6f0  mov     eax, cs:dword_18003CA64
0x18000f6f6  test    esi, esi
0x18000f6f8  jz      short loc_18000F727
0x18000f6fa  cmp     esi, eax
0x18000f6fc  jnz     short loc_18000F727
0x18000f6fe  and     [rsp+38h+var_14], 0
0x18000f703  lea     rdx, [rsp+38h+Source]; Source
0x18000f708  mov     r8d, 10h; SourceSize
0x18000f70e  mov     [rsp+38h+Source], ebx
0x18000f712  lea     rcx, qword_18003CA88; this
0x18000f719  mov     [rsp+38h+var_10], rdi
0x18000f71e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f723  test    al, al
0x18000f725  jnz     short loc_18000F738
0x18000f727  neg     ebx
0x18000f729  sbb     eax, eax
0x18000f72b  and     eax, 83Ah
0x18000f730  add     eax, 0FFFFF7C1h
0x18000f735  lock and [rdi], eax
0x18000f738  lea     rcx, SRWLock; SRWLock
0x18000f73f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f746  nop     dword ptr [rax+rax+00h]
0x18000f74b  mov     rbx, [rsp+38h+arg_0]
0x18000f750  mov     rsi, [rsp+38h+arg_8]
0x18000f755  add     rsp, 30h
0x18000f759  pop     rdi
0x18000f75a  retn
```
