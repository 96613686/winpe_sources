# System.Web.Resources.AtlasWeb::get_ExpressionParser_IncompatibleOperand

- ea: `0x288f0`
- end: `0x28905`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_IncompatibleOperand`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdea0`

## callees

- `0x28080`

## string_xrefs

- `0x288f5`: `ExpressionParser_IncompatibleOperand`

## pseudocode

```c

```

## disassembly

```asm
0x288f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x288f5  ldstr    aExpressionpars_18// "ExpressionParser_IncompatibleOperand"
0x288fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x288ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28904  ret
```
