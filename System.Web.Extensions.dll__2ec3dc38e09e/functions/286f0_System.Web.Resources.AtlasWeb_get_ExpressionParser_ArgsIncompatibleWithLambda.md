# System.Web.Resources.AtlasWeb::get_ExpressionParser_ArgsIncompatibleWithLambda

- ea: `0x286f0`
- end: `0x28705`
- name: `System.Web.Resources.AtlasWeb::get_ExpressionParser_ArgsIncompatibleWithLambda`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd660`

## callees

- `0x28080`

## string_xrefs

- `0x286f5`: `ExpressionParser_ArgsIncompatibleWithLambda`

## pseudocode

```c

```

## disassembly

```asm
0x286f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x286f5  ldstr    aExpressionpars_2// "ExpressionParser_ArgsIncompatibleWithLa"...
0x286fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x286ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28704  ret
```
