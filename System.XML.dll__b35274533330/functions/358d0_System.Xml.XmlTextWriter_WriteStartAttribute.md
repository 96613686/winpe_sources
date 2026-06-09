# System.Xml.XmlTextWriter::WriteStartAttribute

- ea: `0x358d0`
- end: `0x35b5c`
- name: `System.Xml.XmlTextWriter::WriteStartAttribute`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x4dea0`

## callees

- `0x25be0`
- `0x25bf0`
- `0x358d0`
- `0x36270`
- `0x368b0`
- `0x36b10`
- `0x36bd0`
- `0x36c20`
- `0x36ca0`
- `0x36e80`
- `0x62370`

## string_xrefs

- `0x358f8`: `http://www.w3.org/2000/xmlns/`
- `0x3596a`: `http://www.w3.org/2000/xmlns/`
- `0x359c7`: `http://www.w3.org/2000/xmlns/`
- `0x35908`: `xmlns`
- `0x35914`: `xmlns`
- `0x3595e`: `xmlns`
- `0x359bb`: `xmlns`
- `0x35a07`: `Xml_UndefPrefix`
- `0x35aac`: `Xml_NoNamespaces`
- `0x3597a`: `Xml_XmlnsBelongsToReservedNs`
- `0x359d7`: `Xml_XmlnsBelongsToReservedNs`
- `0x35abd`: `xml:lang`
- `0x35ad3`: `xml:space`

## pseudocode

```c

```

## disassembly

