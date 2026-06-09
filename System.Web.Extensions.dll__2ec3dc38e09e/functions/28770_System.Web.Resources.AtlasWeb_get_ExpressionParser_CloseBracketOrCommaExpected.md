# System.Web.Resources.AtlasWeb::get_ExpressionParser_CloseBracketOrCommaExpected

- ea: `0x28770`
- end: `0x28785`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_CloseBracketOrCommaExpected`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdc50`

## callees

- `0x28080`

## string_xrefs

- `0x28775`: `ExpressionParser_CloseBracketOrCommaExpected`

## pseudocode

```c

```

## disassembly

```asm
0x28770  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28775  ldstr    aExpressionpars_6// "ExpressionParser_CloseBracketOrCommaExp"...
0x2877a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2877f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28784  ret
```
