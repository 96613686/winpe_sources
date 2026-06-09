# System.Web.Resources.AtlasWeb::get_WebResourceUtil_SystemWebExtensionsDoesNotContainReleaseWebResource

- ea: `0x2b6f0`
- end: `0x2b705`
- name: `System.Web.Resources.AtlasWeb::get_WebResourceUtil_SystemWebExtensionsDoesNotContainReleaseWebResource`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1a3f0`

## callees

- `0x28080`

## string_xrefs

- `0x2b6f5`: `WebResourceUtil_SystemWebExtensionsDoesNotContainReleaseWebResource`

## pseudocode

```c

```

## disassembly

```asm
0x2b6f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b6f5  ldstr    aWebresourceuti_2// "WebResourceUtil_SystemWebExtensionsDoes"...
0x2b6fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b6ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b704  ret
```
