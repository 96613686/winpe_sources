# Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_UnexpectedValueType

- ea: `0x9720`
- end: `0x9735`
- name: `Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_UnexpectedValueType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb8c0`

## callees

- `0x8e0`

## string_xrefs

- `0x9720`: `The type "{0}" does not have an appropriate mapping to an XML data type.`

## pseudocode

```c

```

## disassembly

```asm
0x9720  ldstr    aTheType0DoesNo// "The type \"{0}\" does not have an appro"...
0x9725  ldc.i4.1
0x9726  newarr   [mscorlib]System.Object
0x972b  dup
0x972c  ldc.i4.0
0x972d  ldarg.0
0x972e  stelem.ref
0x972f  call     string Microsoft.ReportingServices.Common.StringUtil::FormatInvariant(string format, object[] args)
0x9734  ret
```
