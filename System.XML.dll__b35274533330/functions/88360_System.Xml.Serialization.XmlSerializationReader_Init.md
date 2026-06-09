# System.Xml.Serialization.XmlSerializationReader::Init

- ea: `0x88360`
- end: `0x8856e`
- name: `System.Xml.Serialization.XmlSerializationReader::Init`
- size: `526`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x66b80`
- `0xaa2c0`
- `0xaac70`

## callees

- `0x13200`
- `0x21cc0`
- `0x77d90`
- `0x86020`
- `0x88350`
- `0x88360`

## string_xrefs

- `0x883b6`: `http://www.w3.org/2001/XMLSchema`
- `0x8840e`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x88450`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x88492`: `http://schemas.xmlsoap.org/wsdl/`
- `0x883f8`: `http://microsoft.com/wsdl/types/`
- `0x883cc`: `http://www.w3.org/2000/10/XMLSchema`
- `0x883e2`: `http://www.w3.org/1999/XMLSchema`
- `0x88424`: `http://www.w3.org/2000/10/XMLSchema-instance`
- `0x8843a`: `http://www.w3.org/1999/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x88360  ldarg.0
0x88361  ldarg.2
0x88362  stfld    valuetype System.Xml.Serialization.XmlDeserializationEvents System.Xml.Serialization.XmlSerializationReader::events
0x88367  ldsfld   bool System.Xml.Serialization.XmlSerializationReader::checkDeserializeAdvances
0x8836c  brfalse.s loc_88388
0x8836e  ldarg.0
0x8836f  ldarg.1
0x88370  newobj   instance void System.Xml.Serialization.XmlCountingReader::.ctor(class System.Xml.XmlReader xmlReader)
0x88375  stfld    class System.Xml.Serialization.XmlCountingReader System.Xml.Serialization.XmlSerializationReader::countingReader
0x8837a  ldarg.0
0x8837b  ldarg.0
0x8837c  ldfld    class System.Xml.Serialization.XmlCountingReader System.Xml.Serialization.XmlSerializationReader::countingReader
0x88381  stfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88386  br.s     loc_8838F
0x88388  ldarg.0
0x88389  ldarg.1
0x8838a  stfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8838f  ldarg.0
0x88390  ldnull
0x88391  stfld    class System.Xml.XmlDocument System.Xml.Serialization.XmlSerializationReader::d
0x88396  ldarg.0
0x88397  ldarg.3
0x88398  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x8839d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x883a2  stfld    bool System.Xml.Serialization.XmlSerializationReader::soap12
0x883a7  ldarg.0
0x883a8  ldarg.s  4
0x883aa  call     instance void System.Xml.Serialization.XmlSerializationGeneratedCode::Init(class System.Xml.Serialization.TempAssembly tempAssembly)
0x883af  ldarg.0
0x883b0  ldarg.1
0x883b1  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x883b6  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x883bb  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x883c0  stfld    string System.Xml.Serialization.XmlSerializationReader::schemaNsID
0x883c5  ldarg.0
0x883c6  ldarg.1
0x883c7  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x883cc  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2000/10/XMLSchema"
0x883d1  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x883d6  stfld    string System.Xml.Serialization.XmlSerializationReader::schemaNs2000ID
0x883db  ldarg.0
0x883dc  ldarg.1
0x883dd  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x883e2  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XMLSchema"
0x883e7  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x883ec  stfld    string System.Xml.Serialization.XmlSerializationReader::schemaNs1999ID
0x883f1  ldarg.0
0x883f2  ldarg.1
0x883f3  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x883f8  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x883fd  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88402  stfld    string System.Xml.Serialization.XmlSerializationReader::schemaNonXsdTypesNsID
0x88407  ldarg.0
0x88408  ldarg.1
0x88409  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8840e  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0x88413  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88418  stfld    string System.Xml.Serialization.XmlSerializationReader::instanceNsID
0x8841d  ldarg.0
0x8841e  ldarg.1
0x8841f  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88424  ldstr    aHttpWwwW3Org20_4// "http://www.w3.org/2000/10/XMLSchema-ins"...
0x88429  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8842e  stfld    string System.Xml.Serialization.XmlSerializationReader::instanceNs2000ID
0x88433  ldarg.0
0x88434  ldarg.1
0x88435  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8843a  ldstr    aHttpWwwW3Org19_0// "http://www.w3.org/1999/XMLSchema-instan"...
0x8843f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88444  stfld    string System.Xml.Serialization.XmlSerializationReader::instanceNs1999ID
0x88449  ldarg.0
0x8844a  ldarg.1
0x8844b  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88450  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x88455  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8845a  stfld    string System.Xml.Serialization.XmlSerializationReader::soapNsID
0x8845f  ldarg.0
0x88460  ldarg.1
0x88461  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88466  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x8846b  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88470  stfld    string System.Xml.Serialization.XmlSerializationReader::soap12NsID
0x88475  ldarg.0
0x88476  ldarg.1
0x88477  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8847c  ldstr    aSchema// "schema"
0x88481  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88486  stfld    string System.Xml.Serialization.XmlSerializationReader::schemaID
0x8848b  ldarg.0
0x8848c  ldarg.1
0x8848d  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88492  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/wsdl/"
0x88497  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8849c  stfld    string System.Xml.Serialization.XmlSerializationReader::wsdlNsID
0x884a1  ldarg.0
0x884a2  ldarg.1
0x884a3  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x884a8  ldstr    aArraytype// "arrayType"
0x884ad  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x884b2  stfld    string System.Xml.Serialization.XmlSerializationReader::wsdlArrayTypeID
0x884b7  ldarg.0
0x884b8  ldarg.1
0x884b9  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x884be  ldstr    aNull_0// "null"
0x884c3  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x884c8  stfld    string System.Xml.Serialization.XmlSerializationReader::nullID
0x884cd  ldarg.0
0x884ce  ldarg.1
0x884cf  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x884d4  ldstr    aNil// "nil"
0x884d9  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x884de  stfld    string System.Xml.Serialization.XmlSerializationReader::nilID
0x884e3  ldarg.0
0x884e4  ldarg.1
0x884e5  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x884ea  ldstr    aType// "type"
0x884ef  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x884f4  stfld    string System.Xml.Serialization.XmlSerializationReader::typeID
0x884f9  ldarg.0
0x884fa  ldarg.1
0x884fb  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88500  ldstr    aArraytype// "arrayType"
0x88505  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8850a  stfld    string System.Xml.Serialization.XmlSerializationReader::arrayTypeID
0x8850f  ldarg.0
0x88510  ldarg.1
0x88511  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88516  ldstr    aItemtype// "itemType"
0x8851b  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88520  stfld    string System.Xml.Serialization.XmlSerializationReader::itemTypeID
0x88525  ldarg.0
0x88526  ldarg.1
0x88527  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8852c  ldstr    aArraysize// "arraySize"
0x88531  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88536  stfld    string System.Xml.Serialization.XmlSerializationReader::arraySizeID
0x8853b  ldarg.0
0x8853c  ldarg.1
0x8853d  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88542  ldstr    aArray_0// "Array"
0x88547  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8854c  stfld    string System.Xml.Serialization.XmlSerializationReader::arrayID
0x88551  ldarg.0
0x88552  ldarg.1
0x88553  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88558  ldstr    aAnytype// "anyType"
0x8855d  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88562  stfld    string System.Xml.Serialization.XmlSerializationReader::urTypeID
0x88567  ldarg.0
0x88568  callvirt instance void System.Xml.Serialization.XmlSerializationReader::InitIDs()
0x8856d  ret
```
