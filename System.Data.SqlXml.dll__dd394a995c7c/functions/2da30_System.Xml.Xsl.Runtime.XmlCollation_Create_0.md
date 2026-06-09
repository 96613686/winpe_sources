# System.Xml.Xsl.Runtime.XmlCollation::Create_0

- ea: `0x2da30`
- end: `0x2e02e`
- name: `System.Xml.Xsl.Runtime.XmlCollation::Create_0`
- size: `1534`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20f20`
- `0x2da20`

## callees

- `0x3780`
- `0x2d9e0`
- `0x2da10`
- `0x2da30`
- `0x2e200`
- `0x2e210`
- `0x50af0`
- `0x57450`
- `0x57480`
- `0x57490`
- `0x574c0`
- `0x574d0`
- `0x574f0`

## string_xrefs

- `0x2da6f`: `http://collations.microsoft.com`
- `0x2da31`: `http://www.w3.org/2004/10/xpath-functions/collation/codepoint`
- `0x2dac0`: `http://www.w3.org/2004/10/xpath-functions/collation/codepoint`

## pseudocode

```c

```

## disassembly

```asm
0x2da30  ldarg.0
0x2da31  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2004/10/xpath-functio"...
0x2da36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2da3b  brfalse.s loc_2DA43
0x2da3d  call     class System.Xml.Xsl.Runtime.XmlCollation System.Xml.Xsl.Runtime.XmlCollation::get_CodePointCollation()
0x2da42  ret
0x2da43  ldnull
0x2da44  stloc.1
0x2da45  ldloca.s 2
0x2da47  initobj  Options
0x2da4d  ldarg.1
0x2da4e  brfalse.s loc_2DA59
0x2da50  ldarg.0
0x2da51  newobj   instance void [System]System.Uri::.ctor(string)
0x2da56  stloc.0
0x2da57  br.s     loc_2DA66
0x2da59  ldarg.0
0x2da5a  ldc.i4.1
0x2da5b  ldloca.s 0
0x2da5d  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x2da62  brtrue.s loc_2DA66
0x2da64  ldnull
0x2da65  ret
0x2da66  ldloc.0
0x2da67  ldc.i4.1
0x2da68  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x2da6d  stloc.3
0x2da6e  ldloc.3
0x2da6f  ldstr    aHttpCollations// "http://collations.microsoft.com"
0x2da74  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2da79  brfalse.s loc_2DABF
0x2da7b  ldloc.0
0x2da7c  callvirt instance string [System]System.Uri::get_LocalPath()
0x2da81  ldc.i4.1
0x2da82  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2da87  stloc.s  6
0x2da89  ldloc.s  6
0x2da8b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2da90  brfalse.s loc_2DAF9
0x2da92  nop
0x2da93  ldloc.s  6
0x2da95  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0x2da9a  stloc.1
0x2da9b  leave.s  loc_2DAF9
0x2da9d  pop
0x2da9e  ldarg.1
0x2da9f  brtrue.s loc_2DAA9
0x2daa1  ldnull
0x2daa2  stloc.s  7
0x2daa4  leave    loc_2E02B
0x2daa9  ldstr    aCollUnsupporte// "Coll_UnsupportedLanguage"
0x2daae  ldc.i4.1
0x2daaf  newarr   [mscorlib]System.String
0x2dab4  dup
0x2dab5  ldc.i4.0
0x2dab6  ldloc.s  6
0x2dab8  stelem.ref
0x2dab9  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2dabe  throw
0x2dabf  ldloc.0
0x2dac0  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2004/10/xpath-functio"...
0x2dac5  newobj   instance void [System]System.Uri::.ctor(string)
0x2daca  callvirt instance bool [System]System.Uri::IsBaseOf(class [System]System.Uri)
0x2dacf  brfalse.s loc_2DADF
0x2dad1  ldloca.s 2
0x2dad3  ldc.i4   0x40000000
0x2dad8  call     instance void Options::set_CompareOptions(valuetype [mscorlib]System.Globalization.CompareOptions value)
0x2dadd  br.s     loc_2DAF9
0x2dadf  ldarg.1
0x2dae0  brtrue.s loc_2DAE4
0x2dae2  ldnull
0x2dae3  ret
0x2dae4  ldstr    aCollUnsupporte_0// "Coll_Unsupported"
0x2dae9  ldc.i4.1
0x2daea  newarr   [mscorlib]System.String
0x2daef  dup
0x2daf0  ldc.i4.0
0x2daf1  ldarg.0
0x2daf2  stelem.ref
0x2daf3  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2daf8  throw
0x2daf9  ldloc.0
0x2dafa  callvirt instance string [System]System.Uri::get_Query()
0x2daff  stloc.s  4
0x2db01  ldnull
0x2db02  stloc.s  5
0x2db04  ldloc.s  4
0x2db06  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2db0b  brfalse  loc_2DD94
0x2db10  ldloc.s  4
0x2db12  ldc.i4.1
0x2db13  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2db18  ldc.i4.1
0x2db19  newarr   [mscorlib]System.Char
0x2db1e  dup
0x2db1f  ldc.i4.0
0x2db20  ldc.i4.s 0x26
0x2db22  stelem.i2
0x2db23  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2db28  stloc.s  8
0x2db2a  ldc.i4.0
0x2db2b  stloc.s  9
0x2db2d  br       loc_2DD89
0x2db32  ldloc.s  8
0x2db34  ldloc.s  9
0x2db36  ldelem.ref
0x2db37  stloc.s  0xA
0x2db39  ldloc.s  0xA
0x2db3b  ldc.i4.1
0x2db3c  newarr   [mscorlib]System.Char
0x2db41  dup
0x2db42  ldc.i4.0
0x2db43  ldc.i4.s 0x3D
0x2db45  stelem.i2
0x2db46  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2db4b  stloc.s  0xB
0x2db4d  ldloc.s  0xB
0x2db4f  ldlen
0x2db50  conv.i4
0x2db51  ldc.i4.2
0x2db52  beq.s    loc_2DB6F
0x2db54  ldarg.1
0x2db55  brtrue.s loc_2DB59
0x2db57  ldnull
0x2db58  ret
0x2db59  ldstr    aCollBadoptform// "Coll_BadOptFormat"
0x2db5e  ldc.i4.1
0x2db5f  newarr   [mscorlib]System.String
0x2db64  dup
0x2db65  ldc.i4.0
0x2db66  ldloc.s  0xA
0x2db68  stelem.ref
0x2db69  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2db6e  throw
0x2db6f  ldloc.s  0xB
0x2db71  ldc.i4.0
0x2db72  ldelem.ref
0x2db73  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2db78  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x2db7d  stloc.s  0xC
0x2db7f  ldloc.s  0xB
0x2db81  ldc.i4.1
0x2db82  ldelem.ref
0x2db83  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2db88  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x2db8d  stloc.s  0xD
0x2db8f  ldloc.s  0xC
0x2db91  ldstr    aSort_0// "SORT"
0x2db96  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2db9b  brfalse.s loc_2DBA6
0x2db9d  ldloc.s  0xD
0x2db9f  stloc.s  5
0x2dba1  br       loc_2DD83
0x2dba6  ldloc.s  0xC
0x2dba8  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2dbad  stloc.s  0xF
0x2dbaf  ldloc.s  0xF
0x2dbb1  ldc.i4   0x44C7905F
0x2dbb6  bgt.un.s loc_2DBF8
0x2dbb8  ldloc.s  0xF
0x2dbba  ldc.i4   0x17D2C72A
0x2dbbf  bgt.un.s loc_2DBDE
0x2dbc1  ldloc.s  0xF
0x2dbc3  ldc.i4   0x149F9C43
0x2dbc8  beq      loc_2DC8B
0x2dbcd  ldloc.s  0xF
0x2dbcf  ldc.i4   0x17D2C72A
0x2dbd4  beq      loc_2DC6B
0x2dbd9  br       loc_2DCF0
0x2dbde  ldloc.s  0xF
0x2dbe0  ldc.i4   0x20522955
0x2dbe5  beq      loc_2DC7B
0x2dbea  ldloc.s  0xF
0x2dbec  ldc.i4   0x44C7905F
0x2dbf1  beq.s    loc_2DC32
0x2dbf3  br       loc_2DCF0
0x2dbf8  ldloc.s  0xF
0x2dbfa  ldc.i4   0x6073905C
0x2dbff  bgt.un.s loc_2DC1B
0x2dc01  ldloc.s  0xF
0x2dc03  ldc.i4   0x5B9DFE9D
0x2dc08  beq      loc_2DCAB
0x2dc0d  ldloc.s  0xF
0x2dc0f  ldc.i4   0x6073905C
0x2dc14  beq.s    loc_2DC45
0x2dc16  br       loc_2DCF0
0x2dc1b  ldloc.s  0xF
0x2dc1d  ldc.i4   0x669522C0
0x2dc22  beq.s    loc_2DC58
0x2dc24  ldloc.s  0xF
0x2dc26  ldc.i4   0xCB19CFB9
0x2dc2b  beq.s    loc_2DC9B
0x2dc2d  br       loc_2DCF0
0x2dc32  ldloc.s  0xC
0x2dc34  ldstr    aIgnorecase// "IGNORECASE"
0x2dc39  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc3e  brtrue.s loc_2DCBB
0x2dc40  br       loc_2DCF0
0x2dc45  ldloc.s  0xC
0x2dc47  ldstr    aIgnorenonspace// "IGNORENONSPACE"
0x2dc4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc51  brtrue.s loc_2DCC0
0x2dc53  br       loc_2DCF0
0x2dc58  ldloc.s  0xC
0x2dc5a  ldstr    aIgnoresymbols// "IGNORESYMBOLS"
0x2dc5f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc64  brtrue.s loc_2DCC5
0x2dc66  br       loc_2DCF0
0x2dc6b  ldloc.s  0xC
0x2dc6d  ldstr    aIgnorekanatype// "IGNOREKANATYPE"
0x2dc72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc77  brtrue.s loc_2DCCA
0x2dc79  br.s     loc_2DCF0
0x2dc7b  ldloc.s  0xC
0x2dc7d  ldstr    aIgnorewidth// "IGNOREWIDTH"
0x2dc82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc87  brtrue.s loc_2DCCF
0x2dc89  br.s     loc_2DCF0
0x2dc8b  ldloc.s  0xC
0x2dc8d  ldstr    aUpperfirst_0// "UPPERFIRST"
0x2dc92  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dc97  brtrue.s loc_2DCD5
0x2dc99  br.s     loc_2DCF0
0x2dc9b  ldloc.s  0xC
0x2dc9d  ldstr    aEmptygreatest// "EMPTYGREATEST"
0x2dca2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dca7  brtrue.s loc_2DCDE
0x2dca9  br.s     loc_2DCF0
0x2dcab  ldloc.s  0xC
0x2dcad  ldstr    aDescendingorde_0// "DESCENDINGORDER"
0x2dcb2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dcb7  brtrue.s loc_2DCE7
0x2dcb9  br.s     loc_2DCF0
0x2dcbb  ldc.i4.1
0x2dcbc  stloc.s  0xE
0x2dcbe  br.s     loc_2DD0D
0x2dcc0  ldc.i4.2
0x2dcc1  stloc.s  0xE
0x2dcc3  br.s     loc_2DD0D
0x2dcc5  ldc.i4.4
0x2dcc6  stloc.s  0xE
0x2dcc8  br.s     loc_2DD0D
0x2dcca  ldc.i4.8
0x2dccb  stloc.s  0xE
0x2dccd  br.s     loc_2DD0D
0x2dccf  ldc.i4.s 0x10
0x2dcd1  stloc.s  0xE
0x2dcd3  br.s     loc_2DD0D
0x2dcd5  ldc.i4   0x1000
0x2dcda  stloc.s  0xE
0x2dcdc  br.s     loc_2DD0D
0x2dcde  ldc.i4   0x2000
0x2dce3  stloc.s  0xE
0x2dce5  br.s     loc_2DD0D
0x2dce7  ldc.i4   0x4000
0x2dcec  stloc.s  0xE
0x2dcee  br.s     loc_2DD0D
0x2dcf0  ldarg.1
0x2dcf1  brtrue.s loc_2DCF5
0x2dcf3  ldnull
0x2dcf4  ret
0x2dcf5  ldstr    aCollUnsupporte_1// "Coll_UnsupportedOpt"
0x2dcfa  ldc.i4.1
0x2dcfb  newarr   [mscorlib]System.String
0x2dd00  dup
0x2dd01  ldc.i4.0
0x2dd02  ldloc.s  0xB
0x2dd04  ldc.i4.0
0x2dd05  ldelem.ref
0x2dd06  stelem.ref
0x2dd07  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2dd0c  throw
0x2dd0d  ldloc.s  0xD
0x2dd0f  ldstr    a0// "0"
0x2dd14  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dd19  brtrue.s loc_2DD47
0x2dd1b  ldloc.s  0xD
0x2dd1d  ldstr    aFalse_0// "FALSE"
0x2dd22  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dd27  brtrue.s loc_2DD47
0x2dd29  ldloc.s  0xD
0x2dd2b  ldstr    a1// "1"
0x2dd30  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dd35  brtrue.s loc_2DD53
0x2dd37  ldloc.s  0xD
0x2dd39  ldstr    aTrue_0// "TRUE"
0x2dd3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dd43  brtrue.s loc_2DD53
0x2dd45  br.s     loc_2DD5F
0x2dd47  ldloca.s 2
0x2dd49  ldloc.s  0xE
0x2dd4b  ldc.i4.0
0x2dd4c  call     instance void Options::SetFlag(int32 flag, bool value)
0x2dd51  br.s     loc_2DD83
0x2dd53  ldloca.s 2
0x2dd55  ldloc.s  0xE
0x2dd57  ldc.i4.1
0x2dd58  call     instance void Options::SetFlag(int32 flag, bool value)
0x2dd5d  br.s     loc_2DD83
0x2dd5f  ldarg.1
  ... truncated ...
```
