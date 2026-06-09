# Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_CreateRoleRule_SourceOrTargetEntityDoesNotExist

- ea: `0x2d4d0`
- end: `0x2d4db`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_CreateRoleRule_SourceOrTargetEntityDoesNotExist`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26bb0`

## callees

- `0x3a560`

## string_xrefs

- `0x2d4d0`: `CreateRoleRule_SourceOrTargetEntityDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x2d4d0  ldstr    aCreaterolerule_0// "CreateRoleRule_SourceOrTargetEntityDoes"...
0x2d4d5  call     string Keys::GetString(string key)
0x2d4da  ret
```
