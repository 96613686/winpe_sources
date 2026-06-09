# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::AdjustRenderingExtensionForSku

- ea: `0x6d10`
- end: `0x6d6f`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::AdjustRenderingExtensionForSku`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6bc0`

## callees

- `0x4fa0`
- `0x5040`
- `0x5070`
- `0x6d10`
- `0x72a0`
- `0x8150`
- `0x8170`

## string_xrefs

- `0x6d3f`: `Extension `
- `0x6d4a`: ` is not supported on this edition of Reporting Services and has been removed`

## pseudocode

```c

```

## disassembly

```asm
0x6d10  ldarg.0
0x6d11  isinst   Microsoft.ReportingServices.Diagnostics.RenderingExtension
0x6d16  brfalse.s loc_6D6E
0x6d18  ldarg.2
0x6d19  ldarg.0
0x6d1a  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_ClassAndAssembly()
0x6d1f  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsRestrictedRenderingExtension(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, string configTypeAndAssembly)
0x6d24  brfalse.s loc_6D59
0x6d26  ldarg.0
0x6d27  ldarg.1
0x6d28  call     void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::RemoveExtensionFromConfigInfo(class Microsoft.ReportingServices.Diagnostics.Extension extension, class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration extensionsConfig)
0x6d2d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6d32  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6d37  brfalse.s loc_6D59
0x6d39  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6d3e  ldc.i4.3
0x6d3f  ldstr    aExtension_0// "Extension "
0x6d44  ldarg.0
0x6d45  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6d4a  ldstr    aIsNotSupported// " is not supported on this edition of Re"...
0x6d4f  call     string [mscorlib]System.String::Concat(string, string, string)
0x6d54  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6d59  ldarg.2
0x6d5a  ldarg.0
0x6d5b  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_ClassAndAssembly()
0x6d60  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsHiddenRenderingExtension(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, string configTypeAndAssembly)
0x6d65  brfalse.s loc_6D6E
0x6d67  ldarg.0
0x6d68  ldc.i4.0
0x6d69  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Visible(bool value)
0x6d6e  ret
```
