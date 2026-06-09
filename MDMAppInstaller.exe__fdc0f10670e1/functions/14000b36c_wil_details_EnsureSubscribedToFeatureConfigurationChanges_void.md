# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x14000b36c`
- end: `0x14000b38c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b65c`
- `0x14000b79c`
- `0x14000b888`
- `0x14000b9c8`
- `0x14000bb08`
- `0x14000bc48`
- `0x14000bd88`
- `0x14000bec8`
- `0x14000c008`
- `0x14000c148`
- `0x14000c288`
- `0x14000dbf4`
- `0x140015e3c`

## callees

- `0x14000b36c`
- `0x14000b394`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_14002BCE4;
  if ( !dword_14002BCE4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x14000b36c  sub     rsp, 28h
0x14000b370  mov     eax, cs:dword_14002BCE4
0x14000b376  nop
0x14000b377  test    eax, eax
0x14000b379  jnz     short loc_14000B387
0x14000b37b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14000b382  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x14000b387  add     rsp, 28h
0x14000b38b  retn
```
