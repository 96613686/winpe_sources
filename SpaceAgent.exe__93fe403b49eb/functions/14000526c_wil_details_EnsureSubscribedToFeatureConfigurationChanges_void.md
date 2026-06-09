# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x14000526c`
- end: `0x14000528c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006100`
- `0x140009f38`

## callees

- `0x14000526c`
- `0x140005294`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_140027EEC;
  if ( !dword_140027EEC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x14000526c  sub     rsp, 28h
0x140005270  mov     eax, cs:dword_140027EEC
0x140005276  nop
0x140005277  test    eax, eax
0x140005279  jnz     short loc_140005287
0x14000527b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140005282  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x140005287  add     rsp, 28h
0x14000528b  retn
```
