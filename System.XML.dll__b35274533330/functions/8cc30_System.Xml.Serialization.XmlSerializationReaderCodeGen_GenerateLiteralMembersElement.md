# System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateLiteralMembersElement

- ea: `0x8cc30`
- end: `0x8d21c`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateLiteralMembersElement`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `45`
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
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69730`
- `0x69b00`
- `0x69b20`
- `0x69bb0`
- `0x69bf0`
- `0x69ce0`
- `0x69d20`
- `0x72ba0`
- `0x72dd0`
- `0x72e10`
- `0x79510`
- `0x86170`
- `0x8c780`
- `0x8c7e0`
- `0x8cb90`
- `0x8cc30`
- `0x8d220`
- `0x8da00`
- `0x8fd70`
- `0x90670`
- `0x90970`
- `0x90a90`
- `0x91070`
- `0x91950`
- `0x92ef0`
- `0x92f70`
- `0x93050`
- `0x122a30`
- `0x122c70`
- `0x122d50`
- `0x122d70`

## string_xrefs

- `0x8ccba`: `Reader.MoveToContent();`
- `0x8d165`: `Reader.MoveToContent();`
- `0x8d1d1`: `Reader.MoveToContent();`
- `0x8ce25`: `paramsRead[`
- `0x8d0c7`: `Reader.MoveToElement();`
- `0x8d0e2`: `if (Reader.IsEmptyElement) { Reader.Skip(); Reader.MoveToContent(); continue; }`
- `0x8d0f2`: `Reader.ReadStartElement();`
- `0x8d188`: `ReadEndElement();`

## pseudocode

```c

```

## disassembly

