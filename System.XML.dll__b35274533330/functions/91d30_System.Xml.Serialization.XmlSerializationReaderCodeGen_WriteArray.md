# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteArray

- ea: `0x91d30`
- end: `0x92146`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteArray`
- size: `1046`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x8e4c0`
- `0x92150`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68dc0`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x69be0`
- `0x72df0`
- `0x72e00`
- `0x86170`
- `0x8f8c0`
- `0x8fd20`
- `0x90670`
- `0x90970`
- `0x90a90`
- `0x91950`
- `0x91960`
- `0x91c40`
- `0x91ce0`
- `0x91d30`
- `0x92ef0`
- `0x92f70`
- `0x93660`
- `0x122a50`
- `0x122c90`
- `0x122cf0`

## string_xrefs

- `0x9206b`: `Reader.MoveToContent();`
- `0x92016`: `Reader.ReadStartElement();`
- `0x92098`: `ReadEndElement();`
- `0x91fbc`: `Reader.Skip();`
- `0x91d56`: `ReadReferencedElement`
- `0x91d5d`: `ReadReferencingElement`
- `0x91ede`: `if (!ReadNull()) {`
- `0x91f97`: `(Reader.IsEmptyElement)) {`

## pseudocode

```c

```

## disassembly

```asm
0x91d30  ldarg.3
0x91d31  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x91d36  brfalse  loc_91ED8
0x91d3b  ldarg.0
0x91d3c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91d41  ldstr    aObjectRre// "object rre = "
0x91d46  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91d4b  ldarg.0
0x91d4c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91d51  ldarg.s  6
0x91d53  ldc.i4.0
0x91d54  bge.s    loc_91D5D
0x91d56  ldstr    aReadreferenced_0// "ReadReferencedElement"
0x91d5b  br.s     loc_91D62
0x91d5d  ldstr    aReadreferencin// "ReadReferencingElement"
0x91d62  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91d67  ldarg.0
0x91d68  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91d6d  ldstr    asc_12DDFC// "("
0x91d72  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91d77  ldarg.0
0x91d78  ldarg.3
0x91d79  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x91d7e  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteID(string name)
0x91d83  ldarg.0
0x91d84  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91d89  ldstr    asc_128826// ", "
0x91d8e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91d93  ldarg.0
0x91d94  ldarg.3
0x91d95  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x91d9a  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteID(string name)
0x91d9f  ldarg.s  6
0x91da1  ldc.i4.0
0x91da2  blt.s    loc_91DEB
0x91da4  ldarg.0
0x91da5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91daa  ldstr    asc_128826// ", "
0x91daf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91db4  ldarg.0
0x91db5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91dba  ldstr    aOutFixupIds// "out fixup.Ids["
0x91dbf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91dc4  ldarg.0
0x91dc5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91dca  ldarga.s 6
0x91dcc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91dd1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x91dd6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91ddb  ldarg.0
0x91ddc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91de1  ldstr    asc_12BE9E// "]"
0x91de6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91deb  ldarg.0
0x91dec  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91df1  ldstr    asc_133068// ");"
0x91df6  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91dfb  ldarg.3
0x91dfc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x91e01  stloc.0
0x91e02  ldloc.0
0x91e03  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnumerable()
0x91e08  brtrue.s loc_91E12
0x91e0a  ldloc.0
0x91e0b  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsCollection()
0x91e10  brfalse.s loc_91E6C
0x91e12  ldarg.0
0x91e13  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e18  ldstr    aIfRreNull// "if (rre != null) {"
0x91e1d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91e22  ldarg.0
0x91e23  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e28  dup
0x91e29  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91e2e  stloc.1
0x91e2f  ldloc.1
0x91e30  ldc.i4.1
0x91e31  add
0x91e32  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91e37  ldarg.0
0x91e38  ldloc.0
0x91e39  ldarg.s  4
0x91e3b  ldarg.1
0x91e3c  ldstr    aRre// "rre"
0x91e41  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAddCollectionFixup(class System.Xml.Serialization.TypeDesc typeDesc, bool readOnly, string memberSource, string targetSource)
0x91e46  ldarg.0
0x91e47  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e4c  dup
0x91e4d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91e52  stloc.1
0x91e53  ldloc.1
0x91e54  ldc.i4.1
0x91e55  sub
0x91e56  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91e5b  ldarg.0
0x91e5c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e61  ldstr    asc_12E936// "}"
0x91e66  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91e6b  ret
0x91e6c  ldarg.0
0x91e6d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e72  ldstr    aTry// "try {"
0x91e77  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91e7c  ldarg.0
0x91e7d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91e82  dup
0x91e83  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91e88  stloc.1
0x91e89  ldloc.1
0x91e8a  ldc.i4.1
0x91e8b  add
0x91e8c  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91e91  ldarg.0
0x91e92  ldarg.1
0x91e93  ldarg.3
0x91e94  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x91e99  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBeginTyped(string source, class System.Xml.Serialization.TypeDesc typeDesc)
0x91e9e  ldarg.0
0x91e9f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91ea4  ldstr    aRre// "rre"
0x91ea9  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91eae  ldarg.0
0x91eaf  ldarg.1
0x91eb0  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x91eb5  ldarg.0
0x91eb6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91ebb  ldstr    asc_12B71A// ";"
0x91ec0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91ec5  ldarg.0
0x91ec6  ldarg.3
0x91ec7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x91ecc  ldstr    aRre// "rre"
0x91ed1  ldnull
0x91ed2  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteCatchCastException(class System.Xml.Serialization.TypeDesc typeDesc, string source, string id)
0x91ed7  ret
0x91ed8  ldarg.0
0x91ed9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91ede  ldstr    aIfReadnull_0// "if (!ReadNull()) {"
0x91ee3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91ee8  ldarg.0
0x91ee9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91eee  dup
0x91eef  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91ef4  stloc.1
0x91ef5  ldloc.1
0x91ef6  ldc.i4.1
0x91ef7  add
0x91ef8  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91efd  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x91f02  stloc.2
0x91f03  ldloc.2
0x91f04  ldarg.3
0x91f05  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x91f0a  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x91f0f  ldloc.2
0x91f10  ldarg.3
0x91f11  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x91f16  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x91f1b  ldloc.2
0x91f1c  ldarg.s  4
0x91f1e  callvirt instance void System.Xml.Serialization.MemberMapping::set_ReadOnly(bool value)
0x91f23  ldarg.0
0x91f24  ldarg.1
0x91f25  ldarg.2
0x91f26  ldc.i4.0
0x91f27  ldloc.2
0x91f28  ldc.i4.0
0x91f29  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, bool multiRef)
0x91f2e  stloc.3
0x91f2f  ldloc.3
0x91f30  ldc.i4.0
0x91f31  callvirt instance void Member::set_IsNullable(bool value)
0x91f36  ldc.i4.1
0x91f37  newarr   Member
0x91f3c  dup
0x91f3d  ldc.i4.0
0x91f3e  ldloc.3
0x91f3f  stelem.ref
0x91f40  stloc.s  4
0x91f42  ldarg.0
0x91f43  ldloc.s  4
0x91f45  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberBegin(class Member[] members)
0x91f4a  ldarg.s  4
0x91f4c  brfalse.s loc_91F81
0x91f4e  ldarg.0
0x91f4f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91f54  ldstr    aIfObject_1// "if (((object)("
0x91f59  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91f5e  ldarg.0
0x91f5f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91f64  ldloc.3
0x91f65  callvirt instance string Member::get_ArrayName()
0x91f6a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91f6f  ldarg.0
0x91f70  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91f75  ldstr    aNull_9// ") == null) || "
0x91f7a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91f7f  br.s     loc_91F91
0x91f81  ldarg.0
0x91f82  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91f87  ldstr    aIf// "if ("
0x91f8c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x91f91  ldarg.0
0x91f92  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91f97  ldstr    aReaderIsemptye// "(Reader.IsEmptyElement)) {"
0x91f9c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91fa1  ldarg.0
0x91fa2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91fa7  dup
0x91fa8  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91fad  stloc.1
0x91fae  ldloc.1
0x91faf  ldc.i4.1
0x91fb0  add
0x91fb1  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91fb6  ldarg.0
0x91fb7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91fbc  ldstr    aReaderSkip// "Reader.Skip();"
0x91fc1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91fc6  ldarg.0
0x91fc7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91fcc  dup
0x91fcd  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x91fd2  stloc.1
0x91fd3  ldloc.1
0x91fd4  ldc.i4.1
0x91fd5  sub
0x91fd6  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x91fdb  ldarg.0
0x91fdc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91fe1  ldstr    asc_12E936// "}"
0x91fe6  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91feb  ldarg.0
0x91fec  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x91ff1  ldstr    aElse// "else {"
0x91ff6  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x91ffb  ldarg.0
0x91ffc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92001  dup
0x92002  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92007  stloc.1
0x92008  ldloc.1
0x92009  ldc.i4.1
0x9200a  add
0x9200b  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92010  ldarg.0
0x92011  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92016  ldstr    aReaderReadstar// "Reader.ReadStartElement();"
0x9201b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92020  ldarg.0
0x92021  call     instance int32 System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileNotLoopStart()
0x92026  stloc.s  5
0x92028  ldarg.0
0x92029  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9202e  dup
0x9202f  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92034  stloc.1
0x92035  ldloc.1
0x92036  ldc.i4.1
0x92037  add
0x92038  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9203d  ldstr    aUnknownnodeNul_0// "UnknownNode(null, "
0x92042  ldarg.0
0x92043  ldloc.s  4
0x92045  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::ExpectedElements(class Member[] members)
0x9204a  ldstr    asc_133068// ");"
0x9204f  call     string [mscorlib]System.String::Concat(string, string, string)
0x92054  stloc.s  6
0x92056  ldarg.0
0x92057  ldloc.s  4
0x92059  ldloc.s  6
0x9205b  ldloc.s  6
0x9205d  ldnull
0x9205e  ldnull
0x9205f  ldnull
0x92060  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText, string checkTypeHrefsSource)
0x92065  ldarg.0
0x92066  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9206b  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x92070  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92075  ldarg.0
0x92076  ldloc.s  5
0x92078  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileLoopEnd(int32 loopIndex)
0x9207d  ldarg.0
0x9207e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92083  dup
0x92084  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92089  stloc.1
0x9208a  ldloc.1
0x9208b  ldc.i4.1
0x9208c  sub
0x9208d  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92092  ldarg.0
0x92093  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92098  ldstr    aReadendelement// "ReadEndElement();"
0x9209d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x920a2  ldarg.0
0x920a3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x920a8  ldstr    asc_12E936// "}"
0x920ad  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
  ... truncated ...
```
