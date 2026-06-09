# Microsoft.ReportingServices.Modeling.XmlUtil::WriteXsiNilAttribute

- ea: `0xba30`
- end: `0xba4e`
- name: `Microsoft.ReportingServices.Modeling.XmlUtil::WriteXsiNilAttribute`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb4f0`
- `0xb820`

## string_xrefs

- `0xba36`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xba30  ldarg.0
0xba31  ldstr    aNil// "nil"
0xba36  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xba3b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string, string)
0xba40  ldarg.0
0xba41  ldc.i4.1
0xba42  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(bool)
0xba47  ldarg.0
0xba48  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0xba4d  ret
```
