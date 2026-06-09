# Microsoft.ReportingServices.Common.XmlFragmentUtil::ToXmlString_0

- ea: `0x1c50`
- end: `0x1c7e`
- name: `Microsoft.ReportingServices.Common.XmlFragmentUtil::ToXmlString_0`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c40`

## callees

- `0x1c50`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1c55  stloc.0
0x1c56  ldloc.0
0x1c57  ldarg.0
0x1c58  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1c5d  stloc.1
0x1c5e  ldarg.1
0x1c5f  ldloc.1
0x1c60  callvirt instance void class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlWriter>::Invoke(var<u1>)
0x1c65  ldloc.1
0x1c66  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1c6b  leave.s  loc_1C77
0x1c6d  ldloc.1
0x1c6e  brfalse.s loc_1C76
0x1c70  ldloc.1
0x1c71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c76  endfinally
0x1c77  ldloc.0
0x1c78  callvirt instance string [mscorlib]System.Object::ToString()
0x1c7d  ret
```
