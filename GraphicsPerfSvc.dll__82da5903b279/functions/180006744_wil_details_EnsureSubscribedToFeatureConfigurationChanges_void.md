# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180006744`
- end: `0x180006764`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800076b8`
- `0x18000ed78`
- `0x18000ee60`
- `0x18000efa0`
- `0x18000f0e0`
- `0x18000f220`
- `0x180012040`
- `0x1800121a0`
- `0x18001979c`
- `0x1800198dc`
- `0x180019a1c`
- `0x180019b04`
- `0x1800298d0`

## callees

- `0x180006744`
- `0x18000676c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180042F9C;
  if ( !dword_180042F9C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180006744  sub     rsp, 28h
0x180006748  mov     eax, cs:dword_180042F9C
0x18000674e  nop
0x18000674f  test    eax, eax
0x180006751  jnz     short loc_18000675F
0x180006753  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000675a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000675f  add     rsp, 28h
0x180006763  retn
```
