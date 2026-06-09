# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteDerivedSerializable

- ea: `0x92be0`
- end: `0x92eef`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteDerivedSerializable`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x92150`
- `0x92be0`

## callees

- `0x13310`
- `0x13320`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68c50`
- `0x69ff0`
- `0x6a000`
- `0x6a030`
- `0x6a070`
- `0x72ba0`
- `0x72d40`
- `0x72d80`
- `0x86170`
- `0x861a0`
- `0x862f0`
- `0x8fba0`
- `0x91c40`
- `0x91ce0`
- `0x92be0`
- `0xa3e50`

## string_xrefs

- `0x92c90`: `ReadSerializable(( `
- `0x92d42`: `throw CreateBadDerivationException(`
- `0x92e44`: `throw CreateMissingIXmlSerializableType(`

## pseudocode

```c

```

## disassembly

```asm
0x92be0  ldarg.2
0x92be1  brtrue.s loc_92BE4
0x92be3  ret
0x92be4  ldarg.2
0x92be5  callvirt instance class System.Xml.Serialization.SerializableMapping System.Xml.Serialization.SerializableMapping::get_DerivedMappings()
0x92bea  stloc.0
0x92beb  br       loc_92EE8
0x92bf0  ldarg.0
0x92bf1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92bf6  ldstr    aElseIfTserNull// "else if (tser == null"
0x92bfb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92c00  ldarg.0
0x92c01  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92c06  ldstr    asc_134946// " || "
0x92c0b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92c10  ldarg.0
0x92c11  ldstr    aTser// "tser"
0x92c16  ldloc.0
0x92c17  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92c1c  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x92c21  ldloc.0
0x92c22  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92c27  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x92c2c  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteQNameEqual(string source, string name, string ns)
0x92c31  ldarg.0
0x92c32  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92c37  ldstr    asc_134612// ") {"
0x92c3c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92c41  ldarg.0
0x92c42  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92c47  dup
0x92c48  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92c4d  stloc.1
0x92c4e  ldloc.1
0x92c4f  ldc.i4.1
0x92c50  add
0x92c51  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92c56  ldloc.0
0x92c57  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92c5c  ldnull
0x92c5d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x92c62  brfalse  loc_92E17
0x92c67  ldarg.1
0x92c68  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92c6d  ldloc.0
0x92c6e  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92c73  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x92c78  brfalse  loc_92D3C
0x92c7d  ldarg.0
0x92c7e  ldarg.3
0x92c7f  ldarg.1
0x92c80  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92c85  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBeginTyped(string source, class System.Xml.Serialization.TypeDesc typeDesc)
0x92c8a  ldarg.0
0x92c8b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92c90  ldstr    aReadserializab// "ReadSerializable(( "
0x92c95  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92c9a  ldarg.0
0x92c9b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92ca0  ldtoken  System.Xml.Serialization.IXmlSerializable
0x92ca5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x92caa  callvirt instance string [mscorlib]System.Type::get_FullName()
0x92caf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92cb4  ldarg.0
0x92cb5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92cba  ldstr    asc_129CD8// ")"
0x92cbf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92cc4  ldarg.0
0x92cc5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92cca  ldarg.0
0x92ccb  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x92cd0  ldloc.0
0x92cd1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92cd6  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x92cdb  ldloc.0
0x92cdc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92ce1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x92ce6  ldloc.0
0x92ce7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x92cec  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CannotNew()
0x92cf1  ldc.i4.0
0x92cf2  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForCreateInstance(string escapedTypeName, bool useReflection, bool ctorInaccessible, bool cast)
0x92cf7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92cfc  ldarg.s  4
0x92cfe  brfalse.s loc_92D10
0x92d00  ldarg.0
0x92d01  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d06  ldstr    aTrue_4// ", true"
0x92d0b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92d10  ldarg.0
0x92d11  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d16  ldstr    asc_129CD8// ")"
0x92d1b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92d20  ldarg.0
0x92d21  ldarg.3
0x92d22  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x92d27  ldarg.0
0x92d28  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d2d  ldstr    asc_12B71A// ";"
0x92d32  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92d37  br       loc_92EB1
0x92d3c  ldarg.0
0x92d3d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d42  ldstr    aThrowCreatebad// "throw CreateBadDerivationException("
0x92d47  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92d4c  ldarg.0
0x92d4d  ldloc.0
0x92d4e  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92d53  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x92d58  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92d5d  ldarg.0
0x92d5e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d63  ldstr    asc_128826// ", "
0x92d68  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92d6d  ldarg.0
0x92d6e  ldloc.0
0x92d6f  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92d74  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x92d79  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92d7e  ldarg.0
0x92d7f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92d84  ldstr    asc_128826// ", "
0x92d89  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92d8e  ldarg.0
0x92d8f  ldarg.1
0x92d90  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92d95  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x92d9a  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92d9f  ldarg.0
0x92da0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92da5  ldstr    asc_128826// ", "
0x92daa  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92daf  ldarg.0
0x92db0  ldarg.1
0x92db1  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92db6  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x92dbb  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92dc0  ldarg.0
0x92dc1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92dc6  ldstr    asc_128826// ", "
0x92dcb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92dd0  ldarg.0
0x92dd1  ldloc.0
0x92dd2  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92dd7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x92ddc  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92de1  ldarg.0
0x92de2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92de7  ldstr    asc_128826// ", "
0x92dec  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92df1  ldarg.0
0x92df2  ldarg.1
0x92df3  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92df8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x92dfd  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92e02  ldarg.0
0x92e03  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92e08  ldstr    asc_133068// ");"
0x92e0d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92e12  br       loc_92EB1
0x92e17  ldarg.0
0x92e18  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92e1d  ldstr    aMissingRealMap// "// missing real mapping for "
0x92e22  ldloc.0
0x92e23  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92e28  dup
0x92e29  brtrue.s loc_92E2F
0x92e2b  pop
0x92e2c  ldnull
0x92e2d  br.s     loc_92E34
0x92e2f  callvirt instance string [mscorlib]System.Object::ToString()
0x92e34  call     string [mscorlib]System.String::Concat(string, string)
0x92e39  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92e3e  ldarg.0
0x92e3f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92e44  ldstr    aThrowCreatemis// "throw CreateMissingIXmlSerializableType"...
0x92e49  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92e4e  ldarg.0
0x92e4f  ldloc.0
0x92e50  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92e55  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x92e5a  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92e5f  ldarg.0
0x92e60  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92e65  ldstr    asc_128826// ", "
0x92e6a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92e6f  ldarg.0
0x92e70  ldloc.0
0x92e71  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x92e76  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x92e7b  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92e80  ldarg.0
0x92e81  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92e86  ldstr    asc_128826// ", "
0x92e8b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x92e90  ldarg.0
0x92e91  ldarg.1
0x92e92  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x92e97  callvirt instance string [mscorlib]System.Type::get_FullName()
0x92e9c  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x92ea1  ldarg.0
0x92ea2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92ea7  ldstr    asc_133068// ");"
0x92eac  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92eb1  ldarg.0
0x92eb2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92eb7  dup
0x92eb8  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x92ebd  stloc.1
0x92ebe  ldloc.1
0x92ebf  ldc.i4.1
0x92ec0  sub
0x92ec1  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x92ec6  ldarg.0
0x92ec7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x92ecc  ldstr    asc_12E936// "}"
0x92ed1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x92ed6  ldarg.0
0x92ed7  ldarg.1
0x92ed8  ldloc.0
0x92ed9  ldarg.3
0x92eda  ldarg.s  4
0x92edc  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteDerivedSerializable(class System.Xml.Serialization.SerializableMapping head, class System.Xml.Serialization.SerializableMapping mapping, string source, bool isWrappedAny)
0x92ee1  ldloc.0
0x92ee2  callvirt instance class System.Xml.Serialization.SerializableMapping System.Xml.Serialization.SerializableMapping::get_NextDerivedMapping()
0x92ee7  stloc.0
0x92ee8  ldloc.0
0x92ee9  brtrue   loc_92BF0
0x92eee  ret
```
