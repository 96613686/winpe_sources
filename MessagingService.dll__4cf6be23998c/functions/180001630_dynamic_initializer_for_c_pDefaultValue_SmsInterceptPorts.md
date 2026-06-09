# _dynamic_initializer_for__c_pDefaultValue_SmsInterceptPorts__

- ea: `0x180001630`
- end: `0x180001650`
- name: `_dynamic_initializer_for__c_pDefaultValue_SmsInterceptPorts__`
- size: `32`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002634`
- `0x180006fdc`

## pseudocode

```c
int dynamic_initializer_for__c_pDefaultValue_SmsInterceptPorts__()
{
  ConfigValueStringList::ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SmsInterceptPorts);
  return atexit(dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPorts__);
}

```

## disassembly

```asm
0x180001630  sub     rsp, 28h
0x180001634  lea     rcx, ?c_pDefaultValue_SmsInterceptPorts@@3VConfigValueStringList@@B; this
0x18000163b  call    ??0ConfigValueStringList@@QEAA@XZ; ConfigValueStringList::ConfigValueStringList(void)
0x180001640  lea     rcx, _dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPorts__
0x180001647  add     rsp, 28h
0x18000164b  jmp     atexit
```
