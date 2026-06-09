# Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5ViewerRenderer::WriteToggleImage

- ea: `0x37c80`
- end: `0x37ca5`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5ViewerRenderer::WriteToggleImage`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x37a50`

## callees

- `0x8f10`
- `0x37c80`

## string_xrefs

- `0x37c84`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ToggleMinus.gif`
- `0x37c95`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.TogglePlus.gif`

## pseudocode

```c

```

## disassembly

```asm
0x37c80  ldarg.1
0x37c81  brfalse.s loc_37C94
0x37c83  ldarg.0
0x37c84  ldstr    aMicrosoftRepor_141// "Microsoft.ReportingServices.Rendering.H"...
0x37c89  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37c8e  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5Renderer::WriteStream(string)
0x37c93  ret
0x37c94  ldarg.0
0x37c95  ldstr    aMicrosoftRepor_142// "Microsoft.ReportingServices.Rendering.H"...
0x37c9a  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x37c9f  callvirt instance void [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML5Renderer::WriteStream(string)
0x37ca4  ret
```
