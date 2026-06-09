# System.Xml.Xsl.Xslt.Template::GetDebugName

- ea: `0x1dd40`
- end: `0x1de36`
- name: `System.Xml.Xsl.Xslt.Template::GetDebugName`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1dd40`
- `0x374b0`
- `0x37510`
- `0x375d0`

## string_xrefs

- `0x1dd47`: `<xsl:template`

## pseudocode

```c

```

## disassembly

```asm
0x1dd40  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1dd45  stloc.0
0x1dd46  ldloc.0
0x1dd47  ldstr    aXslTemplate// "<xsl:template"
0x1dd4c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dd51  pop
0x1dd52  ldarg.0
0x1dd53  ldfld    string System.Xml.Xsl.Xslt.Template::Match
0x1dd58  brfalse.s loc_1DD7C
0x1dd5a  ldloc.0
0x1dd5b  ldstr    aMatch_0// " match=\""
0x1dd60  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dd65  pop
0x1dd66  ldloc.0
0x1dd67  ldarg.0
0x1dd68  ldfld    string System.Xml.Xsl.Xslt.Template::Match
0x1dd6d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dd72  pop
0x1dd73  ldloc.0
0x1dd74  ldc.i4.s 0x22
0x1dd76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1dd7b  pop
0x1dd7c  ldarg.0
0x1dd7d  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1dd82  ldnull
0x1dd83  call     bool System.Xml.Xsl.Qil.QilName::op_Inequality(class System.Xml.Xsl.Qil.QilName a, class System.Xml.Xsl.Qil.QilName b)
0x1dd88  brfalse.s loc_1DDB1
0x1dd8a  ldloc.0
0x1dd8b  ldstr    aName_0// " name=\""
0x1dd90  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dd95  pop
0x1dd96  ldloc.0
0x1dd97  ldarg.0
0x1dd98  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1dd9d  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x1dda2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dda7  pop
0x1dda8  ldloc.0
0x1dda9  ldc.i4.s 0x22
0x1ddab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1ddb0  pop
0x1ddb1  ldarg.0
0x1ddb2  ldfld    float64 System.Xml.Xsl.Xslt.Template::Priority
0x1ddb7  call     bool [mscorlib]System.Double::IsNaN(float64)
0x1ddbc  brtrue.s loc_1DDED
0x1ddbe  ldloc.0
0x1ddbf  ldstr    aPriority_0// " priority=\""
0x1ddc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ddc9  pop
0x1ddca  ldloc.0
0x1ddcb  ldarg.0
0x1ddcc  ldfld    float64 System.Xml.Xsl.Xslt.Template::Priority
0x1ddd1  stloc.1
0x1ddd2  ldloca.s 1
0x1ddd4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ddd9  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x1ddde  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1dde3  pop
0x1dde4  ldloc.0
0x1dde5  ldc.i4.s 0x22
0x1dde7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1ddec  pop
0x1dded  ldarg.0
0x1ddee  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.Template::Mode
0x1ddf3  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x1ddf8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1ddfd  brfalse.s loc_1DE26
0x1ddff  ldloc.0
0x1de00  ldstr    aMode_0// " mode=\""
0x1de05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1de0a  pop
0x1de0b  ldloc.0
0x1de0c  ldarg.0
0x1de0d  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.Template::Mode
0x1de12  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x1de17  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1de1c  pop
0x1de1d  ldloc.0
0x1de1e  ldc.i4.s 0x22
0x1de20  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1de25  pop
0x1de26  ldloc.0
0x1de27  ldc.i4.s 0x3E
0x1de29  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1de2e  pop
0x1de2f  ldloc.0
0x1de30  callvirt instance string [mscorlib]System.Object::ToString()
0x1de35  ret
```
