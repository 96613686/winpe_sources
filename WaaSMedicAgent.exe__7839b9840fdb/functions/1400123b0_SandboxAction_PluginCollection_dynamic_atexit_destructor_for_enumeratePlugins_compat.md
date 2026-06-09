# SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins_compat__

- ea: `0x1400123b0`
- end: `0x1400123bc`
- name: `SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins_compat__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins_compat__()
{
  std::wstring::~wstring((char **)SandboxAction::PluginCollection::enumeratePlugins_compat);
}

```

## disassembly

```asm
0x1400123b0  lea     rcx, ?enumeratePlugins_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x1400123b7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
