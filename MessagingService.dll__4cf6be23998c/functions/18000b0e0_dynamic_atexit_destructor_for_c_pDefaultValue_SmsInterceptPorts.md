# _dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPorts__

- ea: `0x18000b0e0`
- end: `0x18000b0ec`
- name: `_dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPorts__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000707c`

## pseudocode

```c
void dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPorts__()
{
  ConfigValueStringList::~ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SmsInterceptPorts);
}

```

## disassembly

```asm
0x18000b0e0  lea     rcx, ?c_pDefaultValue_SmsInterceptPorts@@3VConfigValueStringList@@B; this
0x18000b0e7  jmp     ??1ConfigValueStringList@@UEAA@XZ; ConfigValueStringList::~ConfigValueStringList(void)
```
