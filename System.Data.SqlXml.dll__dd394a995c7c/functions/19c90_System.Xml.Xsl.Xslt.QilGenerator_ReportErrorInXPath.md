# System.Xml.Xsl.Xslt.QilGenerator::ReportErrorInXPath

- ea: `0x19c90`
- end: `0x19ccf`
- name: `System.Xml.Xsl.Xslt.QilGenerator::ReportErrorInXPath`
- size: `63`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x19d10`
- `0x19d90`
- `0x19df0`
- `0x19e80`
- `0x19f10`
- `0x19f70`
- `0x19ff0`

## callees

- `0x3800`
- `0x13be0`
- `0x19c90`

## string_xrefs

- `0x19cba`: `Xml_UserException`

## pseudocode

```c

```

## disassembly

```asm
0x19c90  ldarg.1
0x19c91  isinst   System.Xml.Xsl.XPath.XPathCompileException
0x19c96  stloc.0
0x19c97  ldloc.0
0x19c98  brtrue.s loc_19CA2
0x19c9a  ldarg.1
0x19c9b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19ca0  br.s     loc_19CA8
0x19ca2  ldloc.0
0x19ca3  callvirt instance string System.Xml.Xsl.XslTransformException::FormatDetailedMessage()
0x19ca8  stloc.1
0x19ca9  ldarg.0
0x19caa  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x19caf  ldarg.0
0x19cb0  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.QilGenerator::lastScope
0x19cb5  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x19cba  ldstr    aXmlUserexcepti// "Xml_UserException"
0x19cbf  ldc.i4.1
0x19cc0  newarr   [mscorlib]System.String
0x19cc5  dup
0x19cc6  ldc.i4.0
0x19cc7  ldloc.1
0x19cc8  stelem.ref
0x19cc9  callvirt instance void System.Xml.Xsl.Xslt.Compiler::ReportError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x19cce  ret
```
