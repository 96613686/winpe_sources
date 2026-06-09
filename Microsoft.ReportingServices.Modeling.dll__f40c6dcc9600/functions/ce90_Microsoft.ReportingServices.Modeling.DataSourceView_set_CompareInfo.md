# Microsoft.ReportingServices.Modeling.DataSourceView::set_CompareInfo

- ea: `0xce90`
- end: `0xcead`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::set_CompareInfo`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xce30`
- `0x2c100`

## callees

- `0x9d00`
- `0xced0`
- `0x2f840`

## string_xrefs

- `0xcea1`: `CompareInfo`

## pseudocode

```c

```

## disassembly

```asm
0xce90  ldarg.0
0xce91  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::CheckWriteable()
0xce96  ldarg.0
0xce97  ldfld    class IDsvInfo Microsoft.ReportingServices.Modeling.DataSourceView::m_dsvInfo
0xce9c  callvirt instance class [mscorlib]System.Collections.IDictionary IDsvInfo::get_ExtendedProperties()
0xcea1  ldstr    aCompareinfo// "CompareInfo"
0xcea6  ldarg.1
0xcea7  call     void Microsoft.ReportingServices.Modeling.DataSourceView::SetExtendedProperty(class [mscorlib]System.Collections.IDictionary props, string propName, object propValue)
0xceac  ret
```
