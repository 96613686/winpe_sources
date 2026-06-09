# Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::InitFromXml

- ea: `0xd8b0`
- end: `0xda7b`
- name: `Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::InitFromXml`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd8b0`

## string_xrefs

- `0xd97a`: `WebRelativeFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xd8b0  ldarg.0
0xd8b1  ldarg.1
0xd8b2  ldarg.2
0xd8b3  ldarg.3
0xd8b4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd8b9  starg.s  1
0xd8bb  ldarg.1
0xd8bc  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo
0xd8c1  stloc.0
0xd8c2  ldloc.0
0xd8c3  brfalse  loc_DA79
0xd8c8  ldarg.2
0xd8c9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0xd8ce  stloc.s  4
0xd8d0  br       loc_DA56
0xd8d5  ldloc.s  4
0xd8d7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd8dc  castclass [System.Xml]System.Xml.XmlNode
0xd8e1  stloc.1
0xd8e2  ldloc.1
0xd8e3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xd8e8  ldstr    aName// "Name"
0xd8ed  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xd8f2  stloc.2
0xd8f3  ldloc.2
0xd8f4  brfalse  loc_DA56
0xd8f9  ldloc.2
0xd8fa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xd8ff  stloc.3
0xd900  ldloc.3
0xd901  dup
0xd902  stloc.s  5
0xd904  brfalse  loc_DA56
0xd909  volatile.
0xd90b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000279-1
0xd910  brtrue.s loc_D98C
0xd912  ldc.i4.s 9
0xd914  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xd919  dup
0xd91a  ldstr    aCanvascontent1// "CanvasContent1"
0xd91f  ldc.i4.0
0xd920  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd925  dup
0xd926  ldstr    aContenttypeid// "ContentTypeId"
0xd92b  ldc.i4.1
0xd92c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd931  dup
0xd932  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xd937  ldc.i4.2
0xd938  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd93d  dup
0xd93e  ldstr    aName// "Name"
0xd943  ldc.i4.3
0xd944  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd949  dup
0xd94a  ldstr    aPagelayouttype// "PageLayoutType"
0xd94f  ldc.i4.4
0xd950  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd955  dup
0xd956  ldstr    aPromotedstate_0// "PromotedState"
0xd95b  ldc.i4.5
0xd95c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd961  dup
0xd962  ldstr    aSourceitemid// "SourceItemId"
0xd967  ldc.i4.6
0xd968  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd96d  dup
0xd96e  ldstr    aTitle// "Title"
0xd973  ldc.i4.7
0xd974  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd979  dup
0xd97a  ldstr    aWebrelativefol// "WebRelativeFolderPath"
0xd97f  ldc.i4.8
0xd980  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd985  volatile.
0xd987  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000279-1
0xd98c  volatile.
0xd98e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000279-1
0xd993  ldloc.s  5
0xd995  ldloca.s 6
0xd997  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xd99c  brfalse  loc_DA56
0xd9a1  ldloc.s  6
0xd9a3  switch   loc_D9D1, loc_D9E0, loc_D9EF, loc_D9FE, loc_DA0D, loc_DA1C, loc_DA2B, loc_DA3A, loc_DA49
0xd9cc  br       loc_DA56
0xd9d1  ldloc.0
0xd9d2  ldloc.1
0xd9d3  ldarg.3
0xd9d4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd9d9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_CanvasContent1(string)
0xd9de  br.s     loc_DA56
0xd9e0  ldloc.0
0xd9e1  ldloc.1
0xd9e2  ldarg.3
0xd9e3  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd9e8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_ContentTypeId(string)
0xd9ed  br.s     loc_DA56
0xd9ef  ldloc.0
0xd9f0  ldloc.1
0xd9f1  ldarg.3
0xd9f2  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd9f7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_LayoutWebpartsContent(string)
0xd9fc  br.s     loc_DA56
0xd9fe  ldloc.0
0xd9ff  ldloc.1
0xda00  ldarg.3
0xda01  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xda06  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_Name(string)
0xda0b  br.s     loc_DA56
0xda0d  ldloc.0
0xda0e  ldloc.1
0xda0f  ldarg.3
0xda10  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xda15  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_PageLayoutType(string)
0xda1a  br.s     loc_DA56
0xda1c  ldloc.0
0xda1d  ldloc.1
0xda1e  ldarg.3
0xda1f  call     T0x2B000038
0xda24  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_PromotedState(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState)
0xda29  br.s     loc_DA56
0xda2b  ldloc.0
0xda2c  ldloc.1
0xda2d  ldarg.3
0xda2e  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xda33  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_SourceItemId(int32)
0xda38  br.s     loc_DA56
0xda3a  ldloc.0
0xda3b  ldloc.1
0xda3c  ldarg.3
0xda3d  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xda42  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_Title(string)
0xda47  br.s     loc_DA56
0xda49  ldloc.0
0xda4a  ldloc.1
0xda4b  ldarg.3
0xda4c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xda51  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_WebRelativeFolderPath(string)
0xda56  ldloc.s  4
0xda58  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xda5d  brtrue   loc_D8D5
0xda62  leave.s  loc_DA79
0xda64  ldloc.s  4
0xda66  isinst   [mscorlib]System.IDisposable
0xda6b  stloc.s  7
0xda6d  ldloc.s  7
0xda6f  brfalse.s loc_DA78
0xda71  ldloc.s  7
0xda73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xda78  endfinally
0xda79  ldloc.0
0xda7a  ret
```
