# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::.ctor

- ea: `0x7e30`
- end: `0x7e58`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::.ctor`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5120`

## string_xrefs

- `0x7e3c`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x7e30  ldarg.0
0x7e31  ldsfld   class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::DefaultEncoding
0x7e36  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_encoding
0x7e3b  ldarg.0
0x7e3c  ldstr    aTextXml// "text/xml"
0x7e41  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_mimeType
0x7e46  ldarg.0
0x7e47  ldstr    aXml// "xml"
0x7e4c  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_dataFileExtension
0x7e51  ldarg.0
0x7e52  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::.ctor()
0x7e57  ret
```
