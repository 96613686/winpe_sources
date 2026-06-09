# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000543c`
- end: `0x18000545c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006350`
- `0x18000c088`
- `0x18000c1dc`
- `0x18000c2bc`
- `0x18001172c`
- `0x1800149ac`
- `0x180014a8c`
- `0x180014b6c`
- `0x180014c4c`
- `0x180014da8`
- `0x180014f04`
- `0x180015060`
- `0x1800151bc`
- `0x180015318`
- `0x1800153f8`
- `0x1800154d8`
- `0x1800155b8`
- `0x180015698`
- `0x180015778`

## callees

- `0x18000543c`
- `0x180005464`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180027694;
  if ( !dword_180027694 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000543c  sub     rsp, 28h
0x180005440  mov     eax, cs:dword_180027694
0x180005446  nop
0x180005447  test    eax, eax
0x180005449  jnz     short loc_180005457
0x18000544b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180005452  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180005457  add     rsp, 28h
0x18000545b  retn
```
