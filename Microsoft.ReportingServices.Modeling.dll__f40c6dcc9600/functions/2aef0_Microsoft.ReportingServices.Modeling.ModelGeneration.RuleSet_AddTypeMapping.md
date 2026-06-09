# Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping

- ea: `0x2aef0`
- end: `0x2af03`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ada0`

## string_xrefs

- `0x2aef2`: `http://schemas.microsoft.com/sqlserver/2004/10/modelgeneration`

## pseudocode

```c

```

## disassembly

```asm
0x2aef0  ldarg.0
0x2aef1  ldarg.1
0x2aef2  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0x2aef7  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2aefc  ldarg.2
0x2aefd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x2af02  ret
```
