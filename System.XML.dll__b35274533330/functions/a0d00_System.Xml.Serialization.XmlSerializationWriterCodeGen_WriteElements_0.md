# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElements_0

- ea: `0xa0d00`
- end: `0xa17f6`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElements_0`
- size: `2806`
- prototype: ``
- caller_count: `3`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa05c0`
- `0xa07e0`
- `0xa0ce0`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x688b0`
- `0x688d0`
- `0x68990`
- `0x68c50`
- `0x72b90`
- `0x72ba0`
- `0x72d70`
- `0x72d80`
- `0x73000`
- `0x86170`
- `0x861a0`
- `0x862f0`
- `0xa0d00`
- `0xa1800`
- `0xa18d0`
- `0xa2640`
- `0xa2c40`
- `0xa2c80`
- `0xa3c40`

## string_xrefs

- `0xa13d2`: ` && elem.NamespaceURI == `
- `0xa148c`: `throw CreateChoiceIdentifierValueException(`
- `0xa14c1`: `, elem.Name, elem.NamespaceURI);`
- `0xa1583`: `throw CreateUnknownAnyElementException(elem.Name, elem.NamespaceURI);`
- `0xa1781`: `throw CreateUnknownTypeException(`

## pseudocode

```c

```

## disassembly

```asm
0xa0d00  ldarg.3
0xa0d01  ldlen
0xa0d02  brtrue.s loc_A0D09
0xa0d04  ldarg.s  4
0xa0d06  brtrue.s loc_A0D09
0xa0d08  ret
0xa0d09  ldarg.3
0xa0d0a  ldlen
0xa0d0b  conv.i4
0xa0d0c  ldc.i4.1
0xa0d0d  bne.un   loc_A0DB8
0xa0d12  ldarg.s  4
0xa0d14  brtrue   loc_A0DB8
0xa0d19  ldarg.3
0xa0d1a  ldc.i4.0
0xa0d1b  ldelem.ref
0xa0d1c  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsUnbounded()
0xa0d21  brtrue.s loc_A0D32
0xa0d23  ldarg.3
0xa0d24  ldc.i4.0
0xa0d25  ldelem.ref
0xa0d26  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0d2b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0d30  br.s     loc_A0D44
0xa0d32  ldarg.3
0xa0d33  ldc.i4.0
0xa0d34  ldelem.ref
0xa0d35  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0d3a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0d3f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0xa0d44  stloc.0
0xa0d45  ldarg.3
0xa0d46  ldc.i4.0
0xa0d47  ldelem.ref
0xa0d48  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa0d4d  brtrue.s loc_A0DA9
0xa0d4f  ldarg.3
0xa0d50  ldc.i4.0
0xa0d51  ldelem.ref
0xa0d52  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0d57  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0d5c  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa0d61  brtrue.s loc_A0DA9
0xa0d63  ldarg.3
0xa0d64  ldc.i4.0
0xa0d65  ldelem.ref
0xa0d66  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0d6b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0d70  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsOptionalValue()
0xa0d75  brtrue.s loc_A0DA9
0xa0d77  ldc.i4.5
0xa0d78  newarr   [mscorlib]System.String
0xa0d7d  dup
0xa0d7e  ldc.i4.0
0xa0d7f  ldstr    asc_12FF58// "(("
0xa0d84  stelem.ref
0xa0d85  dup
0xa0d86  ldc.i4.1
0xa0d87  ldloc.0
0xa0d88  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa0d8d  stelem.ref
0xa0d8e  dup
0xa0d8f  ldc.i4.2
0xa0d90  ldstr    asc_129CD8// ")"
0xa0d95  stelem.ref
0xa0d96  dup
0xa0d97  ldc.i4.3
0xa0d98  ldarg.1
0xa0d99  stelem.ref
0xa0d9a  dup
0xa0d9b  ldc.i4.4
0xa0d9c  ldstr    asc_129CD8// ")"
0xa0da1  stelem.ref
0xa0da2  call     string [mscorlib]System.String::Concat(string[])
0xa0da7  starg.s  1
0xa0da9  ldarg.0
0xa0daa  ldarg.1
0xa0dab  ldarg.3
0xa0dac  ldc.i4.0
0xa0dad  ldelem.ref
0xa0dae  ldarg.s  6
0xa0db0  ldarg.s  7
0xa0db2  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElement(string source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa0db7  ret
0xa0db8  ldarg.s  8
0xa0dba  brfalse.s loc_A0DEC
0xa0dbc  ldarg.s  5
0xa0dbe  brtrue.s loc_A0DEC
0xa0dc0  ldarg.0
0xa0dc1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0dc6  ldstr    aIfObject_0// "if ((object)("
0xa0dcb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0dd0  ldarg.0
0xa0dd1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0dd6  ldarg.1
0xa0dd7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0ddc  ldarg.0
0xa0ddd  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0de2  ldstr    aNull_12// ") != null)"
0xa0de7  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0dec  ldarg.0
0xa0ded  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0df2  ldstr    asc_12FB82// "{"
0xa0df7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0dfc  ldarg.0
0xa0dfd  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0e02  dup
0xa0e03  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa0e08  stloc.s  6
0xa0e0a  ldloc.s  6
0xa0e0c  ldc.i4.1
0xa0e0d  add
0xa0e0e  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa0e13  ldc.i4.0
0xa0e14  stloc.1
0xa0e15  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa0e1a  stloc.2
0xa0e1b  ldnull
0xa0e1c  stloc.3
0xa0e1d  ldc.i4.0
0xa0e1e  stloc.s  4
0xa0e20  ldarg.s  5
0xa0e22  brfalse.s loc_A0E37
0xa0e24  ldarg.s  5
0xa0e26  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0e2b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0e30  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0xa0e35  br.s     loc_A0E38
0xa0e37  ldnull
0xa0e38  stloc.s  5
0xa0e3a  ldc.i4.0
0xa0e3b  stloc.s  7
0xa0e3d  br       loc_A1176
0xa0e42  ldarg.3
0xa0e43  ldloc.s  7
0xa0e45  ldelem.ref
0xa0e46  stloc.s  8
0xa0e48  ldloc.s  8
0xa0e4a  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa0e4f  brfalse.s loc_A0E89
0xa0e51  ldloc.1
0xa0e52  ldc.i4.1
0xa0e53  add
0xa0e54  stloc.1
0xa0e55  ldloc.s  8
0xa0e57  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa0e5c  brfalse.s loc_A0E7B
0xa0e5e  ldloc.s  8
0xa0e60  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa0e65  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa0e6a  ldc.i4.0
0xa0e6b  ble.s    loc_A0E7B
0xa0e6d  ldloc.2
0xa0e6e  ldloc.s  8
0xa0e70  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa0e75  pop
0xa0e76  br       loc_A1170
0xa0e7b  ldloc.3
0xa0e7c  brtrue   loc_A1170
0xa0e81  ldloc.s  8
0xa0e83  stloc.3
0xa0e84  br       loc_A1170
0xa0e89  ldarg.s  5
0xa0e8b  brfalse  loc_A1059
0xa0e90  ldloc.s  8
0xa0e92  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0e97  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0e9c  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa0ea1  stloc.s  9
0xa0ea3  ldloc.s  8
0xa0ea5  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0eaa  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0eaf  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa0eb4  stloc.s  0xA
0xa0eb6  ldarg.s  5
0xa0eb8  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0ebd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0ec2  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa0ec7  stloc.s  0xB
0xa0ec9  ldloc.s  0xB
0xa0ecb  brtrue.s loc_A0EDB
0xa0ecd  ldloc.s  5
0xa0ecf  ldstr    asc_13444E// ".@"
0xa0ed4  call     string [mscorlib]System.String::Concat(string, string)
0xa0ed9  br.s     loc_A0EE0
0xa0edb  ldstr    asc_1284AE// ""
0xa0ee0  ldarg.0
0xa0ee1  ldloc.s  8
0xa0ee3  ldarg.s  5
0xa0ee5  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0eea  castclass System.Xml.Serialization.EnumMapping
0xa0eef  ldloc.s  0xB
0xa0ef1  call     instance string System.Xml.Serialization.XmlSerializationWriterCodeGen::FindChoiceEnumValue(class System.Xml.Serialization.ElementAccessor element, class System.Xml.Serialization.EnumMapping choiceMapping, bool useReflection)
0xa0ef6  call     string [mscorlib]System.String::Concat(string, string)
0xa0efb  stloc.s  0xC
0xa0efd  ldloc.s  4
0xa0eff  brfalse.s loc_A0F13
0xa0f01  ldarg.0
0xa0f02  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f07  ldstr    aElse_1// "else "
0xa0f0c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f11  br.s     loc_A0F16
0xa0f13  ldc.i4.1
0xa0f14  stloc.s  4
0xa0f16  ldarg.0
0xa0f17  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f1c  ldstr    aIf// "if ("
0xa0f21  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f26  ldarg.0
0xa0f27  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f2c  ldloc.s  0xB
0xa0f2e  brtrue.s loc_A0F33
0xa0f30  ldarg.2
0xa0f31  br.s     loc_A0F41
0xa0f33  ldarg.0
0xa0f34  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0xa0f39  ldarg.2
0xa0f3a  ldloc.s  0xB
0xa0f3c  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForEnumLongValue(string variable, bool useReflection)
0xa0f41  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f46  ldarg.0
0xa0f47  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f4c  ldstr    asc_1386D6// " == "
0xa0f51  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f56  ldarg.0
0xa0f57  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f5c  ldloc.s  0xC
0xa0f5e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f63  ldarg.s  8
0xa0f65  brfalse.s loc_A0F9C
0xa0f67  ldloc.s  8
0xa0f69  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa0f6e  brtrue.s loc_A0F9C
0xa0f70  ldarg.0
0xa0f71  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f76  ldstr    aObject_7// " && ((object)("
0xa0f7b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f80  ldarg.0
0xa0f81  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f86  ldarg.1
0xa0f87  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f8c  ldarg.0
0xa0f8d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0f92  ldstr    aNull_12// ") != null)"
0xa0f97  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0f9c  ldarg.0
0xa0f9d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0fa2  ldstr    asc_134612// ") {"
0xa0fa7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0fac  ldarg.0
0xa0fad  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0fb2  dup
0xa0fb3  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa0fb8  stloc.s  6
0xa0fba  ldloc.s  6
0xa0fbc  ldc.i4.1
0xa0fbd  add
0xa0fbe  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa0fc3  ldarg.0
0xa0fc4  ldarg.1
0xa0fc5  ldloc.s  0xA
0xa0fc7  ldloc.s  9
0xa0fc9  ldarg.s  5
0xa0fcb  ldloc.s  0xC
0xa0fcd  ldloc.s  8
0xa0fcf  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0fd4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa0fd9  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteChoiceTypeCheck(string source, string fullTypeName, bool useReflection, class System.Xml.Serialization.ChoiceIdentifierAccessor choice, string enumName, class System.Xml.Serialization.TypeDesc typeDesc)
0xa0fde  ldarg.1
0xa0fdf  stloc.s  0xD
0xa0fe1  ldloc.s  9
0xa0fe3  brtrue.s loc_A1013
0xa0fe5  ldc.i4.5
0xa0fe6  newarr   [mscorlib]System.String
0xa0feb  dup
0xa0fec  ldc.i4.0
0xa0fed  ldstr    asc_12FF58// "(("
0xa0ff2  stelem.ref
0xa0ff3  dup
0xa0ff4  ldc.i4.1
0xa0ff5  ldloc.s  0xA
0xa0ff7  stelem.ref
0xa0ff8  dup
0xa0ff9  ldc.i4.2
0xa0ffa  ldstr    asc_129CD8// ")"
0xa0fff  stelem.ref
0xa1000  dup
0xa1001  ldc.i4.3
0xa1002  ldarg.1
0xa1003  stelem.ref
0xa1004  dup
0xa1005  ldc.i4.4
0xa1006  ldstr    asc_129CD8// ")"
0xa100b  stelem.ref
0xa100c  call     string [mscorlib]System.String::Concat(string[])
0xa1011  stloc.s  0xD
0xa1013  ldarg.0
0xa1014  ldloc.s  8
0xa1016  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa101b  brtrue.s loc_A1021
  ... truncated ...
```
