# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatchItemHeader

- ea: `0x2060`
- end: `0x20da`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatchItemHeader`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2110`

## callees

- `0x2060`

## string_xrefs

- `0x20a6`: `application/atom+xml`
- `0x20b8`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2060  ldarg.1
0x2061  ldstr    asc_EC8A// "--"
0x2066  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x206b  ldarg.1
0x206c  ldstr    aBatch36522ad7F// "batch_36522ad7-fc75-4b56-8c71-56071383e"...
0x2071  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2076  ldarg.1
0x2077  ldstr    aContentTypeApp// "Content-Type: application/http"
0x207c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2081  ldarg.1
0x2082  ldstr    aContentTransfe// "Content-Transfer-Encoding: binary"
0x2087  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x208c  ldarg.1
0x208d  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0x2092  ldarg.1
0x2093  ldstr    aHttp11200Ok// "HTTP/1.1 200 OK"
0x2098  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x209d  ldarg.2
0x209e  brfalse.s loc_20B2
0x20a0  ldarg.1
0x20a1  ldstr    aContentType0Ty// "Content-Type: {0};type=feed"
0x20a6  ldstr    aApplicationAto_0// "application/atom+xml"
0x20ab  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x20b0  br.s     loc_20CD
0x20b2  ldarg.1
0x20b3  ldstr    aContentType0Ch// "Content-Type: {0};charset={1}"
0x20b8  ldstr    aApplicationXml// "application/xml"
0x20bd  ldarg.0
0x20be  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x20c3  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x20c8  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object, object)
0x20cd  ldarg.1
0x20ce  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0x20d3  ldarg.1
0x20d4  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x20d9  ret
```
