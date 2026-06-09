# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$3

- ea: `0x18000f03d`
- end: `0x18000f049`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$3`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_3()
{
  std::wstring::~wstring((void **)qword_18001FAC0);
}

```

## disassembly

```asm
0x18000f03d  lea     rcx, qword_18001FAC0; void *
0x18000f044  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
