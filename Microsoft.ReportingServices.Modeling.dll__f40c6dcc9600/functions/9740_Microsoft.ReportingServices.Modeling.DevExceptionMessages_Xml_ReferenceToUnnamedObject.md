# Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_ReferenceToUnnamedObject

- ea: `0x9740`
- end: `0x975a`
- name: `Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_ReferenceToUnnamedObject`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb530`

## callees

- `0x8e0`

## string_xrefs

- `0x9740`: `Cannot write a reference to an unnamed {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x9740  ldstr    aCannotWriteARe// "Cannot write a reference to an unnamed "...
0x9745  ldc.i4.1
0x9746  newarr   [mscorlib]System.Object
0x974b  dup
0x974c  ldc.i4.0
0x974d  ldarg.0
0x974e  box      Microsoft.ReportingServices.Modeling.SRObjectDescriptor
0x9753  stelem.ref
0x9754  call     string Microsoft.ReportingServices.Common.StringUtil::FormatInvariant(string format, object[] args)
0x9759  ret
```
