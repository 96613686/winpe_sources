# Microsoft.ReportingServices.Modeling.SemanticModel::.cctor

- ea: `0x17900`
- end: `0x17930`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::.cctor`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8a10`
- `0xa0a0`

## string_xrefs

- `0x1790f`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling/udmbinding`

## pseudocode

```c

```

## disassembly

```asm
0x17900  newobj   instance void [mscorlib]System.Object::.ctor()
0x17905  stsfld   object Microsoft.ReportingServices.Modeling.SemanticModel::__declarationLock
0x1790a  ldstr    aUdmbinding// "UdmBinding"
0x1790f  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0x17914  newobj   instance void Microsoft.ReportingServices.Modeling.QName::.ctor(string name, string ns)
0x17919  ldc.i4.1
0x1791a  box      [mscorlib]System.Boolean
0x1791f  newobj   instance void Microsoft.ReportingServices.Modeling.CustomProperty::.ctor(valuetype Microsoft.ReportingServices.Modeling.QName name, object value)
0x17924  stsfld   class Microsoft.ReportingServices.Modeling.CustomProperty Microsoft.ReportingServices.Modeling.SemanticModel::UdmBindingProperty
0x17929  ldc.i4.0
0x1792a  stsfld   bool Microsoft.ReportingServices.Modeling.SemanticModel::m_suppressDrillthroughDuringLazyClone
0x1792f  ret
```
