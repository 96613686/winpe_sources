# Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5ViewerRenderer::RenderSortImageText

- ea: `0x37cb0`
- end: `0x37ceb`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5ViewerRenderer::RenderSortImageText`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f10`
- `0x37cb0`

## string_xrefs

- `0x37cb5`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.sortAsc.gif`
- `0x37cca`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.sortDesc.gif`
- `0x37cdb`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.unsorted.gif`

## pseudocode

```c

```

## disassembly

```asm
0x37cb0  ldarg.1
0x37cb1  ldc.i4.1
0x37cb2  bne.un.s loc_37CC5
0x37cb4  ldarg.0
0x37cb5  ldstr    aMicrosoftRepor_143// "Microsoft.ReportingServices.Rendering.H"...
0x37cba  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37cbf  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5Renderer::WriteStream(string)
0x37cc4  ret
0x37cc5  ldarg.1
0x37cc6  ldc.i4.2
0x37cc7  bne.un.s loc_37CDA
0x37cc9  ldarg.0
0x37cca  ldstr    aMicrosoftRepor_144// "Microsoft.ReportingServices.Rendering.H"...
0x37ccf  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37cd4  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5Renderer::WriteStream(string)
0x37cd9  ret
0x37cda  ldarg.0
0x37cdb  ldstr    aMicrosoftRepor_145// "Microsoft.ReportingServices.Rendering.H"...
0x37ce0  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37ce5  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5Renderer::WriteStream(string)
0x37cea  ret
```
