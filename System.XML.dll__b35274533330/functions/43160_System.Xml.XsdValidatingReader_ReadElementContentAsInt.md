# System.Xml.XsdValidatingReader::ReadElementContentAsInt

- ea: `0x43160`
- end: `0x431dd`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsInt`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x43160`
- `0x44850`
- `0xd6c00`
- `0xdb210`

## string_xrefs

- `0x4319f`: `Xml_ReadContentAsFormatException`
- `0x431b3`: `Xml_ReadContentAsFormatException`
- `0x431c8`: `Xml_ReadContentAsFormatException`
- `0x4316a`: `ReadElementContentAsInt`

## pseudocode

```c

```

## disassembly

```asm
0x43160  ldarg.0
0x43161  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x43166  ldc.i4.1
0x43167  beq.s    loc_43175
0x43169  ldarg.0
0x4316a  ldstr    aReadelementcon_7// "ReadElementContentAsInt"
0x4316f  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x43174  throw
0x43175  ldarg.0
0x43176  ldloca.s 0
0x43178  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x4317d  stloc.1
0x4317e  ldloc.0
0x4317f  brfalse.s loc_43190
0x43181  ldloc.0
0x43182  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43187  ldloc.1
0x43188  callvirt instance int32 System.Xml.Schema.XmlValueConverter::ToInt32(object value)
0x4318d  stloc.2
0x4318e  leave.s  loc_431DB
0x43190  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x43195  ldloc.1
0x43196  callvirt instance int32 System.Xml.Schema.XmlValueConverter::ToInt32(object value)
0x4319b  stloc.2
0x4319c  leave.s  loc_431DB
0x4319e  stloc.3
0x4319f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x431a4  ldstr    aInt// "Int"
0x431a9  ldloc.3
0x431aa  ldarg.0
0x431ab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x431b0  throw
0x431b1  stloc.s  4
0x431b3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x431b8  ldstr    aInt// "Int"
0x431bd  ldloc.s  4
0x431bf  ldarg.0
0x431c0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x431c5  throw
0x431c6  stloc.s  5
0x431c8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x431cd  ldstr    aInt// "Int"
0x431d2  ldloc.s  5
0x431d4  ldarg.0
0x431d5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x431da  throw
0x431db  ldloc.2
0x431dc  ret
```
