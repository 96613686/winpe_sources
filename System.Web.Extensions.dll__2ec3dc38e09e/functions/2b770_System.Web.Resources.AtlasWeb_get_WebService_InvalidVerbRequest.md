# System.Web.Resources.AtlasWeb::get_WebService_InvalidVerbRequest

- ea: `0x2b770`
- end: `0x2b785`
- name: `System.Web.Resources.AtlasWeb::get_WebService_InvalidVerbRequest`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2da80`

## callees

- `0x28080`

## string_xrefs

- `0x2b775`: `WebService_InvalidVerbRequest`

## pseudocode

```c

```

## disassembly

```asm
0x2b770  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b775  ldstr    aWebserviceInva_1// "WebService_InvalidVerbRequest"
0x2b77a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b77f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b784  ret
```
