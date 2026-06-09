# Microsoft.ReportingServices.Rendering.HtmlRenderer.ViewerRenderer::WriteToggleImage

- ea: `0x37510`
- end: `0x37535`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.ViewerRenderer::WriteToggleImage`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x373e0`

## callees

- `0x8f10`
- `0x37510`

## string_xrefs

- `0x37514`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ToggleMinus.gif`
- `0x37525`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.TogglePlus.gif`

## pseudocode

```c

```

## disassembly

```asm
0x37510  ldarg.1
0x37511  brfalse.s loc_37524
0x37513  ldarg.0
0x37514  ldstr    aMicrosoftRepor_141// "Microsoft.ReportingServices.Rendering.H"...
0x37519  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x3751e  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::WriteStream(string)
0x37523  ret
0x37524  ldarg.0
0x37525  ldstr    aMicrosoftRepor_142// "Microsoft.ReportingServices.Rendering.H"...
0x3752a  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x3752f  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::WriteStream(string)
0x37534  ret
```
