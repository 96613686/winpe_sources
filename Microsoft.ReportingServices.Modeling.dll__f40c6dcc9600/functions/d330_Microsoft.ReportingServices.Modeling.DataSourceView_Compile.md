# Microsoft.ReportingServices.Modeling.DataSourceView::Compile

- ea: `0xd330`
- end: `0xd374`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::Compile`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x17160`

## callees

- `0x84f0`
- `0x9d20`
- `0xce30`
- `0xd330`
- `0xd960`
- `0x2f840`

## string_xrefs

- `0xd363`: `_ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xd330  ldarg.0
0xd331  call     instance class Microsoft.ReportingServices.Modeling.DsvCompareInfo Microsoft.ReportingServices.Modeling.DataSourceView::get_CompareInfo()
0xd336  brfalse.s loc_D344
0xd338  ldarg.0
0xd339  call     instance class Microsoft.ReportingServices.Modeling.DsvCompareInfo Microsoft.ReportingServices.Modeling.DataSourceView::get_CompareInfo()
0xd33e  ldarg.1
0xd33f  callvirt instance void Microsoft.ReportingServices.Modeling.DsvCompareInfo::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0xd344  ldarg.0
0xd345  ldarg.1
0xd346  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0xd34b  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0xd350  ldarg.1
0xd351  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0xd356  brfalse.s loc_D373
0xd358  ldarg.0
0xd359  ldfld    class IDsvInfo Microsoft.ReportingServices.Modeling.DataSourceView::m_dsvInfo
0xd35e  callvirt instance class [mscorlib]System.Collections.IDictionary IDsvInfo::get_ExtendedProperties()
0xd363  ldstr    aReadonly// "_ReadOnly"
0xd368  ldc.i4.1
0xd369  box      [mscorlib]System.Boolean
0xd36e  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xd373  ret
```
