# System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::InitializeDefault

- ea: `0xacdd0`
- end: `0xad09a`
- name: `System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::InitializeDefault`
- size: `714`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0xacb90`
- `0xacce0`
- `0xacdb0`
- `0xad0b0`

## string_xrefs

- `0xacddb`: `TypeCharSchemaImporterExtension`
- `0xacdfa`: `TypeNCharSchemaImporterExtension`
- `0xace19`: `TypeVarCharSchemaImporterExtension`
- `0xace38`: `TypeNVarCharSchemaImporterExtension`
- `0xace57`: `TypeTextSchemaImporterExtension`
- `0xace76`: `TypeNTextSchemaImporterExtension`
- `0xace95`: `TypeVarBinarySchemaImporterExtension`
- `0xaceb4`: `TypeBinarySchemaImporterExtension`
- `0xaced3`: `TypeVarImageSchemaImporterExtension`
- `0xacef2`: `TypeDecimalSchemaImporterExtension`
- `0xacf11`: `TypeNumericSchemaImporterExtension`
- `0xacf30`: `TypeBigIntSchemaImporterExtension`
- `0xacf4f`: `TypeIntSchemaImporterExtension`
- `0xacf6e`: `TypeSmallIntSchemaImporterExtension`
- `0xacf8d`: `TypeTinyIntSchemaImporterExtension`
- `0xacfac`: `TypeBitSchemaImporterExtension`
- `0xacfcb`: `TypeFloatSchemaImporterExtension`
- `0xacfea`: `TypeRealSchemaImporterExtension`
- `0xad009`: `TypeDateTimeSchemaImporterExtension`
- `0xad028`: `TypeSmallDateTimeSchemaImporterExtension`
- `0xad047`: `TypeMoneySchemaImporterExtension`
- `0xad066`: `TypeSmallMoneySchemaImporterExtension`
- `0xad085`: `TypeUniqueIdentifierSchemaImporterExtension`

## pseudocode

```c

