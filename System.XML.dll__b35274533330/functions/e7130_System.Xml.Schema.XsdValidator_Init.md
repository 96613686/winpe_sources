# System.Xml.Schema.XsdValidator::Init

- ea: `0xe7130`
- end: `0xe7259`
- name: `System.Xml.Schema.XsdValidator::Init`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xe70f0`
- `0xe7110`

## callees

- `0xdfe0`
- `0x12ad0`
- `0x13200`
- `0x228e0`
- `0xaeb80`
- `0xc9af0`
- `0xe7130`
- `0xe8430`

## string_xrefs

- `0xe71af`: `http://www.w3.org/2000/xmlns/`
- `0xe71c5`: `http://www.w3.org/2001/XMLSchema`
- `0xe71db`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xe7130  ldarg.0
0xe7131  ldarg.0
0xe7132  ldfld    class System.Xml.XmlValidatingReaderImpl System.Xml.Schema.BaseValidator::reader
0xe7137  callvirt instance class System.Xml.XmlNamespaceManager System.Xml.XmlReader::get_NamespaceManager()
0xe713c  stfld    class System.Xml.XmlNamespaceManager System.Xml.Schema.XsdValidator::nsManager
0xe7141  ldarg.0
0xe7142  ldfld    class System.Xml.XmlNamespaceManager System.Xml.Schema.XsdValidator::nsManager
0xe7147  brtrue.s loc_E7161
0xe7149  ldarg.0
0xe714a  ldarg.0
0xe714b  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe7150  newobj   instance void System.Xml.XmlNamespaceManager::.ctor(class System.Xml.XmlNameTable nameTable)
0xe7155  stfld    class System.Xml.XmlNamespaceManager System.Xml.Schema.XsdValidator::nsManager
0xe715a  ldarg.0
0xe715b  ldc.i4.1
0xe715c  stfld    bool System.Xml.Schema.XsdValidator::bManageNamespaces
0xe7161  ldarg.0
0xe7162  ldc.i4.s 0xA
0xe7164  newobj   instance void System.Xml.HWStack::.ctor(int32 GrowthRate)
0xe7169  stfld    class System.Xml.HWStack System.Xml.Schema.XsdValidator::validationStack
0xe716e  ldarg.0
0xe716f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe7174  stfld    class [mscorlib]System.Text.StringBuilder System.Xml.Schema.BaseValidator::textValue
0xe7179  ldarg.0
0xe717a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xe717f  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Schema.XsdValidator::attPresence
0xe7184  ldarg.0
0xe7185  newobj   instance void System.Xml.Schema.SchemaInfo::.ctor()
0xe718a  stfld    class System.Xml.Schema.SchemaInfo System.Xml.Schema.BaseValidator::schemaInfo
0xe718f  ldarg.0
0xe7190  ldc.i4.0
0xe7191  stfld    bool System.Xml.Schema.BaseValidator::checkDatatype
0xe7196  ldarg.0
0xe7197  ldc.i4.3
0xe7198  stfld    valuetype System.Xml.Schema.XmlSchemaContentProcessing System.Xml.Schema.XsdValidator::processContents
0xe719d  ldarg.0
0xe719e  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0xe71a3  call     instance void System.Xml.Schema.XsdValidator::Push(class System.Xml.XmlQualifiedName elementName)
0xe71a8  ldarg.0
0xe71a9  ldarg.0
0xe71aa  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe71af  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xe71b4  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe71b9  stfld    string System.Xml.Schema.XsdValidator::NsXmlNs
0xe71be  ldarg.0
0xe71bf  ldarg.0
0xe71c0  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe71c5  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xe71ca  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe71cf  stfld    string System.Xml.Schema.XsdValidator::NsXs
0xe71d4  ldarg.0
0xe71d5  ldarg.0
0xe71d6  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe71db  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xe71e0  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe71e5  stfld    string System.Xml.Schema.XsdValidator::NsXsi
0xe71ea  ldarg.0
0xe71eb  ldarg.0
0xe71ec  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe71f1  ldstr    aType// "type"
0xe71f6  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe71fb  stfld    string System.Xml.Schema.XsdValidator::XsiType
0xe7200  ldarg.0
0xe7201  ldarg.0
0xe7202  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe7207  ldstr    aNil// "nil"
0xe720c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe7211  stfld    string System.Xml.Schema.XsdValidator::XsiNil
0xe7216  ldarg.0
0xe7217  ldarg.0
0xe7218  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe721d  ldstr    aSchemalocation// "schemaLocation"
0xe7222  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe7227  stfld    string System.Xml.Schema.XsdValidator::XsiSchemaLocation
0xe722c  ldarg.0
0xe722d  ldarg.0
0xe722e  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe7233  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xe7238  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe723d  stfld    string System.Xml.Schema.XsdValidator::XsiNoNamespaceSchemaLocation
0xe7242  ldarg.0
0xe7243  ldarg.0
0xe7244  call     instance class System.Xml.XmlNameTable System.Xml.Schema.BaseValidator::get_NameTable()
0xe7249  ldstr    aSchema// "schema"
0xe724e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xe7253  stfld    string System.Xml.Schema.XsdValidator::XsdSchema
0xe7258  ret
```
