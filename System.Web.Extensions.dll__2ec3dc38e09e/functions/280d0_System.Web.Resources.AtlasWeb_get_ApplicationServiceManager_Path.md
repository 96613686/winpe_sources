# System.Web.Resources.AtlasWeb::get_ApplicationServiceManager_Path

- ea: `0x280d0`
- end: `0x280e5`
- name: `System.Web.Resources.AtlasWeb::get_ApplicationServiceManager_Path`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x28080`

## string_xrefs

- `0x280d5`: `ApplicationServiceManager_Path`

## pseudocode

```c

```

## disassembly

```asm
0x280d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x280d5  ldstr    aApplicationser// "ApplicationServiceManager_Path"
0x280da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x280df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x280e4  ret
```
