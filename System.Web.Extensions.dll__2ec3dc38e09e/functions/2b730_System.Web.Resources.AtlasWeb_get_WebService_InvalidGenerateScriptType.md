# System.Web.Resources.AtlasWeb::get_WebService_InvalidGenerateScriptType

- ea: `0x2b730`
- end: `0x2b745`
- name: `System.Web.Resources.AtlasWeb::get_WebService_InvalidGenerateScriptType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2ea50`

## callees

- `0x28080`

## string_xrefs

- `0x2b735`: `WebService_InvalidGenerateScriptType`

## pseudocode

```c

```

## disassembly

```asm
0x2b730  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b735  ldstr    aWebserviceInva// "WebService_InvalidGenerateScriptType"
0x2b73a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b73f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b744  ret
```
