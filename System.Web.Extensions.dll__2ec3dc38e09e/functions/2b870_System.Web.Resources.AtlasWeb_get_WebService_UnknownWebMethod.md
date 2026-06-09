# System.Web.Resources.AtlasWeb::get_WebService_UnknownWebMethod

- ea: `0x2b870`
- end: `0x2b885`
- name: `System.Web.Resources.AtlasWeb::get_WebService_UnknownWebMethod`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2e8a0`

## callees

- `0x28080`

## string_xrefs

- `0x2b875`: `WebService_UnknownWebMethod`

## pseudocode

```c

```

## disassembly

```asm
0x2b870  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b875  ldstr    aWebserviceUnkn// "WebService_UnknownWebMethod"
0x2b87a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b87f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b884  ret
```
