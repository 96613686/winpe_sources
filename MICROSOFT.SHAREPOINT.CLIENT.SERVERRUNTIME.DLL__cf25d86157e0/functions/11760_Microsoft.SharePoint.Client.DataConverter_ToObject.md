# Microsoft.SharePoint.Client.DataConverter::ToObject

- ea: `0x11760`
- end: `0x11869`
- name: `Microsoft.SharePoint.Client.DataConverter::ToObject`
- size: `265`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0xc860`
- `0xca40`
- `0xd450`
- `0x10ee0`
- `0x115e0`
- `0x11c70`

## callees

- `0x240`
- `0x250`
- `0x11760`
- `0x12e20`
- `0x150f0`
- `0x15260`
- `0x152f0`
- `0x16900`
- `0x16f00`
- `0x17e60`
- `0x18c00`

## string_xrefs

- `0x11789`: `ObjectPathId`
- `0x1179d`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0x11760  ldnull
0x11761  stloc.0
0x11762  ldarg.0
0x11763  brtrue.s loc_11767
0x11765  ldloc.0
0x11766  ret
0x11767  ldarg.0
0x11768  call     bool Microsoft.SharePoint.Client.Utility::IsNullValue(class [System.Xml]System.Xml.XmlNode xn)
0x1176d  brfalse.s loc_11773
0x1176f  ldnull
0x11770  stloc.0
0x11771  ldloc.0
0x11772  ret
0x11773  ldarg.1
0x11774  brfalse.s loc_11783
0x11776  ldarg.1
0x11777  ldarg.0
0x11778  ldloca.s 0
0x1177a  callvirt instance bool Microsoft.SharePoint.Client.ProxyContext::TryEvaluateExpression(class [System.Xml]System.Xml.XmlNode xe, [out] object& value)
0x1177f  brfalse.s loc_11783
0x11781  ldloc.0
0x11782  ret
0x11783  ldarg.0
0x11784  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11789  ldstr    aObjectpathid// "ObjectPathId"
0x1178e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x11793  stloc.1
0x11794  ldloc.1
0x11795  brfalse.s loc_117B5
0x11797  ldarg.0
0x11798  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1179d  ldstr    aObjectpathid// "ObjectPathId"
0x117a2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x117a7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x117ac  stloc.2
0x117ad  ldarg.1
0x117ae  ldloc.2
0x117af  callvirt instance object Microsoft.SharePoint.Client.ProxyContext::GetObjectFromObjectPathId(string pathId)
0x117b4  ret
0x117b5  ldarg.0
0x117b6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x117bb  ldstr    aTypeid// "TypeId"
0x117c0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x117c5  stloc.1
0x117c6  ldloc.1
0x117c7  brfalse.s loc_11811
0x117c9  ldloc.1
0x117ca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x117cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x117d4  brtrue.s loc_11811
0x117d6  ldloc.1
0x117d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x117dc  stloc.3
0x117dd  ldloca.s 4
0x117df  ldloc.3
0x117e0  call     instance void [mscorlib]System.Guid::.ctor(string)
0x117e5  ldloc.s  4
0x117e7  ldarg.1
0x117e8  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x117ed  call     class Microsoft.SharePoint.Client.ValueTypeConverter Microsoft.SharePoint.Client.ProxyMap::GetValueTypeConverter(valuetype [mscorlib]System.Guid typeId, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x117f2  stloc.s  5
0x117f4  ldloc.s  5
0x117f6  brfalse.s loc_11811
0x117f8  ldloc.s  5
0x117fa  ldarg.0
0x117fb  ldarg.1
0x117fc  callvirt instance object Microsoft.SharePoint.Client.ValueTypeConverter::CustomCreateFromXml(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext context)
0x11801  stloc.0
0x11802  ldloc.0
0x11803  brtrue.s loc_1180F
0x11805  ldloc.s  5
0x11807  ldarg.0
0x11808  ldarg.1
0x11809  callvirt instance object Microsoft.SharePoint.Client.ValueTypeConverter::CreateFromXml(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext context)
0x1180e  stloc.0
0x1180f  ldloc.0
0x11810  ret
0x11811  ldarg.0
0x11812  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11817  ldstr    aType_0// "Type"
0x1181c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x11821  stloc.1
0x11822  ldloc.1
0x11823  brfalse.s loc_11859
0x11825  ldloc.1
0x11826  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1182b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11830  brtrue.s loc_11859
0x11832  ldloc.1
0x11833  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11838  stloc.s  6
0x1183a  ldnull
0x1183b  stloc.s  7
0x1183d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.GetObjectHandler> Microsoft.SharePoint.Client.WellknownTypeBehavior::s_wellknownTypeGetObjectHandler
0x11842  ldloc.s  6
0x11844  ldloca.s 7
0x11846  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.GetObjectHandler>::TryGetValue(var<u1>, !!T0)
0x1184b  brfalse.s loc_11859
0x1184d  ldloc.s  7
0x1184f  ldarg.0
0x11850  ldarg.1
0x11851  callvirt instance object Microsoft.SharePoint.Client.GetObjectHandler::Invoke(class [System.Xml]System.Xml.XmlNode node, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11856  stloc.0
0x11857  ldloc.0
0x11858  ret
0x11859  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0x1185e  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0x11863  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x11868  throw
```
