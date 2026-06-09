# System.Xml.Serialization.TypeScope::.cctor

- ea: `0x73190`
- end: `0x73636`
- name: `System.Xml.Serialization.TypeScope::.cctor`
- size: `1190`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc240`
- `0x132e0`
- `0x6b1c0`
- `0x73190`
- `0x73740`
- `0x73c30`
- `0x73c80`
- `0xd3310`
- `0xd3410`

## string_xrefs

- `0x73546`: `http://www.w3.org/2001/XMLSchema`
- `0x73582`: `http://www.w3.org/2001/XMLSchema`
- `0x735c1`: `http://www.w3.org/2001/XMLSchema`
- `0x735db`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x73537`: `http://microsoft.com/wsdl/types/`
- `0x73573`: `http://microsoft.com/wsdl/types/`
- `0x735b2`: `http://microsoft.com/wsdl/types/`
- `0x731b7`: `anyURI`
- `0x7325a`: `token`
- `0x73382`: `XmlQualifiedName`
- `0x73472`: `XmlName`
- `0x73490`: `XmlNCName`
- `0x734a9`: `NMTOKEN`
- `0x734ae`: `XmlNmToken`
- `0x734c7`: `NMTOKENS`
- `0x734cc`: `XmlNmTokens`

## pseudocode

```c

```

## disassembly

