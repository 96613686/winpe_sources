# System.Xml.XmlWellFormedWriter::WriteStartAttribute

- ea: `0x3cf20`
- end: `0x3d171`
- name: `System.Xml.XmlWellFormedWriter::WriteStartAttribute`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x3cf20`
- `0x3ded0`
- `0x3dfa0`
- `0x3e4e0`
- `0x3e770`
- `0x3e7d0`
- `0x3e830`
- `0x3e890`
- `0x3e9a0`
- `0x40840`
- `0x40970`
- `0x62370`

## string_xrefs

- `0x3d0b6`: `http://www.w3.org/XML/1998/namespace`
- `0x3cf7a`: `http://www.w3.org/2000/xmlns/`
- `0x3cfe8`: `http://www.w3.org/2000/xmlns/`
- `0x3d070`: `http://www.w3.org/2000/xmlns/`
- `0x3cf2c`: `xmlns`
- `0x3cf38`: `xmlns`
- `0x3cf6d`: `xmlns`
- `0x3cfd2`: `xmlns`
- `0x3d05a`: `xmlns`
- `0x3d0c2`: `Xml_XmlPrefix`
- `0x3cff4`: `Xml_XmlnsPrefix`
- `0x3d07c`: `Xml_XmlnsPrefix`
- `0x3cf48`: `Xml_EmptyLocalName`

## pseudocode

```c

```

## disassembly

