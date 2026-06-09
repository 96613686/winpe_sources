# SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins_compat__

- ea: `0x140002160`
- end: `0x14000218d`
- name: `SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins_compat__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000216a`: `EnumeratePlugins`

## pseudocode

```c
int SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins_compat__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)SandboxAction::PluginCollection::enumeratePlugins_compat,
    L"EnumeratePlugins",
    0x10u);
  return atexit(SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins_compat__);
}

```

## disassembly

```asm
0x140002160  sub     rsp, 28h
0x140002164  mov     r8d, 10h
0x14000216a  lea     rdx, aEnumerateplugi; "EnumeratePlugins"
0x140002171  lea     rcx, ?enumeratePlugins_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins_compat
0x140002178  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000217d  lea     rcx, SandboxAction__PluginCollection___dynamic_atexit_destructor_for__enumeratePlugins_compat__
0x140002184  add     rsp, 28h
0x140002188  jmp     atexit
```
