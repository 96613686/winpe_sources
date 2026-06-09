# SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings_compat__

- ea: `0x140002310`
- end: `0x14000233d`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings_compat__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000231a`: `GetPluginDefaultSettings`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__getDefaultSettings_compat__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)SandboxAction::Plugin::getDefaultSettings_compat,
    L"GetPluginDefaultSettings",
    0x18u);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__getDefaultSettings_compat__);
}

```

## disassembly

```asm
0x140002310  sub     rsp, 28h
0x140002314  mov     r8d, 18h
0x14000231a  lea     rdx, aGetplugindefau; "GetPluginDefaultSettings"
0x140002321  lea     rcx, ?getDefaultSettings_compat@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::getDefaultSettings_compat
0x140002328  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000232d  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__getDefaultSettings_compat__
0x140002334  add     rsp, 28h
0x140002338  jmp     atexit
```
