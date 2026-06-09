# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180008d78`
- end: `0x180008d90`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `24`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e80`

## callees

- `0x180008d78`
- `0x180008da0`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002EDCC;
  if ( !dword_18002EDCC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180008d78  mov     eax, cs:dword_18002EDCC
0x180008d7e  nop
0x180008d7f  test    eax, eax
0x180008d81  jz      short loc_180008D84
0x180008d83  retn
0x180008d84  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180008d8b  jmp     ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
```
