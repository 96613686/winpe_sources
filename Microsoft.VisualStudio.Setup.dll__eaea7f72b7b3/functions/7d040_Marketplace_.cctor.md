# Marketplace::.cctor

- ea: `0x7d040`
- end: `0x7d0b9`
- name: `Marketplace::.cctor`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## string_xrefs

- `0x7d045`: `query-marketplaceextensions`
- `0x7d081`: `extensionsCount`
- `0x7d095`: `extensions`

## pseudocode

```c

```

## disassembly

```asm
0x7d040  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::EventPrefix
0x7d045  ldstr    aQueryMarketpla// "query-marketplaceextensions"
0x7d04a  call     string [mscorlib]System.String::Concat(string, string)
0x7d04f  stsfld   string Marketplace::QueryMarketplaceExtensionsEvent
0x7d054  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::PropertyPrefix
0x7d059  ldstr    aInstanceversio// "instanceVersion"
0x7d05e  call     string [mscorlib]System.String::Concat(string, string)
0x7d063  stsfld   string Marketplace::InstanceVersionProperty
0x7d068  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::PropertyPrefix
0x7d06d  ldstr    aProductarch_0// "productArch"
0x7d072  call     string [mscorlib]System.String::Concat(string, string)
0x7d077  stsfld   string Marketplace::ProductArchProperty
0x7d07c  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::PropertyPrefix
0x7d081  ldstr    aExtensionscoun// "extensionsCount"
0x7d086  call     string [mscorlib]System.String::Concat(string, string)
0x7d08b  stsfld   string Marketplace::ExtensionsCountProperty
0x7d090  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::PropertyPrefix
0x7d095  ldstr    aExtensions_0// "extensions"
0x7d09a  call     string [mscorlib]System.String::Concat(string, string)
0x7d09f  stsfld   string Marketplace::ExtensionsProperty
0x7d0a4  ldsfld   string Microsoft.VisualStudio.Setup.SetupTelemetryConstants::EventPrefix
0x7d0a9  ldstr    aGetItemname// "get-itemname"
0x7d0ae  call     string [mscorlib]System.String::Concat(string, string)
0x7d0b3  stsfld   string Marketplace::GetItemNameEvent
0x7d0b8  ret
```
