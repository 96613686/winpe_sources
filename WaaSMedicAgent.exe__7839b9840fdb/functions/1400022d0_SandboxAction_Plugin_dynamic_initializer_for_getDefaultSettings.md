# SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings__

- ea: `0x1400022d0`
- end: `0x1400022fd`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x1400022da`: `Plugin_GetDefaultSettings`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)SandboxAction::Plugin::getDefaultSettings,
    L"Plugin_GetDefaultSettings",
    0x19u);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__getDefaultSettings__);
}

```

## disassembly

```asm
0x1400022d0  sub     rsp, 28h
0x1400022d4  mov     r8d, 19h
0x1400022da  lea     rdx, aPluginGetdefau; "Plugin_GetDefaultSettings"
0x1400022e1  lea     rcx, ?getDefaultSettings@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::getDefaultSettings
0x1400022e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400022ed  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__getDefaultSettings__
0x1400022f4  add     rsp, 28h
0x1400022f8  jmp     atexit
```
