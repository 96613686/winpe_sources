# _dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPrefixes__

- ea: `0x18000b100`
- end: `0x18000b10c`
- name: `_dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPrefixes__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000707c`

## pseudocode

```c
void dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPrefixes__()
{
  ConfigValueStringList::~ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SmsInterceptPrefixes);
}

```

## disassembly

```asm
0x18000b100  lea     rcx, ?c_pDefaultValue_SmsInterceptPrefixes@@3VConfigValueStringList@@B; this
0x18000b107  jmp     ??1ConfigValueStringList@@UEAA@XZ; ConfigValueStringList::~ConfigValueStringList(void)
```
