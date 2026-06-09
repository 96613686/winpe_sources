# Microsoft.SharePoint.Client.Utility::GetTypeFromTypeOrTypeIdAttribute

- ea: `0x181f0`
- end: `0x184de`
- name: `Microsoft.SharePoint.Client.Utility::GetTypeFromTypeOrTypeIdAttribute`
- size: `750`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ba0`
- `0x1c30`
- `0xca40`
- `0xd450`

## callees

- `0xe010`
- `0x12df0`
- `0x16cc0`
- `0x17f80`
- `0x181f0`

## string_xrefs

- `0x18201`: `serviceHost`

## pseudocode

```c

```

## disassembly

```asm
0x181f0  ldarg.0
0x181f1  brtrue.s loc_181FE
0x181f3  ldstr    aXe// "xe"
0x181f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x181fd  throw
0x181fe  ldarg.1
0x181ff  brtrue.s loc_1820C
0x18201  ldstr    aServicehost// "serviceHost"
0x18206  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1820b  throw
0x1820c  ldarg.0
0x1820d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18212  ldstr    aType_0// "Type"
0x18217  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1821c  stloc.0
0x1821d  ldnull
0x1821e  stloc.1
0x1821f  ldloc.0
0x18220  brfalse  loc_1848F
0x18225  ldloc.0
0x18226  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1822b  dup
0x1822c  stloc.3
0x1822d  brfalse  loc_18464
0x18232  volatile.
0x18234  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000659-1
0x18239  brtrue   loc_18313
0x1823e  ldc.i4.s 0x10
0x18240  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x18245  dup
0x18246  ldstr    aBoolean// "Boolean"
0x1824b  ldc.i4.0
0x1824c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18251  dup
0x18252  ldstr    aByte_0// "Byte"
0x18257  ldc.i4.1
0x18258  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1825d  dup
0x1825e  ldstr    aSbyte// "SByte"
0x18263  ldc.i4.2
0x18264  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18269  dup
0x1826a  ldstr    aChar_0// "Char"
0x1826f  ldc.i4.3
0x18270  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18275  dup
0x18276  ldstr    aInt16_0// "Int16"
0x1827b  ldc.i4.4
0x1827c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18281  dup
0x18282  ldstr    aUint16_0// "UInt16"
0x18287  ldc.i4.5
0x18288  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1828d  dup
0x1828e  ldstr    aInt32_0// "Int32"
0x18293  ldc.i4.6
0x18294  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18299  dup
0x1829a  ldstr    aUint32_0// "UInt32"
0x1829f  ldc.i4.7
0x182a0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182a5  dup
0x182a6  ldstr    aInt64_0// "Int64"
0x182ab  ldc.i4.8
0x182ac  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182b1  dup
0x182b2  ldstr    aUint64_0// "UInt64"
0x182b7  ldc.i4.s 9
0x182b9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182be  dup
0x182bf  ldstr    aDatetime// "DateTime"
0x182c4  ldc.i4.s 0xA
0x182c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182cb  dup
0x182cc  ldstr    aSingle_0// "Single"
0x182d1  ldc.i4.s 0xB
0x182d3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182d8  dup
0x182d9  ldstr    aDouble_0// "Double"
0x182de  ldc.i4.s 0xC
0x182e0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182e5  dup
0x182e6  ldstr    aString// "String"
0x182eb  ldc.i4.s 0xD
0x182ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182f2  dup
0x182f3  ldstr    aDecimal_0// "Decimal"
0x182f8  ldc.i4.s 0xE
0x182fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x182ff  dup
0x18300  ldstr    aTimespan// "TimeSpan"
0x18305  ldc.i4.s 0xF
0x18307  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1830c  volatile.
0x1830e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000659-1
0x18313  volatile.
0x18315  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000659-1
0x1831a  ldloc.3
0x1831b  ldloca.s 4
0x1831d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x18322  brfalse  loc_18464
0x18327  ldloc.s  4
0x18329  switch   loc_18373, loc_18383, loc_18393, loc_183A3, loc_183B3, loc_183C3, loc_183D3, loc_183E3, loc_183F3, loc_18403, loc_18413, loc_18423, loc_18430, loc_1843D, loc_1844A, loc_18457
0x1836e  br       loc_18464
0x18373  ldtoken  [mscorlib]System.Boolean
0x18378  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1837d  stloc.1
0x1837e  br       loc_184A8
0x18383  ldtoken  [mscorlib]System.Byte
0x18388  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1838d  stloc.1
0x1838e  br       loc_184A8
0x18393  ldtoken  [mscorlib]System.SByte
0x18398  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1839d  stloc.1
0x1839e  br       loc_184A8
0x183a3  ldtoken  [mscorlib]System.Char
0x183a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183ad  stloc.1
0x183ae  br       loc_184A8
0x183b3  ldtoken  [mscorlib]System.Int16
0x183b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183bd  stloc.1
0x183be  br       loc_184A8
0x183c3  ldtoken  [mscorlib]System.UInt16
0x183c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183cd  stloc.1
0x183ce  br       loc_184A8
0x183d3  ldtoken  [mscorlib]System.Int32
0x183d8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183dd  stloc.1
0x183de  br       loc_184A8
0x183e3  ldtoken  [mscorlib]System.UInt32
0x183e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183ed  stloc.1
0x183ee  br       loc_184A8
0x183f3  ldtoken  [mscorlib]System.Int64
0x183f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183fd  stloc.1
0x183fe  br       loc_184A8
0x18403  ldtoken  [mscorlib]System.UInt64
0x18408  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1840d  stloc.1
0x1840e  br       loc_184A8
0x18413  ldtoken  [mscorlib]System.DateTime
0x18418  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1841d  stloc.1
0x1841e  br       loc_184A8
0x18423  ldtoken  [mscorlib]System.Single
0x18428  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1842d  stloc.1
0x1842e  br.s     loc_184A8
0x18430  ldtoken  [mscorlib]System.Double
0x18435  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1843a  stloc.1
0x1843b  br.s     loc_184A8
0x1843d  ldtoken  [mscorlib]System.String
0x18442  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18447  stloc.1
0x18448  br.s     loc_184A8
0x1844a  ldtoken  [mscorlib]System.Decimal
0x1844f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18454  stloc.1
0x18455  br.s     loc_184A8
0x18457  ldtoken  [mscorlib]System.TimeSpan
0x1845c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18461  stloc.1
0x18462  br.s     loc_184A8
0x18464  ldarg.1
0x18465  ldc.i4   0x1C50C3
0x1846a  ldc.i4.1
0x1846b  ldstr    aUnknownType0// "Unknown type {0}"
0x18470  ldc.i4.1
0x18471  newarr   [mscorlib]System.Object
0x18476  stloc.s  5
0x18478  ldloc.s  5
0x1847a  ldc.i4.0
0x1847b  ldloc.0
0x1847c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x18481  stelem.ref
0x18482  ldloc.s  5
0x18484  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x18489  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1848e  throw
0x1848f  ldarg.0
0x18490  ldstr    aTypeid// "TypeId"
0x18495  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0x1849a  stloc.2
0x1849b  ldloc.2
0x1849c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x184a1  ldarg.1
0x184a2  call     class [mscorlib]System.Type Microsoft.SharePoint.Client.ProxyMap::GetServerTypeFromTypeId(valuetype [mscorlib]System.Guid typeId, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x184a7  stloc.1
0x184a8  ldloc.1
0x184a9  ldnull
0x184aa  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x184af  brfalse.s loc_184DC
0x184b1  ldarg.1
0x184b2  ldc.i4   0x1C50C4
0x184b7  ldc.i4.1
0x184b8  ldstr    aCannotFindType_0// "Cannot find type for expression {0}"
0x184bd  ldc.i4.1
0x184be  newarr   [mscorlib]System.Object
0x184c3  stloc.s  6
0x184c5  ldloc.s  6
0x184c7  ldc.i4.0
0x184c8  ldarg.0
0x184c9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x184ce  stelem.ref
0x184cf  ldloc.s  6
0x184d1  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x184d6  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x184db  throw
0x184dc  ldloc.1
0x184dd  ret
```
