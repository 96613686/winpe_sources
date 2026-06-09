# Microsoft.ReportingServices.Modeling.RolePathItem::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement

- ea: `0x1ef80`
- end: `0x1efb6`
- name: `Microsoft.ReportingServices.Modeling.RolePathItem::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa740`
- `0xa760`
- `0xa7b0`
- `0xaec0`
- `0xb1c0`
- `0x1ef80`

## string_xrefs

- `0x1efa2`: `RolePathItem.RoleID`

## pseudocode

```c

```

## disassembly

```asm
0x1ef80  ldarg.1
0x1ef81  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x1ef86  brfalse.s loc_1EFB4
0x1ef88  ldarg.1
0x1ef89  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x1ef8e  ldstr    aRoleid// "RoleID"
0x1ef93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ef98  brfalse.s loc_1EFB4
0x1ef9a  ldarg.1
0x1ef9b  callvirt instance class Microsoft.ReportingServices.Modeling.DeserializationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Context()
0x1efa0  ldarg.0
0x1efa1  ldarg.1
0x1efa2  ldstr    aRolepathitemRo// "RolePathItem.RoleID"
0x1efa7  ldc.i4.1
0x1efa8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ModelingReference Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadReferenceByID(string propertyName, bool multipleInScope)
0x1efad  callvirt instance void Microsoft.ReportingServices.Modeling.DeserializationContext::AddReference(class Microsoft.ReportingServices.Modeling.IDeserializationCallback item, valuetype Microsoft.ReportingServices.Modeling.ModelingReference reference)
0x1efb2  ldc.i4.1
0x1efb3  ret
0x1efb4  ldc.i4.0
0x1efb5  ret
```
