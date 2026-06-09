# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteLiteralStructMethod

- ea: `0x8e9e0`
- end: `0x8f321`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteLiteralStructMethod`
- size: `2369`
- prototype: ``
- caller_count: `1`
- callee_count: `61`
- tags: `registry_config`

## callers

- `0x8e9c0`

## callees

- `0x622f0`
- `0x65610`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x691c0`
- `0x69420`
- `0x69600`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69b00`
- `0x69b20`
- `0x69bf0`
- `0x72b90`
- `0x72ba0`
- `0x72bf0`
- `0x72c20`
- `0x72d60`
- `0x72d80`
- `0x72dd0`
- `0x72e10`
- `0x72e40`
- `0x72e50`
- `0x74700`
- `0x86170`
- `0x861a0`
- `0x86200`
- `0x862f0`
- `0x8cbf0`
- `0x8e3b0`
- `0x8e4c0`
- `0x8e9e0`
- `0x8fba0`
- `0x8fd70`
- `0x90670`
- `0x90970`
- `0x90a90`
- `0x91070`
- `0x91950`
- `0x92ef0`

## string_xrefs

- `0x8f2c1`: `Reader.MoveToContent();`
- `0x8eed1`: `paramsRead[`
- `0x8f1ce`: `Reader.MoveToElement();`
- `0x8f250`: `Reader.ReadStartElement();`
- `0x8f2e1`: `ReadEndElement();`
- `0x8eae6`: `if (isNullable) isNull = ReadNull();`
- `0x8eb56`: `)ReadTypedNull(xsiType);`
- `0x8ec69`: `return ReadTypedPrimitive(new System.Xml.XmlQualifiedName("anyType", "http://www.w3.org/2001/XMLSchema"));`
- `0x8ecff`: `return ReadTypedPrimitive((`
- `0x8ed11`: `throw CreateUnknownTypeException((`
- `0x8ed9a`: `throw CreateAbstractTypeException(`
- `0x8efe3`: `XmlSequenceHierarchy`
- `0x8f1de`: `if (Reader.IsEmptyElement) {`
- `0x8f203`: `Reader.Skip();`

## pseudocode

```c

```

## disassembly

```asm
0x8e9e0  ldarg.0
0x8e9e1  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationCodeGen::get_MethodNames()
0x8e9e6  ldarg.1
0x8e9e7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8e9ec  castclass [mscorlib]System.String
0x8e9f1  stloc.0
0x8e9f2  ldarg.1
0x8e9f3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e9f8  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x8e9fd  stloc.1
0x8e9fe  ldloc.1
0x8e9ff  brtrue.s loc_8EA0E
0x8ea01  ldarg.1
0x8ea02  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ea07  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8ea0c  br.s     loc_8EA13
0x8ea0e  ldstr    aObject_3// "object"
0x8ea13  stloc.2
0x8ea14  ldarg.0
0x8ea15  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea1a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8ea1f  ldarg.0
0x8ea20  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea25  ldloc.2
0x8ea26  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ea2b  ldarg.0
0x8ea2c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea31  ldstr    asc_129382// " "
0x8ea36  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ea3b  ldarg.0
0x8ea3c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea41  ldloc.0
0x8ea42  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ea47  ldarg.0
0x8ea48  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea4d  ldstr    asc_12DDFC// "("
0x8ea52  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ea57  ldarg.1
0x8ea58  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ea5d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x8ea62  brfalse.s loc_8EA74
0x8ea64  ldarg.0
0x8ea65  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea6a  ldstr    aBoolIsnullable// "bool isNullable, "
0x8ea6f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ea74  ldarg.0
0x8ea75  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea7a  ldstr    aBoolChecktype_0// "bool checkType) {"
0x8ea7f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ea84  ldarg.0
0x8ea85  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea8a  dup
0x8ea8b  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ea90  stloc.3
0x8ea91  ldloc.3
0x8ea92  ldc.i4.1
0x8ea93  add
0x8ea94  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ea99  ldarg.0
0x8ea9a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ea9f  ldtoken  System.Xml.XmlQualifiedName
0x8eaa4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8eaa9  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8eaae  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8eab3  ldarg.0
0x8eab4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eab9  ldstr    aXsitypeCheckty// " xsiType = checkType ? GetXsiType() : n"...
0x8eabe  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8eac3  ldarg.0
0x8eac4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eac9  ldstr    aBoolIsnullFals// "bool isNull = false;"
0x8eace  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ead3  ldarg.1
0x8ead4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ead9  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x8eade  brfalse.s loc_8EAF0
0x8eae0  ldarg.0
0x8eae1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eae6  ldstr    aIfIsnullableIs// "if (isNullable) isNull = ReadNull();"
0x8eaeb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8eaf0  ldarg.0
0x8eaf1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eaf6  ldstr    aIfChecktype// "if (checkType) {"
0x8eafb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8eb00  ldarg.1
0x8eb01  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8eb06  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8eb0b  brfalse  loc_8EBED
0x8eb10  ldarg.0
0x8eb11  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb16  dup
0x8eb17  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8eb1c  stloc.3
0x8eb1d  ldloc.3
0x8eb1e  ldc.i4.1
0x8eb1f  add
0x8eb20  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8eb25  ldarg.0
0x8eb26  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb2b  ldstr    aIfIsnull// "if (isNull) {"
0x8eb30  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8eb35  ldarg.0
0x8eb36  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb3b  dup
0x8eb3c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8eb41  stloc.3
0x8eb42  ldloc.3
0x8eb43  ldc.i4.1
0x8eb44  add
0x8eb45  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8eb4a  ldarg.0
0x8eb4b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb50  ldstr    aIfXsitypeNullR// "if (xsiType != null) return ("
0x8eb55  ldloc.2
0x8eb56  ldstr    aReadtypednullX// ")ReadTypedNull(xsiType);"
0x8eb5b  call     string [mscorlib]System.String::Concat(string, string, string)
0x8eb60  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8eb65  ldarg.0
0x8eb66  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb6b  ldstr    aElseReturn// "else return "
0x8eb70  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8eb75  ldarg.1
0x8eb76  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8eb7b  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x8eb80  brfalse.s loc_8EBB8
0x8eb82  ldarg.0
0x8eb83  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eb88  ldarg.0
0x8eb89  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x8eb8e  ldarg.1
0x8eb8f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8eb94  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8eb99  ldloc.1
0x8eb9a  ldc.i4.0
0x8eb9b  ldc.i4.0
0x8eb9c  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForCreateInstance(string escapedTypeName, bool useReflection, bool ctorInaccessible, bool cast)
0x8eba1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8eba6  ldarg.0
0x8eba7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ebac  ldstr    asc_12B71A// ";"
0x8ebb1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ebb6  br.s     loc_8EBC8
0x8ebb8  ldarg.0
0x8ebb9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ebbe  ldstr    aNull_4// "null;"
0x8ebc3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ebc8  ldarg.0
0x8ebc9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ebce  dup
0x8ebcf  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ebd4  stloc.3
0x8ebd5  ldloc.3
0x8ebd6  ldc.i4.1
0x8ebd7  sub
0x8ebd8  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ebdd  ldarg.0
0x8ebde  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ebe3  ldstr    asc_12E936// "}"
0x8ebe8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ebed  ldarg.0
0x8ebee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ebf3  ldstr    aIfXsitypeNull// "if (xsiType == null"
0x8ebf8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ebfd  ldarg.1
0x8ebfe  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ec03  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8ec08  brtrue.s loc_8EC31
0x8ec0a  ldarg.0
0x8ec0b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec10  ldstr    asc_134946// " || "
0x8ec15  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ec1a  ldarg.0
0x8ec1b  ldstr    aXsitype// "xsiType"
0x8ec20  ldarg.1
0x8ec21  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x8ec26  ldarg.1
0x8ec27  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x8ec2c  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteQNameEqual(string source, string name, string ns)
0x8ec31  ldarg.0
0x8ec32  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec37  ldstr    asc_134612// ") {"
0x8ec3c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ec41  ldarg.1
0x8ec42  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ec47  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8ec4c  brfalse.s loc_8EC88
0x8ec4e  ldarg.0
0x8ec4f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec54  dup
0x8ec55  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ec5a  stloc.3
0x8ec5b  ldloc.3
0x8ec5c  ldc.i4.1
0x8ec5d  add
0x8ec5e  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ec63  ldarg.0
0x8ec64  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec69  ldstr    aReturnReadtype// "return ReadTypedPrimitive(new System.Xm"...
0x8ec6e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ec73  ldarg.0
0x8ec74  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec79  dup
0x8ec7a  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ec7f  stloc.3
0x8ec80  ldloc.3
0x8ec81  ldc.i4.1
0x8ec82  sub
0x8ec83  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ec88  ldarg.0
0x8ec89  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ec8e  ldstr    asc_12E936// "}"
0x8ec93  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ec98  ldarg.0
0x8ec99  ldarg.1
0x8ec9a  ldloc.1
0x8ec9b  brtrue.s loc_8ECAD
0x8ec9d  ldarg.1
0x8ec9e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8eca3  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8eca8  ldc.i4.0
0x8eca9  ceq
0x8ecab  br.s     loc_8ECAE
0x8ecad  ldc.i4.0
0x8ecae  ldloc.2
0x8ecaf  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteDerivedTypes(class System.Xml.Serialization.StructMapping mapping, bool isTypedReturn, string returnTypeName)
0x8ecb4  ldarg.1
0x8ecb5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ecba  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8ecbf  brfalse.s loc_8ECC7
0x8ecc1  ldarg.0
0x8ecc2  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteEnumAndArrayTypes()
0x8ecc7  ldarg.0
0x8ecc8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8eccd  ldstr    aElse_0// "else"
0x8ecd2  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ecd7  ldarg.0
0x8ecd8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ecdd  dup
0x8ecde  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ece3  stloc.3
0x8ece4  ldloc.3
0x8ece5  ldc.i4.1
0x8ece6  add
0x8ece7  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ecec  ldarg.1
0x8eced  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ecf2  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8ecf7  brfalse.s loc_8ED0B
0x8ecf9  ldarg.0
0x8ecfa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ecff  ldstr    aReturnReadtype_0// "return ReadTypedPrimitive(("
0x8ed04  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ed09  br.s     loc_8ED1B
0x8ed0b  ldarg.0
0x8ed0c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed11  ldstr    aThrowCreateunk_1// "throw CreateUnknownTypeException(("
0x8ed16  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ed1b  ldarg.0
0x8ed1c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed21  ldtoken  System.Xml.XmlQualifiedName
0x8ed26  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8ed2b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8ed30  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ed35  ldarg.0
0x8ed36  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed3b  ldstr    aXsitype_0// ")xsiType);"
0x8ed40  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ed45  ldarg.0
0x8ed46  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed4b  dup
0x8ed4c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ed51  stloc.3
0x8ed52  ldloc.3
0x8ed53  ldc.i4.1
0x8ed54  sub
0x8ed55  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ed5a  ldarg.0
0x8ed5b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed60  ldstr    asc_12E936// "}"
0x8ed65  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ed6a  ldarg.1
0x8ed6b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ed70  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x8ed75  brfalse.s loc_8ED87
0x8ed77  ldarg.0
0x8ed78  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed7d  ldstr    aIfIsnullReturn// "if (isNull) return null;"
0x8ed82  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ed87  ldarg.1
0x8ed88  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8ed8d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0x8ed92  brfalse.s loc_8EDE1
0x8ed94  ldarg.0
0x8ed95  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ed9a  ldstr    aThrowCreateabs// "throw CreateAbstractTypeException("
0x8ed9f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8eda4  ldarg.0
0x8eda5  ldarg.1
0x8eda6  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x8edab  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
  ... truncated ...
```
