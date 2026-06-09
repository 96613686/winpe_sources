# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800085b4`
- end: `0x1800085d4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008918`
- `0x1800089f8`
- `0x180008ad8`
- `0x180008bb8`
- `0x180008c98`
- `0x1800090fc`
- `0x18000c7b8`
- `0x18000c898`

## callees

- `0x1800085b4`
- `0x1800085dc`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002159C;
  if ( !dword_18002159C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800085b4  sub     rsp, 28h
0x1800085b8  mov     eax, cs:dword_18002159C
0x1800085be  nop
0x1800085bf  test    eax, eax
0x1800085c1  jnz     short loc_1800085CF
0x1800085c3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800085ca  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800085cf  add     rsp, 28h
0x1800085d3  retn
```
