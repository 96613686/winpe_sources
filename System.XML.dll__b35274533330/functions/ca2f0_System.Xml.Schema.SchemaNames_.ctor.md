# System.Xml.Schema.SchemaNames::.ctor

- ea: `0xca2f0`
- end: `0xcb02e`
- name: `System.Xml.Schema.SchemaNames::.ctor`
- size: `3390`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x85130`
- `0x85b40`
- `0xae6a0`
- `0xaeb90`
- `0xcf970`
- `0xd1220`
- `0xd5f10`

## callees

- `0x13200`
- `0x132d0`
- `0x132e0`
- `0xcb030`

## string_xrefs

- `0xca33f`: `http://www.w3.org/XML/1998/namespace`
- `0xca350`: `http://www.w3.org/2000/xmlns/`
- `0xca437`: `xmlns`
- `0xca383`: `http://www.w3.org/2001/XMLSchema`
- `0xca394`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xca30c`: `urn:schemas-microsoft-com:datatypes`
- `0xca971`: `xpath`
- `0xcad19`: `complexType`
- `0xcaf81`: `extension`
- `0xcaf2d`: `complexContent`
- `0xca6c7`: `nmtoken`
- `0xca6dd`: `nmtokens`
- `0xca361`: `urn:schemas-microsoft-com:xml-data`

## pseudocode

```c

