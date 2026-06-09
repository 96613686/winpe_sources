# System.Windows.CoreCompatibilityPreferences::SetIncludeAllInkInBoundingBoxFromAppSettings

- ea: `0x18700`
- end: `0x1871d`
- name: `System.Windows.CoreCompatibilityPreferences::SetIncludeAllInkInBoundingBoxFromAppSettings`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x185d0`

## callees

- `0x186a0`
- `0x18700`

## string_xrefs

- `0x18701`: `IncludeAllInkInBoundingBox`

## pseudocode

```c

```

## disassembly

```asm
0x18700  ldarg.0
0x18701  ldstr    aIncludeallinki// "IncludeAllInkInBoundingBox"
0x18706  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1870b  stloc.1
0x1870c  ldloc.1
0x1870d  ldloca.s 0
0x1870f  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x18714  brfalse.s loc_1871C
0x18716  ldloc.0
0x18717  call     void System.Windows.CoreCompatibilityPreferences::set_IncludeAllInkInBoundingBox(bool value)
0x1871c  ret
```
