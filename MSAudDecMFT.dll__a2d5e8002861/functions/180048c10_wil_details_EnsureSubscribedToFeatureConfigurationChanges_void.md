# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180048c10`
- end: `0x180048c31`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `33`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180048b28`
- `0x1800594fc`
- `0x1800595e4`
- `0x1800596cc`
- `0x1800597b4`
- `0x180059918`
- `0x18005a4a8`
- `0x18005a918`
- `0x18005aa00`

## callees

- `0x180048c10`
- `0x1800593e0`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_1800E5E64;
  if ( !dword_1800E5E64 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180048c10  sub     rsp, 28h
0x180048c14  mov     eax, cs:dword_1800E5E64
0x180048c1a  nop
0x180048c1b  test    eax, eax
0x180048c1d  jnz     short loc_180048C2B
0x180048c1f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180048c26  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180048c2b  add     rsp, 28h
0x180048c2f  retn
```
