# SandboxAction::Plugin::_dynamic_atexit_destructor_for__init__

- ea: `0x1400124b0`
- end: `0x1400124bc`
- name: `SandboxAction::Plugin::_dynamic_atexit_destructor_for__init__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::Plugin::_dynamic_atexit_destructor_for__init__()
{
  std::wstring::~wstring(&SandboxAction::Plugin::init);
}

```

## disassembly

```asm
0x1400124b0  lea     rcx, ?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x1400124b7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
