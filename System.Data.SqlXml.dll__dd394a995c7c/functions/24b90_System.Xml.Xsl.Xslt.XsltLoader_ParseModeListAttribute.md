# System.Xml.Xsl.Xslt.XsltLoader::ParseModeListAttribute

- ea: `0x24b90`
- end: `0x24d42`
- name: `System.Xml.Xsl.Xslt.XsltLoader::ParseModeListAttribute`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x22ce0`

## callees

- `0x13b60`
- `0x13b70`
- `0x1f920`
- `0x20590`
- `0x206d0`
- `0x24b90`
- `0x24ee0`
- `0x25580`
- `0x255c0`

## string_xrefs

- `0x24c3e`: `xsl:apply-templates[@mode='#current']`
- `0x24bc3`: `xsl:template[@mode='#all']`
- `0x24bf3`: `Xslt_ModeListEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x24b90  ldarg.0
0x24b91  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24b96  ldarg.1
0x24b97  ldstr    aMode// "mode"
0x24b9c  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x24ba1  brtrue.s loc_24BA9
0x24ba3  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24ba8  ret
0x24ba9  ldarg.0
0x24baa  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24baf  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x24bb4  stloc.0
0x24bb5  ldloc.0
0x24bb6  ldstr    aAll// "#all"
0x24bbb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24bc0  brfalse.s loc_24BD3
0x24bc2  ldarg.0
0x24bc3  ldstr    aXslTemplateMod// "xsl:template[@mode='#all']"
0x24bc8  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24bcd  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24bd2  ret
0x24bd3  ldloc.0
0x24bd4  call     string[] [System.Xml]System.Xml.XmlConvert::SplitString(string)
0x24bd9  stloc.1
0x24bda  ldloc.1
0x24bdb  ldlen
0x24bdc  conv.i4
0x24bdd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::.ctor(int32)
0x24be2  stloc.2
0x24be3  ldarg.0
0x24be4  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x24be9  callvirt instance void System.Xml.Xsl.Xslt.Compiler::EnterForwardsCompatible()
0x24bee  ldloc.1
0x24bef  ldlen
0x24bf0  brtrue.s loc_24C08
0x24bf2  ldarg.0
0x24bf3  ldstr    aXsltModelistem// "Xslt_ModeListEmpty"
0x24bf8  ldc.i4.0
0x24bf9  newarr   [mscorlib]System.String
0x24bfe  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x24c03  br       loc_24CE9
0x24c08  ldloc.1
0x24c09  stloc.3
0x24c0a  ldc.i4.0
0x24c0b  stloc.s  4
0x24c0d  br       loc_24CDF
0x24c12  ldloc.3
0x24c13  ldloc.s  4
0x24c15  ldelem.ref
0x24c16  stloc.s  5
0x24c18  ldloc.s  5
0x24c1a  ldstr    aDefault// "#default"
0x24c1f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c24  brfalse.s loc_24C2F
0x24c26  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24c2b  stloc.s  6
0x24c2d  br.s     loc_24C78
0x24c2f  ldloc.s  5
0x24c31  ldstr    aCurrent_0// "#current"
0x24c36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c3b  brfalse.s loc_24C4D
0x24c3d  ldarg.0
0x24c3e  ldstr    aXslApplyTempla_0// "xsl:apply-templates[@mode='#current']"
0x24c43  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24c48  br       loc_24CE9
0x24c4d  ldloc.s  5
0x24c4f  ldstr    aAll// "#all"
0x24c54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c59  brfalse.s loc_24C6E
0x24c5b  ldarg.0
0x24c5c  ldstr    aXsltModelistal// "Xslt_ModeListAll"
0x24c61  ldc.i4.0
0x24c62  newarr   [mscorlib]System.String
0x24c67  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x24c6c  br.s     loc_24CE9
0x24c6e  ldarg.0
0x24c6f  ldloc.s  5
0x24c71  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::CreateXPathQName(string qname)
0x24c76  stloc.s  6
0x24c78  ldc.i4.0
0x24c79  stloc.s  7
0x24c7b  ldloc.2
0x24c7c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::GetEnumerator()
0x24c81  stloc.s  8
0x24c83  br.s     loc_24C9C
0x24c85  ldloca.s 8
0x24c87  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilName>::get_Current()
0x24c8c  stloc.s  9
0x24c8e  ldloc.s  7
0x24c90  ldloc.s  9
0x24c92  ldloc.s  6
0x24c94  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x24c99  or
0x24c9a  stloc.s  7
0x24c9c  ldloca.s 8
0x24c9e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilName>::MoveNext()
0x24ca3  brtrue.s loc_24C85
0x24ca5  leave.s  loc_24CB5
0x24ca7  ldloca.s 8
0x24ca9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilName>
0x24caf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24cb4  endfinally
0x24cb5  ldloc.s  7
0x24cb7  brfalse.s loc_24CD1
0x24cb9  ldarg.0
0x24cba  ldstr    aXsltModelistdu// "Xslt_ModeListDup"
0x24cbf  ldc.i4.1
0x24cc0  newarr   [mscorlib]System.String
0x24cc5  dup
0x24cc6  ldc.i4.0
0x24cc7  ldloc.s  5
0x24cc9  stelem.ref
0x24cca  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x24ccf  br.s     loc_24CD9
0x24cd1  ldloc.2
0x24cd2  ldloc.s  6
0x24cd4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::Add(var<u1>)
0x24cd9  ldloc.s  4
0x24cdb  ldc.i4.1
0x24cdc  add
0x24cdd  stloc.s  4
0x24cdf  ldloc.s  4
0x24ce1  ldloc.3
0x24ce2  ldlen
0x24ce3  conv.i4
0x24ce4  blt      loc_24C12
0x24ce9  ldarg.0
0x24cea  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x24cef  ldarg.0
0x24cf0  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24cf5  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x24cfa  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ExitForwardsCompatible(bool fwdCompat)
0x24cff  brtrue.s loc_24D12
0x24d01  ldloc.2
0x24d02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::Clear()
0x24d07  ldloc.2
0x24d08  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24d0d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::Add(var<u1>)
0x24d12  ldc.i4.1
0x24d13  ldloc.2
0x24d14  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::get_Count()
0x24d19  bge.s    loc_24D2C
0x24d1b  ldarg.0
0x24d1c  ldstr    aMultipeModes// "Multipe modes"
0x24d21  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24d26  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24d2b  ret
0x24d2c  ldloc.2
0x24d2d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::get_Count()
0x24d32  brtrue.s loc_24D3A
0x24d34  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24d39  ret
0x24d3a  ldloc.2
0x24d3b  ldc.i4.0
0x24d3c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilName>::get_Item(!!T0)
0x24d41  ret
```
