# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180009fc0`
- end: `0x180009fe1`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `33`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ad74`
- `0x180012c0c`
- `0x180012d54`
- `0x180012e9c`
- `0x180012fe4`
- `0x18001312c`
- `0x180013274`
- `0x1800133bc`
- `0x180013504`
- `0x18001364c`
- `0x180013794`
- `0x1800138dc`
- `0x180013a24`
- `0x180013b6c`
- `0x180013cb4`
- `0x180016f24`

## callees

- `0x180009fc0`
- `0x180009fe8`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180029CBC;
  if ( !dword_180029CBC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180009fc0  sub     rsp, 28h
0x180009fc4  mov     eax, cs:dword_180029CBC
0x180009fca  nop
0x180009fcb  test    eax, eax
0x180009fcd  jnz     short loc_180009FDB
0x180009fcf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180009fd6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180009fdb  add     rsp, 28h
0x180009fdf  retn
```
