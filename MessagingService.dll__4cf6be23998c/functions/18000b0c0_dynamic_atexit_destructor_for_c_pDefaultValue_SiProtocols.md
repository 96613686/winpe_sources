# _dynamic_atexit_destructor_for__c_pDefaultValue_SiProtocols__

- ea: `0x18000b0c0`
- end: `0x18000b0cc`
- name: `_dynamic_atexit_destructor_for__c_pDefaultValue_SiProtocols__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000707c`

## pseudocode

```c
void dynamic_atexit_destructor_for__c_pDefaultValue_SiProtocols__()
{
  ConfigValueStringList::~ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SiProtocols);
}

```

## disassembly

```asm
0x18000b0c0  lea     rcx, ?c_pDefaultValue_SiProtocols@@3VConfigValueStringList@@B; this
0x18000b0c7  jmp     ??1ConfigValueStringList@@UEAA@XZ; ConfigValueStringList::~ConfigValueStringList(void)
```
