# Microsoft.ReportingServices.Modeling.ExpressionPath::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement

- ea: `0x1e1a0`
- end: `0x1e1d7`
- name: `Microsoft.ReportingServices.Modeling.ExpressionPath::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa760`
- `0xa7b0`
- `0x1e1a0`
- `0x1eb50`
- `0x1ed20`

## string_xrefs

- `0x1e1b0`: `RolePathItem`

## pseudocode

```c

```

## disassembly

```asm
0x1e1a0  ldnull
0x1e1a1  stloc.0
0x1e1a2  ldarg.1
0x1e1a3  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x1e1a8  brfalse.s loc_1E1C2
0x1e1aa  ldarg.1
0x1e1ab  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x1e1b0  ldstr    aRolepathitem// "RolePathItem"
0x1e1b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e1ba  brfalse.s loc_1E1C2
0x1e1bc  newobj   instance void Microsoft.ReportingServices.Modeling.RolePathItem::.ctor()
0x1e1c1  stloc.0
0x1e1c2  ldloc.0
0x1e1c3  brfalse.s loc_1E1D5
0x1e1c5  ldloc.0
0x1e1c6  ldarg.1
0x1e1c7  callvirt instance void Microsoft.ReportingServices.Modeling.PathItem::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x1e1cc  ldarg.0
0x1e1cd  ldloc.0
0x1e1ce  call     instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::Add(var<u1>)
0x1e1d3  ldc.i4.1
0x1e1d4  ret
0x1e1d5  ldc.i4.0
0x1e1d6  ret
```
