# Microsoft.ReportingServices.Modeling.DataSourceView::.cctor

- ea: `0xd610`
- end: `0xd62f`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::.cctor`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xd615`: `http://schemas.microsoft.com/analysisservices/2003/engine`

## pseudocode

```c

```

## disassembly

```asm
0xd610  ldstr    aDatasourceview// "DataSourceView"
0xd615  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xd61a  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0xd61f  stsfld   class [System.Xml]System.Xml.XmlQualifiedName Microsoft.ReportingServices.Modeling.DataSourceView::DataSourceViewType
0xd624  newobj   instance void [mscorlib]System.Object::.ctor()
0xd629  stsfld   object Microsoft.ReportingServices.Modeling.DataSourceView::__declarationLock
0xd62e  ret
```
