# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::CreateXmlWriter

- ea: `0x2300`
- end: `0x233f`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::CreateXmlWriter`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a90`
- `0x2110`

## callees

- `0x2300`

## pseudocode

```c

```

## disassembly

```asm
0x2300  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x2305  stloc.0
0x2306  ldarg.2
0x2307  brfalse.s loc_2324
0x2309  ldarg.0
0x230a  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x230f  isinst   [mscorlib]System.Text.UTF8Encoding
0x2314  brfalse.s loc_2324
0x2316  ldloc.0
0x2317  ldc.i4.0
0x2318  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool)
0x231d  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x2322  br.s     loc_2330
0x2324  ldloc.0
0x2325  ldarg.0
0x2326  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x232b  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x2330  ldloc.0
0x2331  ldc.i4.1
0x2332  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_NewLineHandling(valuetype [System.Xml]System.Xml.NewLineHandling)
0x2337  ldarg.1
0x2338  ldloc.0
0x2339  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlWriterSettings)
0x233e  ret
```
