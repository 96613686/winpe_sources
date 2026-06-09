# System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateEncodedMembersElement

- ea: `0x8d310`
- end: `0x8d6e8`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateEncodedMembersElement`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config`

## callers

- `0x8cb70`

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
- `0x69620`
- `0x69730`
- `0x69b00`
- `0x69b20`
- `0x69bb0`
- `0x69bf0`
- `0x69ce0`
- `0x69d20`
- `0x69d40`
- `0x69d60`
- `0x72ba0`
- `0x79510`
- `0x86170`
- `0x8d220`
- `0x8d310`
- `0x8da00`
- `0x8f650`
- `0x8fc70`
- `0x90540`
- `0x90a90`
- `0x92ef0`
- `0x92f70`
- `0x93050`
- `0x93090`
- `0x931b0`
- `0x932a0`
- `0x122a10`
- `0x122c70`
- `0x122d50`
- `0x122d70`

## string_xrefs

- `0x8d410`: `Reader`
- `0x8d39c`: `Reader.MoveToContent();`
- `0x8d651`: `Reader.MoveToContent();`
- `0x8d501`: `paramsRead[`
- `0x8d45c`: `Reader.ReadStartElement();`
- `0x8d43c`: `) throw CreateUnknownNodeException();`
- `0x8d44c`: `bool isEmptyWrapper = Reader.IsEmptyElement;`
- `0x8d62a`: `if (Reader.GetAttribute("id", null) != null) { ReadReferencedElement(); } else { UnknownNode((object)p); }`
- `0x8d66c`: `if (!isEmptyWrapper) ReadEndElement();`
- `0x8d68a`: `ReadReferencedElements();`

## pseudocode

```c

```

## disassembly

