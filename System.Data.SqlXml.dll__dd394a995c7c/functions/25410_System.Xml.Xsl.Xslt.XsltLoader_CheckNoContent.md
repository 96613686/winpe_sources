# System.Xml.Xsl.Xslt.XsltLoader::CheckNoContent

- ea: `0x25410`
- end: `0x25452`
- name: `System.Xml.Xsl.Xslt.XsltLoader::CheckNoContent`
- size: `66`
- prototype: ``
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x21c10`
- `0x21ca0`
- `0x21d30`
- `0x21d90`
- `0x21df0`
- `0x22530`
- `0x22670`
- `0x229b0`
- `0x23220`
- `0x23300`
- `0x23b20`
- `0x23e80`
- `0x24010`
- `0x24690`

## callees

- `0x13be0`
- `0x20540`
- `0x205f0`
- `0x25410`
- `0x25460`
- `0x56c00`

## string_xrefs

- `0x25438`: `Xslt_NotEmptyContents`

## pseudocode

```c

```

## disassembly

```asm
0x25410  ldarg.0
0x25411  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x25416  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::MoveToElement()
0x2541b  ldarg.0
0x2541c  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x25421  callvirt instance valuetype DelayedQName System.Xml.Xsl.Xslt.XsltInput::get_ElementName()
0x25426  stloc.0
0x25427  ldarg.0
0x25428  call     instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XsltLoader::SkipEmptyContent()
0x2542d  stloc.1
0x2542e  ldloc.1
0x2542f  brfalse.s loc_25451
0x25431  ldarg.0
0x25432  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x25437  ldloc.1
0x25438  ldstr    aXsltNotemptyco// "Xslt_NotEmptyContents"
0x2543d  ldc.i4.1
0x2543e  newarr   [mscorlib]System.String
0x25443  dup
0x25444  ldc.i4.0
0x25445  ldloc.0
0x25446  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x2544b  stelem.ref
0x2544c  callvirt instance void System.Xml.Xsl.Xslt.Compiler::ReportError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x25451  ret
```
