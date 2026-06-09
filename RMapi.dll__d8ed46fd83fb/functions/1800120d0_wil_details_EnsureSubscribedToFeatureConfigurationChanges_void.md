# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800120d0`
- end: `0x1800120f0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001244c`
- `0x180012540`
- `0x180012634`
- `0x180012728`
- `0x18001281c`
- `0x180012910`
- `0x180012a04`
- `0x180012af8`
- `0x18001379c`
- `0x18001e994`
- `0x1800241d0`
- `0x1800242c8`
- `0x1800243bc`

## callees

- `0x1800120d0`
- `0x1800120f8`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180037A14;
  if ( !dword_180037A14 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800120d0  sub     rsp, 28h
0x1800120d4  mov     eax, cs:dword_180037A14
0x1800120da  nop
0x1800120db  test    eax, eax
0x1800120dd  jnz     short loc_1800120EB
0x1800120df  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800120e6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800120eb  add     rsp, 28h
0x1800120ef  retn
```