```asm
0x358d0  ldarg.0
0x358d1  ldc.i4.7
0x358d2  call     instance void System.Xml.XmlTextWriter::AutoComplete(valuetype Token token)
0x358d7  ldarg.0
0x358d8  ldc.i4.0
0x358d9  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x358de  ldarg.0
0x358df  ldfld    bool System.Xml.XmlTextWriter::namespaces
0x358e4  brfalse  loc_35A96
0x358e9  ldarg.1
0x358ea  brfalse.s loc_358F7
0x358ec  ldarg.1
0x358ed  callvirt instance int32 [mscorlib]System.String::get_Length()
0x358f2  brtrue.s loc_358F7
0x358f4  ldnull
0x358f5  starg.s  1
0x358f7  ldarg.3
0x358f8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x358fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35902  brfalse.s loc_3591B
0x35904  ldarg.1
0x35905  brtrue.s loc_3591B
0x35907  ldarg.2
0x35908  ldstr    aXmlns// "xmlns"
0x3590d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x35912  brfalse.s loc_3591B
0x35914  ldstr    aXmlns// "xmlns"
0x35919  starg.s  1
0x3591b  ldarg.1
0x3591c  ldstr    aXml// "xml"
0x35921  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35926  brfalse.s loc_3595D
0x35928  ldarg.2
0x35929  ldstr    aLang// "lang"
0x3592e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35933  brfalse.s loc_35941
0x35935  ldarg.0
0x35936  ldc.i4.2
0x35937  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x3593c  br       loc_35A70
0x35941  ldarg.2
0x35942  ldstr    aSpace// "space"
0x35947  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3594c  brfalse  loc_35A70
0x35951  ldarg.0
0x35952  ldc.i4.1
0x35953  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x35958  br       loc_35A70
0x3595d  ldarg.1
0x3595e  ldstr    aXmlns// "xmlns"
0x35963  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35968  brfalse.s loc_359B7
0x3596a  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3596f  ldarg.3
0x35970  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x35975  brfalse.s loc_3598A
0x35977  ldarg.3
0x35978  brfalse.s loc_3598A
0x3597a  ldstr    aXmlXmlnsbelong// "Xml_XmlnsBelongsToReservedNs"
0x3597f  call     string System.Xml.Res::GetString(string name)
0x35984  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x35989  throw
0x3598a  ldarg.2
0x3598b  brfalse.s loc_35995
0x3598d  ldarg.2
0x3598e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35993  brtrue.s loc_359A4
0x35995  ldarg.1
0x35996  starg.s  2
0x35998  ldnull
0x35999  starg.s  1
0x3599b  ldarg.0
0x3599c  ldnull
0x3599d  stfld    string System.Xml.XmlTextWriter::prefixForXmlNs
0x359a2  br.s     loc_359AB
0x359a4  ldarg.0
0x359a5  ldarg.2
0x359a6  stfld    string System.Xml.XmlTextWriter::prefixForXmlNs
0x359ab  ldarg.0
0x359ac  ldc.i4.3
0x359ad  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x359b2  br       loc_35A70
0x359b7  ldarg.1
0x359b8  brtrue.s loc_359F7
0x359ba  ldarg.2
0x359bb  ldstr    aXmlns// "xmlns"
0x359c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x359c5  brfalse.s loc_359F7
0x359c7  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x359cc  ldarg.3
0x359cd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x359d2  brfalse.s loc_359E7
0x359d4  ldarg.3
0x359d5  brfalse.s loc_359E7
0x359d7  ldstr    aXmlXmlnsbelong// "Xml_XmlnsBelongsToReservedNs"
0x359dc  call     string System.Xml.Res::GetString(string name)
0x359e1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x359e6  throw
0x359e7  ldarg.0
0x359e8  ldc.i4.3
0x359e9  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x359ee  ldarg.0
0x359ef  ldnull
0x359f0  stfld    string System.Xml.XmlTextWriter::prefixForXmlNs
0x359f5  br.s     loc_35A70
0x359f7  ldarg.3
0x359f8  brtrue.s loc_35A17
0x359fa  ldarg.1
0x359fb  brfalse.s loc_35A70
0x359fd  ldarg.0
0x359fe  ldarg.1
0x359ff  call     instance int32 System.Xml.XmlTextWriter::LookupNamespace(string prefix)
0x35a04  ldc.i4.m1
0x35a05  bne.un.s loc_35A70
0x35a07  ldstr    aXmlUndefprefix// "Xml_UndefPrefix"
0x35a0c  call     string System.Xml.Res::GetString(string name)
0x35a11  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x35a16  throw
0x35a17  ldarg.3
0x35a18  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35a1d  brtrue.s loc_35A28
0x35a1f  ldsfld   string [mscorlib]System.String::Empty
0x35a24  starg.s  1
0x35a26  br.s     loc_35A70
0x35a28  ldarg.0
0x35a29  ldarg.1
0x35a2a  ldarg.3
0x35a2b  call     instance void System.Xml.XmlTextWriter::VerifyPrefixXml(string prefix, string ns)
0x35a30  ldarg.1
0x35a31  brfalse.s loc_35A40
0x35a33  ldarg.0
0x35a34  ldarg.1
0x35a35  call     instance int32 System.Xml.XmlTextWriter::LookupNamespaceInCurrentScope(string prefix)
0x35a3a  ldc.i4.m1
0x35a3b  beq.s    loc_35A40
0x35a3d  ldnull
0x35a3e  starg.s  1
0x35a40  ldarg.0
0x35a41  ldarg.3
0x35a42  call     instance string System.Xml.XmlTextWriter::FindPrefix(string ns)
0x35a47  stloc.0
0x35a48  ldloc.0
0x35a49  brfalse.s loc_35A5C
0x35a4b  ldarg.1
0x35a4c  brfalse.s loc_35A57
0x35a4e  ldarg.1
0x35a4f  ldloc.0
0x35a50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35a55  brfalse.s loc_35A5C
0x35a57  ldloc.0
0x35a58  starg.s  1
0x35a5a  br.s     loc_35A70
0x35a5c  ldarg.1
0x35a5d  brtrue.s loc_35A67
0x35a5f  ldarg.0
0x35a60  call     instance string System.Xml.XmlTextWriter::GeneratePrefix()
0x35a65  starg.s  1
0x35a67  ldarg.0
0x35a68  ldarg.1
0x35a69  ldarg.3
0x35a6a  ldc.i4.0
0x35a6b  call     instance void System.Xml.XmlTextWriter::PushNamespace(string prefix, string ns, bool declared)
0x35a70  ldarg.1
0x35a71  brfalse.s loc_35AE6
0x35a73  ldarg.1
0x35a74  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35a79  brfalse.s loc_35AE6
0x35a7b  ldarg.0
0x35a7c  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x35a81  ldarg.1
0x35a82  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35a87  ldarg.0
0x35a88  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x35a8d  ldc.i4.s 0x3A
0x35a8f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x35a94  br.s     loc_35AE6
0x35a96  ldarg.3
0x35a97  brfalse.s loc_35AA1
0x35a99  ldarg.3
0x35a9a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35a9f  brtrue.s loc_35AAC
0x35aa1  ldarg.1
0x35aa2  brfalse.s loc_35ABC
0x35aa4  ldarg.1
0x35aa5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35aaa  brfalse.s loc_35ABC
0x35aac  ldstr    aXmlNonamespace// "Xml_NoNamespaces"
0x35ab1  call     string System.Xml.Res::GetString(string name)
0x35ab6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x35abb  throw
0x35abc  ldarg.2
0x35abd  ldstr    aXmlLang// "xml:lang"
0x35ac2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35ac7  brfalse.s loc_35AD2
0x35ac9  ldarg.0
0x35aca  ldc.i4.2
0x35acb  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x35ad0  br.s     loc_35AE6
0x35ad2  ldarg.2
0x35ad3  ldstr    aXmlSpace// "xml:space"
0x35ad8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35add  brfalse.s loc_35AE6
0x35adf  ldarg.0
0x35ae0  ldc.i4.1
0x35ae1  stfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x35ae6  ldarg.0
0x35ae7  ldfld    class System.Xml.XmlTextEncoder System.Xml.XmlTextWriter::xmlEncoder
0x35aec  ldarg.0
0x35aed  ldfld    valuetype SpecialAttr System.Xml.XmlTextWriter::specialAttr
0x35af2  ldc.i4.0
0x35af3  cgt.un
0x35af5  callvirt instance void System.Xml.XmlTextEncoder::StartAttribute(bool cacheAttrValue)
0x35afa  ldarg.0
0x35afb  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x35b00  ldarg.2
0x35b01  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35b06  ldarg.0
0x35b07  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x35b0c  ldc.i4.s 0x3D
0x35b0e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x35b13  ldarg.0
0x35b14  ldfld    char System.Xml.XmlTextWriter::curQuoteChar
0x35b19  ldarg.0
0x35b1a  ldfld    char System.Xml.XmlTextWriter::quoteChar
0x35b1f  beq.s    loc_35B3E
0x35b21  ldarg.0
0x35b22  ldarg.0
0x35b23  ldfld    char System.Xml.XmlTextWriter::quoteChar
0x35b28  stfld    char System.Xml.XmlTextWriter::curQuoteChar
0x35b2d  ldarg.0
0x35b2e  ldfld    class System.Xml.XmlTextEncoder System.Xml.XmlTextWriter::xmlEncoder
0x35b33  ldarg.0
0x35b34  ldfld    char System.Xml.XmlTextWriter::quoteChar
0x35b39  callvirt instance void System.Xml.XmlTextEncoder::set_QuoteChar(char value)
0x35b3e  ldarg.0
0x35b3f  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x35b44  ldarg.0
0x35b45  ldfld    char System.Xml.XmlTextWriter::curQuoteChar
0x35b4a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x35b4f  leave.s  loc_35B5B
0x35b51  pop
0x35b52  ldarg.0
0x35b53  ldc.i4.8
0x35b54  stfld    valuetype State System.Xml.XmlTextWriter::currentState
0x35b59  rethrow
0x35b5b  ret
```
