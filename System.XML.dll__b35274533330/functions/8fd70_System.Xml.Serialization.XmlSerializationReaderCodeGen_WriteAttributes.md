# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttributes

- ea: `0x8fd70`
- end: `0x90244`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttributes`
- size: `1236`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x8cc30`
- `0x8e9e0`
- `0x8f330`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x68a50`
- `0x69620`
- `0x69640`
- `0x69730`
- `0x69750`
- `0x72ba0`
- `0x86170`
- `0x862f0`
- `0x8fc70`
- `0x8fd70`
- `0x90250`
- `0x122c70`
- `0x122c80`
- `0x122ca0`
- `0x122d40`

## string_xrefs

- `0x8fe77`: `http://www.w3.org/XML/1998/namespace`
- `0x901c5`: `http://www.w3.org/XML/1998/namespace`
- `0x8fe6b`: `Reader`
- `0x8fe84`: `Reader`
- `0x8fd80`: `while (Reader.MoveToNextAttribute()) {`
- `0x8ff2f`: `if (IsXmlnsAttribute(Reader.Name)) {`
- `0x9001b`: `.Add(Reader.Name.Length == 5 ? "" : Reader.LocalName, Reader.Value);`
- `0x90077`: `if (!IsXmlnsAttribute(Reader.Name)) {`
- `0x900f6`: `) Document.ReadNode(Reader);`

## pseudocode

```c

```

## disassembly

