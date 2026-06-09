# System.Web.Resources.AtlasWeb::get_WebService_InvalidXmlReturnType

- ea: `0x2b7b0`
- end: `0x2b7c5`
- name: `System.Web.Resources.AtlasWeb::get_WebService_InvalidXmlReturnType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x2db40`

## callees

- `0x28080`

## string_xrefs

- `0x2b7b5`: `WebService_InvalidXmlReturnType`

## pseudocode

```c

```

## disassembly

```asm
0x2b7b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b7b5  ldstr    aWebserviceInva_3// "WebService_InvalidXmlReturnType"
0x2b7ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b7bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b7c4  ret
```
