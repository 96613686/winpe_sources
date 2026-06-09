# System.Web.Resources.AtlasWeb::get_LinqDataSource_UpdateParameters

- ea: `0x29410`
- end: `0x29425`
- name: `System.Web.Resources.AtlasWeb::get_LinqDataSource_UpdateParameters`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x28080`

## string_xrefs

- `0x29415`: `LinqDataSource_UpdateParameters`

## pseudocode

```c

```

## disassembly

```asm
0x29410  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29415  ldstr    aLinqdatasource_33// "LinqDataSource_UpdateParameters"
0x2941a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2941f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29424  ret
```
