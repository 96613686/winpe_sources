# SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector__

- ea: `0x1400124f0`
- end: `0x1400124fc`
- name: `SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector__()
{
  std::wstring::~wstring((char **)&SandboxAction::PluginCollection::setCorrelationVector);
}

```

## disassembly

```asm
0x1400124f0  lea     rcx, ?setCorrelationVector@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x1400124f7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
