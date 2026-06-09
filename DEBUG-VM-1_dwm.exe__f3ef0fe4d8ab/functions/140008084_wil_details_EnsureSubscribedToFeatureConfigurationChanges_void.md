# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140008084`
- end: `0x1400080a4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000921c`
- `0x14000cf54`

## callees

- `0x140008084`
- `0x1400080ac`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_14001BFDC;
  if ( !dword_14001BFDC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x140008084  sub     rsp, 28h
0x140008088  mov     eax, cs:dword_14001BFDC
0x14000808e  nop
0x14000808f  test    eax, eax
0x140008091  jnz     short loc_14000809F
0x140008093  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14000809a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x14000809f  add     rsp, 28h
0x1400080a3  retn
```
