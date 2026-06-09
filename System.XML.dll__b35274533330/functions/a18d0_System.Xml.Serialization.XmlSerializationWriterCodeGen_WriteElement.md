# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElement

- ea: `0xa18d0`
- end: `0xa24a1`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElement`
- size: `3025`
- prototype: ``
- caller_count: `2`
- callee_count: `47`
- tags: `registry_config`

## callers

- `0xa0d00`
- `0xa18d0`

## callees

- `0x62370`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68610`
- `0x68620`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x688b0`
- `0x688d0`
- `0x688e0`
- `0x688f0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68d70`
- `0x68de0`
- `0x72ba0`
- `0x72c40`
- `0x72d80`
- `0x72e10`
- `0x72e40`
- `0x73000`
- `0x730b0`
- `0x86170`
- `0x861a0`
- `0x861c0`
- `0x86200`
- `0x86260`
- `0x862f0`
- `0x9d990`
- `0x9dc20`
- `0x9dfd0`
- `0x9dfe0`
- `0x9e040`
- `0xa07e0`
- `0xa18d0`
- `0xa24b0`
- `0xa26e0`
- `0xa2790`
- `0xa2c10`
- `0xa3ca0`

## string_xrefs

- `0xa2490`: `XmlInternalError`
- `0xa1adf`: `WritePotentiallyReferencingElement(`
- `0xa213b`: `WritePotentiallyReferencingElement(`
- `0xa1faf`: `Writer.WriteStartElement(`
- `0xa2028`: `WriteElementString`
- `0xa20d1`: `WriteElementString`
- `0xa20df`: `WriteNullableString`
- `0xa230a`: `WriteSerializable`
- `0xa23cb`: `WriteElementLiteral`
- `0xa2442`: `throw CreateInvalidAnyTypeException(`

## pseudocode

```c

```

## disassembly

```asm
0xa18d0  ldarg.s  4
0xa18d2  brtrue.s loc_A18E1
0xa18d4  ldarg.2
0xa18d5  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa18da  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0xa18df  br.s     loc_A18E7
0xa18e1  ldarg.2
0xa18e2  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa18e7  stloc.0
0xa18e8  ldarg.2
0xa18e9  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa18ee  brfalse.s loc_A18FD
0xa18f0  ldarg.2
0xa18f1  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa18f6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa18fb  brfalse.s loc_A1926
0xa18fd  ldarg.2
0xa18fe  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa1903  ldc.i4.1
0xa1904  beq.s    loc_A190D
0xa1906  ldstr    asc_1284AE// ""
0xa190b  br.s     loc_A1927
0xa190d  ldarg.s  4
0xa190f  brtrue.s loc_A191E
0xa1911  ldarg.2
0xa1912  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1917  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0xa191c  br.s     loc_A1927
0xa191e  ldarg.2
0xa191f  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa1924  br.s     loc_A1927
0xa1926  ldnull
0xa1927  stloc.1
0xa1928  ldarg.2
0xa1929  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa192e  isinst   System.Xml.Serialization.NullableMapping
0xa1933  brfalse  loc_A1AB0
0xa1938  ldarg.0
0xa1939  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa193e  ldstr    aIf// "if ("
0xa1943  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1948  ldarg.0
0xa1949  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa194e  ldarg.1
0xa194f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1954  ldarg.0
0xa1955  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa195a  ldstr    aNull_8// " != null) {"
0xa195f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1964  ldarg.0
0xa1965  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa196a  dup
0xa196b  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa1970  stloc.s  5
0xa1972  ldloc.s  5
0xa1974  ldc.i4.1
0xa1975  add
0xa1976  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa197b  ldarg.2
0xa197c  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1981  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1986  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0xa198b  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa1990  stloc.2
0xa1991  ldarg.1
0xa1992  stloc.3
0xa1993  ldarg.2
0xa1994  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1999  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa199e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0xa19a3  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa19a8  brtrue.s loc_A19D6
0xa19aa  ldc.i4.5
0xa19ab  newarr   [mscorlib]System.String
0xa19b0  dup
0xa19b1  ldc.i4.0
0xa19b2  ldstr    asc_12FF58// "(("
0xa19b7  stelem.ref
0xa19b8  dup
0xa19b9  ldc.i4.1
0xa19ba  ldloc.2
0xa19bb  stelem.ref
0xa19bc  dup
0xa19bd  ldc.i4.2
0xa19be  ldstr    asc_129CD8// ")"
0xa19c3  stelem.ref
0xa19c4  dup
0xa19c5  ldc.i4.3
0xa19c6  ldarg.1
0xa19c7  stelem.ref
0xa19c8  dup
0xa19c9  ldc.i4.4
0xa19ca  ldstr    asc_129CD8// ")"
0xa19cf  stelem.ref
0xa19d0  call     string [mscorlib]System.String::Concat(string[])
0xa19d5  stloc.3
0xa19d6  ldarg.2
0xa19d7  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.ElementAccessor::Clone()
0xa19dc  stloc.s  4
0xa19de  ldloc.s  4
0xa19e0  ldarg.2
0xa19e1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa19e6  castclass System.Xml.Serialization.NullableMapping
0xa19eb  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.NullableMapping::get_BaseMapping()
0xa19f0  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0xa19f5  ldarg.0
0xa19f6  ldloc.s  4
0xa19f8  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa19fd  brtrue.s loc_A1A02
0xa19ff  ldloc.3
0xa1a00  br.s     loc_A1A03
0xa1a02  ldarg.1
0xa1a03  ldloc.s  4
0xa1a05  ldarg.3
0xa1a06  ldarg.s  4
0xa1a08  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteElement(string source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa1a0d  ldarg.0
0xa1a0e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1a13  dup
0xa1a14  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa1a19  stloc.s  5
0xa1a1b  ldloc.s  5
0xa1a1d  ldc.i4.1
0xa1a1e  sub
0xa1a1f  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa1a24  ldarg.0
0xa1a25  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1a2a  ldstr    asc_12E936// "}"
0xa1a2f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1a34  ldarg.2
0xa1a35  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa1a3a  brfalse  loc_A24A0
0xa1a3f  ldarg.0
0xa1a40  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1a45  ldstr    aElse// "else {"
0xa1a4a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1a4f  ldarg.0
0xa1a50  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1a55  dup
0xa1a56  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa1a5b  stloc.s  5
0xa1a5d  ldloc.s  5
0xa1a5f  ldc.i4.1
0xa1a60  add
0xa1a61  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa1a66  ldarg.0
0xa1a67  ldarg.2
0xa1a68  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa1a6d  ldarg.2
0xa1a6e  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa1a73  ldc.i4.1
0xa1a74  beq.s    loc_A1A7D
0xa1a76  ldstr    asc_1284AE// ""
0xa1a7b  br.s     loc_A1A83
0xa1a7d  ldarg.2
0xa1a7e  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa1a83  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteLiteralNullTag(string name, string ns)
0xa1a88  ldarg.0
0xa1a89  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1a8e  dup
0xa1a8f  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa1a94  stloc.s  5
0xa1a96  ldloc.s  5
0xa1a98  ldc.i4.1
0xa1a99  sub
0xa1a9a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa1a9f  ldarg.0
0xa1aa0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1aa5  ldstr    asc_12E936// "}"
0xa1aaa  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1aaf  ret
0xa1ab0  ldarg.2
0xa1ab1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1ab6  isinst   System.Xml.Serialization.ArrayMapping
0xa1abb  brfalse  loc_A1F71
0xa1ac0  ldarg.2
0xa1ac1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1ac6  castclass System.Xml.Serialization.ArrayMapping
0xa1acb  stloc.s  6
0xa1acd  ldloc.s  6
0xa1acf  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0xa1ad4  brfalse  loc_A1BA9
0xa1ad9  ldarg.0
0xa1ada  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1adf  ldstr    aWritepotential// "WritePotentiallyReferencingElement("
0xa1ae4  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1ae9  ldarg.0
0xa1aea  ldloc.0
0xa1aeb  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0xa1af0  ldarg.0
0xa1af1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1af6  ldstr    asc_128826// ", "
0xa1afb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b00  ldarg.0
0xa1b01  ldloc.1
0xa1b02  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0xa1b07  ldarg.0
0xa1b08  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b0d  ldstr    asc_128826// ", "
0xa1b12  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b17  ldarg.0
0xa1b18  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b1d  ldarg.1
0xa1b1e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b23  ldarg.s  4
0xa1b25  brtrue.s loc_A1B77
0xa1b27  ldarg.0
0xa1b28  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b2d  ldstr    asc_128826// ", "
0xa1b32  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b37  ldarg.0
0xa1b38  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b3d  ldarg.0
0xa1b3e  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0xa1b43  ldloc.s  6
0xa1b45  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1b4a  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa1b4f  ldloc.s  6
0xa1b51  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1b56  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa1b5b  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForTypeof(string typeFullName, bool useReflection)
0xa1b60  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b65  ldarg.0
0xa1b66  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b6b  ldstr    aTrue_5// ", true, "
0xa1b70  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b75  br.s     loc_A1B87
0xa1b77  ldarg.0
0xa1b78  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b7d  ldstr    aNullFalse// ", null, false, "
0xa1b82  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1b87  ldarg.0
0xa1b88  ldarg.2
0xa1b89  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa1b8e  box      [mscorlib]System.Boolean
0xa1b93  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteValue(object value)
0xa1b98  ldarg.0
0xa1b99  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1b9e  ldstr    asc_133068// ");"
0xa1ba3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1ba8  ret
0xa1ba9  ldarg.2
0xa1baa  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsUnbounded()
0xa1baf  brfalse  loc_A1E42
0xa1bb4  ldloc.s  6
0xa1bb6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1bbb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0xa1bc0  stloc.s  7
0xa1bc2  ldloc.s  7
0xa1bc4  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa1bc9  stloc.s  8
0xa1bcb  ldstr    aEl// "el"
0xa1bd0  ldarg.3
0xa1bd1  call     string [mscorlib]System.String::Concat(string, string)
0xa1bd6  stloc.s  9
0xa1bd8  ldstr    aC// "c"
0xa1bdd  ldloc.s  9
0xa1bdf  call     string [mscorlib]System.String::Concat(string, string)
0xa1be4  stloc.s  0xA
0xa1be6  ldarg.0
0xa1be7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1bec  ldstr    asc_12FB82// "{"
0xa1bf1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1bf6  ldarg.0
0xa1bf7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1bfc  dup
0xa1bfd  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa1c02  stloc.s  5
0xa1c04  ldloc.s  5
0xa1c06  ldc.i4.1
0xa1c07  add
0xa1c08  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa1c0d  ldarg.0
0xa1c0e  ldloc.s  8
0xa1c10  ldloc.s  9
0xa1c12  ldarg.1
0xa1c13  ldloc.s  6
0xa1c15  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1c1a  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteArrayLocalDecl(string typeName, string variableName, string initValue, class System.Xml.Serialization.TypeDesc arrayTypeDesc)
0xa1c1f  ldarg.2
0xa1c20  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa1c25  brfalse.s loc_A1C32
0xa1c27  ldarg.0
0xa1c28  ldloc.s  9
0xa1c2a  ldarg.2
0xa1c2b  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteNullCheckBegin(string source, class System.Xml.Serialization.ElementAccessor element)
0xa1c30  br.s     loc_A1C94
0xa1c32  ldloc.s  6
0xa1c34  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1c39  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa1c3e  brfalse.s loc_A1C6D
0xa1c40  ldarg.0
0xa1c41  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1c46  ldstr    aIf// "if ("
0xa1c4b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1c50  ldarg.0
0xa1c51  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1c56  ldloc.s  9
0xa1c58  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1c5d  ldarg.0
  ... truncated ...
```
