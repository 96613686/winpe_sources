# System.Web.Resources.AtlasWeb::get_ExtenderControl_TargetControlDifferentUpdatePanel

- ea: `0x28c10`
- end: `0x28c25`
- name: `System.Web.Resources.AtlasWeb::get_ExtenderControl_TargetControlDifferentUpdatePanel`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10450`

## callees

- `0x28080`

## string_xrefs

- `0x28c15`: `ExtenderControl_TargetControlDifferentUpdatePanel`

## pseudocode

```c

```

## disassembly

```asm
0x28c10  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28c15  ldstr    aExtendercontro_0// "ExtenderControl_TargetControlDifferentU"...
0x28c1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28c1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28c24  ret
```
