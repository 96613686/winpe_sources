# Microsoft.ReportingServices.Modeling.DataSourceView::get_CompareInfo

- ea: `0xce30`
- end: `0xce88`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::get_CompareInfo`
- size: `88`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xd330`
- `0xd4a0`
- `0x28e20`
- `0x2c100`
- `0x2c440`

## callees

- `0x97d0`
- `0x9cf0`
- `0xce30`
- `0xce90`
- `0xd650`
- `0x2f840`

## string_xrefs

- `0xce3b`: `CompareInfo`
- `0xce59`: `compareInfo is not DsvCompareInfo on compiled DataSourceView`

## pseudocode

```c

```

## disassembly

```asm
0xce30  ldarg.0
0xce31  ldfld    class IDsvInfo Microsoft.ReportingServices.Modeling.DataSourceView::m_dsvInfo
0xce36  callvirt instance class [mscorlib]System.Collections.IDictionary IDsvInfo::get_ExtendedProperties()
0xce3b  ldstr    aCompareinfo// "CompareInfo"
0xce40  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xce45  stloc.0
0xce46  ldloc.0
0xce47  brfalse.s loc_CE81
0xce49  ldloc.0
0xce4a  isinst   Microsoft.ReportingServices.Modeling.DsvCompareInfo
0xce4f  brtrue.s loc_CE81
0xce51  ldarg.0
0xce52  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0xce57  brfalse.s loc_CE64
0xce59  ldstr    aCompareinfoIsN// "compareInfo is not DsvCompareInfo on co"...
0xce5e  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xce63  throw
0xce64  nop
0xce65  ldloc.0
0xce66  callvirt instance string [mscorlib]System.Object::ToString()
0xce6b  call     class Microsoft.ReportingServices.Modeling.DsvCompareInfo Microsoft.ReportingServices.Modeling.DsvCompareInfo::FromXml(string xml)
0xce70  stloc.1
0xce71  leave.s  loc_CE78
0xce73  pop
0xce74  ldnull
0xce75  stloc.1
0xce76  leave.s  loc_CE78
0xce78  ldarg.0
0xce79  ldloc.1
0xce7a  call     instance void Microsoft.ReportingServices.Modeling.DataSourceView::set_CompareInfo(class Microsoft.ReportingServices.Modeling.DsvCompareInfo value)
0xce7f  ldloc.1
0xce80  ret
0xce81  ldloc.0
0xce82  castclass Microsoft.ReportingServices.Modeling.DsvCompareInfo
0xce87  ret
```
