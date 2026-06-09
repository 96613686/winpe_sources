# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000d7e0`
- end: `0x18000d800`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000df60`
- `0x18000e040`
- `0x18000e120`
- `0x18000e200`
- `0x18000e2e0`
- `0x18000e3c0`
- `0x18000e4a0`
- `0x18000e580`
- `0x18000e660`
- `0x18000e740`
- `0x18000e820`
- `0x18000e900`
- `0x18000e9e0`
- `0x18000eac0`
- `0x18001054c`
- `0x18001f444`
- `0x18001f524`
- `0x18001f67c`

## callees

- `0x18000d7e0`
- `0x18000d808`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18003B5EC;
  if ( !dword_18003B5EC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000d7e0  sub     rsp, 28h
0x18000d7e4  mov     eax, cs:dword_18003B5EC
0x18000d7ea  nop
0x18000d7eb  test    eax, eax
0x18000d7ed  jnz     short loc_18000D7FB
0x18000d7ef  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000d7f6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000d7fb  add     rsp, 28h
0x18000d7ff  retn
```
