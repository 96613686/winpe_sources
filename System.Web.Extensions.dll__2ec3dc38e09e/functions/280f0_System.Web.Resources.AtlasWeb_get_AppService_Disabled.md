# System.Web.Resources.AtlasWeb::get_AppService_Disabled

- ea: `0x280f0`
- end: `0x28105`
- name: `System.Web.Resources.AtlasWeb::get_AppService_Disabled`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x39200`
- `0x392f0`
- `0x39320`

## callees

- `0x28080`

## string_xrefs

- `0x280f5`: `AppService_Disabled`

## pseudocode

```c

```

## disassembly

```asm
0x280f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x280f5  ldstr    aAppserviceDisa// "AppService_Disabled"
0x280fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x280ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28104  ret
```
