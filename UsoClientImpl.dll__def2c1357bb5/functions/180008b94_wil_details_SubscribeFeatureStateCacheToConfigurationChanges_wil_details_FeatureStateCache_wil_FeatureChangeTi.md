# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008b94`
- end: `0x180008c23`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b974`
- `0x18001bb04`
- `0x18001bc94`
- `0x180029030`
- `0x180029318`
- `0x180029600`
- `0x18002b6bc`
- `0x18002c168`
- `0x180045b94`
- `0x180045d6c`
- `0x180046778`
- `0x1800471b4`
- `0x1800474dc`
- `0x18004abe0`
- `0x18004afc0`

## callees

- `0x180008580`
- `0x180008b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bbb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c0d`

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
      || a3 != dword_18009D48C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18009D4C0, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180008b94  mov     [rsp+arg_10], rbx
0x180008b99  mov     [rsp+arg_18], rsi
0x180008b9e  push    rdi
0x180008b9f  sub     rsp, 30h
0x180008ba3  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008baa  mov     esi, r8d
0x180008bad  mov     edi, edx
0x180008baf  mov     rbx, rcx
0x180008bb2  jz      short loc_180008C13
0x180008bb4  lea     rcx, SRWLock; SRWLock
0x180008bbb  call    cs:__imp_AcquireSRWLockExclusive
0x180008bc1  mov     eax, cs:dword_18009D48C
0x180008bc7  test    esi, esi
0x180008bc9  jz      short loc_180008BF5
0x180008bcb  cmp     esi, eax
0x180008bcd  jnz     short loc_180008BF5
0x180008bcf  lea     rdx, [rsp+38h+var_18]; void *
0x180008bd4  mov     [rsp+38h+var_14], 0
0x180008bdc  lea     rcx, qword_18009D4C0; this
0x180008be3  mov     [rsp+38h+var_18], edi
0x180008be7  mov     [rsp+38h+var_10], rbx
0x180008bec  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008bf1  test    al, al
0x180008bf3  jnz     short loc_180008C06
0x180008bf5  neg     edi
0x180008bf7  sbb     eax, eax
0x180008bf9  and     eax, 83Ah
0x180008bfe  add     eax, 0FFFFF7C1h
0x180008c03  lock and [rbx], eax
0x180008c06  lea     rcx, SRWLock; SRWLock
0x180008c0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c13  mov     rbx, [rsp+38h+arg_10]
0x180008c18  mov     rsi, [rsp+38h+arg_18]
0x180008c1d  add     rsp, 30h
0x180008c21  pop     rdi
0x180008c22  retn
```
