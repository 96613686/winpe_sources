# Microsoft.ReportingServices.Rendering.HtmlRenderer.ViewerRenderer::RenderSortImageText

- ea: `0x37540`
- end: `0x3757b`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.ViewerRenderer::RenderSortImageText`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f10`
- `0x37540`

## string_xrefs

- `0x37545`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.sortAsc.gif`
- `0x3755a`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.sortDesc.gif`
- `0x3756b`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.unsorted.gif`

## pseudocode

```c

```

## disassembly

```asm
0x37540  ldarg.1
0x37541  ldc.i4.1
0x37542  bne.un.s loc_37555
0x37544  ldarg.0
0x37545  ldstr    aMicrosoftRepor_143// "Microsoft.ReportingServices.Rendering.H"...
0x3754a  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x3754f  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::WriteStream(string)
0x37554  ret
0x37555  ldarg.1
0x37556  ldc.i4.2
0x37557  bne.un.s loc_3756A
0x37559  ldarg.0
0x3755a  ldstr    aMicrosoftRepor_144// "Microsoft.ReportingServices.Rendering.H"...
0x3755f  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37564  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::WriteStream(string)
0x37569  ret
0x3756a  ldarg.0
0x3756b  ldstr    aMicrosoftRepor_145// "Microsoft.ReportingServices.Rendering.H"...
0x37570  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37575  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::WriteStream(string)
0x3757a  ret
```
