# System.Web.Resources.AtlasWeb::get_LinqDataSource_EnableUpdate

- ea: `0x291d0`
- end: `0x291e5`
- name: `System.Web.Resources.AtlasWeb::get_LinqDataSource_EnableUpdate`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x28080`

## string_xrefs

- `0x291d5`: `LinqDataSource_EnableUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x291d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x291d5  ldstr    aLinqdatasource_15// "LinqDataSource_EnableUpdate"
0x291da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x291df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x291e4  ret
```
