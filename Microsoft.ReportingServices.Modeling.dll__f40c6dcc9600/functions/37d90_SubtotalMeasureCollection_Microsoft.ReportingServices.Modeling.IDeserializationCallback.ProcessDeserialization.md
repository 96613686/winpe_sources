# SubtotalMeasureCollection::Microsoft.ReportingServices.Modeling.IDeserializationCallback.ProcessDeserializationReference

- ea: `0x37d90`
- end: `0x37db9`
- name: `SubtotalMeasureCollection::Microsoft.ReportingServices.Modeling.IDeserializationCallback.ProcessDeserializationReference`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xb040`
- `0xb0e0`
- `0x23680`
- `0x37d90`

## string_xrefs

- `0x37d97`: `SubtotalMeasures.MeasureName`

## pseudocode

```c

```

## disassembly

```asm
0x37d90  ldarga.s 1
0x37d92  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x37d97  ldstr    aSubtotalmeasur_0// "SubtotalMeasures.MeasureName"
0x37d9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37da1  brfalse.s loc_37DB7
0x37da3  ldarg.0
0x37da4  ldarg.1
0x37da5  ldarg.2
0x37da6  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.DeserializationContext::get_Validation()
0x37dab  call     class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.SemanticQuery::TryGetMeasure(valuetype Microsoft.ReportingServices.Modeling.ModelingReference itemRef, class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x37db0  call     instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::Add(var<u1>)
0x37db5  ldc.i4.1
0x37db6  ret
0x37db7  ldc.i4.0
0x37db8  ret
```
