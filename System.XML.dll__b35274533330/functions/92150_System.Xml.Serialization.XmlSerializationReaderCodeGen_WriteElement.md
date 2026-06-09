# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteElement

- ea: `0x92150`
- end: `0x92be0`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteElement`
- size: `2704`
- prototype: ``
- caller_count: `3`
- callee_count: `48`
- tags: `registry_config`

## callers

- `0x8e7f0`
- `0x90fe0`
- `0x910a0`

## callees

- `0xc240`
- `0x13310`
- `0x13320`
- `0x62370`
- `0x65610`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68620`
- `0x68690`
- `0x688b0`
- `0x689b0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x69ff0`
- `0x6a070`
- `0x72b90`
- `0x72ba0`
- `0x72bf0`
- `0x72c00`
- `0x72c10`
- `0x72c20`
- `0x72d40`
- `0x72d80`
- `0x72e40`
- `0x86170`
- `0x861a0`
- `0x861c0`
- `0x86260`
- `0x87090`
- `0x8c7e0`
- `0x8da80`
- `0x8fba0`
- `0x8fd20`
- `0x91c40`
- `0x91c90`
- `0x91ce0`
- `0x91d30`
- `0x92150`
- `0x92be0`
- `0x93190`
- `0x93660`
- `0xa3d60`
- `0xa3e50`

## string_xrefs

- `0x92b37`: `XmlInternalError`
- `0x92b47`: `XmlInternalError`
- `0x92340`: `if (Reader.IsEmptyElement) {`
- `0x92400`: `if (Reader.IsEmptyElement) {`
- `0x92365`: `Reader.Skip();`
- `0x92425`: `Reader.Skip();`
- `0x92617`: `ReadReferencedElement`
- `0x9261e`: `ReadReferencingElement`
- `0x9223c`: `if (ReadNull()) {`
- `0x924b6`: `Reader.ReadElementString()`
- `0x92562`: `Reader.ReadElementString()`
- `0x92522`: `ReadElementQualifiedName()`
- `0x927fc`: `) == null) Reader.Skip(); else `
- `0x9290c`: `ReadXmlNode(`
- `0x92913`: `ReadXmlDocument(`
- `0x92a29`: `ReadSerializable(( `

## pseudocode

```c

```

## disassembly