```asm
0x8fd70  ldc.i4.0
0x8fd71  stloc.0
0x8fd72  ldnull
0x8fd73  stloc.1
0x8fd74  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x8fd79  stloc.2
0x8fd7a  ldarg.0
0x8fd7b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fd80  ldstr    aWhileReaderMov// "while (Reader.MoveToNextAttribute()) {"
0x8fd85  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8fd8a  ldarg.0
0x8fd8b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fd90  dup
0x8fd91  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8fd96  stloc.3
0x8fd97  ldloc.3
0x8fd98  ldc.i4.1
0x8fd99  add
0x8fd9a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8fd9f  ldc.i4.0
0x8fda0  stloc.s  4
0x8fda2  br       loc_8FF05
0x8fda7  ldarg.1
0x8fda8  ldloc.s  4
0x8fdaa  ldelem.ref
0x8fdab  stloc.s  5
0x8fdad  ldloc.s  5
0x8fdaf  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8fdb4  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x8fdb9  brfalse.s loc_8FDC3
0x8fdbb  ldloc.s  5
0x8fdbd  stloc.1
0x8fdbe  br       loc_8FEFF
0x8fdc3  ldloc.s  5
0x8fdc5  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8fdca  callvirt instance bool System.Xml.Serialization.AccessorMapping::get_Ignore()
0x8fdcf  brtrue   loc_8FEFF
0x8fdd4  ldloc.s  5
0x8fdd6  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8fddb  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x8fde0  stloc.s  6
0x8fde2  ldloc.s  6
0x8fde4  brfalse  loc_8FEFF
0x8fde9  ldloc.s  6
0x8fdeb  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x8fdf0  brtrue   loc_8FEFF
0x8fdf5  ldloc.2
0x8fdf6  ldloc.s  6
0x8fdf8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8fdfd  pop
0x8fdfe  ldloc.0
0x8fdff  dup
0x8fe00  ldc.i4.1
0x8fe01  add
0x8fe02  stloc.0
0x8fe03  ldc.i4.0
0x8fe04  ble.s    loc_8FE16
0x8fe06  ldarg.0
0x8fe07  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fe0c  ldstr    aElse_1// "else "
0x8fe11  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8fe16  ldarg.0
0x8fe17  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fe1c  ldstr    aIf// "if ("
0x8fe21  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8fe26  ldloc.s  5
0x8fe28  callvirt instance string Member::get_ParamsReadSource()
0x8fe2d  brfalse.s loc_8FE61
0x8fe2f  ldarg.0
0x8fe30  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fe35  ldstr    asc_135226// "!"
0x8fe3a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8fe3f  ldarg.0
0x8fe40  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fe45  ldloc.s  5
0x8fe47  callvirt instance string Member::get_ParamsReadSource()
0x8fe4c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8fe51  ldarg.0
0x8fe52  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fe57  ldstr    asc_13518E// " && "
0x8fe5c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8fe61  ldloc.s  6
0x8fe63  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsSpecialXmlNamespace()
0x8fe68  brfalse.s loc_8FE83
0x8fe6a  ldarg.0
0x8fe6b  ldstr    aReader_2// "Reader"
0x8fe70  ldloc.s  6
0x8fe72  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8fe77  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x8fe7c  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteXmlNodeEqual(string source, string name, string ns)
0x8fe81  br.s     loc_8FEAD
0x8fe83  ldarg.0
0x8fe84  ldstr    aReader_2// "Reader"
0x8fe89  ldloc.s  6
0x8fe8b  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8fe90  ldloc.s  6
0x8fe92  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x8fe97  ldc.i4.1
0x8fe98  beq.s    loc_8FEA1
0x8fe9a  ldstr    asc_1284AE// ""
0x8fe9f  br.s     loc_8FEA8
0x8fea1  ldloc.s  6
0x8fea3  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x8fea8  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteXmlNodeEqual(string source, string name, string ns)
0x8fead  ldarg.0
0x8feae  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8feb3  ldstr    asc_134612// ") {"
0x8feb8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8febd  ldarg.0
0x8febe  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fec3  dup
0x8fec4  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8fec9  stloc.3
0x8feca  ldloc.3
0x8fecb  ldc.i4.1
0x8fecc  add
0x8fecd  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8fed2  ldarg.0
0x8fed3  ldloc.s  5
0x8fed5  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttribute(class Member member)
0x8feda  ldarg.0
0x8fedb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fee0  dup
0x8fee1  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8fee6  stloc.3
0x8fee7  ldloc.3
0x8fee8  ldc.i4.1
0x8fee9  sub
0x8feea  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8feef  ldarg.0
0x8fef0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8fef5  ldstr    asc_12E936// "}"
0x8fefa  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8feff  ldloc.s  4
0x8ff01  ldc.i4.1
0x8ff02  add
0x8ff03  stloc.s  4
0x8ff05  ldloc.s  4
0x8ff07  ldarg.1
0x8ff08  ldlen
0x8ff09  conv.i4
0x8ff0a  blt      loc_8FDA7
0x8ff0f  ldloc.0
0x8ff10  ldc.i4.0
0x8ff11  ble.s    loc_8FF23
0x8ff13  ldarg.0
0x8ff14  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff19  ldstr    aElse_1// "else "
0x8ff1e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ff23  ldloc.1
0x8ff24  brfalse  loc_90071
0x8ff29  ldarg.0
0x8ff2a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff2f  ldstr    aIfIsxmlnsattri// "if (IsXmlnsAttribute(Reader.Name)) {"
0x8ff34  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ff39  ldarg.0
0x8ff3a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff3f  dup
0x8ff40  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8ff45  stloc.3
0x8ff46  ldloc.3
0x8ff47  ldc.i4.1
0x8ff48  add
0x8ff49  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8ff4e  ldarg.0
0x8ff4f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff54  ldstr    aIf// "if ("
0x8ff59  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ff5e  ldarg.0
0x8ff5f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff64  ldloc.1
0x8ff65  callvirt instance string Member::get_Source()
0x8ff6a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ff6f  ldarg.0
0x8ff70  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff75  ldstr    aNull_3// " == null) "
0x8ff7a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ff7f  ldarg.0
0x8ff80  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff85  ldloc.1
0x8ff86  callvirt instance string Member::get_Source()
0x8ff8b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ff90  ldarg.0
0x8ff91  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ff96  ldstr    aNew_1// " = new "
0x8ff9b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ffa0  ldarg.0
0x8ffa1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ffa6  ldloc.1
0x8ffa7  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8ffac  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x8ffb1  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8ffb6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8ffbb  ldarg.0
0x8ffbc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ffc1  ldstr    asc_132DE6// "();"
0x8ffc6  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8ffcb  ldarg.0
0x8ffcc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8ffd1  ldc.i4.5
0x8ffd2  newarr   [mscorlib]System.String
0x8ffd7  dup
0x8ffd8  ldc.i4.0
0x8ffd9  ldstr    asc_12FF58// "(("
0x8ffde  stelem.ref
0x8ffdf  dup
0x8ffe0  ldc.i4.1
0x8ffe1  ldloc.1
0x8ffe2  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x8ffe7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x8ffec  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8fff1  stelem.ref
0x8fff2  dup
0x8fff3  ldc.i4.2
0x8fff4  ldstr    asc_129CD8// ")"
0x8fff9  stelem.ref
0x8fffa  dup
0x8fffb  ldc.i4.3
0x8fffc  ldloc.1
0x8fffd  callvirt instance string Member::get_ArraySource()
0x90002  stelem.ref
0x90003  dup
0x90004  ldc.i4.4
0x90005  ldstr    asc_129CD8// ")"
0x9000a  stelem.ref
0x9000b  call     string [mscorlib]System.String::Concat(string[])
0x90010  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90015  ldarg.0
0x90016  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9001b  ldstr    aAddReaderNameL// ".Add(Reader.Name.Length == 5 ? \"\" : R"...
0x90020  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90025  ldarg.0
0x90026  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9002b  dup
0x9002c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90031  stloc.3
0x90032  ldloc.3
0x90033  ldc.i4.1
0x90034  sub
0x90035  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9003a  ldarg.0
0x9003b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90040  ldstr    asc_12E936// "}"
0x90045  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9004a  ldarg.0
0x9004b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90050  ldstr    aElse// "else {"
0x90055  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9005a  ldarg.0
0x9005b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90060  dup
0x90061  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90066  stloc.3
0x90067  ldloc.3
0x90068  ldc.i4.1
0x90069  add
0x9006a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9006f  br.s     loc_90096
0x90071  ldarg.0
0x90072  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90077  ldstr    aIfIsxmlnsattri_0// "if (!IsXmlnsAttribute(Reader.Name)) {"
0x9007c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90081  ldarg.0
0x90082  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90087  dup
0x90088  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9008d  stloc.3
0x9008e  ldloc.3
0x9008f  ldc.i4.1
0x90090  add
0x90091  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x90096  ldarg.2
0x90097  brfalse  loc_9011C
0x9009c  ldarg.0
0x9009d  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x900a2  ldtoken  System.Xml.XmlAttribute
0x900a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x900ac  callvirt instance string [mscorlib]System.Type::get_FullName()
0x900b1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x900b6  ldarg.0
0x900b7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x900bc  ldstr    aAttr// " attr = "
0x900c1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x900c6  ldarg.0
0x900c7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x900cc  ldstr    asc_12DDFC// "("
0x900d1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x900d6  ldarg.0
0x900d7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x900dc  ldtoken  System.Xml.XmlAttribute
0x900e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x900e6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x900eb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x900f0  ldarg.0
0x900f1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x900f6  ldstr    aDocumentReadno// ") Document.ReadNode(Reader);"
0x900fb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90100  ldarg.0
0x90101  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90106  ldstr    aParsewsdlarray// "ParseWsdlArrayType(attr);"
  ... truncated ...
```
