# SandboxAction::Plugin::_dynamic_atexit_destructor_for__detectCondition__

- ea: `0x140012370`
- end: `0x14001237c`
- name: `SandboxAction::Plugin::_dynamic_atexit_destructor_for__detectCondition__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004670`

## pseudocode

```c
void SandboxAction::Plugin::_dynamic_atexit_destructor_for__detectCondition__()
{
  std::wstring::~wstring((char **)&SandboxAction::Plugin::detectCondition);
}

```

## disassembly

```asm
0x140012370  lea     rcx, ?detectCondition@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; void *
0x140012377  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
