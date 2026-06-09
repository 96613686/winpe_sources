# Microsoft.ReportingServices.Modeling.RolePathItem::Microsoft.ReportingServices.Modeling.IDeserializationCallback.ProcessDeserializationReference

- ea: `0x1efc0`
- end: `0x1efef`
- name: `Microsoft.ReportingServices.Modeling.RolePathItem::Microsoft.ReportingServices.Modeling.IDeserializationCallback.ProcessDeserializationReference`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xb040`
- `0xb0e0`
- `0xb0f0`
- `0x1efc0`

## string_xrefs

- `0x1efc7`: `RolePathItem.RoleID`

## pseudocode

```c

```

## disassembly

```asm
0x1efc0  ldarga.s 1
0x1efc2  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x1efc7  ldstr    aRolepathitemRo// "RolePathItem.RoleID"
0x1efcc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1efd1  brfalse.s loc_1EFED
0x1efd3  ldarg.0
0x1efd4  ldarg.2
0x1efd5  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.DeserializationContext::get_CurrentModel()
0x1efda  ldarg.1
0x1efdb  ldarg.2
0x1efdc  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.DeserializationContext::get_Validation()
0x1efe1  callvirt T0x2B000077
0x1efe6  stfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1efeb  ldc.i4.1
0x1efec  ret
0x1efed  ldc.i4.0
0x1efee  ret
```
