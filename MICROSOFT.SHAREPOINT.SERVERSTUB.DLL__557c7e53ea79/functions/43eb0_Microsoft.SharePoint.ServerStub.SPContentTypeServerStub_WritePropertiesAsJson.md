# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::WritePropertiesAsJson

- ea: `0x43eb0`
- end: `0x443c1`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::WritePropertiesAsJson`
- size: `1297`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x43eb0`

## string_xrefs

- `0x43fad`: `DocumentTemplateUrl`
- `0x43fb9`: `DocumentTemplateUrl`
- `0x43fc4`: `DocumentTemplateUrl`
- `0x43fdc`: `DocumentTemplateUrl`
- `0x442d9`: `SchemaXml`
- `0x442e5`: `SchemaXml`
- `0x442f0`: `SchemaXml`
- `0x44308`: `SchemaXml`
- `0x43f73`: `DocumentTemplate`
- `0x43f7f`: `DocumentTemplate`
- `0x43f8a`: `DocumentTemplate`
- `0x43fa2`: `DocumentTemplate`
- `0x43eff`: `DisplayFormTemplateName`
- `0x43f0b`: `DisplayFormTemplateName`
- `0x43f16`: `DisplayFormTemplateName`
- `0x43f2e`: `DisplayFormTemplateName`
- `0x43fe7`: `EditFormTemplateName`
- `0x43ff3`: `EditFormTemplateName`
- `0x43ffe`: `EditFormTemplateName`
- `0x44016`: `EditFormTemplateName`
- `0x44109`: `JSLink`
- `0x44115`: `JSLink`
- `0x44120`: `JSLink`
- `0x44138`: `JSLink`
- `0x4422b`: `NewFormTemplateName`
- `0x44237`: `NewFormTemplateName`
- `0x44242`: `NewFormTemplateName`
- `0x4425a`: `NewFormTemplateName`
- `0x4429f`: `ReadOnly`
- `0x442ab`: `ReadOnly`
- `0x442b6`: `ReadOnly`
- `0x442ce`: `ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x43eb0  ldarg.2
0x43eb1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x43eb6  stloc.0
0x43eb7  ldloc.0
0x43eb8  brtrue.s loc_43EBB
0x43eba  ret
0x43ebb  ldarg.0
0x43ebc  ldarg.1
0x43ebd  ldarg.2
0x43ebe  ldarg.3
0x43ebf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43ec4  ldarg.0
0x43ec5  ldstr    aDescription// "Description"
0x43eca  ldarg.3
0x43ecb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43ed0  ldarg.1
0x43ed1  ldstr    aDescription// "Description"
0x43ed6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43edb  ldarg.3
0x43edc  ldstr    aDescription// "Description"
0x43ee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43ee6  ldarg.1
0x43ee7  ldloc.0
0x43ee8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Description()
0x43eed  ldarg.3
0x43eee  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43ef3  ldarg.3
0x43ef4  ldstr    aDescription// "Description"
0x43ef9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43efe  ldarg.0
0x43eff  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43f04  ldarg.3
0x43f05  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f0a  ldarg.1
0x43f0b  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43f10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43f15  ldarg.3
0x43f16  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43f1b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43f20  ldarg.1
0x43f21  ldloc.0
0x43f22  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormTemplateName()
0x43f27  ldarg.3
0x43f28  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f2d  ldarg.3
0x43f2e  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43f33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43f38  ldarg.0
0x43f39  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43f3e  ldarg.3
0x43f3f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f44  ldarg.1
0x43f45  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43f4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43f4f  ldarg.3
0x43f50  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43f55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43f5a  ldarg.1
0x43f5b  ldloc.0
0x43f5c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormUrl()
0x43f61  ldarg.3
0x43f62  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f67  ldarg.3
0x43f68  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43f6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43f72  ldarg.0
0x43f73  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x43f78  ldarg.3
0x43f79  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f7e  ldarg.1
0x43f7f  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x43f84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43f89  ldarg.3
0x43f8a  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x43f8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43f94  ldarg.1
0x43f95  ldloc.0
0x43f96  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DocumentTemplate()
0x43f9b  ldarg.3
0x43f9c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43fa1  ldarg.3
0x43fa2  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x43fa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43fac  ldarg.0
0x43fad  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x43fb2  ldarg.3
0x43fb3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43fb8  ldarg.1
0x43fb9  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x43fbe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43fc3  ldarg.3
0x43fc4  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x43fc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43fce  ldarg.1
0x43fcf  ldloc.0
0x43fd0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DocumentTemplateUrl()
0x43fd5  ldarg.3
0x43fd6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43fdb  ldarg.3
0x43fdc  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x43fe1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43fe6  ldarg.0
0x43fe7  ldstr    aEditformtempla// "EditFormTemplateName"
0x43fec  ldarg.3
0x43fed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43ff2  ldarg.1
0x43ff3  ldstr    aEditformtempla// "EditFormTemplateName"
0x43ff8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43ffd  ldarg.3
0x43ffe  ldstr    aEditformtempla// "EditFormTemplateName"
0x44003  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x44008  ldarg.1
0x44009  ldloc.0
0x4400a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_EditFormTemplateName()
0x4400f  ldarg.3
0x44010  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44015  ldarg.3
0x44016  ldstr    aEditformtempla// "EditFormTemplateName"
0x4401b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x44020  ldarg.0
0x44021  ldstr    aEditformurl// "EditFormUrl"
0x44026  ldarg.3
0x44027  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4402c  ldarg.1
0x4402d  ldstr    aEditformurl// "EditFormUrl"
0x44032  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44037  ldarg.3
0x44038  ldstr    aEditformurl// "EditFormUrl"
0x4403d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x44042  ldarg.1
0x44043  ldloc.0
0x44044  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_EditFormUrl()
0x44049  ldarg.3
0x4404a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4404f  ldarg.3
0x44050  ldstr    aEditformurl// "EditFormUrl"
0x44055  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4405a  ldarg.0
0x4405b  ldstr    aGroup// "Group"
0x44060  ldarg.3
0x44061  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44066  ldarg.1
0x44067  ldstr    aGroup// "Group"
0x4406c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44071  ldarg.3
0x44072  ldstr    aGroup// "Group"
0x44077  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4407c  ldarg.1
0x4407d  ldloc.0
0x4407e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Group()
0x44083  ldarg.3
0x44084  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44089  ldarg.3
0x4408a  ldstr    aGroup// "Group"
0x4408f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x44094  ldarg.0
0x44095  ldstr    aHidden// "Hidden"
0x4409a  ldarg.3
0x4409b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x440a0  ldarg.1
0x440a1  ldstr    aHidden// "Hidden"
0x440a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x440ab  ldarg.3
0x440ac  ldstr    aHidden// "Hidden"
0x440b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x440b6  ldarg.1
0x440b7  ldloc.0
0x440b8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Hidden()
0x440bd  ldarg.3
0x440be  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x440c3  ldarg.3
0x440c4  ldstr    aHidden// "Hidden"
0x440c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x440ce  ldarg.0
0x440cf  ldstr    aId_0// "Id"
0x440d4  ldarg.3
0x440d5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x440da  ldarg.1
0x440db  ldstr    aId_0// "Id"
0x440e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x440e5  ldarg.3
0x440e6  ldstr    aId_0// "Id"
0x440eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x440f0  ldarg.1
0x440f1  ldloc.0
0x440f2  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0x440f7  ldarg.3
0x440f8  call     T0x2B000156
0x440fd  ldarg.3
0x440fe  ldstr    aId_0// "Id"
0x44103  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x44108  ldarg.0
0x44109  ldstr    aJslink// "JSLink"
0x4410e  ldarg.3
0x4410f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44114  ldarg.1
0x44115  ldstr    aJslink// "JSLink"
0x4411a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4411f  ldarg.3
0x44120  ldstr    aJslink// "JSLink"
0x44125  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4412a  ldarg.1
0x4412b  ldloc.0
0x4412c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_JSLink()
0x44131  ldarg.3
0x44132  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44137  ldarg.3
0x44138  ldstr    aJslink// "JSLink"
0x4413d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x44142  ldarg.0
0x44143  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x44148  ldarg.3
0x44149  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4414e  ldarg.1
0x4414f  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x44154  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44159  ldarg.3
0x4415a  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x4415f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x44164  ldarg.1
0x44165  ldloc.0
0x44166  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileDisplayFormUrl()
0x4416b  ldarg.3
0x4416c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44171  ldarg.3
0x44172  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x44177  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4417c  ldarg.0
0x4417d  ldstr    aMobileeditform// "MobileEditFormUrl"
0x44182  ldarg.3
0x44183  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44188  ldarg.1
0x44189  ldstr    aMobileeditform// "MobileEditFormUrl"
0x4418e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44193  ldarg.3
0x44194  ldstr    aMobileeditform// "MobileEditFormUrl"
0x44199  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4419e  ldarg.1
0x4419f  ldloc.0
0x441a0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileEditFormUrl()
0x441a5  ldarg.3
0x441a6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x441ab  ldarg.3
0x441ac  ldstr    aMobileeditform// "MobileEditFormUrl"
0x441b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x441b6  ldarg.0
0x441b7  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x441bc  ldarg.3
0x441bd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x441c2  ldarg.1
0x441c3  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x441c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x441cd  ldarg.3
0x441ce  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x441d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x441d8  ldarg.1
0x441d9  ldloc.0
0x441da  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileNewFormUrl()
0x441df  ldarg.3
0x441e0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x441e5  ldarg.3
0x441e6  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x441eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x441f0  ldarg.0
0x441f1  ldstr    aName// "Name"
0x441f6  ldarg.3
0x441f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x441fc  ldarg.1
0x441fd  ldstr    aName// "Name"
0x44202  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44207  ldarg.3
0x44208  ldstr    aName// "Name"
0x4420d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x44212  ldarg.1
0x44213  ldloc.0
0x44214  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x44219  ldarg.3
0x4421a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4421f  ldarg.3
0x44220  ldstr    aName// "Name"
0x44225  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4422a  ldarg.0
0x4422b  ldstr    aNewformtemplat// "NewFormTemplateName"
0x44230  ldarg.3
0x44231  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44236  ldarg.1
0x44237  ldstr    aNewformtemplat// "NewFormTemplateName"
0x4423c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x44241  ldarg.3
0x44242  ldstr    aNewformtemplat// "NewFormTemplateName"
0x44247  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4424c  ldarg.1
0x4424d  ldloc.0
0x4424e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_NewFormTemplateName()
0x44253  ldarg.3
0x44254  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44259  ldarg.3
0x4425a  ldstr    aNewformtemplat// "NewFormTemplateName"
0x4425f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x44264  ldarg.0
  ... truncated ...
```
