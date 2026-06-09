# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005a7c`
- end: `0x180005a9c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000697c`
- `0x18000f178`
- `0x180011dd8`
- `0x180011f18`

## callees

- `0x180005a7c`
- `0x180005aa4`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180024B2C;
  if ( !dword_180024B2C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180005a7c  sub     rsp, 28h
0x180005a80  mov     eax, cs:dword_180024B2C
0x180005a86  nop
0x180005a87  test    eax, eax
0x180005a89  jnz     short loc_180005A97
0x180005a8b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180005a92  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180005a97  add     rsp, 28h
0x180005a9b  retn
```
