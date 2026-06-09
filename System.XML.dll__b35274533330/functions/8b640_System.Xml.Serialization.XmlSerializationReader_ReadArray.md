# System.Xml.Serialization.XmlSerializationReader::ReadArray

- ea: `0x8b640`
- end: `0x8bb22`
- name: `System.Xml.Serialization.XmlSerializationReader::ReadArray`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x8bbf0`

## callees

- `0x132e0`
- `0x13310`
- `0x13320`
- `0x13410`
- `0x13450`
- `0x214b0`
- `0x21500`
- `0x21510`
- `0x21570`
- `0x21b70`
- `0x21ca0`
- `0x21e40`
- `0x21e90`
- `0x622f0`
- `0x74600`
- `0x885a0`
- `0x88c00`
- `0x8a740`
- `0x8a940`
- `0x8aaf0`
- `0x8ae20`
- `0x8b110`
- `0x8b140`
- `0x8b390`
- `0x8b640`
- `0x8bbc0`
- `0x8bbe0`
- `0x8bde0`
- `0x8c140`
- `0x8c1a0`
- `0x9b6d0`
- `0x1228a0`

## string_xrefs

- `0x8b9c6`: `http://www.w3.org/2001/XMLSchema`
- `0x8b8c0`: `XmlRpcArrayOfValueTypes`
- `0x8b706`: `XmlInvalidArrayDimentions`

## pseudocode

```c

```

## disassembly

