# Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::VideoProviderFromXml

- ea: `0x2da0`
- end: `0x3120`
- name: `Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::VideoProviderFromXml`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3120`

## callees

- `0x2910`
- `0x2970`
- `0x2da0`
- `0x31a0`
- `0x3210`

## string_xrefs

- `0x2daf`: `serviceName`
- `0x2dc7`: `Provider serviceName cannot be empty`
- `0x3046`: `appServiceId`

## pseudocode

```c

```

## disassembly

```asm
0x2da0  ldarg.0
0x2da1  brtrue.s loc_2DAE
0x2da3  ldstr    aProvidernode// "providerNode"
0x2da8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2dad  throw
0x2dae  ldarg.0
0x2daf  ldstr    aServicename// "serviceName"
0x2db4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2db9  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2dbe  stloc.0
0x2dbf  ldloc.0
0x2dc0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dc5  brfalse.s loc_2DD2
0x2dc7  ldstr    aProviderServic// "Provider serviceName cannot be empty"
0x2dcc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2dd1  throw
0x2dd2  ldarg.0
0x2dd3  ldstr    aId// "id"
0x2dd8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2ddd  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2de2  stloc.1
0x2de3  ldloc.1
0x2de4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2de9  brfalse.s loc_2DF6
0x2deb  ldstr    aProviderIdCann// "Provider id cannot be empty"
0x2df0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2df5  throw
0x2df6  ldarg.0
0x2df7  ldstr    aEmbedformat// "embedFormat"
0x2dfc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2e01  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2e06  stloc.2
0x2e07  ldloc.2
0x2e08  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e0d  brfalse.s loc_2E1A
0x2e0f  ldstr    aProviderEmbedf// "Provider embedFormat cannot be empty"
0x2e14  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2e19  throw
0x2e1a  ldloc.2
0x2e1b  ldstr    aMarket// "{market}"
0x2e20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2e25  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2e2a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2e2f  stloc.2
0x2e30  ldarg.0
0x2e31  ldstr    aEditorformat// "editorFormat"
0x2e36  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2e3b  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2e40  stloc.3
0x2e41  ldloc.3
0x2e42  ldstr    aMarket// "{market}"
0x2e47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2e4c  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2e51  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2e56  stloc.3
0x2e57  ldarg.0
0x2e58  ldstr    aEmbedpatterns// "embedPatterns"
0x2e5d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2e62  stloc.s  4
0x2e64  ldloc.s  4
0x2e66  brtrue.s loc_2E73
0x2e68  ldstr    aProviderEmbedp// "Provider embedPatterns cannot be empty"
0x2e6d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2e72  throw
0x2e73  ldloc.s  4
0x2e75  ldstr    aPattern// "pattern"
0x2e7a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2e7f  stloc.s  5
0x2e81  ldloc.s  5
0x2e83  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2e88  brtrue.s loc_2E95
0x2e8a  ldstr    aProviderPatter// "Provider pattern cannot be empty"
0x2e8f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2e94  throw
0x2e95  ldloc.s  5
0x2e97  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2e9c  newarr   Microsoft.SharePoint.Spx.WebSite.VideoConverter.EmbedPattern
0x2ea1  stloc.s  6
0x2ea3  ldc.i4.0
0x2ea4  stloc.s  7
0x2ea6  ldloc.s  5
0x2ea8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2ead  stloc.s  0x1F
0x2eaf  br.s     loc_2EF3
0x2eb1  ldloc.s  0x1F
0x2eb3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2eb8  castclass [System.Xml]System.Xml.XmlNode
0x2ebd  stloc.s  8
0x2ebf  ldloc.s  8
0x2ec1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2ec6  ldstr    aName// "name"
0x2ecb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2ed0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2ed5  stloc.s  9
0x2ed7  ldloc.s  8
0x2ed9  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2ede  stloc.s  0xA
0x2ee0  ldloc.s  6
0x2ee2  ldloc.s  7
0x2ee4  dup
0x2ee5  ldc.i4.1
0x2ee6  add
0x2ee7  stloc.s  7
0x2ee9  ldloc.s  9
0x2eeb  ldloc.s  0xA
0x2eed  newobj   instance void Microsoft.SharePoint.Spx.WebSite.VideoConverter.EmbedPattern::.ctor(string attr, string pattern)
0x2ef2  stelem.ref
0x2ef3  ldloc.s  0x1F
0x2ef5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2efa  brtrue.s loc_2EB1
0x2efc  leave.s  loc_2F13
0x2efe  ldloc.s  0x1F
0x2f00  isinst   [mscorlib]System.IDisposable
0x2f05  stloc.s  0x20
0x2f07  ldloc.s  0x20
0x2f09  brfalse.s loc_2F12
0x2f0b  ldloc.s  0x20
0x2f0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f12  endfinally
0x2f13  ldarg.0
0x2f14  ldstr    aUrlformat// "urlFormat"
0x2f19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2f1e  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2f23  stloc.s  0xB
0x2f25  ldloc.s  0xB
0x2f27  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f2c  brfalse.s loc_2F39
0x2f2e  ldstr    aProviderUrlfor// "Provider urlFormat cannot be empty"
0x2f33  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2f38  throw
0x2f39  ldarg.0
0x2f3a  ldstr    aUrlpattern// "urlPattern"
0x2f3f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2f44  stloc.s  0xC
0x2f46  ldloc.s  0xC
0x2f48  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2f4d  stloc.s  0xD
0x2f4f  ldloc.s  0xD
0x2f51  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f56  brfalse.s loc_2F63
0x2f58  ldstr    aProviderUrlpat// "Provider urlPattern cannot be empty"
0x2f5d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2f62  throw
0x2f63  ldc.i4.0
0x2f64  stloc.s  0xE
0x2f66  ldloc.s  0xC
0x2f68  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2f6d  ldstr    aError// "error"
0x2f72  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2f77  brfalse.s loc_2F97
0x2f79  ldloc.s  0xC
0x2f7b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2f80  ldstr    aError// "error"
0x2f85  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2f8a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2f8f  ldc.i4.0
0x2f90  call     bool Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::ToBool(string boolValue, bool defaultValue)
0x2f95  stloc.s  0xE
0x2f97  ldarg.0
0x2f98  ldstr    aSize_0// "size"
0x2f9d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2fa2  stloc.s  0x11
0x2fa4  ldloc.s  0x11
0x2fa6  brtrue.s loc_2FB3
0x2fa8  ldstr    aProviderSizeCa// "Provider size cannot be empty"
0x2fad  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2fb2  throw
0x2fb3  ldloc.s  0x11
0x2fb5  ldstr    aWidth_0// "width"
0x2fba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2fbf  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2fc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2fc9  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2fce  stloc.s  0xF
0x2fd0  ldloc.s  0x11
0x2fd2  ldstr    aHeight_0// "height"
0x2fd7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2fdc  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x2fe1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2fe6  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2feb  stloc.s  0x10
0x2fed  ldarg.0
0x2fee  ldstr    aBackgroundcolo// "backgroundColor"
0x2ff3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2ff8  stloc.s  0x12
0x2ffa  ldloc.s  0x12
0x2ffc  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x3001  stloc.s  0x13
0x3003  ldarg.0
0x3004  ldstr    aUrlatompattern// "urlAtomPattern"
0x3009  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x300e  stloc.s  0x14
0x3010  ldsfld   string [mscorlib]System.String::Empty
0x3015  stloc.s  0x15
0x3017  ldloc.s  0x14
0x3019  brfalse.s loc_3024
0x301b  ldloc.s  0x14
0x301d  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x3022  stloc.s  0x15
0x3024  ldarg.0
0x3025  ldstr    aUrlatomformat// "urlAtomFormat"
0x302a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x302f  stloc.s  0x16
0x3031  ldsfld   string [mscorlib]System.String::Empty
0x3036  stloc.s  0x17
0x3038  ldloc.s  0x16
0x303a  brfalse.s loc_3045
0x303c  ldloc.s  0x16
0x303e  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x3043  stloc.s  0x17
0x3045  ldarg.0
0x3046  ldstr    aAppserviceid// "appServiceId"
0x304b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3050  stloc.s  0x18
0x3052  ldloc.s  0x18
0x3054  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x3059  stloc.s  0x19
0x305b  ldarg.0
0x305c  ldstr    aPublishpingurl// "publishPingUrl"
0x3061  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3066  stloc.s  0x1A
0x3068  ldnull
0x3069  stloc.s  0x1B
0x306b  ldloc.s  0x1A
0x306d  brfalse  loc_3100
0x3072  ldloc.s  0x1A
0x3074  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3079  ldstr    aStart// "start"
0x307e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3083  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3088  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x308d  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3092  stloc.s  0x1C
0x3094  ldloc.s  0x1A
0x3096  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x309b  ldstr    aEnd// "end"
0x30a0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30a5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30af  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x30b4  stloc.s  0x1D
0x30b6  ldloc.s  0x1D
0x30b8  ldloc.s  0x1C
0x30ba  sub
0x30bb  ldc.i4.1
0x30bc  add
0x30bd  newarr   [mscorlib]System.String
0x30c2  stloc.s  0x1B
0x30c4  ldc.i4.0
0x30c5  stloc.s  0x1E
0x30c7  br.s     loc_30F8
0x30c9  ldloc.s  0x1B
0x30cb  ldloc.s  0x1E
0x30cd  ldloc.s  0x1A
0x30cf  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::NodeText(class [System.Xml]System.Xml.XmlNode node)
0x30d4  ldstr    aI// "{i}"
0x30d9  ldloc.s  0x1E
0x30db  ldloc.s  0x1C
0x30dd  add
0x30de  stloc.s  0x21
0x30e0  ldloca.s 0x21
0x30e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30e7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x30ec  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x30f1  stelem.ref
0x30f2  ldloc.s  0x1E
0x30f4  ldc.i4.1
0x30f5  add
0x30f6  stloc.s  0x1E
0x30f8  ldloc.s  0x1E
0x30fa  ldloc.s  0x1B
0x30fc  ldlen
0x30fd  conv.i4
0x30fe  blt.s    loc_30C9
0x3100  ldloc.0
0x3101  ldloc.1
0x3102  ldloc.2
0x3103  ldloc.3
0x3104  ldloc.s  0xB
0x3106  ldloc.s  6
0x3108  ldloc.s  0xD
0x310a  ldloc.s  0xE
0x310c  ldloc.s  0xF
0x310e  ldloc.s  0x10
0x3110  ldloc.s  0x13
0x3112  ldloc.s  0x19
0x3114  ldloc.s  0x1B
0x3116  ldloc.s  0x15
0x3118  ldloc.s  0x17
0x311a  newobj   instance void Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider::.ctor(string serviceName, string serviceId, string embedFormat, string editorFormat, string urlFormat, class Microsoft.SharePoint.Spx.WebSite.VideoConverter.EmbedPattern[] embedPatterns, string urlPattern, bool urlConvertError, int32 width, int32 height, string useBackgroundColor, string appId, string[] publishPingUrls, string urlAtomPattern, string urlAtomFormat)
0x311f  ret
```
