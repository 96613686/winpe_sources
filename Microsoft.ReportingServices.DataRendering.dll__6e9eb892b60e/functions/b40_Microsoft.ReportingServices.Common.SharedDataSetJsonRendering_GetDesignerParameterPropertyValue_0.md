# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDesignerParameterPropertyValue_0

- ea: `0xb40`
- end: `0xb5e`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDesignerParameterPropertyValue_0`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaf0`

## callees

- `0xb40`

## string_xrefs

- `0xb42`: `http://schemas.microsoft.com/SQLServer/reporting/reportdesigner`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldarg.0
0xb41  ldarg.1
0xb42  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/SQLServer/"...
0xb47  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0xb4c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0xb51  stloc.0
0xb52  ldloc.0
0xb53  brfalse.s loc_B5C
0xb55  ldloc.0
0xb56  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0xb5b  ret
0xb5c  ldnull
0xb5d  ret
```
