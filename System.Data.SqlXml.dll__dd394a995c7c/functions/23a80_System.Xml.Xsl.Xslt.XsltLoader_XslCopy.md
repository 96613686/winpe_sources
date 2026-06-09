# System.Xml.Xsl.Xslt.XsltLoader::XslCopy

- ea: `0x23a80`
- end: `0x23b16`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslCopy`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x23380`

## callees

- `0x1e170`
- `0x20590`
- `0x20800`
- `0x23370`
- `0x23a80`
- `0x24950`
- `0x25080`
- `0x25200`
- `0x25270`
- `0x252a0`
- `0x254e0`
- `0x255c0`

## string_xrefs

- `0x23a94`: `copy-namespaces`
- `0x23ab6`: `xsl:copy[@copy-namespaces    = 'no']`
- `0x23ac4`: `xsl:copy[@inherit-namespaces = 'no']`

## pseudocode

```c

```

## disassembly

```asm
0x23a80  ldarg.0
0x23a81  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23a86  ldarg.0
0x23a87  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::copyAttributes
0x23a8c  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x23a91  stloc.0
0x23a92  ldarg.0
0x23a93  ldc.i4.0
0x23a94  ldstr    aCopyNamespaces// "copy-namespaces"
0x23a99  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x23a9e  ldc.i4.0
0x23a9f  cgt.un
0x23aa1  stloc.1
0x23aa2  ldarg.0
0x23aa3  ldc.i4.1
0x23aa4  ldstr    aInheritNamespa// "inherit-namespaces"
0x23aa9  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x23aae  ldc.i4.0
0x23aaf  cgt.un
0x23ab1  stloc.2
0x23ab2  ldloc.1
0x23ab3  brtrue.s loc_23AC0
0x23ab5  ldarg.0
0x23ab6  ldstr    aXslCopyCopyNam// "xsl:copy[@copy-namespaces    = 'no']"
0x23abb  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x23ac0  ldloc.2
0x23ac1  brtrue.s loc_23ACE
0x23ac3  ldarg.0
0x23ac4  ldstr    aXslCopyInherit// "xsl:copy[@inherit-namespaces = 'no']"
0x23ac9  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x23ace  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::.ctor()
0x23ad3  stloc.3
0x23ad4  ldarg.0
0x23ad5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23ada  ldc.i4.2
0x23adb  ldstr    aUseAttributeSe// "use-attribute-sets"
0x23ae0  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x23ae5  brfalse.s loc_23AEE
0x23ae7  ldarg.0
0x23ae8  ldloc.3
0x23ae9  call     instance void System.Xml.Xsl.Xslt.XsltLoader::AddUseAttributeSets(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> list)
0x23aee  ldarg.0
0x23aef  ldc.i4.3
0x23af0  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseTypeAttribute(int32 attNum)
0x23af5  ldarg.0
0x23af6  ldc.i4.4
0x23af7  ldc.i4.0
0x23af8  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseValidationAttribute(int32 attNum, bool defVal)
0x23afd  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::Copy()
0x23b02  ldarg.0
0x23b03  ldarg.0
0x23b04  ldloc.3
0x23b05  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x23b0a  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadEndTag(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x23b0f  ldloc.0
0x23b10  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x23b15  ret
```
