# Microsoft.ReportingServices.Modeling.ModelGeneration.SR::CreateRoleRule_RoleNameWithEntity

- ea: `0x2d640`
- end: `0x2d64d`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SR::CreateRoleRule_RoleNameWithEntity`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26ea0`

## callees

- `0x3a5a0`

## string_xrefs

- `0x2d640`: `CreateRoleRule_RoleNameWithEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2d640  ldstr    aCreaterolerule_2// "CreateRoleRule_RoleNameWithEntity"
0x2d645  ldarg.0
0x2d646  ldarg.1
0x2d647  call     string Keys::GetString(string key, object arg0, object arg1)
0x2d64c  ret
```
