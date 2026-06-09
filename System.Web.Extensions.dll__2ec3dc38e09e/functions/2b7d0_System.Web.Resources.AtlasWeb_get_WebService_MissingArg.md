# System.Web.Resources.AtlasWeb::get_WebService_MissingArg

- ea: `0x2b7d0`
- end: `0x2b7e5`
- name: `System.Web.Resources.AtlasWeb::get_WebService_MissingArg`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2f2f0`

## callees

- `0x28080`

## string_xrefs

- `0x2b7d5`: `WebService_MissingArg`

## pseudocode

```c

```

## disassembly

```asm
0x2b7d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b7d5  ldstr    aWebserviceMiss// "WebService_MissingArg"
0x2b7da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b7df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b7e4  ret
```
