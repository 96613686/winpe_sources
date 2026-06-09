# System.Web.Resources.AtlasWeb::get_UpdateProgress_NoUpdatePanel

- ea: `0x2b630`
- end: `0x2b645`
- name: `System.Web.Resources.AtlasWeb::get_UpdateProgress_NoUpdatePanel`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x3b250`

## callees

- `0x28080`

## string_xrefs

- `0x2b635`: `UpdateProgress_NoUpdatePanel`

## pseudocode

```c

```

## disassembly

```asm
0x2b630  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b635  ldstr    aUpdateprogress_3// "UpdateProgress_NoUpdatePanel"
0x2b63a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b63f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b644  ret
```
