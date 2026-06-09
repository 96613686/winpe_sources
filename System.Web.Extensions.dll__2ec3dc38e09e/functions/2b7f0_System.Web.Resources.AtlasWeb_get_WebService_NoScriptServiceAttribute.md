# System.Web.Resources.AtlasWeb::get_WebService_NoScriptServiceAttribute

- ea: `0x2b7f0`
- end: `0x2b805`
- name: `System.Web.Resources.AtlasWeb::get_WebService_NoScriptServiceAttribute`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2e660`

## callees

- `0x28080`

## string_xrefs

- `0x2b7f5`: `WebService_NoScriptServiceAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x2b7f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b7f5  ldstr    aWebserviceNosc// "WebService_NoScriptServiceAttribute"
0x2b7fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b7ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b804  ret
```
