# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180036170`
- end: `0x180036190`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003649c`
- `0x180036590`
- `0x180036704`
- `0x180036878`
- `0x1800369ec`
- `0x180036b60`
- `0x180036c54`
- `0x180036d48`
- `0x180036e3c`
- `0x180036f30`

## callees

- `0x180036170`
- `0x180036198`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18004A554;
  if ( !dword_18004A554 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180036170  sub     rsp, 28h
0x180036174  mov     eax, cs:dword_18004A554
0x18003617a  nop
0x18003617b  test    eax, eax
0x18003617d  jnz     short loc_18003618B
0x18003617f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180036186  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18003618b  add     rsp, 28h
0x18003618f  retn
```
