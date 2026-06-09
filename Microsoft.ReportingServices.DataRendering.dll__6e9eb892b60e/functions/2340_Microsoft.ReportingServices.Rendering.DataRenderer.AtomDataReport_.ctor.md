# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::.ctor

- ea: `0x2340`
- end: `0x2368`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::.ctor`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5120`

## string_xrefs

- `0x2357`: `application/atomsvc+xml`

## pseudocode

```c

```

## disassembly

```asm
0x2340  ldarg.0
0x2341  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2346  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x234b  ldarg.0
0x234c  ldstr    aAtomsvc// "atomsvc"
0x2351  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x2356  ldarg.0
0x2357  ldstr    aApplicationAto// "application/atomsvc+xml"
0x235c  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x2361  ldarg.0
0x2362  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::.ctor()
0x2367  ret
```
