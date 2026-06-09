# SubtotalMeasureCollection::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement

- ea: `0x37d50`
- end: `0x37d86`
- name: `SubtotalMeasureCollection::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa740`
- `0xa760`
- `0xa7b0`
- `0xaed0`
- `0xb1c0`
- `0x37d50`

## string_xrefs

- `0x37d5e`: `MeasureName`
- `0x37d72`: `SubtotalMeasures.MeasureName`

## pseudocode

```c

```

## disassembly

```asm
0x37d50  ldarg.1
0x37d51  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x37d56  brfalse.s loc_37D84
0x37d58  ldarg.1
0x37d59  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x37d5e  ldstr    aMeasurename// "MeasureName"
0x37d63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37d68  brfalse.s loc_37D84
0x37d6a  ldarg.1
0x37d6b  callvirt instance class Microsoft.ReportingServices.Modeling.DeserializationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Context()
0x37d70  ldarg.0
0x37d71  ldarg.1
0x37d72  ldstr    aSubtotalmeasur_0// "SubtotalMeasures.MeasureName"
0x37d77  ldc.i4.1
0x37d78  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ModelingReference Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadReferenceByName(string propertyName, bool multipleInScope)
0x37d7d  callvirt instance void Microsoft.ReportingServices.Modeling.DeserializationContext::AddReference(class Microsoft.ReportingServices.Modeling.IDeserializationCallback item, valuetype Microsoft.ReportingServices.Modeling.ModelingReference reference)
0x37d82  ldc.i4.1
0x37d83  ret
0x37d84  ldc.i4.0
0x37d85  ret
```
