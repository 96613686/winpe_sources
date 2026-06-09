# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteQualifiedNameElement

- ea: `0x9d990`
- end: `0x9dadc`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteQualifiedNameElement`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0xa18d0`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68c10`
- `0x68c30`
- `0x86170`
- `0x862f0`
- `0x9d990`
- `0xa2580`

## string_xrefs

- `0x9d9f0`: `WriteElementQualifiedName`
- `0x9d9f7`: `WriteNullableQualifiedName`
- `0x9da5f`: `, new System.Xml.XmlQualifiedName(`

## pseudocode

```c

```

## disassembly

```asm
0x9d990  ldarg.3
0x9d991  brfalse.s loc_9D9A0
0x9d993  ldarg.3
0x9d994  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9d999  ceq
0x9d99b  ldc.i4.0
0x9d99c  ceq
0x9d99e  br.s     loc_9D9A1
0x9d9a0  ldc.i4.0
0x9d9a1  stloc.0
0x9d9a2  ldloc.0
0x9d9a3  brfalse.s loc_9D9D5
0x9d9a5  ldarg.0
0x9d9a6  ldarg.s  4
0x9d9a8  ldarg.3
0x9d9a9  ldarg.s  5
0x9d9ab  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteCheckDefault(string source, object value, bool isNullable)
0x9d9b0  ldarg.0
0x9d9b1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9d9b6  ldstr    asc_132D98// " {"
0x9d9bb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9d9c0  ldarg.0
0x9d9c1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9d9c6  dup
0x9d9c7  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9d9cc  stloc.2
0x9d9cd  ldloc.2
0x9d9ce  ldc.i4.1
0x9d9cf  add
0x9d9d0  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9d9d5  ldarg.s  6
0x9d9d7  brtrue.s loc_9D9E0
0x9d9d9  ldstr    aLiteral// "Literal"
0x9d9de  br.s     loc_9D9E5
0x9d9e0  ldstr    aEncoded// "Encoded"
0x9d9e5  stloc.1
0x9d9e6  ldarg.0
0x9d9e7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9d9ec  ldarg.s  5
0x9d9ee  brtrue.s loc_9D9F7
0x9d9f0  ldstr    aWriteelementqu// "WriteElementQualifiedName"
0x9d9f5  br.s     loc_9DA02
0x9d9f7  ldstr    aWritenullableq// "WriteNullableQualifiedName"
0x9d9fc  ldloc.1
0x9d9fd  call     string [mscorlib]System.String::Concat(string, string)
0x9da02  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da07  ldarg.0
0x9da08  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da0d  ldstr    asc_12DDFC// "("
0x9da12  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da17  ldarg.0
0x9da18  ldarg.1
0x9da19  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9da1e  ldarg.2
0x9da1f  brfalse.s loc_9DA38
0x9da21  ldarg.0
0x9da22  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da27  ldstr    asc_128826// ", "
0x9da2c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da31  ldarg.0
0x9da32  ldarg.2
0x9da33  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9da38  ldarg.0
0x9da39  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da3e  ldstr    asc_128826// ", "
0x9da43  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da48  ldarg.0
0x9da49  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da4e  ldarg.s  4
0x9da50  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da55  ldarg.s  6
0x9da57  brfalse.s loc_9DAA3
0x9da59  ldarg.0
0x9da5a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da5f  ldstr    aNewSystemXmlXm// ", new System.Xml.XmlQualifiedName("
0x9da64  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da69  ldarg.0
0x9da6a  ldarg.s  7
0x9da6c  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x9da71  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9da76  ldarg.0
0x9da77  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da7c  ldstr    asc_128826// ", "
0x9da81  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9da86  ldarg.0
0x9da87  ldarg.s  7
0x9da89  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x9da8e  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9da93  ldarg.0
0x9da94  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9da99  ldstr    asc_129CD8// ")"
0x9da9e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9daa3  ldarg.0
0x9daa4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9daa9  ldstr    asc_133068// ");"
0x9daae  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9dab3  ldloc.0
0x9dab4  brfalse.s loc_9DADB
0x9dab6  ldarg.0
0x9dab7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9dabc  dup
0x9dabd  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9dac2  stloc.2
0x9dac3  ldloc.2
0x9dac4  ldc.i4.1
0x9dac5  sub
0x9dac6  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9dacb  ldarg.0
0x9dacc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9dad1  ldstr    asc_12E936// "}"
0x9dad6  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9dadb  ret
```