```

## disassembly

```asm
0xca2f0  ldarg.0
0xca2f1  ldc.i4.s 0x7B
0xca2f3  newarr   System.Xml.XmlQualifiedName
0xca2f8  stfld    class System.Xml.XmlQualifiedName[] System.Xml.Schema.SchemaNames::TokenToQName
0xca2fd  ldarg.0
0xca2fe  call     instance void [mscorlib]System.Object::.ctor()
0xca303  ldarg.0
0xca304  ldarg.1
0xca305  stfld    class System.Xml.XmlNameTable System.Xml.Schema.SchemaNames::nameTable
0xca30a  ldarg.0
0xca30b  ldarg.1
0xca30c  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:datatypes"
0xca311  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca316  stfld    string System.Xml.Schema.SchemaNames::NsDataType
0xca31b  ldarg.0
0xca31c  ldarg.1
0xca31d  ldstr    aUuidC2f4101065// "uuid:C2F41010-65B3-11D1-A29F-00AA00C148"...
0xca322  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca327  stfld    string System.Xml.Schema.SchemaNames::NsDataTypeAlias
0xca32c  ldarg.0
0xca32d  ldarg.1
0xca32e  ldstr    aUrnUuidC2f4101// "urn:uuid:C2F41010-65B3-11D1-A29F-00AA00"...
0xca333  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca338  stfld    string System.Xml.Schema.SchemaNames::NsDataTypeOld
0xca33d  ldarg.0
0xca33e  ldarg.1
0xca33f  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xca344  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca349  stfld    string System.Xml.Schema.SchemaNames::NsXml
0xca34e  ldarg.0
0xca34f  ldarg.1
0xca350  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xca355  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca35a  stfld    string System.Xml.Schema.SchemaNames::NsXmlNs
0xca35f  ldarg.0
0xca360  ldarg.1
0xca361  ldstr    aUrnSchemasMicr_1// "urn:schemas-microsoft-com:xml-data"
0xca366  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca36b  stfld    string System.Xml.Schema.SchemaNames::NsXdr
0xca370  ldarg.0
0xca371  ldarg.1
0xca372  ldstr    aUuidBdc6e3f06d// "uuid:BDC6E3F0-6DA3-11D1-A2A3-00AA00C148"...
0xca377  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca37c  stfld    string System.Xml.Schema.SchemaNames::NsXdrAlias
0xca381  ldarg.0
0xca382  ldarg.1
0xca383  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xca388  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca38d  stfld    string System.Xml.Schema.SchemaNames::NsXs
0xca392  ldarg.0
0xca393  ldarg.1
0xca394  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xca399  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca39e  stfld    string System.Xml.Schema.SchemaNames::NsXsi
0xca3a3  ldarg.0
0xca3a4  ldarg.1
0xca3a5  ldstr    aType// "type"
0xca3aa  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca3af  stfld    string System.Xml.Schema.SchemaNames::XsiType
0xca3b4  ldarg.0
0xca3b5  ldarg.1
0xca3b6  ldstr    aNil// "nil"
0xca3bb  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca3c0  stfld    string System.Xml.Schema.SchemaNames::XsiNil
0xca3c5  ldarg.0
0xca3c6  ldarg.1
0xca3c7  ldstr    aSchemalocation// "schemaLocation"
0xca3cc  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca3d1  stfld    string System.Xml.Schema.SchemaNames::XsiSchemaLocation
0xca3d6  ldarg.0
0xca3d7  ldarg.1
0xca3d8  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xca3dd  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca3e2  stfld    string System.Xml.Schema.SchemaNames::XsiNoNamespaceSchemaLocation
0xca3e7  ldarg.0
0xca3e8  ldarg.1
0xca3e9  ldstr    aSchema// "schema"
0xca3ee  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca3f3  stfld    string System.Xml.Schema.SchemaNames::XsdSchema
0xca3f8  ldarg.0
0xca3f9  ldarg.1
0xca3fa  ldstr    aSchema_0// "Schema"
0xca3ff  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca404  stfld    string System.Xml.Schema.SchemaNames::XdrSchema
0xca409  ldarg.0
0xca40a  ldarg.1
0xca40b  ldstr    aPcdata// "#PCDATA"
0xca410  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca415  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca41a  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnPCData
0xca41f  ldarg.0
0xca420  ldarg.1
0xca421  ldstr    aXml// "xml"
0xca426  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca42b  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca430  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnXml
0xca435  ldarg.0
0xca436  ldarg.1
0xca437  ldstr    aXmlns// "xmlns"
0xca43c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca441  ldarg.0
0xca442  ldfld    string System.Xml.Schema.SchemaNames::NsXmlNs
0xca447  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xca44c  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnXmlNs
0xca451  ldarg.0
0xca452  ldarg.1
0xca453  ldstr    aDt// "dt"
0xca458  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca45d  ldarg.0
0xca45e  ldfld    string System.Xml.Schema.SchemaNames::NsDataType
0xca463  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xca468  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnDtDt
0xca46d  ldarg.0
0xca46e  ldarg.1
0xca46f  ldstr    aLang// "lang"
0xca474  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca479  ldarg.0
0xca47a  ldfld    string System.Xml.Schema.SchemaNames::NsXml
0xca47f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xca484  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnXmlLang
0xca489  ldarg.0
0xca48a  ldarg.1
0xca48b  ldstr    aName// "name"
0xca490  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca495  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca49a  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnName
0xca49f  ldarg.0
0xca4a0  ldarg.1
0xca4a1  ldstr    aType// "type"
0xca4a6  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca4ab  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca4b0  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnType
0xca4b5  ldarg.0
0xca4b6  ldarg.1
0xca4b7  ldstr    aMaxoccurs// "maxOccurs"
0xca4bc  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca4c1  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca4c6  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnMaxOccurs
0xca4cb  ldarg.0
0xca4cc  ldarg.1
0xca4cd  ldstr    aMinoccurs// "minOccurs"
0xca4d2  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca4d7  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca4dc  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnMinOccurs
0xca4e1  ldarg.0
0xca4e2  ldarg.1
0xca4e3  ldstr    asc_128452// "*"
0xca4e8  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca4ed  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca4f2  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnInfinite
0xca4f7  ldarg.0
0xca4f8  ldarg.1
0xca4f9  ldstr    aModel// "model"
0xca4fe  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca503  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca508  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnModel
0xca50d  ldarg.0
0xca50e  ldarg.1
0xca50f  ldstr    aOpen// "open"
0xca514  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca519  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca51e  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnOpen
0xca523  ldarg.0
0xca524  ldarg.1
0xca525  ldstr    aClosed_0// "closed"
0xca52a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca52f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca534  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnClosed
0xca539  ldarg.0
0xca53a  ldarg.1
0xca53b  ldstr    aContent// "content"
0xca540  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca545  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca54a  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnContent
0xca54f  ldarg.0
0xca550  ldarg.1
0xca551  ldstr    aMixed// "mixed"
0xca556  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca55b  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca560  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnMixed
0xca565  ldarg.0
0xca566  ldarg.1
0xca567  ldstr    aEmpty_0// "empty"
0xca56c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca571  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca576  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnEmpty
0xca57b  ldarg.0
0xca57c  ldarg.1
0xca57d  ldstr    aEltonly// "eltOnly"
0xca582  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca587  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca58c  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnEltOnly
0xca591  ldarg.0
0xca592  ldarg.1
0xca593  ldstr    aTextonly_0// "textOnly"
0xca598  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca59d  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca5a2  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnTextOnly
0xca5a7  ldarg.0
0xca5a8  ldarg.1
0xca5a9  ldstr    aOrder_0// "order"
0xca5ae  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca5b3  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca5b8  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnOrder
0xca5bd  ldarg.0
0xca5be  ldarg.1
0xca5bf  ldstr    aSeq// "seq"
0xca5c4  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca5c9  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca5ce  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnSeq
0xca5d3  ldarg.0
0xca5d4  ldarg.1
0xca5d5  ldstr    aOne// "one"
0xca5da  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca5df  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca5e4  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnOne
0xca5e9  ldarg.0
0xca5ea  ldarg.1
0xca5eb  ldstr    aMany// "many"
0xca5f0  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca5f5  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca5fa  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnMany
0xca5ff  ldarg.0
0xca600  ldarg.1
0xca601  ldstr    aRequired// "required"
0xca606  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca60b  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca610  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnRequired
0xca615  ldarg.0
0xca616  ldarg.1
0xca617  ldstr    aYes// "yes"
0xca61c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca621  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca626  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnYes
0xca62b  ldarg.0
0xca62c  ldarg.1
0xca62d  ldstr    aNo// "no"
0xca632  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca637  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca63c  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnNo
0xca641  ldarg.0
0xca642  ldarg.1
0xca643  ldstr    aString// "string"
0xca648  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca64d  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca652  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnString
0xca657  ldarg.0
0xca658  ldarg.1
0xca659  ldstr    aId// "id"
0xca65e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca663  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca668  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnID
0xca66d  ldarg.0
0xca66e  ldarg.1
0xca66f  ldstr    aIdref_0// "idref"
0xca674  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca679  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca67e  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnIDRef
0xca683  ldarg.0
0xca684  ldarg.1
0xca685  ldstr    aIdrefs_0// "idrefs"
0xca68a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca68f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca694  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnIDRefs
0xca699  ldarg.0
0xca69a  ldarg.1
0xca69b  ldstr    aEntity_0// "entity"
0xca6a0  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca6a5  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca6aa  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnEntity
0xca6af  ldarg.0
0xca6b0  ldarg.1
0xca6b1  ldstr    aEntities_0// "entities"
0xca6b6  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca6bb  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca6c0  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnEntities
0xca6c5  ldarg.0
0xca6c6  ldarg.1
0xca6c7  ldstr    aNmtoken_1// "nmtoken"
0xca6cc  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca6d1  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca6d6  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnNmToken
0xca6db  ldarg.0
0xca6dc  ldarg.1
0xca6dd  ldstr    aNmtokens_0// "nmtokens"
0xca6e2  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca6e7  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca6ec  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnNmTokens
0xca6f1  ldarg.0
0xca6f2  ldarg.1
0xca6f3  ldstr    aEnumeration// "enumeration"
0xca6f8  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca6fd  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca702  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnEnumeration
0xca707  ldarg.0
0xca708  ldarg.1
0xca709  ldstr    aDefault// "default"
0xca70e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0xca713  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0xca718  stfld    class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaNames::QnDefault
  ... truncated ...
```
