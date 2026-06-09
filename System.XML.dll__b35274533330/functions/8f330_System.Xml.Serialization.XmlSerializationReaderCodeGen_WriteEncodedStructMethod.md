# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteEncodedStructMethod

- ea: `0x8f330`
- end: `0x8f64d`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteEncodedStructMethod`
- size: `797`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config`

## callers

- `0x8e9c0`

## callees

- `0x65610`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x69b00`
- `0x69b20`
- `0x69bf0`
- `0x72ba0`
- `0x72d60`
- `0x72d80`
- `0x72e50`
- `0x74700`
- `0x86170`
- `0x861a0`
- `0x86200`
- `0x862f0`
- `0x8cbf0`
- `0x8f330`
- `0x8f650`
- `0x8fd70`
- `0x90540`
- `0x90a90`
- `0x92ef0`
- `0x92f70`
- `0x93050`
- `0x93450`
- `0xa3cc0`
- `0x122a30`
- `0x122d50`
- `0x122d70`

## string_xrefs

- `0x8f5cb`: `Reader.MoveToContent();`
- `0x8f4f3`: `paramsRead[`
- `0x8f568`: `Reader.MoveToElement();`
- `0x8f588`: `Reader.ReadStartElement();`
- `0x8f5e3`: `ReadEndElement();`
- `0x8f3dd`: `throw CreateAbstractTypeException(`
- `0x8f578`: `if (Reader.IsEmptyElement) { Reader.Skip(); return o; }`

## pseudocode

```c

```

## disassembly

```asm
0x8f330  ldarg.1
0x8f331  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f336  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8f33b  brfalse.s loc_8F33E
0x8f33d  ret
0x8f33e  ldarg.1
0x8f33f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f344  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x8f349  stloc.0
0x8f34a  ldarg.0
0x8f34b  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationCodeGen::get_MethodNames()
0x8f350  ldarg.1
0x8f351  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8f356  castclass [mscorlib]System.String
0x8f35b  stloc.1
0x8f35c  ldarg.0
0x8f35d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f362  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8f367  ldarg.0
0x8f368  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f36d  ldstr    aObject_3// "object"
0x8f372  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f377  ldarg.0
0x8f378  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f37d  ldstr    asc_129382// " "
0x8f382  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f387  ldarg.0
0x8f388  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f38d  ldloc.1
0x8f38e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f393  ldarg.0
0x8f394  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f399  ldstr    asc_12DDFC// "("
0x8f39e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f3a3  ldarg.0
0x8f3a4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f3a9  ldstr    asc_134612// ") {"
0x8f3ae  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f3b3  ldarg.0
0x8f3b4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f3b9  dup
0x8f3ba  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8f3bf  stloc.s  5
0x8f3c1  ldloc.s  5
0x8f3c3  ldc.i4.1
0x8f3c4  add
0x8f3c5  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8f3ca  ldarg.1
0x8f3cb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f3d0  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0x8f3d5  brfalse.s loc_8F430
0x8f3d7  ldarg.0
0x8f3d8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f3dd  ldstr    aThrowCreateabs// "throw CreateAbstractTypeException("
0x8f3e2  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f3e7  ldarg.0
0x8f3e8  ldarg.1
0x8f3e9  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x8f3ee  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x8f3f3  ldarg.0
0x8f3f4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f3f9  ldstr    asc_128826// ", "
0x8f3fe  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8f403  ldarg.0
0x8f404  ldarg.1
0x8f405  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x8f40a  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x8f40f  ldarg.0
0x8f410  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f415  ldstr    asc_133068// ");"
0x8f41a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f41f  ldc.i4.0
0x8f420  newarr   Member
0x8f425  stloc.2
0x8f426  ldc.i4.0
0x8f427  stloc.3
0x8f428  ldnull
0x8f429  stloc.s  4
0x8f42b  br       loc_8F5FD
0x8f430  ldarg.0
0x8f431  ldarg.1
0x8f432  ldstr    aO_0// "o"
0x8f437  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteCreateMapping(class System.Xml.Serialization.TypeMapping mapping, string local)
0x8f43c  ldarg.1
0x8f43d  call     class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.TypeScope::GetSettableMembers(class System.Xml.Serialization.StructMapping structMapping)
0x8f442  stloc.s  6
0x8f444  ldloc.s  6
0x8f446  ldlen
0x8f447  conv.i4
0x8f448  newarr   Member
0x8f44d  stloc.2
0x8f44e  ldc.i4.0
0x8f44f  stloc.s  8
0x8f451  br       loc_8F51F
0x8f456  ldloc.s  6
0x8f458  ldloc.s  8
0x8f45a  ldelem.ref
0x8f45b  stloc.s  9
0x8f45d  ldloc.s  9
0x8f45f  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8f464  call     void System.Xml.Serialization.CodeIdentifier::CheckValidIdentifier(string ident)
0x8f469  ldarg.0
0x8f46a  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x8f46f  ldstr    aO_0// "o"
0x8f474  ldloc.s  9
0x8f476  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8f47b  ldarg.1
0x8f47c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f481  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForMember(string obj, string memberName, class System.Xml.Serialization.TypeDesc typeDesc)
0x8f486  stloc.s  0xA
0x8f488  ldarg.0
0x8f489  ldloc.s  0xA
0x8f48b  ldloc.s  0xA
0x8f48d  ldstr    aA_0// "a"
0x8f492  ldloc.s  8
0x8f494  ldloc.s  9
0x8f496  ldarg.0
0x8f497  ldloc.s  9
0x8f499  ldstr    aO_0// "o"
0x8f49e  ldarg.1
0x8f49f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f4a4  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::GetChoiceIdentifierSource(class System.Xml.Serialization.MemberMapping mapping, string parent, class System.Xml.Serialization.TypeDesc parentTypeDesc)
0x8f4a9  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, string choiceSource)
0x8f4ae  stloc.s  0xB
0x8f4b0  ldloc.s  9
0x8f4b2  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x8f4b7  ldc.i4.2
0x8f4b8  bne.un.s loc_8F4E8
0x8f4ba  ldloc.s  0xB
0x8f4bc  ldarg.0
0x8f4bd  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x8f4c2  ldstr    aO_0// "o"
0x8f4c7  ldloc.s  9
0x8f4c9  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x8f4ce  ldstr    aSpecified// "Specified"
0x8f4d3  call     string [mscorlib]System.String::Concat(string, string)
0x8f4d8  ldarg.1
0x8f4d9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f4de  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForMember(string obj, string memberName, class System.Xml.Serialization.TypeDesc typeDesc)
0x8f4e3  callvirt instance void Member::set_CheckSpecifiedSource(string value)
0x8f4e8  ldloc.s  9
0x8f4ea  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x8f4ef  brtrue.s loc_8F513
0x8f4f1  ldloc.s  0xB
0x8f4f3  ldstr    aParamsread// "paramsRead["
0x8f4f8  ldloca.s 8
0x8f4fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f4ff  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8f504  ldstr    asc_12BE9E// "]"
0x8f509  call     string [mscorlib]System.String::Concat(string, string, string)
0x8f50e  callvirt instance void Member::set_ParamsReadSource(string value)
0x8f513  ldloc.2
0x8f514  ldloc.s  8
0x8f516  ldloc.s  0xB
0x8f518  stelem.ref
0x8f519  ldloc.s  8
0x8f51b  ldc.i4.1
0x8f51c  add
0x8f51d  stloc.s  8
0x8f51f  ldloc.s  8
0x8f521  ldloc.s  6
0x8f523  ldlen
0x8f524  conv.i4
0x8f525  blt      loc_8F456
0x8f52a  ldstr    aFixup// "fixup_"
0x8f52f  ldloc.1
0x8f530  call     string [mscorlib]System.String::Concat(string, string)
0x8f535  stloc.s  4
0x8f537  ldarg.0
0x8f538  ldloc.2
0x8f539  ldloc.s  4
0x8f53b  ldstr    aO_0// "o"
0x8f540  call     instance bool System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberFixupBegin(class Member[] members, string fixupMethodName, string source)
0x8f545  stloc.3
0x8f546  ldarg.0
0x8f547  ldloc.s  6
0x8f549  ldlen
0x8f54a  conv.i4
0x8f54b  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteParamsRead(int32 length)
0x8f550  ldarg.0
0x8f551  ldloc.2
0x8f552  ldnull
0x8f553  ldstr    aUnknownnode// "UnknownNode"
0x8f558  ldstr    aObjectO// "(object)o"
0x8f55d  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttributes(class Member[] members, class Member anyAttribute, string elseCall, string firstParam)
0x8f562  ldarg.0
0x8f563  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f568  ldstr    aReaderMovetoel// "Reader.MoveToElement();"
0x8f56d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f572  ldarg.0
0x8f573  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f578  ldstr    aIfReaderIsempt_1// "if (Reader.IsEmptyElement) { Reader.Ski"...
0x8f57d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f582  ldarg.0
0x8f583  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f588  ldstr    aReaderReadstar// "Reader.ReadStartElement();"
0x8f58d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f592  ldarg.0
0x8f593  call     instance int32 System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileNotLoopStart()
0x8f598  stloc.s  7
0x8f59a  ldarg.0
0x8f59b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f5a0  dup
0x8f5a1  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8f5a6  stloc.s  5
0x8f5a8  ldloc.s  5
0x8f5aa  ldc.i4.1
0x8f5ab  add
0x8f5ac  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8f5b1  ldarg.0
0x8f5b2  ldloc.2
0x8f5b3  ldstr    aUnknownnodeObj_2// "UnknownNode((object)o);"
0x8f5b8  ldstr    aUnknownnodeObj_2// "UnknownNode((object)o);"
0x8f5bd  ldnull
0x8f5be  ldnull
0x8f5bf  ldnull
0x8f5c0  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText, string checkTypeHrefsSource)
0x8f5c5  ldarg.0
0x8f5c6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f5cb  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x8f5d0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f5d5  ldarg.0
0x8f5d6  ldloc.s  7
0x8f5d8  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileLoopEnd(int32 loopIndex)
0x8f5dd  ldarg.0
0x8f5de  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f5e3  ldstr    aReadendelement// "ReadEndElement();"
0x8f5e8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f5ed  ldarg.0
0x8f5ee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f5f3  ldstr    aReturnO// "return o;"
0x8f5f8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f5fd  ldarg.0
0x8f5fe  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f603  dup
0x8f604  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8f609  stloc.s  5
0x8f60b  ldloc.s  5
0x8f60d  ldc.i4.1
0x8f60e  sub
0x8f60f  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8f614  ldarg.0
0x8f615  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8f61a  ldstr    asc_12E936// "}"
0x8f61f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8f624  ldloc.3
0x8f625  brfalse.s loc_8F64C
0x8f627  ldarg.0
0x8f628  ldloc.s  4
0x8f62a  ldloc.2
0x8f62b  ldarg.1
0x8f62c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f631  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8f636  ldarg.1
0x8f637  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8f63c  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x8f641  ldc.i4.1
0x8f642  ldstr    aO_0// "o"
0x8f647  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteFixupMethod(string fixupMethodName, class Member[] members, string typeName, bool useReflection, bool typed, string source)
0x8f64c  ret
```
