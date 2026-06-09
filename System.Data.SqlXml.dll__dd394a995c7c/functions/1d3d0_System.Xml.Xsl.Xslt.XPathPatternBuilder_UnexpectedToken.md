# System.Xml.Xsl.Xslt.XPathPatternBuilder::UnexpectedToken

- ea: `0x1d3d0`
- end: `0x1d3f1`
- name: `System.Xml.Xsl.Xslt.XPathPatternBuilder::UnexpectedToken`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1d3b0`
- `0x1d3c0`

## string_xrefs

- `0x1d3d5`: `Internal Error: {0} is not allowed in XSLT pattern outside of predicate.`

## pseudocode

```c

```

## disassembly

```asm
0x1d3d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d3d5  ldstr    aInternalError0// "Internal Error: {0} is not allowed in X"...
0x1d3da  ldc.i4.1
0x1d3db  newarr   [mscorlib]System.Object
0x1d3e0  dup
0x1d3e1  ldc.i4.0
0x1d3e2  ldarg.1
0x1d3e3  stelem.ref
0x1d3e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1d3e9  stloc.0
0x1d3ea  ldloc.0
0x1d3eb  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1d3f0  throw
```
