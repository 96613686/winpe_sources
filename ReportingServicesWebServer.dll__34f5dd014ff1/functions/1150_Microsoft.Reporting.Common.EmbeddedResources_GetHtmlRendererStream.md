# Microsoft.Reporting.Common.EmbeddedResources::GetHtmlRendererStream

- ea: `0x1150`
- end: `0x117e`
- name: `Microsoft.Reporting.Common.EmbeddedResources::GetHtmlRendererStream`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1110`

## callees

- `0xfd0`
- `0x1040`
- `0x1080`
- `0x1150`

## string_xrefs

- `0x1163`: `Microsoft.ReportingServices.HtmlRendering.dll`

## pseudocode

```c

```

## disassembly

```asm
0x1150  ldarg.0
0x1151  ldarg.1
0x1152  ldloca.s 0
0x1154  callvirt instance bool Microsoft.Reporting.Common.ResourceList::TryGetResourceItem(string name, [out] class Microsoft.Reporting.Common.ResourceItem& item)
0x1159  brfalse.s loc_1179
0x115b  ldarg.2
0x115c  ldloc.0
0x115d  callvirt instance string Microsoft.Reporting.Common.ResourceItem::get_MimeType()
0x1162  stind.ref
0x1163  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.HtmlRenderi"...
0x1168  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x116d  ldloc.0
0x116e  callvirt instance string Microsoft.Reporting.Common.ResourceItem::get_EffectiveName()
0x1173  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x1178  ret
0x1179  ldarg.2
0x117a  ldnull
0x117b  stind.ref
0x117c  ldnull
0x117d  ret
```
