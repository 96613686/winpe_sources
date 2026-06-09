# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140005578`
- end: `0x140005598`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005350`
- `0x14000548c`

## callees

- `0x140005578`
- `0x140005634`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_1400187E4;
  if ( !dword_1400187E4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x140005578  sub     rsp, 28h
0x14000557c  mov     eax, cs:dword_1400187E4
0x140005582  nop
0x140005583  test    eax, eax
0x140005585  jnz     short loc_140005593
0x140005587  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14000558e  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x140005593  add     rsp, 28h
0x140005597  retn
```
