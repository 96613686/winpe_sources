# _dynamic_initializer_for__c_pDefaultValue_SmsInterceptPrefixes__

- ea: `0x180001660`
- end: `0x180001680`
- name: `_dynamic_initializer_for__c_pDefaultValue_SmsInterceptPrefixes__`
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
int dynamic_initializer_for__c_pDefaultValue_SmsInterceptPrefixes__()
{
  ConfigValueStringList::ConfigValueStringList((ConfigValueStringList *)c_pDefaultValue_SmsInterceptPrefixes);
  return atexit(dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPrefixes__);
}

```

## disassembly

```asm
0x180001660  sub     rsp, 28h
0x180001664  lea     rcx, ?c_pDefaultValue_SmsInterceptPrefixes@@3VConfigValueStringList@@B; this
0x18000166b  call    ??0ConfigValueStringList@@QEAA@XZ; ConfigValueStringList::ConfigValueStringList(void)
0x180001670  lea     rcx, _dynamic_atexit_destructor_for__c_pDefaultValue_SmsInterceptPrefixes__
0x180001677  add     rsp, 28h
0x18000167b  jmp     atexit
```
