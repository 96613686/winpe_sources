# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$6

- ea: `0x18000f073`
- end: `0x18000f07f`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$6`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_6()
{
  std::wstring::~wstring((void **)qword_18001FB20);
}

```

## disassembly

```asm
0x18000f073  lea     rcx, qword_18001FB20; void *
0x18000f07a  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
