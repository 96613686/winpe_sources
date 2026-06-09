# Microsoft.SharePoint.Client.DataConverter::GetObject

- ea: `0x11c70`
- end: `0x11e60`
- name: `Microsoft.SharePoint.Client.DataConverter::GetObject`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x240`
- `0x250`
- `0x11760`
- `0x11c70`
- `0x12df0`
- `0x150f0`
- `0x15260`
- `0x152f0`
- `0x168e0`
- `0x16920`
- `0x17e60`
- `0x18c00`

## string_xrefs

- `0x11de6`: `ObjectPathId`
- `0x11dfe`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  ldarg.0
0x11c71  brtrue.s loc_11C7E
0x11c73  ldloca.s 0xD
0x11c75  initobj  mvar<u1>
0x11c7b  ldloc.s  0xD
0x11c7d  ret
0x11c7e  ldarg.0
0x11c7f  call     bool Microsoft.SharePoint.Client.Utility::IsNullValue(class [System.Xml]System.Xml.XmlNode xn)
0x11c84  brfalse.s loc_11C91
0x11c86  ldloca.s 0xE
0x11c88  initobj  mvar<u1>
0x11c8e  ldloc.s  0xE
0x11c90  ret
0x11c91  ldarg.1
0x11c92  brfalse.s loc_11CB9
0x11c94  ldarg.1
0x11c95  ldarg.0
0x11c96  ldloca.s 0
0x11c98  callvirt instance bool Microsoft.SharePoint.Client.ProxyContext::TryEvaluateExpression(class [System.Xml]System.Xml.XmlNode xe, [out] object& value)
0x11c9d  brfalse.s loc_11CB9
0x11c9f  ldloc.0
0x11ca0  isinst   mvar<u1>
0x11ca5  brfalse.s loc_11CAE
0x11ca7  ldloc.0
0x11ca8  unbox.any mvar<u1>
0x11cad  ret
0x11cae  ldloca.s 0xF
0x11cb0  initobj  mvar<u1>
0x11cb6  ldloc.s  0xF
0x11cb8  ret
0x11cb9  ldtoken  mvar<u1>
0x11cbe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11cc3  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x11cc8  brfalse.s loc_11CF0
0x11cca  ldarg.0
0x11ccb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x11cd0  stloc.1
0x11cd1  ldtoken  mvar<u1>
0x11cd6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11cdb  call     class [mscorlib]System.Type [mscorlib]System.Enum::GetUnderlyingType(class [mscorlib]System.Type)
0x11ce0  stloc.2
0x11ce1  ldloc.1
0x11ce2  ldloc.2
0x11ce3  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type)
0x11ce8  stloc.3
0x11ce9  ldloc.3
0x11cea  unbox.any mvar<u1>
0x11cef  ret
0x11cf0  ldtoken  mvar<u1>
0x11cf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11cfa  call     instance bool [mscorlib]System.Type::get_IsArray()
0x11cff  brfalse.s loc_11D63
0x11d01  ldtoken  Microsoft.SharePoint.Client.DataConverter
0x11d06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d0b  ldstr    aGetobjectarray// "GetObjectArray"
0x11d10  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x11d15  stloc.s  4
0x11d17  ldloc.s  4
0x11d19  ldc.i4.1
0x11d1a  newarr   [mscorlib]System.Type
0x11d1f  stloc.s  0x10
0x11d21  ldloc.s  0x10
0x11d23  ldc.i4.0
0x11d24  ldtoken  mvar<u1>
0x11d29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d2e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x11d33  stelem.ref
0x11d34  ldloc.s  0x10
0x11d36  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.MethodInfo::MakeGenericMethod(class [mscorlib]System.Type[])
0x11d3b  stloc.s  5
0x11d3d  ldloc.s  5
0x11d3f  ldnull
0x11d40  ldc.i4.2
0x11d41  newarr   [mscorlib]System.Object
0x11d46  stloc.s  0x11
0x11d48  ldloc.s  0x11
0x11d4a  ldc.i4.0
0x11d4b  ldarg.0
0x11d4c  stelem.ref
0x11d4d  ldloc.s  0x11
0x11d4f  ldc.i4.1
0x11d50  ldarg.1
0x11d51  stelem.ref
0x11d52  ldloc.s  0x11
0x11d54  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x11d59  stloc.s  6
0x11d5b  ldloc.s  6
0x11d5d  unbox.any mvar<u1>
0x11d62  ret
0x11d63  ldnull
0x11d64  stloc.s  7
0x11d66  ldnull
0x11d67  stloc.s  8
0x11d69  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.WellknownTypeBehavior> Microsoft.SharePoint.Client.WellknownTypeBehavior::s_wellknownTypeBehaviors
0x11d6e  ldtoken  mvar<u1>
0x11d73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d78  ldloca.s 8
0x11d7a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.WellknownTypeBehavior>::TryGetValue(var<u1>, !!T0)
0x11d7f  brfalse.s loc_11D8A
0x11d81  ldloc.s  8
0x11d83  ldfld    class Microsoft.SharePoint.Client.GetObjectHandler Microsoft.SharePoint.Client.WellknownTypeBehavior::GetObjectFromXmlNodeFunc
0x11d88  stloc.s  7
0x11d8a  ldloc.s  7
0x11d8c  brfalse.s loc_11DA1
0x11d8e  ldloc.s  7
0x11d90  ldarg.0
0x11d91  ldarg.1
0x11d92  callvirt instance object Microsoft.SharePoint.Client.GetObjectHandler::Invoke(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11d97  stloc.s  9
0x11d99  ldloc.s  9
0x11d9b  unbox.any mvar<u1>
0x11da0  ret
0x11da1  ldtoken  mvar<u1>
0x11da6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11dab  ldtoken  [mscorlib]System.Object
0x11db0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11db5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11dba  brfalse.s loc_11DC9
0x11dbc  ldarg.0
0x11dbd  ldarg.1
0x11dbe  call     object Microsoft.SharePoint.Client.DataConverter::ToObject(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11dc3  unbox.any mvar<u1>
0x11dc8  ret
0x11dc9  ldtoken  mvar<u1>
0x11dce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11dd3  ldarg.1
0x11dd4  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x11dd9  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x11dde  brfalse.s loc_11E1D
0x11de0  ldarg.0
0x11de1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11de6  ldstr    aObjectpathid// "ObjectPathId"
0x11deb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x11df0  brtrue.s loc_11DF8
0x11df2  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x11df7  throw
0x11df8  ldarg.0
0x11df9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11dfe  ldstr    aObjectpathid// "ObjectPathId"
0x11e03  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x11e08  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11e0d  stloc.s  0xA
0x11e0f  ldarg.1
0x11e10  ldloc.s  0xA
0x11e12  callvirt instance object Microsoft.SharePoint.Client.ProxyContext::GetObjectFromObjectPathId(string pathId)
0x11e17  unbox.any mvar<u1>
0x11e1c  ret
0x11e1d  ldtoken  mvar<u1>
0x11e22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11e27  ldarg.1
0x11e28  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x11e2d  call     class Microsoft.SharePoint.Client.ValueTypeConverter Microsoft.SharePoint.Client.ProxyMap::GetValueTypeConverter(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x11e32  stloc.s  0xB
0x11e34  ldloc.s  0xB
0x11e36  brtrue.s loc_11E3E
0x11e38  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x11e3d  throw
0x11e3e  ldloc.s  0xB
0x11e40  ldarg.0
0x11e41  ldarg.1
0x11e42  callvirt instance object Microsoft.SharePoint.Client.ValueTypeConverter::CustomCreateFromXml(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext context)
0x11e47  stloc.s  0xC
0x11e49  ldloc.s  0xC
0x11e4b  brtrue.s loc_11E58
0x11e4d  ldloc.s  0xB
0x11e4f  ldarg.0
0x11e50  ldarg.1
0x11e51  callvirt instance object Microsoft.SharePoint.Client.ValueTypeConverter::CreateFromXml(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext context)
0x11e56  stloc.s  0xC
0x11e58  ldloc.s  0xC
0x11e5a  unbox.any mvar<u1>
0x11e5f  ret
```
