# System.Xml.Schema.XmlSchemaValidator::Init

- ea: `0xd7160`
- end: `0xd7288`
- name: `System.Xml.Schema.XmlSchemaValidator::Init`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xd7080`

## callees

- `0xdfe0`
- `0xe2b0`
- `0x13200`
- `0x132b0`
- `0xd7290`
- `0xd8e90`
- `0xd96a0`
- `0xf2300`

## string_xrefs

- `0xd7220`: `http://www.w3.org/XML/1998/namespace`
- `0xd720a`: `http://www.w3.org/2000/xmlns/`
- `0xd71de`: `http://www.w3.org/2001/XMLSchema`
- `0xd71f4`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xd7160  ldarg.0
0xd7161  ldc.i4.s 0xA
0xd7163  newobj   instance void System.Xml.HWStack::.ctor(int32 GrowthRate)
0xd7168  stfld    class System.Xml.HWStack System.Xml.Schema.XmlSchemaValidator::validationStack
0xd716d  ldarg.0
0xd716e  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xd7173  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Schema.XmlSchemaValidator::attPresence
0xd7178  ldarg.0
0xd7179  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0xd717e  call     instance void System.Xml.Schema.XmlSchemaValidator::Push(class System.Xml.XmlQualifiedName elementName)
0xd7183  ldarg.0
0xd7184  newobj   instance void System.Xml.PositionInfo::.ctor()
0xd7189  stfld    class System.Xml.IXmlLineInfo System.Xml.Schema.XmlSchemaValidator::dummyPositionInfo
0xd718e  ldarg.0
0xd718f  ldarg.0
0xd7190  ldfld    class System.Xml.IXmlLineInfo System.Xml.Schema.XmlSchemaValidator::dummyPositionInfo
0xd7195  stfld    class System.Xml.IXmlLineInfo System.Xml.Schema.XmlSchemaValidator::positionInfo
0xd719a  ldarg.0
0xd719b  ldarg.0
0xd719c  stfld    object System.Xml.Schema.XmlSchemaValidator::validationEventSender
0xd71a1  ldarg.0
0xd71a2  ldc.i4.0
0xd71a3  stfld    valuetype System.Xml.Schema.ValidatorState System.Xml.Schema.XmlSchemaValidator::currentState
0xd71a8  ldarg.0
0xd71a9  ldc.i4.s 0x64
0xd71ab  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xd71b0  stfld    class [mscorlib]System.Text.StringBuilder System.Xml.Schema.XmlSchemaValidator::textValue
0xd71b5  ldarg.0
0xd71b6  call     class System.Xml.XmlResolver System.Xml.XmlConfiguration.XmlReaderSection::CreateDefaultResolver()
0xd71bb  stfld    class System.Xml.XmlResolver System.Xml.Schema.XmlSchemaValidator::xmlResolver
0xd71c0  ldarg.0
0xd71c1  newobj   instance void System.Xml.XmlQualifiedName::.ctor()
0xd71c6  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaValidator::contextQName
0xd71cb  ldarg.0
0xd71cc  call     instance void System.Xml.Schema.XmlSchemaValidator::Reset()
0xd71d1  ldarg.0
0xd71d2  call     instance void System.Xml.Schema.XmlSchemaValidator::RecompileSchemaSet()
0xd71d7  ldarg.0
0xd71d8  ldarg.0
0xd71d9  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd71de  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xd71e3  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd71e8  stfld    string System.Xml.Schema.XmlSchemaValidator::NsXs
0xd71ed  ldarg.0
0xd71ee  ldarg.0
0xd71ef  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd71f4  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xd71f9  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd71fe  stfld    string System.Xml.Schema.XmlSchemaValidator::NsXsi
0xd7203  ldarg.0
0xd7204  ldarg.0
0xd7205  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd720a  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xd720f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd7214  stfld    string System.Xml.Schema.XmlSchemaValidator::NsXmlNs
0xd7219  ldarg.0
0xd721a  ldarg.0
0xd721b  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd7220  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xd7225  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd722a  stfld    string System.Xml.Schema.XmlSchemaValidator::NsXml
0xd722f  ldarg.0
0xd7230  ldarg.0
0xd7231  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd7236  ldstr    aType// "type"
0xd723b  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd7240  stfld    string System.Xml.Schema.XmlSchemaValidator::xsiTypeString
0xd7245  ldarg.0
0xd7246  ldarg.0
0xd7247  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd724c  ldstr    aNil// "nil"
0xd7251  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd7256  stfld    string System.Xml.Schema.XmlSchemaValidator::xsiNilString
0xd725b  ldarg.0
0xd725c  ldarg.0
0xd725d  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd7262  ldstr    aSchemalocation// "schemaLocation"
0xd7267  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd726c  stfld    string System.Xml.Schema.XmlSchemaValidator::xsiSchemaLocationString
0xd7271  ldarg.0
0xd7272  ldarg.0
0xd7273  ldfld    class System.Xml.XmlNameTable System.Xml.Schema.XmlSchemaValidator::nameTable
0xd7278  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xd727d  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xd7282  stfld    string System.Xml.Schema.XmlSchemaValidator::xsiNoNamespaceSchemaLocationString
0xd7287  ret
```
