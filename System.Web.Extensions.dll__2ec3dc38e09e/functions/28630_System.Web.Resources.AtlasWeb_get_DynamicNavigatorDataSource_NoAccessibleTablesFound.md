# System.Web.Resources.AtlasWeb::get_DynamicNavigatorDataSource_NoAccessibleTablesFound

- ea: `0x28630`
- end: `0x28645`
- name: `System.Web.Resources.AtlasWeb::get_DynamicNavigatorDataSource_NoAccessibleTablesFound`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x28635`: `DynamicNavigatorDataSource_NoAccessibleTablesFound`

## pseudocode

```c

```

## disassembly

```asm
0x28630  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28635  ldstr    aDynamicnavigat// "DynamicNavigatorDataSource_NoAccessible"...
0x2863a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2863f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28644  ret
```
