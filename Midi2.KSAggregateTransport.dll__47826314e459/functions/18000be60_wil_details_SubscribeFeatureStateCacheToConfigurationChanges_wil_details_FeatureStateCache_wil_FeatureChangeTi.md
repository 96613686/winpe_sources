# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000be60`
- end: `0x18000bef0`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e3e4`
- `0x18000e5b8`
- `0x18000e72c`
- `0x18000e8a0`
- `0x18000ea14`
- `0x18000eb88`
- `0x18000ecfc`
- `0x18000ee70`
- `0x18000ef50`
- `0x18000f030`
- `0x18000f110`
- `0x18000f1f0`
- `0x18000f2d0`
- `0x18000f3b0`
- `0x180024e9c`
- `0x180046c78`
- `0x180046e4c`
- `0x180046f2c`
- `0x18004d748`
- `0x180057ee4`

## callees

- `0x18000be60`
- `0x18000c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000beda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000beda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be88`

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
      || a3 != dword_1800968D4
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800968F8, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000be60  mov     [rsp+arg_0], rbx
0x18000be65  mov     [rsp+arg_8], rsi
0x18000be6a  push    rdi
0x18000be6b  sub     rsp, 30h
0x18000be6f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000be75  mov     esi, r8d
0x18000be78  mov     ebx, edx
0x18000be7a  mov     rdi, rcx
0x18000be7d  test    eax, eax
0x18000be7f  jz      short loc_18000BEE0
0x18000be81  lea     rcx, SRWLock; SRWLock
0x18000be88  call    cs:__imp_AcquireSRWLockExclusive
0x18000be8e  mov     eax, cs:dword_1800968D4
0x18000be94  test    esi, esi
0x18000be96  jz      short loc_18000BEC2
0x18000be98  cmp     esi, eax
0x18000be9a  jnz     short loc_18000BEC2
0x18000be9c  lea     rdx, [rsp+38h+var_18]; void *
0x18000bea1  mov     [rsp+38h+var_14], 0
0x18000bea9  lea     rcx, qword_1800968F8; this
0x18000beb0  mov     [rsp+38h+var_18], ebx
0x18000beb4  mov     [rsp+38h+var_10], rdi
0x18000beb9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000bebe  test    al, al
0x18000bec0  jnz     short loc_18000BED3
0x18000bec2  neg     ebx
0x18000bec4  sbb     eax, eax
0x18000bec6  and     eax, 83Ah
0x18000becb  add     eax, 0FFFFF7C1h
0x18000bed0  lock and [rdi], eax
0x18000bed3  lea     rcx, SRWLock; SRWLock
0x18000beda  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bee0  mov     rbx, [rsp+38h+arg_0]
0x18000bee5  mov     rsi, [rsp+38h+arg_8]
0x18000beea  add     rsp, 30h
0x18000beee  pop     rdi
0x18000beef  retn
```
