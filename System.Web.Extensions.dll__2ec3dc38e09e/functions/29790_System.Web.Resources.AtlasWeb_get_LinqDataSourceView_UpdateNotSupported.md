# System.Web.Resources.AtlasWeb::get_LinqDataSourceView_UpdateNotSupported

- ea: `0x29790`
- end: `0x297a5`
- name: `System.Web.Resources.AtlasWeb::get_LinqDataSourceView_UpdateNotSupported`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1e240`

## callees

- `0x28080`

## string_xrefs

- `0x29795`: `LinqDataSourceView_UpdateNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x29790  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29795  ldstr    aLinqdatasource_61// "LinqDataSourceView_UpdateNotSupported"
0x2979a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2979f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x297a4  ret
```
