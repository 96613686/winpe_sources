# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004944`
- end: `0x180004964`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004d14`
- `0x180004e44`
- `0x180004f74`
- `0x1800050a4`
- `0x1800051d4`
- `0x180005304`
- `0x180005434`
- `0x180005564`
- `0x180005694`
- `0x1800057c4`
- `0x1800058f4`
- `0x180005a24`
- `0x180006efc`

## callees

- `0x180004944`
- `0x18000496c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180018234;
  if ( !dword_180018234 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180004944  sub     rsp, 28h
0x180004948  mov     eax, cs:dword_180018234
0x18000494e  nop
0x18000494f  test    eax, eax
0x180004951  jnz     short loc_18000495F
0x180004953  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000495a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000495f  add     rsp, 28h
0x180004963  retn
```