```asm
0x8b640  ldnull
0x8b641  stloc.1
0x8b642  ldarg.0
0x8b643  ldfld    bool System.Xml.Serialization.XmlSerializationReader::soap12
0x8b648  brfalse  loc_8B6D5
0x8b64d  ldarg.0
0x8b64e  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b653  ldarg.0
0x8b654  ldfld    string System.Xml.Serialization.XmlSerializationReader::itemTypeID
0x8b659  ldarg.0
0x8b65a  ldfld    string System.Xml.Serialization.XmlSerializationReader::soap12NsID
0x8b65f  callvirt instance string System.Xml.XmlReader::GetAttribute(string name, string namespaceURI)
0x8b664  stloc.s  8
0x8b666  ldarg.0
0x8b667  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b66c  ldarg.0
0x8b66d  ldfld    string System.Xml.Serialization.XmlSerializationReader::arraySizeID
0x8b672  ldarg.0
0x8b673  ldfld    string System.Xml.Serialization.XmlSerializationReader::soap12NsID
0x8b678  callvirt instance string System.Xml.XmlReader::GetAttribute(string name, string namespaceURI)
0x8b67d  stloc.s  9
0x8b67f  ldarg.0
0x8b680  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationReader::types
0x8b685  ldarg.1
0x8b686  ldarg.2
0x8b687  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x8b68c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8b691  castclass [mscorlib]System.Type
0x8b696  stloc.s  0xA
0x8b698  ldloc.s  8
0x8b69a  brtrue.s loc_8B6B5
0x8b69c  ldloc.s  9
0x8b69e  brtrue.s loc_8B6B5
0x8b6a0  ldloc.s  0xA
0x8b6a2  ldnull
0x8b6a3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b6a8  brtrue.s loc_8B6B3
0x8b6aa  ldloc.s  0xA
0x8b6ac  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x8b6b1  brtrue.s loc_8B6B5
0x8b6b3  ldnull
0x8b6b4  ret
0x8b6b5  ldarg.0
0x8b6b6  ldloc.s  8
0x8b6b8  ldloc.s  9
0x8b6ba  call     instance valuetype SoapArrayInfo System.Xml.Serialization.XmlSerializationReader::ParseSoap12ArrayType(string itemType, string arraySize)
0x8b6bf  stloc.0
0x8b6c0  ldloc.s  0xA
0x8b6c2  ldnull
0x8b6c3  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b6c8  brfalse.s loc_8B6FD
0x8b6ca  ldloc.s  0xA
0x8b6cc  ldnull
0x8b6cd  call     class [mscorlib]System.Type System.Xml.Serialization.TypeScope::GetArrayElementType(class [mscorlib]System.Type type, string memberInfo)
0x8b6d2  stloc.1
0x8b6d3  br.s     loc_8B6FD
0x8b6d5  ldarg.0
0x8b6d6  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b6db  ldarg.0
0x8b6dc  ldfld    string System.Xml.Serialization.XmlSerializationReader::arrayTypeID
0x8b6e1  ldarg.0
0x8b6e2  ldfld    string System.Xml.Serialization.XmlSerializationReader::soapNsID
0x8b6e7  callvirt instance string System.Xml.XmlReader::GetAttribute(string name, string namespaceURI)
0x8b6ec  stloc.s  0xB
0x8b6ee  ldloc.s  0xB
0x8b6f0  brtrue.s loc_8B6F4
0x8b6f2  ldnull
0x8b6f3  ret
0x8b6f4  ldarg.0
0x8b6f5  ldloc.s  0xB
0x8b6f7  call     instance valuetype SoapArrayInfo System.Xml.Serialization.XmlSerializationReader::ParseArrayType(string value)
0x8b6fc  stloc.0
0x8b6fd  ldloc.0
0x8b6fe  ldfld    int32 SoapArrayInfo::dimensions
0x8b703  ldc.i4.1
0x8b704  beq.s    loc_8B725
0x8b706  ldstr    aXmlinvalidarra_0// "XmlInvalidArrayDimentions"
0x8b70b  ldc.i4.1
0x8b70c  newarr   [mscorlib]System.Object
0x8b711  dup
0x8b712  ldc.i4.0
0x8b713  ldarg.0
0x8b714  call     instance string System.Xml.Serialization.XmlSerializationReader::CurrentTag()
0x8b719  stelem.ref
0x8b71a  call     string System.Xml.Res::GetString(string name, object[] args)
0x8b71f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8b724  throw
0x8b725  ldnull
0x8b726  stloc.s  4
0x8b728  ldarg.0
0x8b729  ldfld    string System.Xml.Serialization.XmlSerializationReader::urTypeID
0x8b72e  ldarg.0
0x8b72f  ldfld    string System.Xml.Serialization.XmlSerializationReader::schemaNsID
0x8b734  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x8b739  stloc.s  5
0x8b73b  ldloc.0
0x8b73c  ldfld    string SoapArrayInfo::qname
0x8b741  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8b746  ldc.i4.0
0x8b747  ble.s    loc_8B76C
0x8b749  ldarg.0
0x8b74a  ldloc.0
0x8b74b  ldfld    string SoapArrayInfo::qname
0x8b750  ldc.i4.0
0x8b751  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSerializationReader::ToXmlQualifiedName(string value, bool decodeName)
0x8b756  stloc.2
0x8b757  ldarg.0
0x8b758  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationReader::types
0x8b75d  ldloc.2
0x8b75e  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8b763  castclass [mscorlib]System.Type
0x8b768  stloc.s  4
0x8b76a  br.s     loc_8B76F
0x8b76c  ldloc.s  5
0x8b76e  stloc.2
0x8b76f  ldarg.0
0x8b770  ldfld    bool System.Xml.Serialization.XmlSerializationReader::soap12
0x8b775  brfalse.s loc_8B78D
0x8b777  ldloc.s  4
0x8b779  ldtoken  [mscorlib]System.Object
0x8b77e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8b783  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b788  brfalse.s loc_8B78D
0x8b78a  ldnull
0x8b78b  stloc.s  4
0x8b78d  ldloc.s  4
0x8b78f  ldnull
0x8b790  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b795  brfalse  loc_8B833
0x8b79a  ldarg.0
0x8b79b  ldfld    bool System.Xml.Serialization.XmlSerializationReader::soap12
0x8b7a0  brtrue.s loc_8B7B3
0x8b7a2  ldarg.0
0x8b7a3  ldloc.2
0x8b7a4  ldc.i4.1
0x8b7a5  call     instance class [mscorlib]System.Type System.Xml.Serialization.XmlSerializationReader::GetPrimitiveType(class System.Xml.XmlQualifiedName typeName, bool throwOnUnknown)
0x8b7aa  stloc.s  4
0x8b7ac  ldc.i4.1
0x8b7ad  stloc.3
0x8b7ae  br       loc_8B83B
0x8b7b3  ldloc.2
0x8b7b4  ldloc.s  5
0x8b7b6  call     bool System.Xml.XmlQualifiedName::op_Inequality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x8b7bb  brfalse.s loc_8B7C7
0x8b7bd  ldarg.0
0x8b7be  ldloc.2
0x8b7bf  ldc.i4.0
0x8b7c0  call     instance class [mscorlib]System.Type System.Xml.Serialization.XmlSerializationReader::GetPrimitiveType(class System.Xml.XmlQualifiedName typeName, bool throwOnUnknown)
0x8b7c5  stloc.s  4
0x8b7c7  ldloc.s  4
0x8b7c9  ldnull
0x8b7ca  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b7cf  brfalse.s loc_8B7D5
0x8b7d1  ldc.i4.1
0x8b7d2  stloc.3
0x8b7d3  br.s     loc_8B83B
0x8b7d5  ldloc.1
0x8b7d6  ldnull
0x8b7d7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8b7dc  brfalse.s loc_8B7EE
0x8b7de  ldtoken  [mscorlib]System.Object
0x8b7e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8b7e8  stloc.s  4
0x8b7ea  ldc.i4.0
0x8b7eb  stloc.3
0x8b7ec  br.s     loc_8B83B
0x8b7ee  ldloc.1
0x8b7ef  stloc.s  4
0x8b7f1  ldarg.0
0x8b7f2  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationReader::typesReverse
0x8b7f7  ldloc.s  4
0x8b7f9  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8b7fe  castclass System.Xml.XmlQualifiedName
0x8b803  stloc.s  0xC
0x8b805  ldloc.s  0xC
0x8b807  ldnull
0x8b808  call     bool System.Xml.XmlQualifiedName::op_Equality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x8b80d  brfalse.s loc_8B81C
0x8b80f  ldloc.s  4
0x8b811  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSerializationWriter::GetPrimitiveTypeNameInternal(class [mscorlib]System.Type type)
0x8b816  stloc.s  0xC
0x8b818  ldc.i4.1
0x8b819  stloc.3
0x8b81a  br.s     loc_8B824
0x8b81c  ldloc.s  4
0x8b81e  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x8b823  stloc.3
0x8b824  ldloc.s  0xC
0x8b826  ldnull
0x8b827  call     bool System.Xml.XmlQualifiedName::op_Inequality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x8b82c  brfalse.s loc_8B83B
0x8b82e  ldloc.s  0xC
0x8b830  stloc.2
0x8b831  br.s     loc_8B83B
0x8b833  ldloc.s  4
0x8b835  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x8b83a  stloc.3
0x8b83b  ldarg.0
0x8b83c  ldfld    bool System.Xml.Serialization.XmlSerializationReader::soap12
0x8b841  brtrue.s loc_8B86A
0x8b843  ldloc.0
0x8b844  ldfld    int32 SoapArrayInfo::jaggedDimensions
0x8b849  ldc.i4.0
0x8b84a  ble.s    loc_8B86A
0x8b84c  ldc.i4.0
0x8b84d  stloc.s  0xD
0x8b84f  br.s     loc_8B860
0x8b851  ldloc.s  4
0x8b853  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeArrayType()
0x8b858  stloc.s  4
0x8b85a  ldloc.s  0xD
0x8b85c  ldc.i4.1
0x8b85d  add
0x8b85e  stloc.s  0xD
0x8b860  ldloc.s  0xD
0x8b862  ldloc.0
0x8b863  ldfld    int32 SoapArrayInfo::jaggedDimensions
0x8b868  blt.s    loc_8B851
0x8b86a  ldarg.0
0x8b86b  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b870  callvirt instance bool System.Xml.XmlReader::get_IsEmptyElement()
0x8b875  brfalse.s loc_8B88B
0x8b877  ldarg.0
0x8b878  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b87d  callvirt instance void System.Xml.XmlReader::Skip()
0x8b882  ldloc.s  4
0x8b884  ldc.i4.0
0x8b885  call     class [mscorlib]System.Array [mscorlib]System.Array::CreateInstance(class [mscorlib]System.Type, int32)
0x8b88a  ret
0x8b88b  ldarg.0
0x8b88c  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b891  callvirt instance void System.Xml.XmlReader::ReadStartElement()
0x8b896  ldarg.0
0x8b897  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b89c  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::MoveToContent()
0x8b8a1  pop
0x8b8a2  ldc.i4.0
0x8b8a3  stloc.s  6
0x8b8a5  ldnull
0x8b8a6  stloc.s  7
0x8b8a8  ldloc.s  4
0x8b8aa  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x8b8af  brfalse  loc_8B955
0x8b8b4  ldloc.3
0x8b8b5  brtrue.s loc_8B8E0
0x8b8b7  ldloc.s  4
0x8b8b9  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x8b8be  brtrue.s loc_8B8E0
0x8b8c0  ldstr    aXmlrpcarrayofv// "XmlRpcArrayOfValueTypes"
0x8b8c5  ldc.i4.1
0x8b8c6  newarr   [mscorlib]System.Object
0x8b8cb  dup
0x8b8cc  ldc.i4.0
0x8b8cd  ldloc.s  4
0x8b8cf  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8b8d4  stelem.ref
0x8b8d5  call     string System.Xml.Res::GetString(string name, object[] args)
0x8b8da  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x8b8df  throw
0x8b8e0  ldc.i4.0
0x8b8e1  stloc.s  0xE
0x8b8e3  ldarg.0
0x8b8e4  call     instance int32 System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x8b8e9  stloc.s  0xF
0x8b8eb  br.s     loc_8B932
0x8b8ed  ldarg.0
0x8b8ee  ldloc.s  7
0x8b8f0  ldloc.s  6
0x8b8f2  ldloc.s  4
0x8b8f4  call     instance class [mscorlib]System.Array System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array a, int32 index, class [mscorlib]System.Type elementType)
0x8b8f9  stloc.s  7
0x8b8fb  ldloc.s  7
0x8b8fd  ldarg.0
0x8b8fe  ldloc.2
0x8b8ff  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x8b904  ldloc.2
0x8b905  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x8b90a  call     instance object System.Xml.Serialization.XmlSerializationReader::ReadReferencedElement(string name, string ns)
0x8b90f  ldloc.s  6
0x8b911  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x8b916  ldloc.s  6
0x8b918  ldc.i4.1
0x8b919  add
0x8b91a  stloc.s  6
0x8b91c  ldarg.0
0x8b91d  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b922  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::MoveToContent()
0x8b927  pop
0x8b928  ldarg.0
0x8b929  ldloca.s 0xE
0x8b92b  ldloca.s 0xF
0x8b92d  call     instance void System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32& whileIterations, int32& readerCount)
0x8b932  ldarg.0
0x8b933  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8b938  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x8b93d  ldc.i4.s 0xF
0x8b93f  bne.un.s loc_8B8ED
0x8b941  ldarg.0
0x8b942  ldloc.s  7
0x8b944  ldloc.s  6
  ... truncated ...
```
