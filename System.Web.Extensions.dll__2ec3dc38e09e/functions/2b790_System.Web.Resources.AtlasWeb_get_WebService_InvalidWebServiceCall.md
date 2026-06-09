# System.Web.Resources.AtlasWeb::get_WebService_InvalidWebServiceCall

- ea: `0x2b790`
- end: `0x2b7a5`
- name: `System.Web.Resources.AtlasWeb::get_WebService_InvalidWebServiceCall`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2d880`

## callees

- `0x28080`

## string_xrefs

- `0x2b795`: `WebService_InvalidWebServiceCall`

## pseudocode

```c

```

## disassembly

```asm
0x2b790  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b795  ldstr    aWebserviceInva_2// "WebService_InvalidWebServiceCall"
0x2b79a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b79f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b7a4  ret
```
