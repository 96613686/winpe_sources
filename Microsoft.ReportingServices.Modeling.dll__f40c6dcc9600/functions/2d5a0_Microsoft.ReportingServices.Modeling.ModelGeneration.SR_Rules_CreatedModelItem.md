# Microsoft.ReportingServices.Modeling.ModelGeneration.SR::Rules_CreatedModelItem

- ea: `0x2d5a0`
- end: `0x2d5b1`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SR::Rules_CreatedModelItem`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29770`
- `0x29790`
- `0x297d0`

## callees

- `0x3a580`

## string_xrefs

- `0x2d5a0`: `Rules_CreatedModelItem`

## pseudocode

```c

```

## disassembly

```asm
0x2d5a0  ldstr    aRulesCreatedmo// "Rules_CreatedModelItem"
0x2d5a5  ldarg.0
0x2d5a6  box      Microsoft.ReportingServices.Modeling.SRObjectDescriptor
0x2d5ab  call     string Keys::GetString(string key, object arg0)
0x2d5b0  ret
```
