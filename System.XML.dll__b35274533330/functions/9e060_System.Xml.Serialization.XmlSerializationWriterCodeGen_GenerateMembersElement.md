# System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateMembersElement

- ea: `0x9e060`
- end: `0x9e867`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateMembersElement`
- size: `2055`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config`

## callers

- `0x9d750`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68600`
- `0x68660`
- `0x686d0`
- `0x686f0`
- `0x68890`
- `0x68990`
- `0x68b80`
- `0x68c50`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x69690`
- `0x696f0`
- `0x69710`
- `0x69730`
- `0x69750`
- `0x69b00`
- `0x69b20`
- `0x69bb0`
- `0x69ce0`
- `0x69d20`
- `0x69d60`
- `0x72ba0`
- `0x72d80`
- `0x79510`
- `0x795b0`
- `0x86170`
- `0x862f0`
- `0x9dfd0`
- `0x9dfe0`
- `0x9e060`
- `0x9ea60`
- `0x9fe70`
- `0xa05c0`
- `0xa2ac0`
- `0xa2af0`
- `0xa2b10`

## string_xrefs

- `0x9e0ee`: `WriteStartDocument();`
- `0x9e694`: `WriteRpcResult(`
- `0x9e833`: `WriteReferencedElements();`

## pseudocode

```c

```

## disassembly