```

## disassembly

```asm
0xacdd0  ldarg.0
0xacdd1  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacdd6  ldstr    aSqltypesschema// "SqlTypesSchemaImporterChar"
0xacddb  ldstr    aTypecharschema// "TypeCharSchemaImporterExtension"
0xacde0  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacde5  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacdea  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacdef  ldarg.0
0xacdf0  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacdf5  ldstr    aSqltypesschema_0// "SqlTypesSchemaImporterNChar"
0xacdfa  ldstr    aTypencharschem// "TypeNCharSchemaImporterExtension"
0xacdff  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace04  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xace09  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xace0e  ldarg.0
0xace0f  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xace14  ldstr    aSqltypesschema_1// "SqlTypesSchemaImporterVarChar"
0xace19  ldstr    aTypevarcharsch// "TypeVarCharSchemaImporterExtension"
0xace1e  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace23  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xace28  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xace2d  ldarg.0
0xace2e  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xace33  ldstr    aSqltypesschema_2// "SqlTypesSchemaImporterNVarChar"
0xace38  ldstr    aTypenvarcharsc// "TypeNVarCharSchemaImporterExtension"
0xace3d  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace42  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xace47  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xace4c  ldarg.0
0xace4d  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xace52  ldstr    aSqltypesschema_3// "SqlTypesSchemaImporterText"
0xace57  ldstr    aTypetextschema// "TypeTextSchemaImporterExtension"
0xace5c  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace61  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xace66  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xace6b  ldarg.0
0xace6c  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xace71  ldstr    aSqltypesschema_4// "SqlTypesSchemaImporterNText"
0xace76  ldstr    aTypentextschem// "TypeNTextSchemaImporterExtension"
0xace7b  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace80  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xace85  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xace8a  ldarg.0
0xace8b  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xace90  ldstr    aSqltypesschema_5// "SqlTypesSchemaImporterVarBinary"
0xace95  ldstr    aTypevarbinarys// "TypeVarBinarySchemaImporterExtension"
0xace9a  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xace9f  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacea4  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacea9  ldarg.0
0xaceaa  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xaceaf  ldstr    aSqltypesschema_6// "SqlTypesSchemaImporterBinary"
0xaceb4  ldstr    aTypebinarysche// "TypeBinarySchemaImporterExtension"
0xaceb9  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacebe  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacec3  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacec8  ldarg.0
0xacec9  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacece  ldstr    aSqltypesschema_7// "SqlTypesSchemaImporterImage"
0xaced3  ldstr    aTypevarimagesc// "TypeVarImageSchemaImporterExtension"
0xaced8  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacedd  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacee2  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacee7  ldarg.0
0xacee8  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xaceed  ldstr    aSqltypesschema_8// "SqlTypesSchemaImporterDecimal"
0xacef2  ldstr    aTypedecimalsch// "TypeDecimalSchemaImporterExtension"
0xacef7  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacefc  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf01  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacf06  ldarg.0
0xacf07  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacf0c  ldstr    aSqltypesschema_9// "SqlTypesSchemaImporterNumeric"
0xacf11  ldstr    aTypenumericsch// "TypeNumericSchemaImporterExtension"
0xacf16  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacf1b  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf20  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacf25  ldarg.0
0xacf26  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacf2b  ldstr    aSqltypesschema_10// "SqlTypesSchemaImporterBigInt"
0xacf30  ldstr    aTypebigintsche// "TypeBigIntSchemaImporterExtension"
0xacf35  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacf3a  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf3f  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacf44  ldarg.0
0xacf45  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacf4a  ldstr    aSqltypesschema_11// "SqlTypesSchemaImporterInt"
0xacf4f  ldstr    aTypeintschemai// "TypeIntSchemaImporterExtension"
0xacf54  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacf59  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf5e  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacf63  ldarg.0
0xacf64  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacf69  ldstr    aSqltypesschema_12// "SqlTypesSchemaImporterSmallInt"
0xacf6e  ldstr    aTypesmallintsc// "TypeSmallIntSchemaImporterExtension"
0xacf73  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacf78  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf7d  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacf82  ldarg.0
0xacf83  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacf88  ldstr    aSqltypesschema_13// "SqlTypesSchemaImporterTinyInt"
0xacf8d  ldstr    aTypetinyintsch// "TypeTinyIntSchemaImporterExtension"
0xacf92  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacf97  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacf9c  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacfa1  ldarg.0
0xacfa2  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacfa7  ldstr    aSqltypesschema_14// "SqlTypesSchemaImporterBit"
0xacfac  ldstr    aTypebitschemai// "TypeBitSchemaImporterExtension"
0xacfb1  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacfb6  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacfbb  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacfc0  ldarg.0
0xacfc1  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacfc6  ldstr    aSqltypesschema_15// "SqlTypesSchemaImporterFloat"
0xacfcb  ldstr    aTypefloatschem// "TypeFloatSchemaImporterExtension"
0xacfd0  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacfd5  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacfda  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacfdf  ldarg.0
0xacfe0  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xacfe5  ldstr    aSqltypesschema_16// "SqlTypesSchemaImporterReal"
0xacfea  ldstr    aTyperealschema// "TypeRealSchemaImporterExtension"
0xacfef  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xacff4  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xacff9  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xacffe  ldarg.0
0xacfff  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xad004  ldstr    aSqltypesschema_17// "SqlTypesSchemaImporterDateTime"
0xad009  ldstr    aTypedatetimesc// "TypeDateTimeSchemaImporterExtension"
0xad00e  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xad013  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xad018  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xad01d  ldarg.0
0xad01e  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xad023  ldstr    aSqltypesschema_18// "SqlTypesSchemaImporterSmallDateTime"
0xad028  ldstr    aTypesmalldatet// "TypeSmallDateTimeSchemaImporterExtensio"...
0xad02d  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xad032  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xad037  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xad03c  ldarg.0
0xad03d  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xad042  ldstr    aSqltypesschema_19// "SqlTypesSchemaImporterMoney"
0xad047  ldstr    aTypemoneyschem// "TypeMoneySchemaImporterExtension"
0xad04c  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xad051  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xad056  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xad05b  ldarg.0
0xad05c  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xad061  ldstr    aSqltypesschema_20// "SqlTypesSchemaImporterSmallMoney"
0xad066  ldstr    aTypesmallmoney// "TypeSmallMoneySchemaImporterExtension"
0xad06b  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xad070  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xad075  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xad07a  ldarg.0
0xad07b  call     instance class System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::get_SchemaImporterExtensions()
0xad080  ldstr    aSqltypesschema_21// "SqlTypesSchemaImporterUniqueIdentifier"
0xad085  ldstr    aTypeuniqueiden// "TypeUniqueIdentifierSchemaImporterExten"...
0xad08a  call     string System.Xml.Serialization.Configuration.SchemaImporterExtensionsSection::GetSqlTypeSchemaImporter(string typeName)
0xad08f  newobj   instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElement::.ctor(string name, string type)
0xad094  callvirt instance void System.Xml.Serialization.Configuration.SchemaImporterExtensionElementCollection::Add(class System.Xml.Serialization.Configuration.SchemaImporterExtensionElement element)
0xad099  ret
```
