# System.Web.Resources.AtlasWeb::get_ExpressionParser_CloseParenOrCommaExpected

- ea: `0x28790`
- end: `0x287a5`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_CloseParenOrCommaExpected`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd530`
- `0xdbd0`

## callees

- `0x28080`

## string_xrefs

- `0x28795`: `ExpressionParser_CloseParenOrCommaExpected`

## pseudocode

```c

```

## disassembly

```asm
0x28790  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28795  ldstr    aExpressionpars_7// "ExpressionParser_CloseParenOrCommaExpec"...
0x2879a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2879f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x287a4  ret
```
