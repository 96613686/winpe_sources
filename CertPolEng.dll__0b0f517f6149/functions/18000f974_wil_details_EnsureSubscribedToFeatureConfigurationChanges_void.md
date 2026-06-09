# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000f974`
- end: `0x18000f994`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009220`
- `0x180018924`

## callees

- `0x18000f974`
- `0x18000f99c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_1800290EC;
  if ( !dword_1800290EC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000f974  sub     rsp, 28h
0x18000f978  mov     eax, cs:dword_1800290EC
0x18000f97e  nop
0x18000f97f  test    eax, eax
0x18000f981  jnz     short loc_18000F98F
0x18000f983  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000f98a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000f98f  add     rsp, 28h
0x18000f993  retn
```
