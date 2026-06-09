# System.Web.Resources.AtlasWeb::get_ProfileServiceManager_LoadProperitesWithNonDefaultPath

- ea: `0x2a6d0`
- end: `0x2a6e5`
- name: `System.Web.Resources.AtlasWeb::get_ProfileServiceManager_LoadProperitesWithNonDefaultPath`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x12170`

## callees

- `0x28080`

## string_xrefs

- `0x2a6d5`: `ProfileServiceManager_LoadProperitesWithNonDefaultPath`

## pseudocode

```c

```

## disassembly

```asm
0x2a6d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2a6d5  ldstr    aProfileservice// "ProfileServiceManager_LoadProperitesWit"...
0x2a6da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2a6df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2a6e4  ret
```
