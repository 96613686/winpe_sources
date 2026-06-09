# SandboxAction::Plugin::_dynamic_atexit_destructor_for__getDefaultSettings__

- ea: `0x140012470`
- end: `0x14001247c`
- name: `SandboxAction::Plugin::_dynamic_atexit_destructor_for__getDefaultSettings__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::Plugin::_dynamic_atexit_destructor_for__getDefaultSettings__()
{
  std::wstring::~wstring((char **)SandboxAction::Plugin::getDefaultSettings);
}

```

## disassembly

```asm
0x140012470  lea     rcx, ?getDefaultSettings@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x140012477  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
