# System.Web.Resources.AtlasWeb::get_AppService_MultiplePaths

- ea: `0x28110`
- end: `0x28125`
- name: `System.Web.Resources.AtlasWeb::get_AppService_MultiplePaths`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xf270`

## callees

- `0x28080`

## string_xrefs

- `0x28115`: `AppService_MultiplePaths`

## pseudocode

```c

```

## disassembly

```asm
0x28110  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28115  ldstr    aAppserviceMult// "AppService_MultiplePaths"
0x2811a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2811f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28124  ret
```
