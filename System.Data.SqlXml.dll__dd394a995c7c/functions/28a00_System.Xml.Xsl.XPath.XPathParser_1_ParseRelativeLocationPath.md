# System.Xml.Xsl.XPath.XPathParser`1::ParseRelativeLocationPath

- ea: `0x28a00`
- end: `0x28ac4`
- name: `System.Xml.Xsl.XPath.XPathParser`1::ParseRelativeLocationPath`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28a00`
- `0x29ea0`
- `0x2a000`
- `0x2a890`

## string_xrefs

- `0x28a25`: `Xslt_InputTooComplex`

## pseudocode

```c

```

## disassembly

```asm
0x28a00  ldarg.0
0x28a01  ldarg.0
0x28a02  ldfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseRelativePath
0x28a07  ldc.i4.1
0x28a08  add
0x28a09  stloc.1
0x28a0a  ldloc.1
0x28a0b  stfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseRelativePath
0x28a10  ldloc.1
0x28a11  ldc.i4   0x400
0x28a16  ble.s    loc_28A36
0x28a18  call     bool [System.Xml]System.Xml.XmlConfiguration.XsltConfigSection::get_LimitXPathComplexity()
0x28a1d  brfalse.s loc_28A36
0x28a1f  ldarg.0
0x28a20  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28a25  ldstr    aXsltInputtooco// "Xslt_InputTooComplex"
0x28a2a  ldc.i4.0
0x28a2b  newarr   [mscorlib]System.String
0x28a30  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28a35  throw
0x28a36  ldarg.0
0x28a37  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseStep()
0x28a3c  stloc.0
0x28a3d  ldarg.0
0x28a3e  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28a43  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28a48  ldc.i4.s 0x2F
0x28a4a  bne.un.s loc_28A6C
0x28a4c  ldarg.0
0x28a4d  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28a52  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28a57  ldarg.0
0x28a58  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28a5d  ldloc.0
0x28a5e  ldarg.0
0x28a5f  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseRelativeLocationPath()
0x28a64  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::JoinStep(!!T0, var<u1>)
0x28a69  stloc.0
0x28a6a  br.s     loc_28AB4
0x28a6c  ldarg.0
0x28a6d  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28a72  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28a77  ldc.i4.s 0x12
0x28a79  bne.un.s loc_28AB4
0x28a7b  ldarg.0
0x28a7c  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28a81  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28a86  ldarg.0
0x28a87  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28a8c  ldloc.0
0x28a8d  ldarg.0
0x28a8e  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28a93  ldarg.0
0x28a94  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28a99  ldc.i4.6
0x28a9a  ldc.i4.s 9
0x28a9c  ldnull
0x28a9d  ldnull
0x28a9e  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Axis(!!T0, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, string)
0x28aa3  ldarg.0
0x28aa4  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseRelativeLocationPath()
0x28aa9  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::JoinStep(!!T0, var<u1>)
0x28aae  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::JoinStep(!!T0, var<u1>)
0x28ab3  stloc.0
0x28ab4  ldarg.0
0x28ab5  ldarg.0
0x28ab6  ldfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseRelativePath
0x28abb  ldc.i4.1
0x28abc  sub
0x28abd  stfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseRelativePath
0x28ac2  ldloc.0
0x28ac3  ret
```
