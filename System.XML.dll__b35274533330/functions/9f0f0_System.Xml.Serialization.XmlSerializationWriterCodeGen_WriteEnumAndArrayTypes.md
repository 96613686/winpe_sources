# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumAndArrayTypes

- ea: `0x9f0f0`
- end: `0x9f46f`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumAndArrayTypes`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x9f470`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68de0`
- `0x72ba0`
- `0x72d80`
- `0x72e10`
- `0x72fd0`
- `0x74f30`
- `0x86170`
- `0x861f0`
- `0x86260`
- `0x862f0`
- `0x9f0f0`
- `0xa05c0`
- `0xa2c30`
- `0xa2c50`

## string_xrefs

- `0x9f1bf`: `WriteXsiType(`
- `0x9f398`: `WriteXsiType(`
- `0x9f1af`: `Writer.WriteStartElement(n, ns);`
- `0x9f388`: `Writer.WriteStartElement(n, ns);`
- `0x9f209`: `Writer.WriteString(`
- `0x9f270`: `Writer.WriteEndElement();`
- `0x9f3ff`: `Writer.WriteEndElement();`

## pseudocode

```c

```

## disassembly

```asm
0x9f0f0  ldarg.0
0x9f0f1  call     instance class System.Xml.Serialization.TypeScope[] System.Xml.Serialization.XmlSerializationCodeGen::get_Scopes()
0x9f0f6  stloc.0
0x9f0f7  ldc.i4.0
0x9f0f8  stloc.1
0x9f0f9  br       loc_9F465
0x9f0fe  ldloc.0
0x9f0ff  ldloc.1
0x9f100  ldelem.ref
0x9f101  stloc.2
0x9f102  ldloc.2
0x9f103  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.TypeScope::get_TypeMappings()
0x9f108  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9f10d  stloc.3
0x9f10e  br       loc_9F440
0x9f113  ldloc.3
0x9f114  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9f119  castclass System.Xml.Serialization.Mapping
0x9f11e  stloc.s  4
0x9f120  ldloc.s  4
0x9f122  isinst   System.Xml.Serialization.EnumMapping
0x9f127  brfalse  loc_9F2B6
0x9f12c  ldloc.s  4
0x9f12e  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9f133  brtrue   loc_9F2B6
0x9f138  ldloc.s  4
0x9f13a  castclass System.Xml.Serialization.EnumMapping
0x9f13f  stloc.s  5
0x9f141  ldloc.s  5
0x9f143  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f148  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9f14d  stloc.s  6
0x9f14f  ldarg.0
0x9f150  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f155  ldstr    aElseIf// "else if ("
0x9f15a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f15f  ldarg.0
0x9f160  ldstr    aT_0// "t"
0x9f165  ldloc.s  6
0x9f167  ldloc.s  5
0x9f169  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f16e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f173  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteTypeCompare(string variable, string escapedTypeName, bool useReflection)
0x9f178  ldarg.0
0x9f179  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f17e  ldstr    asc_134612// ") {"
0x9f183  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f188  ldarg.0
0x9f189  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f18e  dup
0x9f18f  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f194  stloc.s  8
0x9f196  ldloc.s  8
0x9f198  ldc.i4.1
0x9f199  add
0x9f19a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f19f  ldarg.0
0x9f1a0  ldloc.s  5
0x9f1a2  call     instance string System.Xml.Serialization.XmlSerializationCodeGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x9f1a7  stloc.s  7
0x9f1a9  ldarg.0
0x9f1aa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f1af  ldstr    aWriterWritesta// "Writer.WriteStartElement(n, ns);"
0x9f1b4  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f1b9  ldarg.0
0x9f1ba  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f1bf  ldstr    aWritexsitype// "WriteXsiType("
0x9f1c4  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f1c9  ldarg.0
0x9f1ca  ldloc.s  5
0x9f1cc  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x9f1d1  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9f1d6  ldarg.0
0x9f1d7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f1dc  ldstr    asc_128826// ", "
0x9f1e1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f1e6  ldarg.0
0x9f1e7  ldloc.s  5
0x9f1e9  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x9f1ee  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9f1f3  ldarg.0
0x9f1f4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f1f9  ldstr    asc_133068// ");"
0x9f1fe  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f203  ldarg.0
0x9f204  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f209  ldstr    aWriterWritestr_0// "Writer.WriteString("
0x9f20e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f213  ldarg.0
0x9f214  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f219  ldloc.s  7
0x9f21b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f220  ldarg.0
0x9f221  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f226  ldstr    asc_12DDFC// "("
0x9f22b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f230  ldloc.s  5
0x9f232  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f237  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f23c  brtrue.s loc_9F25A
0x9f23e  ldarg.0
0x9f23f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f244  ldstr    asc_12DDFC// "("
0x9f249  ldloc.s  6
0x9f24b  ldstr    asc_129CD8// ")"
0x9f250  call     string [mscorlib]System.String::Concat(string, string, string)
0x9f255  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f25a  ldarg.0
0x9f25b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f260  ldstr    aO_2// "o));"
0x9f265  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f26a  ldarg.0
0x9f26b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f270  ldstr    aWriterWriteend// "Writer.WriteEndElement();"
0x9f275  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f27a  ldarg.0
0x9f27b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f280  ldstr    aReturn_3// "return;"
0x9f285  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f28a  ldarg.0
0x9f28b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f290  dup
0x9f291  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f296  stloc.s  8
0x9f298  ldloc.s  8
0x9f29a  ldc.i4.1
0x9f29b  sub
0x9f29c  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f2a1  ldarg.0
0x9f2a2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f2a7  ldstr    asc_12E936// "}"
0x9f2ac  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f2b1  br       loc_9F440
0x9f2b6  ldloc.s  4
0x9f2b8  isinst   System.Xml.Serialization.ArrayMapping
0x9f2bd  brfalse  loc_9F440
0x9f2c2  ldloc.s  4
0x9f2c4  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9f2c9  brtrue   loc_9F440
0x9f2ce  ldloc.s  4
0x9f2d0  isinst   System.Xml.Serialization.ArrayMapping
0x9f2d5  stloc.s  9
0x9f2d7  ldloc.s  9
0x9f2d9  brfalse  loc_9F440
0x9f2de  ldloc.s  4
0x9f2e0  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9f2e5  brtrue   loc_9F440
0x9f2ea  ldloc.s  9
0x9f2ec  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f2f1  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9f2f6  stloc.s  0xA
0x9f2f8  ldarg.0
0x9f2f9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f2fe  ldstr    aElseIf// "else if ("
0x9f303  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f308  ldloc.s  9
0x9f30a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f30f  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArray()
0x9f314  brfalse.s loc_9F342
0x9f316  ldarg.0
0x9f317  ldstr    aT_0// "t"
0x9f31c  ldloc.s  0xA
0x9f31e  ldloc.s  9
0x9f320  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f325  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x9f32a  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9f32f  ldloc.s  9
0x9f331  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f336  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f33b  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteArrayTypeCompare(string variable, string escapedTypeName, string elementTypeName, bool useReflection)
0x9f340  br.s     loc_9F35B
0x9f342  ldarg.0
0x9f343  ldstr    aT_0// "t"
0x9f348  ldloc.s  0xA
0x9f34a  ldloc.s  9
0x9f34c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f351  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f356  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteTypeCompare(string variable, string escapedTypeName, bool useReflection)
0x9f35b  ldarg.0
0x9f35c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f361  ldstr    asc_134612// ") {"
0x9f366  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f36b  ldarg.0
0x9f36c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f371  dup
0x9f372  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f377  stloc.s  8
0x9f379  ldloc.s  8
0x9f37b  ldc.i4.1
0x9f37c  add
0x9f37d  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f382  ldarg.0
0x9f383  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f388  ldstr    aWriterWritesta// "Writer.WriteStartElement(n, ns);"
0x9f38d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f392  ldarg.0
0x9f393  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f398  ldstr    aWritexsitype// "WriteXsiType("
0x9f39d  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f3a2  ldarg.0
0x9f3a3  ldloc.s  9
0x9f3a5  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x9f3aa  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9f3af  ldarg.0
0x9f3b0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f3b5  ldstr    asc_128826// ", "
0x9f3ba  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f3bf  ldarg.0
0x9f3c0  ldloc.s  9
0x9f3c2  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x9f3c7  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9f3cc  ldarg.0
0x9f3cd  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f3d2  ldstr    asc_133068// ");"
0x9f3d7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f3dc  ldarg.0
0x9f3dd  ldstr    aO_0// "o"
0x9f3e2  ldnull
0x9f3e3  ldloc.s  9
0x9f3e5  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_ElementsSortedByDerivation()
0x9f3ea  ldnull
0x9f3eb  ldnull
0x9f3ec  ldloc.s  9
0x9f3ee  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f3f3  ldc.i4.1
0x9f3f4  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteMember(string source, string choiceSource, class System.Xml.Serialization.ElementAccessor[] elements, class System.Xml.Serialization.TextAccessor text, class System.Xml.Serialization.ChoiceIdentifierAccessor choice, class System.Xml.Serialization.TypeDesc memberTypeDesc, bool writeAccessors)
0x9f3f9  ldarg.0
0x9f3fa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f3ff  ldstr    aWriterWriteend// "Writer.WriteEndElement();"
0x9f404  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f409  ldarg.0
0x9f40a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f40f  ldstr    aReturn_3// "return;"
0x9f414  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f419  ldarg.0
0x9f41a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f41f  dup
0x9f420  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f425  stloc.s  8
0x9f427  ldloc.s  8
0x9f429  ldc.i4.1
0x9f42a  sub
0x9f42b  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f430  ldarg.0
0x9f431  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f436  ldstr    asc_12E936// "}"
0x9f43b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f440  ldloc.3
0x9f441  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9f446  brtrue   loc_9F113
0x9f44b  leave.s  loc_9F461
0x9f44d  ldloc.3
0x9f44e  isinst   [mscorlib]System.IDisposable
0x9f453  stloc.s  0xB
0x9f455  ldloc.s  0xB
0x9f457  brfalse.s loc_9F460
0x9f459  ldloc.s  0xB
0x9f45b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9f460  endfinally
0x9f461  ldloc.1
0x9f462  ldc.i4.1
0x9f463  add
0x9f464  stloc.1
0x9f465  ldloc.1
0x9f466  ldloc.0
0x9f467  ldlen
0x9f468  conv.i4
0x9f469  blt      loc_9F0FE
0x9f46e  ret
```
