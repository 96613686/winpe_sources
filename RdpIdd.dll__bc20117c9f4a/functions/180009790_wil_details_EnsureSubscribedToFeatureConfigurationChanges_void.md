# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180009790`
- end: `0x1800097b1`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `33`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000eed4`
- `0x180016a54`
- `0x180016b9c`
- `0x180016ce4`
- `0x180016e2c`
- `0x180016f74`
- `0x1800170bc`
- `0x18002a8a0`
- `0x18002a9e8`
- `0x18002ab30`
- `0x18002ac78`
- `0x18002adc0`
- `0x18002af08`
- `0x18002b050`
- `0x1800373ec`

## callees

- `0x180009790`
- `0x1800097b8`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_1800578F4;
  if ( !dword_1800578F4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180009790  sub     rsp, 28h
0x180009794  mov     eax, cs:dword_1800578F4
0x18000979a  nop
0x18000979b  test    eax, eax
0x18000979d  jnz     short loc_1800097AB
0x18000979f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800097a6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800097ab  add     rsp, 28h
0x1800097af  retn
```
