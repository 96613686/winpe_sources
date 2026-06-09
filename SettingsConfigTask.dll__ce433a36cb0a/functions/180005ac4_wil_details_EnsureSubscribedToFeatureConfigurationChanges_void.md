# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005ac4`
- end: `0x180005ae4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `37`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006070`
- `0x180006158`
- `0x180006240`
- `0x18000711c`
- `0x180013bfc`
- `0x180013d3c`
- `0x180013e80`
- `0x180013fc0`
- `0x180014100`
- `0x180014240`
- `0x18001432c`
- `0x18001446c`
- `0x180014554`
- `0x18001463c`
- `0x180014724`
- `0x18001480c`
- `0x1800148f4`
- `0x1800149dc`
- `0x180014ac4`
- `0x180014c04`
- `0x180014d44`
- `0x180014e84`
- `0x180014fc4`
- `0x180015104`
- `0x180015248`
- `0x180015334`
- `0x180015474`
- `0x1800155b4`
- `0x1800156f4`
- `0x180015834`
- `0x180015974`
- `0x180015ab4`
- `0x180015bf4`
- `0x180015d34`
- `0x180015e74`
- `0x180015fb4`
- `0x1800160f4`

## callees

- `0x180005ac4`
- `0x180005aec`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002EED4;
  if ( !dword_18002EED4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180005ac4  sub     rsp, 28h
0x180005ac8  mov     eax, cs:dword_18002EED4
0x180005ace  nop
0x180005acf  test    eax, eax
0x180005ad1  jnz     short loc_180005ADF
0x180005ad3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180005ada  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180005adf  add     rsp, 28h
0x180005ae3  retn
```
