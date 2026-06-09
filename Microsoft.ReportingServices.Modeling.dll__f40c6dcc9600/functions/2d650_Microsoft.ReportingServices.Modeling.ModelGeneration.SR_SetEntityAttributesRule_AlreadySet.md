# Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_AlreadySet

- ea: `0x2d650`
- end: `0x2d667`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_AlreadySet`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b290`

## callees

- `0x3a5a0`

## string_xrefs

- `0x2d650`: `SetEntityAttributesRule_AlreadySet`

## pseudocode

```c

```

## disassembly

```asm
0x2d650  ldstr    aSetentityattri_1// "SetEntityAttributesRule_AlreadySet"
0x2d655  ldarg.0
0x2d656  box      Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment
0x2d65b  ldarg.1
0x2d65c  box      Microsoft.ReportingServices.Modeling.SRObjectDescriptor
0x2d661  call     string Keys::GetString(string key, object arg0, object arg1)
0x2d666  ret
```