```asm
0x8d310  ldarg.1
0x8d311  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x8d316  stloc.0
0x8d317  ldloc.0
0x8d318  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8d31d  castclass System.Xml.Serialization.MembersMapping
0x8d322  stloc.1
0x8d323  ldloc.1
0x8d324  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x8d329  stloc.2
0x8d32a  ldloc.1
0x8d32b  callvirt instance bool System.Xml.Serialization.MembersMapping::get_HasWrapperElement()
0x8d330  stloc.3
0x8d331  ldloc.1
0x8d332  callvirt instance bool System.Xml.Serialization.MembersMapping::get_WriteAccessors()
0x8d337  stloc.s  4
0x8d339  ldarg.0
0x8d33a  ldloc.0
0x8d33b  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8d340  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::NextMethodName(string name)
0x8d345  stloc.s  5
0x8d347  ldarg.0
0x8d348  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d34d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8d352  ldarg.0
0x8d353  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d358  ldstr    aPublicObject// "public object[] "
0x8d35d  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d362  ldarg.0
0x8d363  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d368  ldloc.s  5
0x8d36a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d36f  ldarg.0
0x8d370  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d375  ldstr    asc_133CB8// "() {"
0x8d37a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d37f  ldarg.0
0x8d380  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d385  dup
0x8d386  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8d38b  stloc.s  0xC
0x8d38d  ldloc.s  0xC
0x8d38f  ldc.i4.1
0x8d390  add
0x8d391  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8d396  ldarg.0
0x8d397  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d39c  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x8d3a1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d3a6  ldarg.0
0x8d3a7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d3ac  ldstr    aObjectPNewObje// "object[] p = new object["
0x8d3b1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d3b6  ldarg.0
0x8d3b7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d3bc  ldloc.2
0x8d3bd  ldlen
0x8d3be  conv.i4
0x8d3bf  stloc.s  0xC
0x8d3c1  ldloca.s 0xC
0x8d3c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d3c8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d3cd  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d3d2  ldarg.0
0x8d3d3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d3d8  ldstr    asc_133D9E// "];"
0x8d3dd  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d3e2  ldarg.0
0x8d3e3  ldstr    aP// "p"
0x8d3e8  ldloc.2
0x8d3e9  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::InitializeValueTypes(string arrayName, class System.Xml.Serialization.MemberMapping[] mappings)
0x8d3ee  ldloc.3
0x8d3ef  brfalse.s loc_8D466
0x8d3f1  ldarg.0
0x8d3f2  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteReadNonRoots()
0x8d3f7  ldloc.1
0x8d3f8  callvirt instance bool System.Xml.Serialization.MembersMapping::get_ValidateRpcWrapperElement()
0x8d3fd  brfalse.s loc_8D446
0x8d3ff  ldarg.0
0x8d400  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d405  ldstr    aIf_0// "if (!"
0x8d40a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d40f  ldarg.0
0x8d410  ldstr    aReader_2// "Reader"
0x8d415  ldloc.0
0x8d416  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8d41b  ldloc.0
0x8d41c  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x8d421  ldc.i4.1
0x8d422  beq.s    loc_8D42B
0x8d424  ldstr    asc_1284AE// ""
0x8d429  br.s     loc_8D431
0x8d42b  ldloc.0
0x8d42c  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x8d431  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteXmlNodeEqual(string source, string name, string ns)
0x8d436  ldarg.0
0x8d437  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d43c  ldstr    aThrowCreateunk// ") throw CreateUnknownNodeException();"
0x8d441  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d446  ldarg.0
0x8d447  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d44c  ldstr    aBoolIsemptywra// "bool isEmptyWrapper = Reader.IsEmptyEle"...
0x8d451  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d456  ldarg.0
0x8d457  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d45c  ldstr    aReaderReadstar// "Reader.ReadStartElement();"
0x8d461  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d466  ldloc.2
0x8d467  ldlen
0x8d468  conv.i4
0x8d469  newarr   Member
0x8d46e  stloc.s  6
0x8d470  ldc.i4.0
0x8d471  stloc.s  0xD
0x8d473  br       loc_8D593
0x8d478  ldloc.2
0x8d479  ldloc.s  0xD
0x8d47b  ldelem.ref
0x8d47c  stloc.s  0xE
0x8d47e  ldstr    aP_0// "p["
0x8d483  ldloca.s 0xD
0x8d485  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d48a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d48f  ldstr    asc_12BE9E// "]"
0x8d494  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d499  stloc.s  0xF
0x8d49b  ldloc.s  0xF
0x8d49d  stloc.s  0x10
0x8d49f  ldloc.s  0xE
0x8d4a1  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x8d4a6  brfalse.s loc_8D4E1
0x8d4a8  ldc.i4.5
0x8d4a9  newarr   [mscorlib]System.String
0x8d4ae  dup
0x8d4af  ldc.i4.0
0x8d4b0  ldstr    asc_12FF58// "(("
0x8d4b5  stelem.ref
0x8d4b6  dup
0x8d4b7  ldc.i4.1
0x8d4b8  ldloc.s  0xE
0x8d4ba  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x8d4bf  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8d4c4  stelem.ref
0x8d4c5  dup
0x8d4c6  ldc.i4.2
0x8d4c7  ldstr    asc_129CD8// ")"
0x8d4cc  stelem.ref
0x8d4cd  dup
0x8d4ce  ldc.i4.3
0x8d4cf  ldloc.s  0xF
0x8d4d1  stelem.ref
0x8d4d2  dup
0x8d4d3  ldc.i4.4
0x8d4d4  ldstr    asc_129CD8// ")"
0x8d4d9  stelem.ref
0x8d4da  call     string [mscorlib]System.String::Concat(string[])
0x8d4df  stloc.s  0x10
0x8d4e1  ldarg.0
0x8d4e2  ldloc.s  0xF
0x8d4e4  ldloc.s  0x10
0x8d4e6  ldstr    aA_0// "a"
0x8d4eb  ldloc.s  0xD
0x8d4ed  ldloc.s  0xE
0x8d4ef  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping)
0x8d4f4  stloc.s  0x11
0x8d4f6  ldloc.s  0xE
0x8d4f8  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x8d4fd  brtrue.s loc_8D521
0x8d4ff  ldloc.s  0x11
0x8d501  ldstr    aParamsread// "paramsRead["
0x8d506  ldloca.s 0xD
0x8d508  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d50d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d512  ldstr    asc_12BE9E// "]"
0x8d517  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d51c  callvirt instance void Member::set_ParamsReadSource(string value)
0x8d521  ldloc.s  6
0x8d523  ldloc.s  0xD
0x8d525  ldloc.s  0x11
0x8d527  stelem.ref
0x8d528  ldloc.s  0xE
0x8d52a  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x8d52f  ldc.i4.2
0x8d530  bne.un.s loc_8D58D
0x8d532  ldloc.s  0xE
0x8d534  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8d539  ldstr    aSpecified// "Specified"
0x8d53e  call     string [mscorlib]System.String::Concat(string, string)
0x8d543  stloc.s  0x12
0x8d545  ldc.i4.0
0x8d546  stloc.s  0x13
0x8d548  br.s     loc_8D586
0x8d54a  ldloc.2
0x8d54b  ldloc.s  0x13
0x8d54d  ldelem.ref
0x8d54e  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8d553  ldloc.s  0x12
0x8d555  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8d55a  brfalse.s loc_8D580
0x8d55c  ldloc.s  0x11
0x8d55e  ldstr    aP_0// "p["
0x8d563  ldloca.s 0x13
0x8d565  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d56a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d56f  ldstr    asc_12BE9E// "]"
0x8d574  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d579  callvirt instance void Member::set_CheckSpecifiedSource(string value)
0x8d57e  br.s     loc_8D58D
0x8d580  ldloc.s  0x13
0x8d582  ldc.i4.1
0x8d583  add
0x8d584  stloc.s  0x13
0x8d586  ldloc.s  0x13
0x8d588  ldloc.2
0x8d589  ldlen
0x8d58a  conv.i4
0x8d58b  blt.s    loc_8D54A
0x8d58d  ldloc.s  0xD
0x8d58f  ldc.i4.1
0x8d590  add
0x8d591  stloc.s  0xD
0x8d593  ldloc.s  0xD
0x8d595  ldloc.2
0x8d596  ldlen
0x8d597  conv.i4
0x8d598  blt      loc_8D478
0x8d59d  ldstr    aFixup// "fixup_"
0x8d5a2  ldloc.s  5
0x8d5a4  call     string [mscorlib]System.String::Concat(string, string)
0x8d5a9  stloc.s  7
0x8d5ab  ldarg.0
0x8d5ac  ldloc.s  6
0x8d5ae  ldloc.s  7
0x8d5b0  ldstr    aP// "p"
0x8d5b5  call     instance bool System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberFixupBegin(class Member[] members, string fixupMethodName, string source)
0x8d5ba  stloc.s  8
0x8d5bc  ldloc.s  6
0x8d5be  ldlen
0x8d5bf  brfalse.s loc_8D5E1
0x8d5c1  ldloc.s  6
0x8d5c3  ldc.i4.0
0x8d5c4  ldelem.ref
0x8d5c5  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8d5ca  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsReturnValue()
0x8d5cf  brfalse.s loc_8D5E1
0x8d5d1  ldarg.0
0x8d5d2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d5d7  ldstr    aIsreturnvalueT// "IsReturnValue = true;"
0x8d5dc  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d5e1  ldloc.3
0x8d5e2  brtrue.s loc_8D5E8
0x8d5e4  ldloc.s  4
0x8d5e6  brfalse.s loc_8D5EB
0x8d5e8  ldnull
0x8d5e9  br.s     loc_8D5F0
0x8d5eb  ldstr    aHreflist// "hrefList"
0x8d5f0  stloc.s  9
0x8d5f2  ldloc.s  9
0x8d5f4  brfalse.s loc_8D5FE
0x8d5f6  ldarg.0
0x8d5f7  ldloc.s  9
0x8d5f9  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteInitCheckTypeHrefList(string source)
0x8d5fe  ldarg.0
0x8d5ff  ldloc.2
0x8d600  ldlen
0x8d601  conv.i4
0x8d602  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteParamsRead(int32 length)
0x8d607  ldarg.0
0x8d608  call     instance int32 System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileNotLoopStart()
0x8d60d  stloc.s  0xA
0x8d60f  ldarg.0
0x8d610  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d615  dup
0x8d616  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8d61b  stloc.s  0xC
0x8d61d  ldloc.s  0xC
0x8d61f  ldc.i4.1
0x8d620  add
0x8d621  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8d626  ldloc.s  9
0x8d628  brfalse.s loc_8D631
0x8d62a  ldstr    aIfReaderGetatt// "if (Reader.GetAttribute(\"id\", null) !"...
0x8d62f  br.s     loc_8D636
0x8d631  ldstr    aUnknownnodeObj_0// "UnknownNode((object)p);"
0x8d636  stloc.s  0xB
0x8d638  ldarg.0
0x8d639  ldloc.s  6
0x8d63b  ldloc.s  0xB
0x8d63d  ldstr    aUnknownnodeObj_0// "UnknownNode((object)p);"
0x8d642  ldnull
0x8d643  ldnull
0x8d644  ldloc.s  9
0x8d646  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText, string checkTypeHrefsSource)
0x8d64b  ldarg.0
0x8d64c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d651  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x8d656  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d65b  ldarg.0
0x8d65c  ldloc.s  0xA
0x8d65e  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileLoopEnd(int32 loopIndex)
  ... truncated ...
```
