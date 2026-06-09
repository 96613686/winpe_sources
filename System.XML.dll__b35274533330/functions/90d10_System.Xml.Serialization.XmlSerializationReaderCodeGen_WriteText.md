# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteText

- ea: `0x90d10`
- end: `0x90ea6`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteText`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x90bc0`

## callees

- `0x62370`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68c50`
- `0x696f0`
- `0x72c00`
- `0x72c10`
- `0x72cf0`
- `0x86170`
- `0x861b0`
- `0x8da80`
- `0x90d10`
- `0x91c40`
- `0x91c90`
- `0x91ce0`
- `0x122c70`
- `0x122ca0`
- `0x122cc0`

## string_xrefs

- `0x90d6a`: `XmlInternalError`
- `0x90d5e`: `Document.CreateTextNode(Reader.ReadString())`
- `0x90db7`: `CollapseWhitespace(Reader.ReadString())`
- `0x90dcc`: `Reader.ReadString()`
- `0x90e7f`: `Reader.ReadString()`
- `0x90e10`: `tmp = ReadString(tmp, `

## pseudocode

```c

```

## disassembly

```asm
0x90d10  ldarg.1
0x90d11  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x90d16  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x90d1b  stloc.0
0x90d1c  ldloc.0
0x90d1d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90d22  isinst   System.Xml.Serialization.SpecialMapping
0x90d27  brfalse.s loc_90D8B
0x90d29  ldloc.0
0x90d2a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90d2f  castclass System.Xml.Serialization.SpecialMapping
0x90d34  stloc.1
0x90d35  ldarg.0
0x90d36  ldarg.1
0x90d37  callvirt instance string Member::get_ArraySource()
0x90d3c  ldloc.1
0x90d3d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90d42  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBeginTyped(string source, class System.Xml.Serialization.TypeDesc typeDesc)
0x90d47  ldloc.1
0x90d48  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90d4d  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x90d52  stloc.2
0x90d53  ldloc.2
0x90d54  ldc.i4.s 9
0x90d56  bne.un.s loc_90D6A
0x90d58  ldarg.0
0x90d59  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90d5e  ldstr    aDocumentCreate// "Document.CreateTextNode(Reader.ReadStri"...
0x90d63  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90d68  br.s     loc_90D7A
0x90d6a  ldstr    aXmlinternalerr// "XmlInternalError"
0x90d6f  call     string System.Xml.Res::GetString(string name)
0x90d74  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x90d79  throw
0x90d7a  ldarg.0
0x90d7b  ldarg.1
0x90d7c  callvirt instance string Member::get_ArraySource()
0x90d81  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x90d86  br       loc_90E95
0x90d8b  ldarg.1
0x90d8c  callvirt instance bool Member::get_IsArrayLike()
0x90d91  brfalse.s loc_90DDB
0x90d93  ldarg.0
0x90d94  ldarg.1
0x90d95  callvirt instance string Member::get_ArraySource()
0x90d9a  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x90d9f  ldloc.0
0x90da0  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90da5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90daa  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x90daf  brfalse.s loc_90DC6
0x90db1  ldarg.0
0x90db2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90db7  ldstr    aCollapsewhites_1// "CollapseWhitespace(Reader.ReadString())"
0x90dbc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90dc1  br       loc_90E89
0x90dc6  ldarg.0
0x90dc7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90dcc  ldstr    aReaderReadstri// "Reader.ReadString()"
0x90dd1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90dd6  br       loc_90E89
0x90ddb  ldloc.0
0x90ddc  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90de1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90de6  ldarg.0
0x90de7  call     instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.XmlSerializationCodeGen::get_StringTypeDesc()
0x90dec  beq.s    loc_90E0A
0x90dee  ldloc.0
0x90def  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90df4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90df9  callvirt instance string System.Xml.Serialization.TypeDesc::get_FormatterName()
0x90dfe  ldstr    aString_0// "String"
0x90e03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90e08  brfalse.s loc_90E6C
0x90e0a  ldarg.0
0x90e0b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90e10  ldstr    aTmpReadstringT// "tmp = ReadString(tmp, "
0x90e15  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90e1a  ldloc.0
0x90e1b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90e20  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x90e25  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x90e2a  brfalse.s loc_90E3E
0x90e2c  ldarg.0
0x90e2d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90e32  ldstr    aTrue_2// "true);"
0x90e37  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90e3c  br.s     loc_90E4E
0x90e3e  ldarg.0
0x90e3f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90e44  ldstr    aFalse_0// "false);"
0x90e49  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90e4e  ldarg.0
0x90e4f  ldarg.1
0x90e50  callvirt instance string Member::get_ArraySource()
0x90e55  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x90e5a  ldarg.0
0x90e5b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90e60  ldstr    aTmp_2// "tmp"
0x90e65  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90e6a  br.s     loc_90E89
0x90e6c  ldarg.0
0x90e6d  ldarg.1
0x90e6e  callvirt instance string Member::get_ArraySource()
0x90e73  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x90e78  ldarg.0
0x90e79  ldloc.0
0x90e7a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90e7f  ldstr    aReaderReadstri// "Reader.ReadString()"
0x90e84  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x90e89  ldarg.0
0x90e8a  ldarg.1
0x90e8b  callvirt instance string Member::get_ArraySource()
0x90e90  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x90e95  ldarg.0
0x90e96  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90e9b  ldstr    asc_12B71A// ";"
0x90ea0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90ea5  ret
```
