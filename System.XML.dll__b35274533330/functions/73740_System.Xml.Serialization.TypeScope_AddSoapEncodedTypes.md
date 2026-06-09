# System.Xml.Serialization.TypeScope::AddSoapEncodedTypes

- ea: `0x73740`
- end: `0x73c2b`
- name: `System.Xml.Serialization.TypeScope::AddSoapEncodedTypes`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x73190`

## callees

- `0x132e0`
- `0x73740`
- `0x73d10`

## string_xrefs

- `0x7375a`: `http://www.w3.org/2001/XMLSchema`
- `0x73790`: `http://www.w3.org/2001/XMLSchema`
- `0x737cc`: `http://www.w3.org/2001/XMLSchema`
- `0x737f7`: `http://www.w3.org/2001/XMLSchema`
- `0x73825`: `http://www.w3.org/2001/XMLSchema`
- `0x73853`: `http://www.w3.org/2001/XMLSchema`
- `0x73881`: `http://www.w3.org/2001/XMLSchema`
- `0x738af`: `http://www.w3.org/2001/XMLSchema`
- `0x738dd`: `http://www.w3.org/2001/XMLSchema`
- `0x7390b`: `http://www.w3.org/2001/XMLSchema`
- `0x73939`: `http://www.w3.org/2001/XMLSchema`
- `0x73967`: `http://www.w3.org/2001/XMLSchema`
- `0x73995`: `http://www.w3.org/2001/XMLSchema`
- `0x739c3`: `http://www.w3.org/2001/XMLSchema`
- `0x739f1`: `http://www.w3.org/2001/XMLSchema`
- `0x73a1f`: `http://www.w3.org/2001/XMLSchema`
- `0x73a4d`: `http://www.w3.org/2001/XMLSchema`
- `0x73a7b`: `http://www.w3.org/2001/XMLSchema`
- `0x73aa9`: `http://www.w3.org/2001/XMLSchema`
- `0x73ad7`: `http://www.w3.org/2001/XMLSchema`
- `0x73b05`: `http://www.w3.org/2001/XMLSchema`
- `0x73b33`: `http://www.w3.org/2001/XMLSchema`
- `0x73b61`: `http://www.w3.org/2001/XMLSchema`
- `0x73b8f`: `http://www.w3.org/2001/XMLSchema`
- `0x73bbd`: `http://www.w3.org/2001/XMLSchema`
- `0x73beb`: `http://www.w3.org/2001/XMLSchema`
- `0x73c16`: `http://www.w3.org/2001/XMLSchema`
- `0x7395d`: `XmlQualifiedName`
- `0x73acd`: `XmlName`
- `0x73afb`: `XmlNCName`
- `0x73b23`: `NMTOKEN`
- `0x73b29`: `XmlNmToken`
- `0x73b51`: `NMTOKENS`
- `0x73b57`: `XmlNmTokens`

## pseudocode

```c

```

## disassembly

