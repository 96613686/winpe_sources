# SandboxAction::Plugin::_dynamic_atexit_destructor_for__uninit__

- ea: `0x140012530`
- end: `0x14001253c`
- name: `SandboxAction::Plugin::_dynamic_atexit_destructor_for__uninit__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::Plugin::_dynamic_atexit_destructor_for__uninit__()
{
  std::wstring::~wstring((char **)&SandboxAction::Plugin::uninit);
}

```

## disassembly

```asm
0x140012530  lea     rcx, ?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x140012537  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