```asm
0x73190  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x73195  stsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.TypeScope::primitiveTypes
0x7319a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x7319f  stsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.TypeScope::primitiveDataTypes
0x731a4  newobj   instance void System.Xml.Serialization.NameTable::.ctor()
0x731a9  stsfld   class System.Xml.Serialization.NameTable System.Xml.Serialization.TypeScope::primitiveNames
0x731ae  ldc.i4.s 0x14
0x731b0  newarr   [mscorlib]System.String
0x731b5  dup
0x731b6  ldc.i4.0
0x731b7  ldstr    aAnyuri// "anyURI"
0x731bc  stelem.ref
0x731bd  dup
0x731be  ldc.i4.1
0x731bf  ldstr    aDuration// "duration"
0x731c4  stelem.ref
0x731c5  dup
0x731c6  ldc.i4.2
0x731c7  ldstr    aEntity_1// "ENTITY"
0x731cc  stelem.ref
0x731cd  dup
0x731ce  ldc.i4.3
0x731cf  ldstr    aEntities// "ENTITIES"
0x731d4  stelem.ref
0x731d5  dup
0x731d6  ldc.i4.4
0x731d7  ldstr    aGday// "gDay"
0x731dc  stelem.ref
0x731dd  dup
0x731de  ldc.i4.5
0x731df  ldstr    aGmonth// "gMonth"
0x731e4  stelem.ref
0x731e5  dup
0x731e6  ldc.i4.6
0x731e7  ldstr    aGmonthday// "gMonthDay"
0x731ec  stelem.ref
0x731ed  dup
0x731ee  ldc.i4.7
0x731ef  ldstr    aGyear// "gYear"
0x731f4  stelem.ref
0x731f5  dup
0x731f6  ldc.i4.8
0x731f7  ldstr    aGyearmonth// "gYearMonth"
0x731fc  stelem.ref
0x731fd  dup
0x731fe  ldc.i4.s 9
0x73200  ldstr    aId_0// "ID"
0x73205  stelem.ref
0x73206  dup
0x73207  ldc.i4.s 0xA
0x73209  ldstr    aIdref// "IDREF"
0x7320e  stelem.ref
0x7320f  dup
0x73210  ldc.i4.s 0xB
0x73212  ldstr    aIdrefs// "IDREFS"
0x73217  stelem.ref
0x73218  dup
0x73219  ldc.i4.s 0xC
0x7321b  ldstr    aInteger_0// "integer"
0x73220  stelem.ref
0x73221  dup
0x73222  ldc.i4.s 0xD
0x73224  ldstr    aLanguage// "language"
0x73229  stelem.ref
0x7322a  dup
0x7322b  ldc.i4.s 0xE
0x7322d  ldstr    aNegativeintege// "negativeInteger"
0x73232  stelem.ref
0x73233  dup
0x73234  ldc.i4.s 0xF
0x73236  ldstr    aNonnegativeint// "nonNegativeInteger"
0x7323b  stelem.ref
0x7323c  dup
0x7323d  ldc.i4.s 0x10
0x7323f  ldstr    aNonpositiveint// "nonPositiveInteger"
0x73244  stelem.ref
0x73245  dup
0x73246  ldc.i4.s 0x11
0x73248  ldstr    aNotation_0// "NOTATION"
0x7324d  stelem.ref
0x7324e  dup
0x7324f  ldc.i4.s 0x12
0x73251  ldstr    aPositiveintege// "positiveInteger"
0x73256  stelem.ref
0x73257  dup
0x73258  ldc.i4.s 0x13
0x7325a  ldstr    aToken// "token"
0x7325f  stelem.ref
0x73260  stsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x73265  ldtoken  [mscorlib]System.String
0x7326a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7326f  ldstr    aString// "string"
0x73274  ldstr    aString_0// "String"
0x73279  ldc.i4   0x83A
0x7327e  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73283  ldtoken  [mscorlib]System.Int32
0x73288  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7328d  ldstr    aInt_0// "int"
0x73292  ldstr    aInt32// "Int32"
0x73297  ldc.i4   0x1028
0x7329c  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x732a1  ldtoken  [mscorlib]System.Boolean
0x732a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x732ab  ldstr    aBoolean// "boolean"
0x732b0  ldstr    aBoolean_0// "Boolean"
0x732b5  ldc.i4   0x1028
0x732ba  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x732bf  ldtoken  [mscorlib]System.Int16
0x732c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x732c9  ldstr    aShort// "short"
0x732ce  ldstr    aInt16// "Int16"
0x732d3  ldc.i4   0x1028
0x732d8  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x732dd  ldtoken  [mscorlib]System.Int64
0x732e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x732e7  ldstr    aLong_0// "long"
0x732ec  ldstr    aInt64// "Int64"
0x732f1  ldc.i4   0x1028
0x732f6  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x732fb  ldtoken  [mscorlib]System.Single
0x73300  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73305  ldstr    aFloat_0// "float"
0x7330a  ldstr    aSingle// "Single"
0x7330f  ldc.i4   0x1028
0x73314  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73319  ldtoken  [mscorlib]System.Double
0x7331e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73323  ldstr    aDouble_0// "double"
0x73328  ldstr    aDouble// "Double"
0x7332d  ldc.i4   0x1028
0x73332  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73337  ldtoken  [mscorlib]System.Decimal
0x7333c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73341  ldstr    aDecimal_0// "decimal"
0x73346  ldstr    aDecimal// "Decimal"
0x7334b  ldc.i4   0x1028
0x73350  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73355  ldtoken  [mscorlib]System.DateTime
0x7335a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7335f  ldstr    aDatetime_0// "dateTime"
0x73364  ldstr    aDatetime// "DateTime"
0x73369  ldc.i4   0x1068
0x7336e  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73373  ldtoken  System.Xml.XmlQualifiedName
0x73378  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7337d  ldstr    aQname// "QName"
0x73382  ldstr    aXmlqualifiedna// "XmlQualifiedName"
0x73387  ldc.i4   0x146A
0x7338c  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73391  ldtoken  [mscorlib]System.Byte
0x73396  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7339b  ldstr    aUnsignedbyte// "unsignedByte"
0x733a0  ldstr    aByte// "Byte"
0x733a5  ldc.i4   0x1028
0x733aa  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x733af  ldtoken  [mscorlib]System.SByte
0x733b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x733b9  ldstr    aByte_0// "byte"
0x733be  ldstr    aSbyte// "SByte"
0x733c3  ldc.i4   0x1028
0x733c8  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x733cd  ldtoken  [mscorlib]System.UInt16
0x733d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x733d7  ldstr    aUnsignedshort// "unsignedShort"
0x733dc  ldstr    aUint16// "UInt16"
0x733e1  ldc.i4   0x1028
0x733e6  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x733eb  ldtoken  [mscorlib]System.UInt32
0x733f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x733f5  ldstr    aUnsignedint// "unsignedInt"
0x733fa  ldstr    aUint32// "UInt32"
0x733ff  ldc.i4   0x1028
0x73404  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73409  ldtoken  [mscorlib]System.UInt64
0x7340e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73413  ldstr    aUnsignedlong// "unsignedLong"
0x73418  ldstr    aUint64// "UInt64"
0x7341d  ldc.i4   0x1028
0x73422  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73427  ldtoken  [mscorlib]System.DateTime
0x7342c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73431  ldstr    aDate// "date"
0x73436  ldstr    aDate_0// "Date"
0x7343b  ldc.i4   0x10E8
0x73440  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73445  ldtoken  [mscorlib]System.DateTime
0x7344a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7344f  ldstr    aTime// "time"
0x73454  ldstr    aTime_0// "Time"
0x73459  ldc.i4   0x10E8
0x7345e  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73463  ldtoken  [mscorlib]System.String
0x73468  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7346d  ldstr    aName_0// "Name"
0x73472  ldstr    aXmlname// "XmlName"
0x73477  ldc.i4   0xEA
0x7347c  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73481  ldtoken  [mscorlib]System.String
0x73486  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7348b  ldstr    aNcname// "NCName"
0x73490  ldstr    aXmlncname// "XmlNCName"
0x73495  ldc.i4   0xEA
0x7349a  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7349f  ldtoken  [mscorlib]System.String
0x734a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x734a9  ldstr    aNmtoken_0// "NMTOKEN"
0x734ae  ldstr    aXmlnmtoken// "XmlNmToken"
0x734b3  ldc.i4   0xEA
0x734b8  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x734bd  ldtoken  [mscorlib]System.String
0x734c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x734c7  ldstr    aNmtokens// "NMTOKENS"
0x734cc  ldstr    aXmlnmtokens// "XmlNmTokens"
0x734d1  ldc.i4   0xEA
0x734d6  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x734db  ldtoken  unsigned int8[]
0x734e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x734e5  ldstr    aBase64binary// "base64Binary"
0x734ea  ldstr    aBytearraybase6// "ByteArrayBase64"
0x734ef  ldc.i4   0x1AEA
0x734f4  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x734f9  ldtoken  unsigned int8[]
0x734fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73503  ldstr    aHexbinary// "hexBinary"
0x73508  ldstr    aBytearrayhex// "ByteArrayHex"
0x7350d  ldc.i4   0x1AEA
0x73512  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73517  newobj   instance void System.Xml.Schema.XmlSchemaPatternFacet::.ctor()
0x7351c  stloc.0
0x7351d  ldloc.0
0x7351e  ldstr    a09aFaF809aFaF4// "[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-"...
0x73523  callvirt instance void System.Xml.Schema.XmlSchemaFacet::set_Value(string value)
0x73528  ldtoken  [mscorlib]System.Guid
0x7352d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73532  ldstr    aGuid_0// "guid"
0x73537  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7353c  ldstr    aGuid// "Guid"
0x73541  ldstr    aString// "string"
0x73546  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7354b  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73550  ldc.i4.1
0x73551  newarr   System.Xml.Schema.XmlSchemaFacet
0x73556  dup
0x73557  ldc.i4.0
0x73558  ldloc.0
0x73559  stelem.ref
0x7355a  ldc.i4   0x1228
0x7355f  call     void System.Xml.Serialization.TypeScope::AddNonXsdPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, class System.Xml.Schema.XmlSchemaFacet[] facets, valuetype System.Xml.Serialization.TypeFlags flags)
0x73564  ldtoken  [mscorlib]System.Char
0x73569  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7356e  ldstr    aChar_0// "char"
0x73573  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x73578  ldstr    aChar// "Char"
0x7357d  ldstr    aUnsignedshort// "unsignedShort"
0x73582  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73587  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7358c  ldc.i4.0
0x7358d  newarr   System.Xml.Schema.XmlSchemaFacet
0x73592  ldc.i4   0x268
0x73597  call     void System.Xml.Serialization.TypeScope::AddNonXsdPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, class System.Xml.Schema.XmlSchemaFacet[] facets, valuetype System.Xml.Serialization.TypeFlags flags)
0x7359c  call     bool System.LocalAppContextSwitches::get_EnableTimeSpanSerialization()
0x735a1  brfalse.s loc_735DB
0x735a3  ldtoken  [mscorlib]System.TimeSpan
0x735a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x735ad  ldstr    aTimespan// "TimeSpan"
0x735b2  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x735b7  ldstr    aTimespan// "TimeSpan"
0x735bc  ldstr    aDuration// "duration"
0x735c1  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x735c6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x735cb  ldc.i4.0
0x735cc  newarr   System.Xml.Schema.XmlSchemaFacet
0x735d1  ldc.i4   0x1028
0x735d6  call     void System.Xml.Serialization.TypeScope::AddNonXsdPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, class System.Xml.Schema.XmlSchemaFacet[] facets, valuetype System.Xml.Serialization.TypeFlags flags)
0x735db  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x735e0  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedTypes(string ns)
0x735e5  ldtoken  [mscorlib]System.String
0x735ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x735ef  ldstr    aNormalizedstri// "normalizedString"
0x735f4  ldstr    aString_0// "String"
0x735f9  ldc.i4   0x8BA
0x735fe  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73603  ldc.i4.0
0x73604  stloc.1
0x73605  br.s     loc_7362B
0x73607  ldtoken  [mscorlib]System.String
0x7360c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73611  ldsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x73616  ldloc.1
0x73617  ldelem.ref
0x73618  ldstr    aString_0// "String"
0x7361d  ldc.i4   0x80BA
0x73622  call     void System.Xml.Serialization.TypeScope::AddPrimitive(class [mscorlib]System.Type type, string dataTypeName, string formatterName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73627  ldloc.1
0x73628  ldc.i4.1
0x73629  add
0x7362a  stloc.1
0x7362b  ldloc.1
0x7362c  ldsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x73631  ldlen
  ... truncated ...
```
