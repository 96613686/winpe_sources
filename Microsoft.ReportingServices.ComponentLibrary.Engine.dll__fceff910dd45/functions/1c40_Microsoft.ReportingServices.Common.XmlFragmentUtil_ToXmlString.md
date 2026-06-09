# Microsoft.ReportingServices.Common.XmlFragmentUtil::ToXmlString

- ea: `0x1c40`
- end: `0x1c4c`
- name: `Microsoft.ReportingServices.Common.XmlFragmentUtil::ToXmlString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1c50`

## pseudocode

```c

```

## disassembly

```asm
0x1c40  ldsfld   class [System.Xml]System.Xml.XmlWriterSettings Microsoft.ReportingServices.Common.XmlFragmentUtil::m_xmlWriterSettings
0x1c45  ldarg.0
0x1c46  call     string Microsoft.ReportingServices.Common.XmlFragmentUtil::ToXmlString(class [System.Xml]System.Xml.XmlWriterSettings settings, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlWriter> writeTo)
0x1c4b  ret
```