```asm
0x9e060  ldarg.1
0x9e061  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x9e066  stloc.0
0x9e067  ldloc.0
0x9e068  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x9e06d  castclass System.Xml.Serialization.MembersMapping
0x9e072  stloc.1
0x9e073  ldloc.1
0x9e074  callvirt instance bool System.Xml.Serialization.MembersMapping::get_HasWrapperElement()
0x9e079  stloc.2
0x9e07a  ldloc.1
0x9e07b  callvirt instance bool System.Xml.Serialization.MembersMapping::get_WriteAccessors()
0x9e080  stloc.3
0x9e081  ldarg.1
0x9e082  callvirt instance bool System.Xml.Serialization.XmlMapping::get_IsSoap()
0x9e087  ldloc.3
0x9e088  and
0x9e089  stloc.s  4
0x9e08b  ldarg.0
0x9e08c  ldloc.0
0x9e08d  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x9e092  call     instance string System.Xml.Serialization.XmlSerializationWriterCodeGen::NextMethodName(string name)
0x9e097  stloc.s  5
0x9e099  ldarg.0
0x9e09a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e09f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x9e0a4  ldarg.0
0x9e0a5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e0aa  ldstr    aPublicVoid// "public void "
0x9e0af  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e0b4  ldarg.0
0x9e0b5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e0ba  ldloc.s  5
0x9e0bc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e0c1  ldarg.0
0x9e0c2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e0c7  ldstr    aObjectP_0// "(object[] p) {"
0x9e0cc  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e0d1  ldarg.0
0x9e0d2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e0d7  dup
0x9e0d8  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e0dd  stloc.s  6
0x9e0df  ldloc.s  6
0x9e0e1  ldc.i4.1
0x9e0e2  add
0x9e0e3  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e0e8  ldarg.0
0x9e0e9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e0ee  ldstr    aWritestartdocu// "WriteStartDocument();"
0x9e0f3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e0f8  ldloc.1
0x9e0f9  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9e0fe  brtrue.s loc_9E110
0x9e100  ldarg.0
0x9e101  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e106  ldstr    aToplevelelemen// "TopLevelElement();"
0x9e10b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e110  ldarg.0
0x9e111  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e116  ldstr    aIntPlengthPLen// "int pLength = p.Length;"
0x9e11b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e120  ldloc.2
0x9e121  brfalse  loc_9E42C
0x9e126  ldarg.0
0x9e127  ldloc.0
0x9e128  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x9e12d  ldloc.0
0x9e12e  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x9e133  ldc.i4.1
0x9e134  beq.s    loc_9E13D
0x9e136  ldstr    asc_1284AE// ""
0x9e13b  br.s     loc_9E143
0x9e13d  ldloc.0
0x9e13e  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x9e143  ldloc.1
0x9e144  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9e149  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteStartElement(string name, string ns, bool writePrefixed)
0x9e14e  ldarg.0
0x9e14f  ldloc.1
0x9e150  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x9e155  call     instance int32 System.Xml.Serialization.XmlSerializationWriterCodeGen::FindXmlnsIndex(class System.Xml.Serialization.MemberMapping[] members)
0x9e15a  stloc.s  7
0x9e15c  ldloc.s  7
0x9e15e  ldc.i4.0
0x9e15f  blt      loc_9E232
0x9e164  ldloc.1
0x9e165  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x9e16a  ldloc.s  7
0x9e16c  ldelem.ref
0x9e16d  stloc.s  8
0x9e16f  ldc.i4.5
0x9e170  newarr   [mscorlib]System.String
0x9e175  dup
0x9e176  ldc.i4.0
0x9e177  ldstr    asc_12FF58// "(("
0x9e17c  stelem.ref
0x9e17d  dup
0x9e17e  ldc.i4.1
0x9e17f  ldtoken  System.Xml.Serialization.XmlSerializerNamespaces
0x9e184  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9e189  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9e18e  stelem.ref
0x9e18f  dup
0x9e190  ldc.i4.2
0x9e191  ldstr    aP_1// ")p["
0x9e196  stelem.ref
0x9e197  dup
0x9e198  ldc.i4.3
0x9e199  ldloca.s 7
0x9e19b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e1a0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e1a5  stelem.ref
0x9e1a6  dup
0x9e1a7  ldc.i4.4
0x9e1a8  ldstr    asc_134DD4// "])"
0x9e1ad  stelem.ref
0x9e1ae  call     string [mscorlib]System.String::Concat(string[])
0x9e1b3  stloc.s  9
0x9e1b5  ldarg.0
0x9e1b6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e1bb  ldstr    aIfPlength// "if (pLength > "
0x9e1c0  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e1c5  ldarg.0
0x9e1c6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e1cb  ldloca.s 7
0x9e1cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e1d2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e1d7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e1dc  ldarg.0
0x9e1dd  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e1e2  ldstr    asc_134612// ") {"
0x9e1e7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e1ec  ldarg.0
0x9e1ed  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e1f2  dup
0x9e1f3  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e1f8  stloc.s  6
0x9e1fa  ldloc.s  6
0x9e1fc  ldc.i4.1
0x9e1fd  add
0x9e1fe  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e203  ldarg.0
0x9e204  ldloc.s  9
0x9e206  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteNamespaces(string source)
0x9e20b  ldarg.0
0x9e20c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e211  dup
0x9e212  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e217  stloc.s  6
0x9e219  ldloc.s  6
0x9e21b  ldc.i4.1
0x9e21c  sub
0x9e21d  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e222  ldarg.0
0x9e223  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e228  ldstr    asc_12E936// "}"
0x9e22d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e232  ldc.i4.0
0x9e233  stloc.s  0xA
0x9e235  br       loc_9E41D
0x9e23a  ldloc.1
0x9e23b  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x9e240  ldloc.s  0xA
0x9e242  ldelem.ref
0x9e243  stloc.s  0xB
0x9e245  ldloc.s  0xB
0x9e247  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x9e24c  brfalse  loc_9E417
0x9e251  ldloc.s  0xB
0x9e253  callvirt instance bool System.Xml.Serialization.AccessorMapping::get_Ignore()
0x9e258  brtrue   loc_9E417
0x9e25d  ldstr    aP_0// "p["
0x9e262  ldloca.s 0xA
0x9e264  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e269  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e26e  ldstr    asc_12BE9E// "]"
0x9e273  call     string [mscorlib]System.String::Concat(string, string, string)
0x9e278  stloc.s  0xC
0x9e27a  ldnull
0x9e27b  stloc.s  0xD
0x9e27d  ldc.i4.0
0x9e27e  stloc.s  0xE
0x9e280  ldloc.s  0xB
0x9e282  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x9e287  brfalse.s loc_9E2ED
0x9e289  ldloc.s  0xB
0x9e28b  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x9e290  ldstr    aSpecified// "Specified"
0x9e295  call     string [mscorlib]System.String::Concat(string, string)
0x9e29a  stloc.s  0xF
0x9e29c  ldc.i4.0
0x9e29d  stloc.s  0x10
0x9e29f  br.s     loc_9E2E1
0x9e2a1  ldloc.1
0x9e2a2  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x9e2a7  ldloc.s  0x10
0x9e2a9  ldelem.ref
0x9e2aa  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x9e2af  ldloc.s  0xF
0x9e2b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9e2b6  brfalse.s loc_9E2DB
0x9e2b8  ldstr    aBoolP// "((bool) p["
0x9e2bd  ldloca.s 0x10
0x9e2bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e2c4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e2c9  ldstr    asc_134DD4// "])"
0x9e2ce  call     string [mscorlib]System.String::Concat(string, string, string)
0x9e2d3  stloc.s  0xD
0x9e2d5  ldloc.s  0x10
0x9e2d7  stloc.s  0xE
0x9e2d9  br.s     loc_9E2ED
0x9e2db  ldloc.s  0x10
0x9e2dd  ldc.i4.1
0x9e2de  add
0x9e2df  stloc.s  0x10
0x9e2e1  ldloc.s  0x10
0x9e2e3  ldloc.1
0x9e2e4  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x9e2e9  ldlen
0x9e2ea  conv.i4
0x9e2eb  blt.s    loc_9E2A1
0x9e2ed  ldarg.0
0x9e2ee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e2f3  ldstr    aIfPlength// "if (pLength > "
0x9e2f8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e2fd  ldarg.0
0x9e2fe  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e303  ldloca.s 0xA
0x9e305  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e30a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e30f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e314  ldarg.0
0x9e315  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e31a  ldstr    asc_134612// ") {"
0x9e31f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e324  ldarg.0
0x9e325  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e32a  dup
0x9e32b  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e330  stloc.s  6
0x9e332  ldloc.s  6
0x9e334  ldc.i4.1
0x9e335  add
0x9e336  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e33b  ldloc.s  0xD
0x9e33d  brfalse.s loc_9E3AA
0x9e33f  ldarg.0
0x9e340  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e345  ldstr    aIfPlength_0// "if (pLength <= "
0x9e34a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e34f  ldarg.0
0x9e350  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e355  ldloca.s 0xE
0x9e357  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e35c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e361  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e366  ldarg.0
0x9e367  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e36c  ldstr    asc_134946// " || "
0x9e371  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e376  ldarg.0
0x9e377  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e37c  ldloc.s  0xD
0x9e37e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9e383  ldarg.0
0x9e384  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e389  ldstr    asc_134612// ") {"
0x9e38e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9e393  ldarg.0
0x9e394  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e399  dup
0x9e39a  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e39f  stloc.s  6
0x9e3a1  ldloc.s  6
0x9e3a3  ldc.i4.1
0x9e3a4  add
0x9e3a5  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e3aa  ldarg.0
0x9e3ab  ldloc.s  0xC
0x9e3ad  ldloc.s  0xB
0x9e3af  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x9e3b4  ldloc.s  0xB
0x9e3b6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x9e3bb  ldstr    aP// "p"
0x9e3c0  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteMember(string source, class System.Xml.Serialization.AttributeAccessor attribute, class System.Xml.Serialization.TypeDesc memberTypeDesc, string parent)
0x9e3c5  ldloc.s  0xD
0x9e3c7  brfalse.s loc_9E3F0
0x9e3c9  ldarg.0
0x9e3ca  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e3cf  dup
0x9e3d0  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9e3d5  stloc.s  6
0x9e3d7  ldloc.s  6
0x9e3d9  ldc.i4.1
0x9e3da  sub
0x9e3db  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9e3e0  ldarg.0
0x9e3e1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9e3e6  ldstr    asc_12E936// "}"
  ... truncated ...
```
