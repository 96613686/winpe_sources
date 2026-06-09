# SandboxAction::Plugin::_dynamic_atexit_destructor_for__performAction__

- ea: `0x1400124d0`
- end: `0x1400124dc`
- name: `SandboxAction::Plugin::_dynamic_atexit_destructor_for__performAction__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::Plugin::_dynamic_atexit_destructor_for__performAction__()
{
  std::wstring::~wstring((char **)&SandboxAction::Plugin::performAction);
}

```

## disassembly

```asm
0x1400124d0  lea     rcx, ?performAction@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x1400124d7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
