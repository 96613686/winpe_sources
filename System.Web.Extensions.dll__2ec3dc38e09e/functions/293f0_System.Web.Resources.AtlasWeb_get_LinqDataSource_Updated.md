# System.Web.Resources.AtlasWeb::get_LinqDataSource_Updated

- ea: `0x293f0`
- end: `0x29405`
- name: `System.Web.Resources.AtlasWeb::get_LinqDataSource_Updated`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x28080`

## string_xrefs

- `0x293f5`: `LinqDataSource_Updated`

## pseudocode

```c

```

## disassembly

```asm
0x293f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x293f5  ldstr    aLinqdatasource_32// "LinqDataSource_Updated"
0x293fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x293ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29404  ret
```
