# _dynamic_initializer_for__c_pDefaultValue_SiProtocols__

- ea: `0x180001600`
- end: `0x180001620`
- name: `_dynamic_initializer_for__c_pDefaultValue_SiProtocols__`
- size: `32`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002634`
- `0x180006fdc`

## pseudocode

```c
int dynamic_initializer_for__c_pDefaultValue_SiProtocols__()
{
  ConfigValueStringList::ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SiProtocols);
  return atexit(dynamic_atexit_destructor_for__c_pDefaultValue_SiProtocols__);
}

```

## disassembly

```asm
0x180001600  sub     rsp, 28h
0x180001604  lea     rcx, ?c_pDefaultValue_SiProtocols@@3VConfigValueStringList@@B; this
0x18000160b  call    ??0ConfigValueStringList@@QEAA@XZ; ConfigValueStringList::ConfigValueStringList(void)
0x180001610  lea     rcx, _dynamic_atexit_destructor_for__c_pDefaultValue_SiProtocols__
0x180001617  add     rsp, 28h
0x18000161b  jmp     atexit
```
