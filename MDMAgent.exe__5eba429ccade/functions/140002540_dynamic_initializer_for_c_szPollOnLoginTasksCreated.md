# _dynamic_initializer_for__c_szPollOnLoginTasksCreated__

- ea: `0x140002540`
- end: `0x140002547`
- name: `_dynamic_initializer_for__c_szPollOnLoginTasksCreated__`
- size: `7`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002540`

## pseudocode

```c
// attributes: thunk
__int64 dynamic_initializer_for__c_szPollOnLoginTasksCreated__()
{
  return RtlIsStateSeparationEnabled();
}

```

## disassembly

```asm
0x140002540  jmp     cs:__imp_RtlIsStateSeparationEnabled
```
