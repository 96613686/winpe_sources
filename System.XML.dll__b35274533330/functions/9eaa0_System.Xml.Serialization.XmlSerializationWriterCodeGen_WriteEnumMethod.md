# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumMethod

- ea: `0x9eaa0`
- end: `0x9ef9f`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumMethod`
- size: `1279`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x9d500`
- `0x9d6c0`

## callees

- `0x65610`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68ea0`
- `0x68ec0`
- `0x68f00`
- `0x68f30`
- `0x68f60`
- `0x72b90`
- `0x72ba0`
- `0x72d80`
- `0x86170`
- `0x861a0`
- `0x86200`
- `0x862f0`
- `0x9eaa0`
- `0xa2bf0`
- `0xa2c70`
- `0xa3c40`

## string_xrefs

- `0x9ee81`: `default: throw CreateInvalidEnumValueException(`
- `0x9ef15`: `WriteXsiType(`
- `0x9ef5d`: `Writer.WriteString(s);`

## pseudocode

```c

```

## disassembly

```asm
0x9eaa0  ldarg.0
0x9eaa1  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationCodeGen::get_MethodNames()
0x9eaa6  ldarg.1
0x9eaa7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9eaac  castclass [mscorlib]System.String
0x9eab1  stloc.0
0x9eab2  ldarg.0
0x9eab3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eab8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x9eabd  ldarg.1
0x9eabe  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9eac3  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9eac8  stloc.1
0x9eac9  ldarg.1
0x9eaca  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9eacf  brfalse.s loc_9EB1B
0x9ead1  ldarg.0
0x9ead2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ead7  ldstr    aVoid// "void "
0x9eadc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eae1  ldarg.0
0x9eae2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eae7  ldloc.0
0x9eae8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eaed  ldarg.0
0x9eaee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eaf3  ldstr    aObjectE_0// "(object e) {"
0x9eaf8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9eafd  ldarg.0
0x9eafe  ldloc.1
0x9eaff  ldstr    aV// "v"
0x9eb04  ldstr    aE// "e"
0x9eb09  ldarg.1
0x9eb0a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9eb0f  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9eb14  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteLocalDecl(string typeName, string variableName, string initValue, bool useReflection)
0x9eb19  br.s     loc_9EB77
0x9eb1b  ldarg.0
0x9eb1c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb21  ldstr    aString_1// "string "
0x9eb26  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eb2b  ldarg.0
0x9eb2c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb31  ldloc.0
0x9eb32  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eb37  ldarg.0
0x9eb38  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb3d  ldstr    asc_12DDFC// "("
0x9eb42  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eb47  ldarg.0
0x9eb48  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb4d  ldarg.1
0x9eb4e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9eb53  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9eb58  brtrue.s loc_9EB5D
0x9eb5a  ldloc.1
0x9eb5b  br.s     loc_9EB62
0x9eb5d  ldstr    aObject_3// "object"
0x9eb62  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9eb67  ldarg.0
0x9eb68  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb6d  ldstr    aV_0// " v) {"
0x9eb72  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9eb77  ldarg.0
0x9eb78  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb7d  dup
0x9eb7e  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9eb83  stloc.3
0x9eb84  ldloc.3
0x9eb85  ldc.i4.1
0x9eb86  add
0x9eb87  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9eb8c  ldarg.0
0x9eb8d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eb92  ldstr    aStringSNull// "string s = null;"
0x9eb97  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9eb9c  ldarg.1
0x9eb9d  callvirt instance class System.Xml.Serialization.ConstantMapping[] System.Xml.Serialization.EnumMapping::get_Constants()
0x9eba2  stloc.2
0x9eba3  ldloc.2
0x9eba4  ldlen
0x9eba5  brfalse  loc_9EF07
0x9ebaa  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x9ebaf  stloc.s  4
0x9ebb1  ldarg.1
0x9ebb2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9ebb7  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9ebbc  brfalse.s loc_9EBF5
0x9ebbe  ldarg.0
0x9ebbf  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ebc4  ldstr    aSwitch// "switch ("
0x9ebc9  ldarg.0
0x9ebca  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x9ebcf  ldstr    aV// "v"
0x9ebd4  ldarg.1
0x9ebd5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9ebda  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9ebdf  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForEnumLongValue(string variable, bool useReflection)
0x9ebe4  ldstr    asc_137BC2// " ){"
0x9ebe9  call     string [mscorlib]System.String::Concat(string, string, string)
0x9ebee  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ebf3  br.s     loc_9EC05
0x9ebf5  ldarg.0
0x9ebf6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ebfb  ldstr    aSwitchV// "switch (v) {"
0x9ec00  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ec05  ldarg.0
0x9ec06  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ec0b  dup
0x9ec0c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9ec11  stloc.3
0x9ec12  ldloc.3
0x9ec13  ldc.i4.1
0x9ec14  add
0x9ec15  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9ec1a  ldc.i4.0
0x9ec1b  stloc.s  5
0x9ec1d  br       loc_9ECA3
0x9ec22  ldloc.2
0x9ec23  ldloc.s  5
0x9ec25  ldelem.ref
0x9ec26  stloc.s  6
0x9ec28  ldloc.s  4
0x9ec2a  ldloc.s  6
0x9ec2c  callvirt instance int64 System.Xml.Serialization.ConstantMapping::get_Value()
0x9ec31  box      [mscorlib]System.Int64
0x9ec36  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9ec3b  brtrue.s loc_9EC9D
0x9ec3d  ldarg.0
0x9ec3e  ldloc.1
0x9ec3f  ldloc.s  6
0x9ec41  ldarg.1
0x9ec42  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9ec47  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9ec4c  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumCase(string fullTypeName, class System.Xml.Serialization.ConstantMapping c, bool useReflection)
0x9ec51  ldarg.0
0x9ec52  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ec57  ldstr    aS_0// "s = "
0x9ec5c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ec61  ldarg.0
0x9ec62  ldloc.s  6
0x9ec64  callvirt instance string System.Xml.Serialization.ConstantMapping::get_XmlName()
0x9ec69  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9ec6e  ldarg.0
0x9ec6f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ec74  ldstr    aBreak_0// "; break;"
0x9ec79  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ec7e  ldloc.s  4
0x9ec80  ldloc.s  6
0x9ec82  callvirt instance int64 System.Xml.Serialization.ConstantMapping::get_Value()
0x9ec87  box      [mscorlib]System.Int64
0x9ec8c  ldloc.s  6
0x9ec8e  callvirt instance int64 System.Xml.Serialization.ConstantMapping::get_Value()
0x9ec93  box      [mscorlib]System.Int64
0x9ec98  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9ec9d  ldloc.s  5
0x9ec9f  ldc.i4.1
0x9eca0  add
0x9eca1  stloc.s  5
0x9eca3  ldloc.s  5
0x9eca5  ldloc.2
0x9eca6  ldlen
0x9eca7  conv.i4
0x9eca8  blt      loc_9EC22
0x9ecad  ldarg.1
0x9ecae  callvirt instance bool System.Xml.Serialization.EnumMapping::get_IsFlags()
0x9ecb3  brfalse  loc_9EE7B
0x9ecb8  ldarg.0
0x9ecb9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ecbe  ldstr    aDefaultSFromen// "default: s = FromEnum("
0x9ecc3  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ecc8  ldarg.0
0x9ecc9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ecce  ldarg.0
0x9eccf  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x9ecd4  ldstr    aV// "v"
0x9ecd9  ldarg.1
0x9ecda  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9ecdf  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9ece4  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForEnumLongValue(string variable, bool useReflection)
0x9ece9  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ecee  ldarg.0
0x9ecef  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ecf4  ldstr    aNewString// ", new string[] {"
0x9ecf9  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ecfe  ldarg.0
0x9ecff  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ed04  dup
0x9ed05  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9ed0a  stloc.3
0x9ed0b  ldloc.3
0x9ed0c  ldc.i4.1
0x9ed0d  add
0x9ed0e  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9ed13  ldc.i4.0
0x9ed14  stloc.s  7
0x9ed16  br.s     loc_9ED46
0x9ed18  ldloc.2
0x9ed19  ldloc.s  7
0x9ed1b  ldelem.ref
0x9ed1c  stloc.s  8
0x9ed1e  ldloc.s  7
0x9ed20  ldc.i4.0
0x9ed21  ble.s    loc_9ED33
0x9ed23  ldarg.0
0x9ed24  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ed29  ldstr    asc_128826// ", "
0x9ed2e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ed33  ldarg.0
0x9ed34  ldloc.s  8
0x9ed36  callvirt instance string System.Xml.Serialization.ConstantMapping::get_XmlName()
0x9ed3b  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9ed40  ldloc.s  7
0x9ed42  ldc.i4.1
0x9ed43  add
0x9ed44  stloc.s  7
0x9ed46  ldloc.s  7
0x9ed48  ldloc.2
0x9ed49  ldlen
0x9ed4a  conv.i4
0x9ed4b  blt.s    loc_9ED18
0x9ed4d  ldarg.0
0x9ed4e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ed53  ldstr    aNew_2// "}, new "
0x9ed58  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ed5d  ldarg.0
0x9ed5e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ed63  ldtoken  [mscorlib]System.Int64
0x9ed68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9ed6d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9ed72  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ed77  ldarg.0
0x9ed78  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ed7d  ldstr    asc_137C60// "[] {"
0x9ed82  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ed87  ldc.i4.0
0x9ed88  stloc.s  9
0x9ed8a  br       loc_9EE29
0x9ed8f  ldloc.2
0x9ed90  ldloc.s  9
0x9ed92  ldelem.ref
0x9ed93  stloc.s  0xA
0x9ed95  ldloc.s  9
0x9ed97  ldc.i4.0
0x9ed98  ble.s    loc_9EDAA
0x9ed9a  ldarg.0
0x9ed9b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9eda0  ldstr    asc_128826// ", "
0x9eda5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9edaa  ldarg.0
0x9edab  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9edb0  ldstr    aLong_2// "(long)"
0x9edb5  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9edba  ldarg.1
0x9edbb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9edc0  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9edc5  brfalse.s loc_9EDE9
0x9edc7  ldarg.0
0x9edc8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9edcd  ldloc.s  0xA
0x9edcf  callvirt instance int64 System.Xml.Serialization.ConstantMapping::get_Value()
0x9edd4  stloc.s  0xB
0x9edd6  ldloca.s 0xB
0x9edd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9eddd  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x9ede2  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ede7  br.s     loc_9EE23
0x9ede9  ldarg.0
0x9edea  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9edef  ldloc.1
0x9edf0  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9edf5  ldarg.0
0x9edf6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9edfb  ldstr    asc_13444E// ".@"
0x9ee00  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ee05  ldloc.s  0xA
0x9ee07  callvirt instance string System.Xml.Serialization.ConstantMapping::get_Name()
0x9ee0c  call     void System.Xml.Serialization.CodeIdentifier::CheckValidIdentifier(string ident)
0x9ee11  ldarg.0
0x9ee12  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ee17  ldloc.s  0xA
0x9ee19  callvirt instance string System.Xml.Serialization.ConstantMapping::get_Name()
0x9ee1e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ee23  ldloc.s  9
0x9ee25  ldc.i4.1
0x9ee26  add
0x9ee27  stloc.s  9
0x9ee29  ldloc.s  9
0x9ee2b  ldloc.2
0x9ee2c  ldlen
0x9ee2d  conv.i4
0x9ee2e  blt      loc_9ED8F
0x9ee33  ldarg.0
0x9ee34  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ee39  dup
0x9ee3a  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9ee3f  stloc.3
0x9ee40  ldloc.3
0x9ee41  ldc.i4.1
0x9ee42  sub
  ... truncated ...
```
