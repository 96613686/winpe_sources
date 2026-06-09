# System.Web.Resources.AtlasWeb::get_WebService_InvalidInlineVirtualPath

- ea: `0x2b750`
- end: `0x2b765`
- name: `System.Web.Resources.AtlasWeb::get_WebService_InvalidInlineVirtualPath`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x190a0`

## callees

- `0x28080`

## string_xrefs

- `0x2b755`: `WebService_InvalidInlineVirtualPath`

## pseudocode

```c

```

## disassembly

```asm
0x2b750  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b755  ldstr    aWebserviceInva_0// "WebService_InvalidInlineVirtualPath"
0x2b75a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b75f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b764  ret
```