```asm
0x8cc30  ldarg.1
0x8cc31  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x8cc36  stloc.0
0x8cc37  ldloc.0
0x8cc38  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8cc3d  castclass System.Xml.Serialization.MembersMapping
0x8cc42  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x8cc47  stloc.1
0x8cc48  ldloc.0
0x8cc49  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8cc4e  castclass System.Xml.Serialization.MembersMapping
0x8cc53  callvirt instance bool System.Xml.Serialization.MembersMapping::get_HasWrapperElement()
0x8cc58  stloc.2
0x8cc59  ldarg.0
0x8cc5a  ldloc.0
0x8cc5b  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8cc60  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::NextMethodName(string name)
0x8cc65  stloc.3
0x8cc66  ldarg.0
0x8cc67  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cc6c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8cc71  ldarg.0
0x8cc72  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cc77  ldstr    aPublicObject// "public object[] "
0x8cc7c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8cc81  ldarg.0
0x8cc82  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cc87  ldloc.3
0x8cc88  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8cc8d  ldarg.0
0x8cc8e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cc93  ldstr    asc_133CB8// "() {"
0x8cc98  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8cc9d  ldarg.0
0x8cc9e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cca3  dup
0x8cca4  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8cca9  stloc.s  0xF
0x8ccab  ldloc.s  0xF
0x8ccad  ldc.i4.1
0x8ccae  add
0x8ccaf  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ccb4  ldarg.0
0x8ccb5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ccba  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x8ccbf  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ccc4  ldarg.0
0x8ccc5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ccca  ldstr    aObjectPNewObje// "object[] p = new object["
0x8cccf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ccd4  ldarg.0
0x8ccd5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ccda  ldloc.1
0x8ccdb  ldlen
0x8ccdc  conv.i4
0x8ccdd  stloc.s  0xF
0x8ccdf  ldloca.s 0xF
0x8cce1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8cce6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8cceb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ccf0  ldarg.0
0x8ccf1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ccf6  ldstr    asc_133D9E// "];"
0x8ccfb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8cd00  ldarg.0
0x8cd01  ldstr    aP// "p"
0x8cd06  ldloc.1
0x8cd07  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::InitializeValueTypes(string arrayName, class System.Xml.Serialization.MemberMapping[] mappings)
0x8cd0c  ldc.i4.0
0x8cd0d  stloc.s  4
0x8cd0f  ldloc.2
0x8cd10  brfalse.s loc_8CD53
0x8cd12  ldarg.0
0x8cd13  call     instance int32 System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileNotLoopStart()
0x8cd18  stloc.s  4
0x8cd1a  ldarg.0
0x8cd1b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8cd20  dup
0x8cd21  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8cd26  stloc.s  0xF
0x8cd28  ldloc.s  0xF
0x8cd2a  ldc.i4.1
0x8cd2b  add
0x8cd2c  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8cd31  ldarg.0
0x8cd32  ldloc.0
0x8cd33  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8cd38  ldloc.0
0x8cd39  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x8cd3e  ldc.i4.1
0x8cd3f  beq.s    loc_8CD48
0x8cd41  ldstr    asc_1284AE// ""
0x8cd46  br.s     loc_8CD4E
0x8cd48  ldloc.0
0x8cd49  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x8cd4e  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteIsStartTag(string name, string ns)
0x8cd53  ldnull
0x8cd54  stloc.s  5
0x8cd56  ldnull
0x8cd57  stloc.s  6
0x8cd59  ldnull
0x8cd5a  stloc.s  7
0x8cd5c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x8cd61  stloc.s  8
0x8cd63  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x8cd68  stloc.s  9
0x8cd6a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x8cd6f  stloc.s  0xA
0x8cd71  ldc.i4.0
0x8cd72  stloc.s  0x10
0x8cd74  br       loc_8D013
0x8cd79  ldloc.1
0x8cd7a  ldloc.s  0x10
0x8cd7c  ldelem.ref
0x8cd7d  stloc.s  0x11
0x8cd7f  ldstr    aP_0// "p["
0x8cd84  ldloca.s 0x10
0x8cd86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8cd8b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8cd90  ldstr    asc_12BE9E// "]"
0x8cd95  call     string [mscorlib]System.String::Concat(string, string, string)
0x8cd9a  stloc.s  0x12
0x8cd9c  ldloc.s  0x12
0x8cd9e  stloc.s  0x13
0x8cda0  ldloc.s  0x11
0x8cda2  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x8cda7  brfalse.s loc_8CDE2
0x8cda9  ldc.i4.5
0x8cdaa  newarr   [mscorlib]System.String
0x8cdaf  dup
0x8cdb0  ldc.i4.0
0x8cdb1  ldstr    asc_12FF58// "(("
0x8cdb6  stelem.ref
0x8cdb7  dup
0x8cdb8  ldc.i4.1
0x8cdb9  ldloc.s  0x11
0x8cdbb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x8cdc0  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8cdc5  stelem.ref
0x8cdc6  dup
0x8cdc7  ldc.i4.2
0x8cdc8  ldstr    asc_129CD8// ")"
0x8cdcd  stelem.ref
0x8cdce  dup
0x8cdcf  ldc.i4.3
0x8cdd0  ldloc.s  0x12
0x8cdd2  stelem.ref
0x8cdd3  dup
0x8cdd4  ldc.i4.4
0x8cdd5  ldstr    asc_129CD8// ")"
0x8cdda  stelem.ref
0x8cddb  call     string [mscorlib]System.String::Concat(string[])
0x8cde0  stloc.s  0x13
0x8cde2  ldarg.0
0x8cde3  ldloc.1
0x8cde4  ldloc.s  0x11
0x8cde6  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::GetChoiceIdentifierSource(class System.Xml.Serialization.MemberMapping[] mappings, class System.Xml.Serialization.MemberMapping member)
0x8cdeb  stloc.s  0x14
0x8cded  ldarg.0
0x8cdee  ldloc.s  0x12
0x8cdf0  ldloc.s  0x13
0x8cdf2  ldstr    aA_0// "a"
0x8cdf7  ldloc.s  0x10
0x8cdf9  ldloc.s  0x11
0x8cdfb  ldloc.s  0x14
0x8cdfd  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, string choiceSource)
0x8ce02  stloc.s  0x15
0x8ce04  ldarg.0
0x8ce05  ldloc.s  0x12
0x8ce07  ldnull
0x8ce08  ldstr    aA_0// "a"
0x8ce0d  ldloc.s  0x10
0x8ce0f  ldloc.s  0x11
0x8ce11  ldloc.s  0x14
0x8ce13  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, string choiceSource)
0x8ce18  stloc.s  0x16
0x8ce1a  ldloc.s  0x11
0x8ce1c  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x8ce21  brtrue.s loc_8CE45
0x8ce23  ldloc.s  0x15
0x8ce25  ldstr    aParamsread// "paramsRead["
0x8ce2a  ldloca.s 0x10
0x8ce2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ce31  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8ce36  ldstr    asc_12BE9E// "]"
0x8ce3b  call     string [mscorlib]System.String::Concat(string, string, string)
0x8ce40  callvirt instance void Member::set_ParamsReadSource(string value)
0x8ce45  ldloc.s  0x11
0x8ce47  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x8ce4c  ldc.i4.2
0x8ce4d  bne.un.s loc_8CEAA
0x8ce4f  ldloc.s  0x11
0x8ce51  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8ce56  ldstr    aSpecified// "Specified"
0x8ce5b  call     string [mscorlib]System.String::Concat(string, string)
0x8ce60  stloc.s  0x18
0x8ce62  ldc.i4.0
0x8ce63  stloc.s  0x19
0x8ce65  br.s     loc_8CEA3
0x8ce67  ldloc.1
0x8ce68  ldloc.s  0x19
0x8ce6a  ldelem.ref
0x8ce6b  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8ce70  ldloc.s  0x18
0x8ce72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8ce77  brfalse.s loc_8CE9D
0x8ce79  ldloc.s  0x15
0x8ce7b  ldstr    aP_0// "p["
0x8ce80  ldloca.s 0x19
0x8ce82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ce87  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8ce8c  ldstr    asc_12BE9E// "]"
0x8ce91  call     string [mscorlib]System.String::Concat(string, string, string)
0x8ce96  callvirt instance void Member::set_CheckSpecifiedSource(string value)
0x8ce9b  br.s     loc_8CEAA
0x8ce9d  ldloc.s  0x19
0x8ce9f  ldc.i4.1
0x8cea0  add
0x8cea1  stloc.s  0x19
0x8cea3  ldloc.s  0x19
0x8cea5  ldloc.1
0x8cea6  ldlen
0x8cea7  conv.i4
0x8cea8  blt.s    loc_8CE67
0x8ceaa  ldc.i4.0
0x8ceab  stloc.s  0x17
0x8cead  ldloc.s  0x11
0x8ceaf  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x8ceb4  brfalse.s loc_8CEBA
0x8ceb6  ldloc.s  0x16
0x8ceb8  stloc.s  5
0x8ceba  ldloc.s  0x11
0x8cebc  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x8cec1  brfalse.s loc_8CED5
0x8cec3  ldloc.s  0x11
0x8cec5  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x8ceca  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x8cecf  brfalse.s loc_8CED5
0x8ced1  ldloc.s  0x16
0x8ced3  stloc.s  7
0x8ced5  ldloc.s  0x11
0x8ced7  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x8cedc  brtrue.s loc_8CEE7
0x8cede  ldloc.s  0x11
0x8cee0  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x8cee5  brfalse.s loc_8CEF3
0x8cee7  ldloc.s  0xA
0x8cee9  ldloc.s  0x15
0x8ceeb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8cef0  pop
0x8cef1  br.s     loc_8CF06
0x8cef3  ldloc.s  0x11
0x8cef5  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x8cefa  brfalse.s loc_8CF06
0x8cefc  ldloc.s  9
0x8cefe  ldloc.s  0x15
0x8cf00  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8cf05  pop
0x8cf06  ldloc.s  0x11
0x8cf08  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x8cf0d  brtrue.s loc_8CF73
0x8cf0f  ldc.i4.0
0x8cf10  stloc.s  0x1A
0x8cf12  br.s     loc_8CF66
0x8cf14  ldloc.s  0x11
0x8cf16  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x8cf1b  ldloc.s  0x1A
0x8cf1d  ldelem.ref
0x8cf1e  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x8cf23  brfalse.s loc_8CF60
0x8cf25  ldloc.s  0x11
0x8cf27  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x8cf2c  ldloc.s  0x1A
0x8cf2e  ldelem.ref
0x8cf2f  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8cf34  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8cf39  brtrue.s loc_8CF60
0x8cf3b  ldloc.s  0x16
0x8cf3d  stloc.s  6
0x8cf3f  ldloc.s  0x11
0x8cf41  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x8cf46  brtrue.s loc_8CF5B
0x8cf48  ldloc.s  0x11
0x8cf4a  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x8cf4f  brtrue.s loc_8CF5B
0x8cf51  ldloc.s  9
0x8cf53  ldloc.s  0x16
0x8cf55  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8cf5a  pop
0x8cf5b  ldc.i4.1
0x8cf5c  stloc.s  0x17
0x8cf5e  br.s     loc_8CF73
0x8cf60  ldloc.s  0x1A
0x8cf62  ldc.i4.1
0x8cf63  add
0x8cf64  stloc.s  0x1A
0x8cf66  ldloc.s  0x1A
0x8cf68  ldloc.s  0x11
0x8cf6a  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x8cf6f  ldlen
  ... truncated ...
```
