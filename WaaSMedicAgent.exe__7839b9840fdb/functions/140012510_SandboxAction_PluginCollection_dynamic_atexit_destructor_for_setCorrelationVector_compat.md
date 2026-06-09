# SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector_compat__

- ea: `0x140012510`
- end: `0x14001251c`
- name: `SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector_compat__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector_compat__()
{
  std::wstring::~wstring((char **)SandboxAction::PluginCollection::setCorrelationVector_compat);
}

```

## disassembly

```asm
0x140012510  lea     rcx, ?setCorrelationVector_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x140012517  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