```asm
0x92150  ldarg.s  6
0x92152  brfalse.s loc_9217B
0x92154  ldarg.s  6
0x92156  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9215b  ldc.i4.0
0x9215c  ble.s    loc_9217B
0x9215e  ldarg.0
0x9215f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92164  ldarg.s  6
0x92166  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9216b  ldarg.0
0x9216c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92171  ldstr    aTrue_1// " = true;"
0x92176  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9217b  ldarg.s  4
0x9217d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92182  isinst   System.Xml.Serialization.ArrayMapping
0x92187  brfalse.s loc_921AD
0x92189  ldarg.0
0x9218a  ldarg.1
0x9218b  ldarg.2
0x9218c  ldarg.s  4
0x9218e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92193  castclass System.Xml.Serialization.ArrayMapping
0x92198  ldarg.s  8
0x9219a  ldarg.s  4
0x9219c  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0x921a1  ldarg.s  9
0x921a3  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteArray(string source, string arrayName, class System.Xml.Serialization.ArrayMapping arrayMapping, bool readOnly, bool isNullable, int32 fixupIndex)
0x921a8  br       loc_92B57
0x921ad  ldarg.s  4
0x921af  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x921b4  isinst   System.Xml.Serialization.NullableMapping
0x921b9  brfalse.s loc_92208
0x921bb  ldarg.0
0x921bc  ldarg.s  4
0x921be  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x921c3  call     instance string System.Xml.Serialization.XmlSerializationCodeGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x921c8  stloc.0
0x921c9  ldarg.0
0x921ca  ldarg.1
0x921cb  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x921d0  ldarg.0
0x921d1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x921d6  ldloc.0
0x921d7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x921dc  ldarg.0
0x921dd  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x921e2  ldstr    aTrue_3// "(true)"
0x921e7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x921ec  ldarg.0
0x921ed  ldarg.1
0x921ee  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x921f3  ldarg.0
0x921f4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x921f9  ldstr    asc_12B71A// ";"
0x921fe  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92203  br       loc_92B57
0x92208  ldarg.s  4
0x9220a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x9220f  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x92214  brtrue   loc_925B7
0x92219  ldarg.s  4
0x9221b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92220  isinst   System.Xml.Serialization.PrimitiveMapping
0x92225  brfalse  loc_925B7
0x9222a  ldarg.s  4
0x9222c  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0x92231  brfalse  loc_9230D
0x92236  ldarg.0
0x92237  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9223c  ldstr    aIfReadnull_1// "if (ReadNull()) {"
0x92241  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92246  ldarg.0
0x92247  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9224c  dup
0x9224d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92252  stloc.1
0x92253  ldloc.1
0x92254  ldc.i4.1
0x92255  add
0x92256  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9225b  ldarg.0
0x9225c  ldarg.1
0x9225d  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x92262  ldarg.s  4
0x92264  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92269  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9226e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x92273  brfalse.s loc_922B1
0x92275  ldarg.0
0x92276  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9227b  ldarg.0
0x9227c  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x92281  ldarg.s  4
0x92283  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92288  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9228d  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x92292  ldarg.s  4
0x92294  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x92299  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9229e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x922a3  ldc.i4.0
0x922a4  ldc.i4.0
0x922a5  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForCreateInstance(string escapedTypeName, bool useReflection, bool ctorInaccessible, bool cast)
0x922aa  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x922af  br.s     loc_922C1
0x922b1  ldarg.0
0x922b2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x922b7  ldstr    aNull_0// "null"
0x922bc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x922c1  ldarg.0
0x922c2  ldarg.1
0x922c3  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x922c8  ldarg.0
0x922c9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x922ce  ldstr    asc_12B71A// ";"
0x922d3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x922d8  ldarg.0
0x922d9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x922de  dup
0x922df  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x922e4  stloc.1
0x922e5  ldloc.1
0x922e6  ldc.i4.1
0x922e7  sub
0x922e8  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x922ed  ldarg.0
0x922ee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x922f3  ldstr    asc_12E936// "}"
0x922f8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x922fd  ldarg.0
0x922fe  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92303  ldstr    aElse_1// "else "
0x92308  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9230d  ldarg.s  4
0x9230f  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x92314  brfalse  loc_923A6
0x92319  ldarg.s  4
0x9231b  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x92320  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x92325  beq.s    loc_923A6
0x92327  ldarg.s  4
0x92329  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x9232e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92333  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x92338  brfalse.s loc_923A6
0x9233a  ldarg.0
0x9233b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92340  ldstr    aIfReaderIsempt_0// "if (Reader.IsEmptyElement) {"
0x92345  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9234a  ldarg.0
0x9234b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92350  dup
0x92351  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92356  stloc.1
0x92357  ldloc.1
0x92358  ldc.i4.1
0x92359  add
0x9235a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9235f  ldarg.0
0x92360  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92365  ldstr    aReaderSkip// "Reader.Skip();"
0x9236a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9236f  ldarg.0
0x92370  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92375  dup
0x92376  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9237b  stloc.1
0x9237c  ldloc.1
0x9237d  ldc.i4.1
0x9237e  sub
0x9237f  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92384  ldarg.0
0x92385  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9238a  ldstr    asc_12E936// "}"
0x9238f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92394  ldarg.0
0x92395  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9239a  ldstr    aElse// "else {"
0x9239f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x923a4  br.s     loc_923B6
0x923a6  ldarg.0
0x923a7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x923ac  ldstr    asc_12FB82// "{"
0x923b1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x923b6  ldarg.0
0x923b7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x923bc  dup
0x923bd  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x923c2  stloc.1
0x923c3  ldloc.1
0x923c4  ldc.i4.1
0x923c5  add
0x923c6  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x923cb  ldarg.s  4
0x923cd  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x923d2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x923d7  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x923dc  ldtoken  [mscorlib]System.TimeSpan
0x923e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x923e6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x923eb  brfalse  loc_92501
0x923f0  call     bool System.LocalAppContextSwitches::get_EnableTimeSpanSerialization()
0x923f5  brfalse  loc_92501
0x923fa  ldarg.0
0x923fb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92400  ldstr    aIfReaderIsempt_0// "if (Reader.IsEmptyElement) {"
0x92405  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9240a  ldarg.0
0x9240b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92410  dup
0x92411  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92416  stloc.1
0x92417  ldloc.1
0x92418  ldc.i4.1
0x92419  add
0x9241a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9241f  ldarg.0
0x92420  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92425  ldstr    aReaderSkip// "Reader.Skip();"
0x9242a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9242f  ldarg.0
0x92430  ldarg.1
0x92431  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x92436  ldarg.0
0x92437  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9243c  ldstr    aDefaultSystemT// "default(System.TimeSpan)"
0x92441  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92446  ldarg.0
0x92447  ldarg.1
0x92448  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x9244d  ldarg.0
0x9244e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92453  ldstr    asc_12B71A// ";"
0x92458  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9245d  ldarg.0
0x9245e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92463  dup
0x92464  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92469  stloc.1
0x9246a  ldloc.1
0x9246b  ldc.i4.1
0x9246c  sub
0x9246d  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92472  ldarg.0
0x92473  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92478  ldstr    asc_12E936// "}"
0x9247d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92482  ldarg.0
0x92483  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92488  ldstr    aElse// "else {"
0x9248d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92492  ldarg.0
0x92493  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92498  dup
0x92499  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9249e  stloc.1
0x9249f  ldloc.1
0x924a0  ldc.i4.1
0x924a1  add
0x924a2  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x924a7  ldarg.0
0x924a8  ldarg.1
0x924a9  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x924ae  ldarg.0
0x924af  ldarg.s  4
0x924b1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x924b6  ldstr    aReaderReadelem// "Reader.ReadElementString()"
0x924bb  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x924c0  ldarg.0
0x924c1  ldarg.1
0x924c2  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x924c7  ldarg.0
0x924c8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x924cd  ldstr    asc_12B71A// ";"
0x924d2  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x924d7  ldarg.0
0x924d8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x924dd  dup
0x924de  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x924e3  stloc.1
0x924e4  ldloc.1
0x924e5  ldc.i4.1
0x924e6  sub
0x924e7  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x924ec  ldarg.0
0x924ed  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x924f2  ldstr    asc_12E936// "}"
0x924f7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x924fc  br       loc_9258D
0x92501  ldarg.0
0x92502  ldarg.1
0x92503  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x92508  ldarg.s  4
0x9250a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x9250f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92514  ldarg.0
0x92515  call     instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.XmlSerializationCodeGen::get_QnameTypeDesc()
0x9251a  bne.un.s loc_9252E
  ... truncated ...
```