```asm
0x3cf20  ldarg.2
0x3cf21  brfalse.s loc_3CF2B
0x3cf23  ldarg.2
0x3cf24  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3cf29  brtrue.s loc_3CF58
0x3cf2b  ldarg.1
0x3cf2c  ldstr    aXmlns// "xmlns"
0x3cf31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3cf36  brfalse.s loc_3CF48
0x3cf38  ldstr    aXmlns// "xmlns"
0x3cf3d  starg.s  2
0x3cf3f  ldsfld   string [mscorlib]System.String::Empty
0x3cf44  starg.s  1
0x3cf46  br.s     loc_3CF58
0x3cf48  ldstr    aXmlEmptylocaln// "Xml_EmptyLocalName"
0x3cf4d  call     string System.Xml.Res::GetString(string name)
0x3cf52  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3cf57  throw
0x3cf58  ldarg.0
0x3cf59  ldarg.2
0x3cf5a  call     instance void System.Xml.XmlWellFormedWriter::CheckNCName(string ncname)
0x3cf5f  ldarg.0
0x3cf60  ldc.i4.7
0x3cf61  call     instance void System.Xml.XmlWellFormedWriter::AdvanceState(valuetype Token token)
0x3cf66  ldarg.1
0x3cf67  brtrue.s loc_3CF99
0x3cf69  ldarg.3
0x3cf6a  brfalse.s loc_3CF8F
0x3cf6c  ldarg.2
0x3cf6d  ldstr    aXmlns// "xmlns"
0x3cf72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3cf77  brfalse.s loc_3CF86
0x3cf79  ldarg.3
0x3cf7a  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3cf7f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3cf84  brtrue.s loc_3CF8F
0x3cf86  ldarg.0
0x3cf87  ldarg.3
0x3cf88  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x3cf8d  starg.s  1
0x3cf8f  ldarg.1
0x3cf90  brtrue.s loc_3CF99
0x3cf92  ldsfld   string [mscorlib]System.String::Empty
0x3cf97  starg.s  1
0x3cf99  ldarg.3
0x3cf9a  brtrue.s loc_3CFBB
0x3cf9c  ldarg.1
0x3cf9d  brfalse.s loc_3CFB1
0x3cf9f  ldarg.1
0x3cfa0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3cfa5  ldc.i4.0
0x3cfa6  ble.s    loc_3CFB1
0x3cfa8  ldarg.0
0x3cfa9  ldarg.1
0x3cfaa  call     instance string System.Xml.XmlWellFormedWriter::LookupNamespace(string prefix)
0x3cfaf  starg.s  3
0x3cfb1  ldarg.3
0x3cfb2  brtrue.s loc_3CFBB
0x3cfb4  ldsfld   string [mscorlib]System.String::Empty
0x3cfb9  starg.s  3
0x3cfbb  ldarg.1
0x3cfbc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3cfc1  brtrue   loc_3D04B
0x3cfc6  ldarg.2
0x3cfc7  ldc.i4.0
0x3cfc8  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3cfcd  ldc.i4.s 0x78
0x3cfcf  bne.un.s loc_3D01B
0x3cfd1  ldarg.2
0x3cfd2  ldstr    aXmlns// "xmlns"
0x3cfd7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3cfdc  brfalse.s loc_3D01B
0x3cfde  ldarg.3
0x3cfdf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3cfe4  ldc.i4.0
0x3cfe5  ble.s    loc_3D004
0x3cfe7  ldarg.3
0x3cfe8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3cfed  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3cff2  brfalse.s loc_3D004
0x3cff4  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3cff9  call     string System.Xml.Res::GetString(string name)
0x3cffe  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d003  throw
0x3d004  ldarg.0
0x3d005  ldsfld   string [mscorlib]System.String::Empty
0x3d00a  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d00f  ldarg.0
0x3d010  ldc.i4.1
0x3d011  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3d016  br       loc_3D144
0x3d01b  ldarg.3
0x3d01c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d021  ldc.i4.0
0x3d022  ble      loc_3D134
0x3d027  ldarg.0
0x3d028  ldarg.3
0x3d029  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x3d02e  starg.s  1
0x3d030  ldarg.1
0x3d031  brfalse.s loc_3D03E
0x3d033  ldarg.1
0x3d034  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d039  brtrue   loc_3D134
0x3d03e  ldarg.0
0x3d03f  call     instance string System.Xml.XmlWellFormedWriter::GeneratePrefix()
0x3d044  starg.s  1
0x3d046  br       loc_3D134
0x3d04b  ldarg.1
0x3d04c  ldc.i4.0
0x3d04d  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3d052  ldc.i4.s 0x78
0x3d054  bne.un   loc_3D100
0x3d059  ldarg.1
0x3d05a  ldstr    aXmlns// "xmlns"
0x3d05f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d064  brfalse.s loc_3D09F
0x3d066  ldarg.3
0x3d067  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d06c  ldc.i4.0
0x3d06d  ble.s    loc_3D08C
0x3d06f  ldarg.3
0x3d070  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3d075  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3d07a  brfalse.s loc_3D08C
0x3d07c  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3d081  call     string System.Xml.Res::GetString(string name)
0x3d086  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d08b  throw
0x3d08c  ldarg.0
0x3d08d  ldarg.2
0x3d08e  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d093  ldarg.0
0x3d094  ldc.i4.2
0x3d095  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3d09a  br       loc_3D144
0x3d09f  ldarg.1
0x3d0a0  ldstr    aXml// "xml"
0x3d0a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d0aa  brfalse.s loc_3D100
0x3d0ac  ldarg.3
0x3d0ad  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d0b2  ldc.i4.0
0x3d0b3  ble.s    loc_3D0D2
0x3d0b5  ldarg.3
0x3d0b6  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3d0bb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3d0c0  brfalse.s loc_3D0D2
0x3d0c2  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0x3d0c7  call     string System.Xml.Res::GetString(string name)
0x3d0cc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d0d1  throw
0x3d0d2  ldarg.2
0x3d0d3  ldstr    aSpace// "space"
0x3d0d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d0dd  brtrue.s loc_3D0EE
0x3d0df  ldarg.2
0x3d0e0  ldstr    aLang// "lang"
0x3d0e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d0ea  brtrue.s loc_3D0F7
0x3d0ec  br.s     loc_3D100
0x3d0ee  ldarg.0
0x3d0ef  ldc.i4.3
0x3d0f0  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3d0f5  br.s     loc_3D144
0x3d0f7  ldarg.0
0x3d0f8  ldc.i4.4
0x3d0f9  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3d0fe  br.s     loc_3D144
0x3d100  ldarg.0
0x3d101  ldarg.1
0x3d102  call     instance void System.Xml.XmlWellFormedWriter::CheckNCName(string ncname)
0x3d107  ldarg.3
0x3d108  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d10d  brtrue.s loc_3D118
0x3d10f  ldsfld   string [mscorlib]System.String::Empty
0x3d114  starg.s  1
0x3d116  br.s     loc_3D134
0x3d118  ldarg.0
0x3d119  ldarg.1
0x3d11a  call     instance string System.Xml.XmlWellFormedWriter::LookupLocalNamespace(string prefix)
0x3d11f  stloc.0
0x3d120  ldloc.0
0x3d121  brfalse.s loc_3D134
0x3d123  ldloc.0
0x3d124  ldarg.3
0x3d125  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3d12a  brfalse.s loc_3D134
0x3d12c  ldarg.0
0x3d12d  call     instance string System.Xml.XmlWellFormedWriter::GeneratePrefix()
0x3d132  starg.s  1
0x3d134  ldarg.1
0x3d135  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d13a  brfalse.s loc_3D144
0x3d13c  ldarg.0
0x3d13d  ldarg.1
0x3d13e  ldarg.3
0x3d13f  call     instance void System.Xml.XmlWellFormedWriter::PushNamespaceImplicit(string prefix, string ns)
0x3d144  ldarg.0
0x3d145  ldarg.1
0x3d146  ldarg.2
0x3d147  ldarg.3
0x3d148  call     instance void System.Xml.XmlWellFormedWriter::AddAttribute(string prefix, string localName, string namespaceName)
0x3d14d  ldarg.0
0x3d14e  ldfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x3d153  brtrue.s loc_3D163
0x3d155  ldarg.0
0x3d156  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d15b  ldarg.1
0x3d15c  ldarg.2
0x3d15d  ldarg.3
0x3d15e  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x3d163  leave.s  loc_3D170
0x3d165  pop
0x3d166  ldarg.0
0x3d167  ldc.i4.s 0x10
0x3d169  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3d16e  rethrow
0x3d170  ret
```
