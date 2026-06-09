# System.Xml.Xsl.Xslt.XsltLoader::XslAttribute

- ea: `0x245c0`
- end: `0x2468a`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslAttribute`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x22b10`
- `0x23380`

## callees

- `0x1e120`
- `0x206f0`
- `0x20800`
- `0x24380`
- `0x245c0`
- `0x24eb0`
- `0x25170`
- `0x25270`
- `0x252a0`
- `0x254e0`
- `0x255c0`
- `0x255f0`

## string_xrefs

- `0x245e9`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x245c0  ldarg.0
0x245c1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x245c6  ldarg.0
0x245c7  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::attributeAttributes
0x245cc  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x245d1  stloc.0
0x245d2  ldarg.0
0x245d3  ldc.i4.0
0x245d4  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseNCNameAttribute(int32 attNum)
0x245d9  stloc.1
0x245da  ldarg.0
0x245db  ldc.i4.1
0x245dc  ldstr    aNamespace// "namespace"
0x245e1  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x245e6  stloc.2
0x245e7  ldarg.0
0x245e8  ldloc.2
0x245e9  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x245ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x245f3  ldstr    aXsltReservedns// "Xslt_ReservedNS"
0x245f8  ldc.i4.1
0x245f9  newarr   [mscorlib]System.String
0x245fe  dup
0x245ff  ldc.i4.0
0x24600  ldloc.2
0x24601  stelem.ref
0x24602  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x24607  ldarg.0
0x24608  ldc.i4.2
0x24609  ldstr    aSelect// "select"
0x2460e  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x24613  stloc.3
0x24614  ldloc.3
0x24615  brfalse.s loc_24622
0x24617  ldarg.0
0x24618  ldstr    aXslAttributeSe_0// "xsl:attribute/@select"
0x2461d  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24622  ldarg.0
0x24623  ldc.i4.3
0x24624  ldstr    aSeparator// "separator"
0x24629  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x2462e  stloc.s  4
0x24630  ldloc.s  4
0x24632  brfalse.s loc_2463F
0x24634  ldarg.0
0x24635  ldstr    aXslAttributeSe_1// "xsl:attribute/@separator"
0x2463a  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x2463f  ldloc.s  4
0x24641  brtrue.s loc_24654
0x24643  ldloc.3
0x24644  brtrue.s loc_2464D
0x24646  ldsfld   string [mscorlib]System.String::Empty
0x2464b  br.s     loc_24656
0x2464d  ldstr    asc_58940// " "
0x24652  br.s     loc_24656
0x24654  ldloc.s  4
0x24656  stloc.s  4
0x24658  ldarg.0
0x24659  ldc.i4.4
0x2465a  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseTypeAttribute(int32 attNum)
0x2465f  ldarg.0
0x24660  ldc.i4.5
0x24661  ldc.i4.0
0x24662  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseValidationAttribute(int32 attNum, bool defVal)
0x24667  ldloc.1
0x24668  ldloc.2
0x24669  ldarg.0
0x2466a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2466f  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x24674  call     class System.Xml.Xsl.Xslt.NodeCtor System.Xml.Xsl.Xslt.AstFactory::Attribute(string nameAvt, string nsAvt, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x24679  ldarg.0
0x2467a  ldloc.3
0x2467b  ldnull
0x2467c  cgt.un
0x2467e  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadContent(bool hasSelect)
0x24683  ldloc.0
0x24684  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x24689  ret
```
