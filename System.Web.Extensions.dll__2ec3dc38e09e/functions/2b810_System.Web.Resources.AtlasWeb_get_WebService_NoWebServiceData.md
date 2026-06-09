# System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceData

- ea: `0x2b810`
- end: `0x2b825`
- name: `System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceData`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2e4b0`

## callees

- `0x28080`

## string_xrefs

- `0x2b815`: `WebService_NoWebServiceData`

## pseudocode

```c

```

## disassembly

```asm
0x2b810  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b815  ldstr    aWebserviceNowe// "WebService_NoWebServiceData"
0x2b81a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b81f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b824  ret
```
