# Microsoft.ReportingServices.Modeling.XmlUtil::.cctor

- ea: `0xbc50`
- end: `0xbc8d`
- name: `Microsoft.ReportingServices.Modeling.XmlUtil::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa0a0`

## string_xrefs

- `0xbc73`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xbc5d`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xbc50  ldc.i4.2
0xbc51  newarr   Microsoft.ReportingServices.Modeling.QName
0xbc56  dup
0xbc57  ldc.i4.0
0xbc58  ldstr    aXsd// "xsd"
0xbc5d  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema"
0xbc62  newobj   instance void Microsoft.ReportingServices.Modeling.QName::.ctor(string name, string ns)
0xbc67  stelem   Microsoft.ReportingServices.Modeling.QName
0xbc6c  dup
0xbc6d  ldc.i4.1
0xbc6e  ldstr    aXsi// "xsi"
0xbc73  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xbc78  newobj   instance void Microsoft.ReportingServices.Modeling.QName::.ctor(string name, string ns)
0xbc7d  stelem   Microsoft.ReportingServices.Modeling.QName
0xbc82  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.QName>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xbc87  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.QName> Microsoft.ReportingServices.Modeling.XmlUtil::XmlSchemaNsPrefixes
0xbc8c  ret
```