```asm
0x73740  ldtoken  [mscorlib]System.String
0x73745  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7374a  ldstr    aNormalizedstri// "normalizedString"
0x7374f  ldarg.0
0x73750  ldstr    aString_0// "String"
0x73755  ldstr    aNormalizedstri// "normalizedString"
0x7375a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7375f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73764  ldc.i4   0x8AA
0x73769  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7376e  ldc.i4.0
0x7376f  stloc.0
0x73770  br.s     loc_737A8
0x73772  ldtoken  [mscorlib]System.String
0x73777  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7377c  ldsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x73781  ldloc.0
0x73782  ldelem.ref
0x73783  ldarg.0
0x73784  ldstr    aString_0// "String"
0x73789  ldsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x7378e  ldloc.0
0x7378f  ldelem.ref
0x73790  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73795  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7379a  ldc.i4   0x80AA
0x7379f  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x737a4  ldloc.0
0x737a5  ldc.i4.1
0x737a6  add
0x737a7  stloc.0
0x737a8  ldloc.0
0x737a9  ldsfld   string[] System.Xml.Serialization.TypeScope::unsupportedTypes
0x737ae  ldlen
0x737af  conv.i4
0x737b0  blt.s    loc_73772
0x737b2  ldtoken  [mscorlib]System.String
0x737b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x737bc  ldstr    aString// "string"
0x737c1  ldarg.0
0x737c2  ldstr    aString_0// "String"
0x737c7  ldstr    aString// "string"
0x737cc  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x737d1  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x737d6  ldc.i4.s 0x3A
0x737d8  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x737dd  ldtoken  [mscorlib]System.Int32
0x737e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x737e7  ldstr    aInt_0// "int"
0x737ec  ldarg.0
0x737ed  ldstr    aInt32// "Int32"
0x737f2  ldstr    aString// "string"
0x737f7  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x737fc  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73801  ldc.i4   0x1028
0x73806  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7380b  ldtoken  [mscorlib]System.Boolean
0x73810  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73815  ldstr    aBoolean// "boolean"
0x7381a  ldarg.0
0x7381b  ldstr    aBoolean_0// "Boolean"
0x73820  ldstr    aString// "string"
0x73825  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7382a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7382f  ldc.i4   0x1028
0x73834  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73839  ldtoken  [mscorlib]System.Int16
0x7383e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73843  ldstr    aShort// "short"
0x73848  ldarg.0
0x73849  ldstr    aInt16// "Int16"
0x7384e  ldstr    aString// "string"
0x73853  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73858  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7385d  ldc.i4   0x1028
0x73862  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73867  ldtoken  [mscorlib]System.Int64
0x7386c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73871  ldstr    aLong_0// "long"
0x73876  ldarg.0
0x73877  ldstr    aInt64// "Int64"
0x7387c  ldstr    aString// "string"
0x73881  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73886  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7388b  ldc.i4   0x1028
0x73890  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73895  ldtoken  [mscorlib]System.Single
0x7389a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7389f  ldstr    aFloat_0// "float"
0x738a4  ldarg.0
0x738a5  ldstr    aSingle// "Single"
0x738aa  ldstr    aString// "string"
0x738af  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x738b4  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x738b9  ldc.i4   0x1028
0x738be  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x738c3  ldtoken  [mscorlib]System.Double
0x738c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x738cd  ldstr    aDouble_0// "double"
0x738d2  ldarg.0
0x738d3  ldstr    aDouble// "Double"
0x738d8  ldstr    aString// "string"
0x738dd  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x738e2  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x738e7  ldc.i4   0x1028
0x738ec  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x738f1  ldtoken  [mscorlib]System.Decimal
0x738f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x738fb  ldstr    aDecimal_0// "decimal"
0x73900  ldarg.0
0x73901  ldstr    aDecimal// "Decimal"
0x73906  ldstr    aString// "string"
0x7390b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73910  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73915  ldc.i4   0x1028
0x7391a  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7391f  ldtoken  [mscorlib]System.DateTime
0x73924  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73929  ldstr    aDatetime_0// "dateTime"
0x7392e  ldarg.0
0x7392f  ldstr    aDatetime// "DateTime"
0x73934  ldstr    aString// "string"
0x73939  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7393e  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73943  ldc.i4   0x1068
0x73948  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7394d  ldtoken  System.Xml.XmlQualifiedName
0x73952  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73957  ldstr    aQname// "QName"
0x7395c  ldarg.0
0x7395d  ldstr    aXmlqualifiedna// "XmlQualifiedName"
0x73962  ldstr    aString// "string"
0x73967  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7396c  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73971  ldc.i4   0x146A
0x73976  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x7397b  ldtoken  [mscorlib]System.Byte
0x73980  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73985  ldstr    aUnsignedbyte// "unsignedByte"
0x7398a  ldarg.0
0x7398b  ldstr    aByte// "Byte"
0x73990  ldstr    aString// "string"
0x73995  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7399a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7399f  ldc.i4   0x1028
0x739a4  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x739a9  ldtoken  [mscorlib]System.SByte
0x739ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x739b3  ldstr    aByte_0// "byte"
0x739b8  ldarg.0
0x739b9  ldstr    aSbyte// "SByte"
0x739be  ldstr    aString// "string"
0x739c3  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x739c8  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x739cd  ldc.i4   0x1028
0x739d2  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x739d7  ldtoken  [mscorlib]System.UInt16
0x739dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x739e1  ldstr    aUnsignedshort// "unsignedShort"
0x739e6  ldarg.0
0x739e7  ldstr    aUint16// "UInt16"
0x739ec  ldstr    aString// "string"
0x739f1  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x739f6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x739fb  ldc.i4   0x1028
0x73a00  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73a05  ldtoken  [mscorlib]System.UInt32
0x73a0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73a0f  ldstr    aUnsignedint// "unsignedInt"
0x73a14  ldarg.0
0x73a15  ldstr    aUint32// "UInt32"
0x73a1a  ldstr    aString// "string"
0x73a1f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73a24  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73a29  ldc.i4   0x1028
0x73a2e  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73a33  ldtoken  [mscorlib]System.UInt64
0x73a38  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73a3d  ldstr    aUnsignedlong// "unsignedLong"
0x73a42  ldarg.0
0x73a43  ldstr    aUint64// "UInt64"
0x73a48  ldstr    aString// "string"
0x73a4d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73a52  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73a57  ldc.i4   0x1028
0x73a5c  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73a61  ldtoken  [mscorlib]System.DateTime
0x73a66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73a6b  ldstr    aDate// "date"
0x73a70  ldarg.0
0x73a71  ldstr    aDate_0// "Date"
0x73a76  ldstr    aString// "string"
0x73a7b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73a80  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73a85  ldc.i4   0x10E8
0x73a8a  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73a8f  ldtoken  [mscorlib]System.DateTime
0x73a94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73a99  ldstr    aTime// "time"
0x73a9e  ldarg.0
0x73a9f  ldstr    aTime_0// "Time"
0x73aa4  ldstr    aString// "string"
0x73aa9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73aae  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73ab3  ldc.i4   0x10E8
0x73ab8  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73abd  ldtoken  [mscorlib]System.String
0x73ac2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73ac7  ldstr    aName_0// "Name"
0x73acc  ldarg.0
0x73acd  ldstr    aXmlname// "XmlName"
0x73ad2  ldstr    aString// "string"
0x73ad7  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73adc  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73ae1  ldc.i4   0xEA
0x73ae6  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73aeb  ldtoken  [mscorlib]System.String
0x73af0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73af5  ldstr    aNcname// "NCName"
0x73afa  ldarg.0
0x73afb  ldstr    aXmlncname// "XmlNCName"
0x73b00  ldstr    aString// "string"
0x73b05  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73b0a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73b0f  ldc.i4   0xEA
0x73b14  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73b19  ldtoken  [mscorlib]System.String
0x73b1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73b23  ldstr    aNmtoken_0// "NMTOKEN"
0x73b28  ldarg.0
0x73b29  ldstr    aXmlnmtoken// "XmlNmToken"
0x73b2e  ldstr    aString// "string"
0x73b33  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73b38  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73b3d  ldc.i4   0xEA
0x73b42  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73b47  ldtoken  [mscorlib]System.String
0x73b4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73b51  ldstr    aNmtokens// "NMTOKENS"
0x73b56  ldarg.0
0x73b57  ldstr    aXmlnmtokens// "XmlNmTokens"
0x73b5c  ldstr    aString// "string"
0x73b61  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73b66  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73b6b  ldc.i4   0xEA
0x73b70  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73b75  ldtoken  unsigned int8[]
0x73b7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73b7f  ldstr    aBase64binary// "base64Binary"
0x73b84  ldarg.0
0x73b85  ldstr    aBytearraybase6// "ByteArrayBase64"
0x73b8a  ldstr    aString// "string"
0x73b8f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73b94  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73b99  ldc.i4   0x12EA
0x73b9e  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73ba3  ldtoken  unsigned int8[]
0x73ba8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73bad  ldstr    aHexbinary// "hexBinary"
0x73bb2  ldarg.0
0x73bb3  ldstr    aBytearrayhex// "ByteArrayHex"
0x73bb8  ldstr    aString// "string"
0x73bbd  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73bc2  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73bc7  ldc.i4   0x12EA
0x73bcc  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73bd1  ldtoken  [mscorlib]System.String
0x73bd6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73bdb  ldstr    aArraycoordinat// "arrayCoordinate"
0x73be0  ldarg.0
0x73be1  ldstr    aString_0// "String"
0x73be6  ldstr    aString// "string"
0x73beb  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73bf0  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73bf5  ldc.i4.s 0x28
0x73bf7  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73bfc  ldtoken  unsigned int8[]
0x73c01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73c06  ldstr    aBase64_0// "base64"
0x73c0b  ldarg.0
0x73c0c  ldstr    aBytearraybase6// "ByteArrayBase64"
0x73c11  ldstr    aBase64binary// "base64Binary"
0x73c16  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x73c1b  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x73c20  ldc.i4   0x22A
0x73c25  call     void System.Xml.Serialization.TypeScope::AddSoapEncodedPrimitive(class [mscorlib]System.Type type, string dataTypeName, string ns, string formatterName, class System.Xml.XmlQualifiedName baseTypeName, valuetype System.Xml.Serialization.TypeFlags flags)
0x73c2a  ret
```
