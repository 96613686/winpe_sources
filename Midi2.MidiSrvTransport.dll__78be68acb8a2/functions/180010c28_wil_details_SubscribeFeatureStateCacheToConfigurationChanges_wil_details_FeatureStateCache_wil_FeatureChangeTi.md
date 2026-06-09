# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180010c28`
- end: `0x180010cb8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dacc`
- `0x18000dca0`
- `0x18000dd80`
- `0x18000df54`
- `0x18000e0c8`
- `0x18000e23c`
- `0x18000e3b0`
- `0x18000e524`
- `0x18000e604`
- `0x18000e6e4`
- `0x18000e7c4`
- `0x18000e8a4`

## callees

- `0x180010c28`
- `0x18001162c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010c50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ca2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ca2`

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
      || a3 != dword_18001E40C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001E430, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180010c28  mov     [rsp+arg_0], rbx
0x180010c2d  mov     [rsp+arg_8], rsi
0x180010c32  push    rdi
0x180010c33  sub     rsp, 30h
0x180010c37  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010c3d  mov     esi, r8d
0x180010c40  mov     ebx, edx
0x180010c42  mov     rdi, rcx
0x180010c45  test    eax, eax
0x180010c47  jz      short loc_180010CA8
0x180010c49  lea     rcx, SRWLock; SRWLock
0x180010c50  call    cs:__imp_AcquireSRWLockExclusive
0x180010c56  mov     eax, cs:dword_18001E40C
0x180010c5c  test    esi, esi
0x180010c5e  jz      short loc_180010C8A
0x180010c60  cmp     esi, eax
0x180010c62  jnz     short loc_180010C8A
0x180010c64  lea     rdx, [rsp+38h+var_18]; void *
0x180010c69  mov     [rsp+38h+var_14], 0
0x180010c71  lea     rcx, qword_18001E430; this
0x180010c78  mov     [rsp+38h+var_18], ebx
0x180010c7c  mov     [rsp+38h+var_10], rdi
0x180010c81  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010c86  test    al, al
0x180010c88  jnz     short loc_180010C9B
0x180010c8a  neg     ebx
0x180010c8c  sbb     eax, eax
0x180010c8e  and     eax, 83Ah
0x180010c93  add     eax, 0FFFFF7C1h
0x180010c98  lock and [rdi], eax
0x180010c9b  lea     rcx, SRWLock; SRWLock
0x180010ca2  call    cs:__imp_ReleaseSRWLockExclusive
0x180010ca8  mov     rbx, [rsp+38h+arg_0]
0x180010cad  mov     rsi, [rsp+38h+arg_8]
0x180010cb2  add     rsp, 30h
0x180010cb6  pop     rdi
0x180010cb7  retn
```
