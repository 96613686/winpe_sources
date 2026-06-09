# System.Web.Resources.AtlasWeb::get_ExpressionParser_OpenParenExpected

- ea: `0x28b10`
- end: `0x28b25`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_OpenParenExpected`
- size: `21`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0xd260`
- `0xd530`
- `0xdbd0`
- `0xdc50`

## callees

- `0x28080`

## string_xrefs

- `0x28b15`: `ExpressionParser_OpenParenExpected`

## pseudocode

```c

```

## disassembly

```asm
0x28b10  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28b15  ldstr    aExpressionpars_35// "ExpressionParser_OpenParenExpected"
0x28b1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28b1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28b24  ret
```
