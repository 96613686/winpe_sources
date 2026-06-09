# System.Xml.Xsl.Xslt.XsltLoader::XslElement

- ea: `0x24500`
- end: `0x245bd`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslElement`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x23380`

## callees

- `0x1e190`
- `0x20590`
- `0x206f0`
- `0x20800`
- `0x23370`
- `0x24500`
- `0x24950`
- `0x24eb0`
- `0x25080`
- `0x25170`
- `0x25200`
- `0x25270`
- `0x252a0`
- `0x254e0`
- `0x255c0`
- `0x255f0`

## string_xrefs

- `0x24529`: `http://www.w3.org/2000/xmlns/`
- `0x2455b`: `xsl:copy[@inherit-namespaces = 'no']`

## pseudocode

```c

```

## disassembly

```asm
0x24500  ldarg.0
0x24501  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24506  ldarg.0
0x24507  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::elementAttributes
0x2450c  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x24511  stloc.0
0x24512  ldarg.0
0x24513  ldc.i4.0
0x24514  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseNCNameAttribute(int32 attNum)
0x24519  stloc.1
0x2451a  ldarg.0
0x2451b  ldc.i4.1
0x2451c  ldstr    aNamespace// "namespace"
0x24521  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x24526  stloc.2
0x24527  ldarg.0
0x24528  ldloc.2
0x24529  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x2452e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24533  ldstr    aXsltReservedns// "Xslt_ReservedNS"
0x24538  ldc.i4.1
0x24539  newarr   [mscorlib]System.String
0x2453e  dup
0x2453f  ldc.i4.0
0x24540  ldloc.2
0x24541  stelem.ref
0x24542  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x24547  ldarg.0
0x24548  ldc.i4.2
0x24549  ldstr    aInheritNamespa// "inherit-namespaces"
0x2454e  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x24553  ldc.i4.0
0x24554  cgt.un
0x24556  stloc.3
0x24557  ldloc.3
0x24558  brtrue.s loc_24565
0x2455a  ldarg.0
0x2455b  ldstr    aXslCopyInherit// "xsl:copy[@inherit-namespaces = 'no']"
0x24560  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24565  ldarg.0
0x24566  ldc.i4.4
0x24567  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseTypeAttribute(int32 attNum)
0x2456c  ldarg.0
0x2456d  ldc.i4.5
0x2456e  ldc.i4.0
0x2456f  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseValidationAttribute(int32 attNum, bool defVal)
0x24574  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::.ctor()
0x24579  stloc.s  4
0x2457b  ldarg.0
0x2457c  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24581  ldc.i4.3
0x24582  ldstr    aUseAttributeSe// "use-attribute-sets"
0x24587  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x2458c  brfalse.s loc_24596
0x2458e  ldarg.0
0x2458f  ldloc.s  4
0x24591  call     instance void System.Xml.Xsl.Xslt.XsltLoader::AddUseAttributeSets(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> list)
0x24596  ldloc.1
0x24597  ldloc.2
0x24598  ldarg.0
0x24599  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2459e  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x245a3  call     class System.Xml.Xsl.Xslt.NodeCtor System.Xml.Xsl.Xslt.AstFactory::Element(string nameAvt, string nsAvt, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x245a8  ldarg.0
0x245a9  ldarg.0
0x245aa  ldloc.s  4
0x245ac  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x245b1  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadEndTag(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x245b6  ldloc.0
0x245b7  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x245bc  ret
```
