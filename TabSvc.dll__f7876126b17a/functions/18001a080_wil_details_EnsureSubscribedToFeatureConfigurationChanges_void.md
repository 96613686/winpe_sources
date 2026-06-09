# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001a080`
- end: `0x18001a0a0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800110e0`
- `0x180011ae0`
- `0x180013240`
- `0x180013410`
- `0x180019f98`
- `0x18002062c`
- `0x18002070c`
- `0x1800208ac`
- `0x180020a58`
- `0x180020bb8`
- `0x180020d18`
- `0x180020e78`
- `0x180020fd8`
- `0x1800210b8`
- `0x180021210`
- `0x1800212f0`
- `0x1800213d0`
- `0x1800214b0`
- `0x180021590`
- `0x180021670`
- `0x180021750`
- `0x180021830`
- `0x18002caec`
- `0x18002dd4c`

## callees

- `0x1800181ac`
- `0x18001a080`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180041864;
  if ( !dword_180041864 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18001a080  sub     rsp, 28h
0x18001a084  mov     eax, cs:dword_180041864
0x18001a08a  nop
0x18001a08b  test    eax, eax
0x18001a08d  jnz     short loc_18001A09B
0x18001a08f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001a096  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18001a09b  add     rsp, 28h
0x18001a09f  retn
```
