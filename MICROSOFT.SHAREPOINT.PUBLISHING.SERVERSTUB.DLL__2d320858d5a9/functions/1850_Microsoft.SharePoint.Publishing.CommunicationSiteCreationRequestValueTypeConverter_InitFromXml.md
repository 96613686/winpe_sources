# Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::InitFromXml

- ea: `0x1850`
- end: `0x19f8`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::InitFromXml`
- size: `424`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1850`

## string_xrefs

- `0x190d`: `WebTemplateExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x1850  ldarg.0
0x1851  ldarg.1
0x1852  ldarg.2
0x1853  ldarg.3
0x1854  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1859  starg.s  1
0x185b  ldarg.1
0x185c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest
0x1861  stloc.0
0x1862  ldloc.0
0x1863  brfalse  loc_19F6
0x1868  ldarg.2
0x1869  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x186e  stloc.s  4
0x1870  br       loc_19D3
0x1875  ldloc.s  4
0x1877  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x187c  castclass [System.Xml]System.Xml.XmlNode
0x1881  stloc.1
0x1882  ldloc.1
0x1883  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1888  ldstr    aName// "Name"
0x188d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1892  stloc.2
0x1893  ldloc.2
0x1894  brfalse  loc_19D3
0x1899  ldloc.2
0x189a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x189f  stloc.3
0x18a0  ldloc.3
0x18a1  dup
0x18a2  stloc.s  5
0x18a4  brfalse  loc_19D3
0x18a9  volatile.
0x18ab  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000039-1
0x18b0  brtrue.s loc_191F
0x18b2  ldc.i4.8
0x18b3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x18b8  dup
0x18b9  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x18be  ldc.i4.0
0x18bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18c4  dup
0x18c5  ldstr    aClassification// "Classification"
0x18ca  ldc.i4.1
0x18cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18d0  dup
0x18d1  ldstr    aDescription// "Description"
0x18d6  ldc.i4.2
0x18d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18dc  dup
0x18dd  ldstr    aLcid_0// "lcid"
0x18e2  ldc.i4.3
0x18e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18e8  dup
0x18e9  ldstr    aSitedesignid// "SiteDesignId"
0x18ee  ldc.i4.4
0x18ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18f4  dup
0x18f5  ldstr    aTitle// "Title"
0x18fa  ldc.i4.5
0x18fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1900  dup
0x1901  ldstr    aUrl// "Url"
0x1906  ldc.i4.6
0x1907  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x190c  dup
0x190d  ldstr    aWebtemplateext// "WebTemplateExtensionId"
0x1912  ldc.i4.7
0x1913  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1918  volatile.
0x191a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000039-1
0x191f  volatile.
0x1921  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000039-1
0x1926  ldloc.s  5
0x1928  ldloca.s 6
0x192a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x192f  brfalse  loc_19D3
0x1934  ldloc.s  6
0x1936  switch   loc_195D, loc_196C, loc_197B, loc_198A, loc_1999, loc_19A8, loc_19B7, loc_19C6
0x195b  br.s     loc_19D3
0x195d  ldloc.0
0x195e  ldloc.1
0x195f  ldarg.3
0x1960  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1965  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_AllowFileSharingForGuestUsers(bool)
0x196a  br.s     loc_19D3
0x196c  ldloc.0
0x196d  ldloc.1
0x196e  ldarg.3
0x196f  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1974  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Classification(string)
0x1979  br.s     loc_19D3
0x197b  ldloc.0
0x197c  ldloc.1
0x197d  ldarg.3
0x197e  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1983  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Description(string)
0x1988  br.s     loc_19D3
0x198a  ldloc.0
0x198b  ldloc.1
0x198c  ldarg.3
0x198d  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1992  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_lcid(int32)
0x1997  br.s     loc_19D3
0x1999  ldloc.0
0x199a  ldloc.1
0x199b  ldarg.3
0x199c  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x19a1  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_SiteDesignId(valuetype [mscorlib]System.Guid)
0x19a6  br.s     loc_19D3
0x19a8  ldloc.0
0x19a9  ldloc.1
0x19aa  ldarg.3
0x19ab  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x19b0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Title(string)
0x19b5  br.s     loc_19D3
0x19b7  ldloc.0
0x19b8  ldloc.1
0x19b9  ldarg.3
0x19ba  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x19bf  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Url(string)
0x19c4  br.s     loc_19D3
0x19c6  ldloc.0
0x19c7  ldloc.1
0x19c8  ldarg.3
0x19c9  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x19ce  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_WebTemplateExtensionId(valuetype [mscorlib]System.Guid)
0x19d3  ldloc.s  4
0x19d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19da  brtrue   loc_1875
0x19df  leave.s  loc_19F6
0x19e1  ldloc.s  4
0x19e3  isinst   [mscorlib]System.IDisposable
0x19e8  stloc.s  7
0x19ea  ldloc.s  7
0x19ec  brfalse.s loc_19F5
0x19ee  ldloc.s  7
0x19f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19f5  endfinally
0x19f6  ldloc.0
0x19f7  ret
```
