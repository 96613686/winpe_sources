# System.Web.Resources.AtlasWeb::get_ExpressionParser_IncompatibleOperands

- ea: `0x28910`
- end: `0x28925`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_IncompatibleOperands`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdf30`

## callees

- `0x28080`

## string_xrefs

- `0x28915`: `ExpressionParser_IncompatibleOperands`

## pseudocode

```c

```

## disassembly

```asm
0x28910  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28915  ldstr    aExpressionpars_19// "ExpressionParser_IncompatibleOperands"
0x2891a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2891f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28924  ret
```
