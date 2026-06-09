# Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource_0

- ea: `0x9030`
- end: `0x904e`
- name: `Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource_0`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9020`
- `0x9050`
- `0x9490`

## callees

- `0x9030`
- `0x16a60`

## string_xrefs

- `0x9031`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.`

## pseudocode

```c

```

## disassembly

```asm
0x9030  ldarg.1
0x9031  ldstr    aMicrosoftRepor_11// "Microsoft.ReportingServices.Rendering.H"...
0x9036  ldc.i4.5
0x9037  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x903c  brfalse.s loc_9046
0x903e  ldarg.1
0x903f  ldarg.2
0x9040  call     unsigned int8[] [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTMLRendererResources::GetBytesFullname(string, string&)
0x9045  ret
0x9046  ldarg.1
0x9047  ldarg.2
0x9048  call     unsigned int8[] Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::Get(string name, [out] string& mimeType)
0x904d  ret
```
