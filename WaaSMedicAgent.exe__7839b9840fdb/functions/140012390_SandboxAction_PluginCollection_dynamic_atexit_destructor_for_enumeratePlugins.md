# SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins__

- ea: `0x140012390`
- end: `0x14001239c`
- name: `SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins__()
{
  std::wstring::~wstring((char **)SandboxAction::PluginCollection::enumeratePlugins);
}

```

## disassembly

```asm
0x140012390  lea     rcx, ?enumeratePlugins@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x140012397  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
