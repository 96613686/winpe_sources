# System.Xml.Xsl.Xslt.XsltLoader::ParseModeAttribute

- ea: `0x24ac0`
- end: `0x24b8b`
- name: `System.Xml.Xsl.Xslt.XsltLoader::ParseModeAttribute`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x22ce0`
- `0x239e0`

## callees

- `0x13b60`
- `0x13b70`
- `0x1f920`
- `0x20590`
- `0x206d0`
- `0x214e0`
- `0x24ac0`
- `0x24ee0`
- `0x25580`
- `0x255c0`

## string_xrefs

- `0x24b23`: `xsl:apply-templates[@mode='#current']`

## pseudocode

```c

```

## disassembly

```asm
0x24ac0  ldarg.0
0x24ac1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24ac6  ldarg.1
0x24ac7  ldstr    aMode// "mode"
0x24acc  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x24ad1  brtrue.s loc_24AD9
0x24ad3  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24ad8  ret
0x24ad9  ldarg.0
0x24ada  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x24adf  callvirt instance void System.Xml.Xsl.Xslt.Compiler::EnterForwardsCompatible()
0x24ae4  ldarg.0
0x24ae5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24aea  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x24aef  stloc.0
0x24af0  ldarg.0
0x24af1  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x24af6  brtrue.s loc_24B0D
0x24af8  ldloc.0
0x24af9  ldstr    aDefault// "#default"
0x24afe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24b03  brfalse.s loc_24B0D
0x24b05  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24b0a  stloc.1
0x24b0b  br.s     loc_24B6B
0x24b0d  ldarg.0
0x24b0e  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x24b13  brtrue.s loc_24B35
0x24b15  ldloc.0
0x24b16  ldstr    aCurrent_0// "#current"
0x24b1b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24b20  brfalse.s loc_24B35
0x24b22  ldarg.0
0x24b23  ldstr    aXslApplyTempla_0// "xsl:apply-templates[@mode='#current']"
0x24b28  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24b2d  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24b32  stloc.1
0x24b33  br.s     loc_24B6B
0x24b35  ldarg.0
0x24b36  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x24b3b  brtrue.s loc_24B63
0x24b3d  ldloc.0
0x24b3e  ldstr    aAll// "#all"
0x24b43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24b48  brfalse.s loc_24B63
0x24b4a  ldarg.0
0x24b4b  ldstr    aXsltModelistal// "Xslt_ModeListAll"
0x24b50  ldc.i4.0
0x24b51  newarr   [mscorlib]System.String
0x24b56  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x24b5b  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24b60  stloc.1
0x24b61  br.s     loc_24B6B
0x24b63  ldarg.0
0x24b64  ldloc.0
0x24b65  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::CreateXPathQName(string qname)
0x24b6a  stloc.1
0x24b6b  ldarg.0
0x24b6c  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x24b71  ldarg.0
0x24b72  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24b77  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x24b7c  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ExitForwardsCompatible(bool fwdCompat)
0x24b81  brtrue.s loc_24B89
0x24b83  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x24b88  stloc.1
0x24b89  ldloc.1
0x24b8a  ret
```
