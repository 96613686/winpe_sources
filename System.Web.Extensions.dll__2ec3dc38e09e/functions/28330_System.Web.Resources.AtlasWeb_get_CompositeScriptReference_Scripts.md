# System.Web.Resources.AtlasWeb::get_CompositeScriptReference_Scripts

- ea: `0x28330`
- end: `0x28345`
- name: `System.Web.Resources.AtlasWeb::get_CompositeScriptReference_Scripts`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x28335`: `CompositeScriptReference_Scripts`

## pseudocode

```c

```

## disassembly

```asm
0x28330  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28335  ldstr    aCompositescrip_0// "CompositeScriptReference_Scripts"
0x2833a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2833f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28344  ret
```
