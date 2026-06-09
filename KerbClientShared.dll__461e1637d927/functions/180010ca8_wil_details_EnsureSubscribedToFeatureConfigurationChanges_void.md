# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180010ca8`
- end: `0x180010cc8`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011b40`

## callees

- `0x180010ca8`
- `0x180010cd0`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_18003317C;
  if ( !dword_18003317C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180010ca8  sub     rsp, 28h
0x180010cac  mov     eax, cs:dword_18003317C
0x180010cb2  nop
0x180010cb3  test    eax, eax
0x180010cb5  jnz     short loc_180010CC3
0x180010cb7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180010cbe  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180010cc3  add     rsp, 28h
0x180010cc7  retn
```
