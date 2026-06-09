# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberText

- ea: `0x90bc0`
- end: `0x90d0b`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberText`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x90a90`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x86170`
- `0x90bc0`
- `0x90d10`

## string_xrefs

- `0x90bc6`: `else if (Reader.NodeType == `
- `0x90c00`: `Reader.NodeType == `
- `0x90c3a`: `Reader.NodeType == `
- `0x90c74`: `Reader.NodeType == `

## pseudocode

```c

```

## disassembly

```asm
0x90bc0  ldarg.0
0x90bc1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90bc6  ldstr    aElseIfReaderNo// "else if (Reader.NodeType == "
0x90bcb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90bd0  ldarg.0
0x90bd1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90bd6  ldtoken  System.Xml.XmlNodeType
0x90bdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x90be0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x90be5  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90bea  ldarg.0
0x90beb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90bf0  ldstr    aText_2// ".Text || "
0x90bf5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90bfa  ldarg.0
0x90bfb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c00  ldstr    aReaderNodetype// "Reader.NodeType == "
0x90c05  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c0a  ldarg.0
0x90c0b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c10  ldtoken  System.Xml.XmlNodeType
0x90c15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x90c1a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x90c1f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c24  ldarg.0
0x90c25  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c2a  ldstr    aCdata_5// ".CDATA || "
0x90c2f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90c34  ldarg.0
0x90c35  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c3a  ldstr    aReaderNodetype// "Reader.NodeType == "
0x90c3f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c44  ldarg.0
0x90c45  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c4a  ldtoken  System.Xml.XmlNodeType
0x90c4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x90c54  callvirt instance string [mscorlib]System.Type::get_FullName()
0x90c59  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c5e  ldarg.0
0x90c5f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c64  ldstr    aWhitespace_3// ".Whitespace || "
0x90c69  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90c6e  ldarg.0
0x90c6f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c74  ldstr    aReaderNodetype// "Reader.NodeType == "
0x90c79  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c7e  ldarg.0
0x90c7f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c84  ldtoken  System.Xml.XmlNodeType
0x90c89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x90c8e  callvirt instance string [mscorlib]System.Type::get_FullName()
0x90c93  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90c98  ldarg.0
0x90c99  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90c9e  ldstr    aSignificantwhi_0// ".SignificantWhitespace) {"
0x90ca3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90ca8  ldarg.0
0x90ca9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90cae  dup
0x90caf  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90cb4  stloc.0
0x90cb5  ldloc.0
0x90cb6  ldc.i4.1
0x90cb7  add
0x90cb8  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x90cbd  ldarg.1
0x90cbe  brfalse.s loc_90CC9
0x90cc0  ldarg.0
0x90cc1  ldarg.1
0x90cc2  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteText(class Member member)
0x90cc7  br.s     loc_90CE5
0x90cc9  ldarg.0
0x90cca  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90ccf  ldarg.2
0x90cd0  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90cd5  ldarg.0
0x90cd6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90cdb  ldstr    asc_12B71A// ";"
0x90ce0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90ce5  ldarg.0
0x90ce6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90ceb  dup
0x90cec  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90cf1  stloc.0
0x90cf2  ldloc.0
0x90cf3  ldc.i4.1
0x90cf4  sub
0x90cf5  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x90cfa  ldarg.0
0x90cfb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90d00  ldstr    asc_12E936// "}"
0x90d05  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90d0a  ret
```
