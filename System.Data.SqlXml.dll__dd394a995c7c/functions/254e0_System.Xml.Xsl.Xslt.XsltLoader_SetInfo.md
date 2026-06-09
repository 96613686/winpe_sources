# System.Xml.Xsl.Xslt.XsltLoader::SetInfo

- ea: `0x254e0`
- end: `0x25502`
- name: `System.Xml.Xsl.Xslt.XsltLoader::SetInfo`
- size: `34`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1f5b0`
- `0x22530`
- `0x22b10`
- `0x22ce0`
- `0x238d0`
- `0x239e0`
- `0x23a40`
- `0x23a80`
- `0x23b20`
- `0x23bb0`
- `0x23bf0`
- `0x23d90`
- `0x23db0`
- `0x23e10`
- `0x23e80`
- `0x24010`
- `0x24140`
- `0x24330`
- `0x243d0`
- `0x24430`
- `0x24500`
- `0x245c0`
- `0x24690`
- `0x24780`
- `0x24990`
- `0x24a10`

## callees

- `0x254b0`
- `0x254c0`

## pseudocode

```c

```

## disassembly

```asm
0x254e0  ldarg.0
0x254e1  ldarg.2
0x254e2  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x254e7  stfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x254ec  ldarg.0
0x254ed  ldarg.1
0x254ee  call     void System.Xml.Xsl.Xslt.XsltLoader::SetContent(class System.Xml.Xsl.Xslt.XslNode node, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x254f3  ldarg.0
0x254f4  ldarg.2
0x254f5  ldfld    class System.Xml.Xsl.ISourceLineInfo ContextInfo::lineInfo
0x254fa  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetLineInfo(class System.Xml.Xsl.Xslt.XslNode node, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x254ff  pop
0x25500  ldarg.0
0x25501  ret
```
