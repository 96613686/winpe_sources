# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000b100`
- end: `0x18000b120`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b584`
- `0x18000b664`
- `0x18000b744`
- `0x18000b824`
- `0x18000b904`
- `0x18000b9e4`
- `0x18000bac4`
- `0x18000bba4`
- `0x18000bc84`
- `0x18000bd64`
- `0x18000be44`
- `0x18000bf24`
- `0x18000d930`

## callees

- `0x18000b100`
- `0x18000b128`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180039744;
  if ( !dword_180039744 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000b100  sub     rsp, 28h
0x18000b104  mov     eax, cs:dword_180039744
0x18000b10a  nop
0x18000b10b  test    eax, eax
0x18000b10d  jnz     short loc_18000B11B
0x18000b10f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000b116  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000b11b  add     rsp, 28h
0x18000b11f  retn
```
