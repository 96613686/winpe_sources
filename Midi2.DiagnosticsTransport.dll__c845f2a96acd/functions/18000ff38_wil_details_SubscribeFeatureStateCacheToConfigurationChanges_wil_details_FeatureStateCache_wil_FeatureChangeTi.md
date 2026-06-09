# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000ff38`
- end: `0x18000ffc8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d7a4`
- `0x18000d978`
- `0x18000daec`
- `0x18000dc60`
- `0x18000ddd4`
- `0x18000df48`
- `0x18000e0bc`
- `0x18000e230`
- `0x18000e310`
- `0x18000e3f0`
- `0x18000e4d0`
- `0x18000e5b0`
- `0x18000e690`
- `0x18000e770`

## callees

- `0x18000ff38`
- `0x1800104c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ff60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ff60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ffb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ffb2`

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
      || a3 != dword_18001A354
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001A378, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000ff38  mov     [rsp+arg_0], rbx
0x18000ff3d  mov     [rsp+arg_8], rsi
0x18000ff42  push    rdi
0x18000ff43  sub     rsp, 30h
0x18000ff47  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ff4d  mov     esi, r8d
0x18000ff50  mov     ebx, edx
0x18000ff52  mov     rdi, rcx
0x18000ff55  test    eax, eax
0x18000ff57  jz      short loc_18000FFB8
0x18000ff59  lea     rcx, SRWLock; SRWLock
0x18000ff60  call    cs:__imp_AcquireSRWLockExclusive
0x18000ff66  mov     eax, cs:dword_18001A354
0x18000ff6c  test    esi, esi
0x18000ff6e  jz      short loc_18000FF9A
0x18000ff70  cmp     esi, eax
0x18000ff72  jnz     short loc_18000FF9A
0x18000ff74  lea     rdx, [rsp+38h+var_18]; void *
0x18000ff79  mov     [rsp+38h+var_14], 0
0x18000ff81  lea     rcx, qword_18001A378; this
0x18000ff88  mov     [rsp+38h+var_18], ebx
0x18000ff8c  mov     [rsp+38h+var_10], rdi
0x18000ff91  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ff96  test    al, al
0x18000ff98  jnz     short loc_18000FFAB
0x18000ff9a  neg     ebx
0x18000ff9c  sbb     eax, eax
0x18000ff9e  and     eax, 83Ah
0x18000ffa3  add     eax, 0FFFFF7C1h
0x18000ffa8  lock and [rdi], eax
0x18000ffab  lea     rcx, SRWLock; SRWLock
0x18000ffb2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ffb8  mov     rbx, [rsp+38h+arg_0]
0x18000ffbd  mov     rsi, [rsp+38h+arg_8]
0x18000ffc2  add     rsp, 30h
0x18000ffc6  pop     rdi
0x18000ffc7  retn
```
