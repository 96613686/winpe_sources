# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000422c`
- end: `0x1400042bb`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `31`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005e94`
- `0x1400060c4`
- `0x1400062f4`
- `0x140006524`
- `0x140006754`
- `0x140006984`
- `0x140006bb4`
- `0x140006de4`
- `0x140007014`
- `0x140007244`
- `0x140007474`
- `0x1400076a4`
- `0x1400078d4`
- `0x140007b04`
- `0x140007d34`
- `0x140007f64`
- `0x140008194`
- `0x1400083c4`
- `0x1400085f4`
- `0x140008824`
- `0x140008a54`
- `0x140008c84`
- `0x140008eb4`
- `0x1400090e4`
- `0x140009314`
- `0x140009544`
- `0x140009774`
- `0x1400099a4`
- `0x140009bd4`
- `0x140009e04`
- `0x14000a034`

## callees

- `0x140003b20`
- `0x14000422c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400042a5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400042a5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004253`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004253`

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
      || a3 != dword_14001511C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140015150, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x14000422c  mov     [rsp+arg_10], rbx
0x140004231  mov     [rsp+arg_18], rsi
0x140004236  push    rdi
0x140004237  sub     rsp, 30h
0x14000423b  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004242  mov     esi, r8d
0x140004245  mov     edi, edx
0x140004247  mov     rbx, rcx
0x14000424a  jz      short loc_1400042AB
0x14000424c  lea     rcx, SRWLock; SRWLock
0x140004253  call    cs:__imp_AcquireSRWLockExclusive
0x140004259  mov     eax, cs:dword_14001511C
0x14000425f  test    esi, esi
0x140004261  jz      short loc_14000428D
0x140004263  cmp     esi, eax
0x140004265  jnz     short loc_14000428D
0x140004267  lea     rdx, [rsp+38h+var_18]; void *
0x14000426c  mov     [rsp+38h+var_14], 0
0x140004274  lea     rcx, qword_140015150; this
0x14000427b  mov     [rsp+38h+var_18], edi
0x14000427f  mov     [rsp+38h+var_10], rbx
0x140004284  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140004289  test    al, al
0x14000428b  jnz     short loc_14000429E
0x14000428d  neg     edi
0x14000428f  sbb     eax, eax
0x140004291  and     eax, 83Ah
0x140004296  add     eax, 0FFFFF7C1h
0x14000429b  lock and [rbx], eax
0x14000429e  lea     rcx, SRWLock; SRWLock
0x1400042a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1400042ab  mov     rbx, [rsp+38h+arg_10]
0x1400042b0  mov     rsi, [rsp+38h+arg_18]
0x1400042b5  add     rsp, 30h
0x1400042b9  pop     rdi
0x1400042ba  retn
```
