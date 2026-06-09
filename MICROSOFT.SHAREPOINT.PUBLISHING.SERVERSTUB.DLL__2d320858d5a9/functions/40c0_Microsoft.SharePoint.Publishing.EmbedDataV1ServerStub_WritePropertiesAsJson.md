# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::WritePropertiesAsJson

- ea: `0x40c0`
- end: `0x44e9`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::WritePropertiesAsJson`
- size: `1065`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x40c0`

## string_xrefs

- `0x41bd`: `EmbedServiceResponseCode`
- `0x41c9`: `EmbedServiceResponseCode`
- `0x41d4`: `EmbedServiceResponseCode`
- `0x41ec`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x40c0  ldarg.2
0x40c1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x40c6  stloc.0
0x40c7  ldloc.0
0x40c8  brtrue.s loc_40CB
0x40ca  ret
0x40cb  ldarg.0
0x40cc  ldarg.1
0x40cd  ldarg.2
0x40ce  ldarg.3
0x40cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x40d4  ldarg.0
0x40d5  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x40da  ldarg.3
0x40db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x40e0  ldarg.1
0x40e1  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x40e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x40eb  ldarg.3
0x40ec  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x40f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x40f6  ldarg.1
0x40f7  ldloc.0
0x40f8  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_AllowHttpsEmbed()
0x40fd  ldarg.3
0x40fe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4103  ldarg.3
0x4104  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x4109  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x410e  ldarg.0
0x410f  ldstr    aCreatorname// "CreatorName"
0x4114  ldarg.3
0x4115  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x411a  ldarg.1
0x411b  ldstr    aCreatorname// "CreatorName"
0x4120  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4125  ldarg.3
0x4126  ldstr    aCreatorname// "CreatorName"
0x412b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4130  ldarg.1
0x4131  ldloc.0
0x4132  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_CreatorName()
0x4137  ldarg.3
0x4138  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x413d  ldarg.3
0x413e  ldstr    aCreatorname// "CreatorName"
0x4143  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4148  ldarg.0
0x4149  ldstr    aDatepublisheda// "DatePublishedAt"
0x414e  ldarg.3
0x414f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4154  ldarg.1
0x4155  ldstr    aDatepublisheda// "DatePublishedAt"
0x415a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x415f  ldarg.3
0x4160  ldstr    aDatepublisheda// "DatePublishedAt"
0x4165  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x416a  ldarg.1
0x416b  ldloc.0
0x416c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_DatePublishedAt()
0x4171  ldarg.3
0x4172  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4177  ldarg.3
0x4178  ldstr    aDatepublisheda// "DatePublishedAt"
0x417d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4182  ldarg.0
0x4183  ldstr    aDescription// "Description"
0x4188  ldarg.3
0x4189  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x418e  ldarg.1
0x418f  ldstr    aDescription// "Description"
0x4194  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4199  ldarg.3
0x419a  ldstr    aDescription// "Description"
0x419f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x41a4  ldarg.1
0x41a5  ldloc.0
0x41a6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Description()
0x41ab  ldarg.3
0x41ac  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41b1  ldarg.3
0x41b2  ldstr    aDescription// "Description"
0x41b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x41bc  ldarg.0
0x41bd  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x41c2  ldarg.3
0x41c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c8  ldarg.1
0x41c9  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x41ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x41d3  ldarg.3
0x41d4  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x41d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x41de  ldarg.1
0x41df  ldloc.0
0x41e0  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_EmbedServiceResponseCode()
0x41e5  ldarg.3
0x41e6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41eb  ldarg.3
0x41ec  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x41f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x41f6  ldarg.0
0x41f7  ldstr    aErrormessage// "ErrorMessage"
0x41fc  ldarg.3
0x41fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4202  ldarg.1
0x4203  ldstr    aErrormessage// "ErrorMessage"
0x4208  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x420d  ldarg.3
0x420e  ldstr    aErrormessage// "ErrorMessage"
0x4213  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4218  ldarg.1
0x4219  ldloc.0
0x421a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ErrorMessage()
0x421f  ldarg.3
0x4220  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4225  ldarg.3
0x4226  ldstr    aErrormessage// "ErrorMessage"
0x422b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4230  ldarg.0
0x4231  ldstr    aHtml// "Html"
0x4236  ldarg.3
0x4237  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x423c  ldarg.1
0x423d  ldstr    aHtml// "Html"
0x4242  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4247  ldarg.3
0x4248  ldstr    aHtml// "Html"
0x424d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4252  ldarg.1
0x4253  ldloc.0
0x4254  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Html()
0x4259  ldarg.3
0x425a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x425f  ldarg.3
0x4260  ldstr    aHtml// "Html"
0x4265  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x426a  ldarg.0
0x426b  ldstr    aListid// "ListId"
0x4270  ldarg.3
0x4271  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4276  ldarg.1
0x4277  ldstr    aListid// "ListId"
0x427c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4281  ldarg.3
0x4282  ldstr    aListid// "ListId"
0x4287  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x428c  ldarg.1
0x428d  ldloc.0
0x428e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ListId()
0x4293  ldarg.3
0x4294  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4299  ldarg.3
0x429a  ldstr    aListid// "ListId"
0x429f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x42a4  ldarg.0
0x42a5  ldstr    aPublishername// "PublisherName"
0x42aa  ldarg.3
0x42ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42b0  ldarg.1
0x42b1  ldstr    aPublishername// "PublisherName"
0x42b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x42bb  ldarg.3
0x42bc  ldstr    aPublishername// "PublisherName"
0x42c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x42c6  ldarg.1
0x42c7  ldloc.0
0x42c8  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_PublisherName()
0x42cd  ldarg.3
0x42ce  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42d3  ldarg.3
0x42d4  ldstr    aPublishername// "PublisherName"
0x42d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x42de  ldarg.0
0x42df  ldstr    aResponsecode// "ResponseCode"
0x42e4  ldarg.3
0x42e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42ea  ldarg.1
0x42eb  ldstr    aResponsecode// "ResponseCode"
0x42f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x42f5  ldarg.3
0x42f6  ldstr    aResponsecode// "ResponseCode"
0x42fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4300  ldarg.1
0x4301  ldloc.0
0x4302  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ResponseCode()
0x4307  ldarg.3
0x4308  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x430d  ldarg.3
0x430e  ldstr    aResponsecode// "ResponseCode"
0x4313  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4318  ldarg.0
0x4319  ldstr    aSiteid// "SiteId"
0x431e  ldarg.3
0x431f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4324  ldarg.1
0x4325  ldstr    aSiteid// "SiteId"
0x432a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x432f  ldarg.3
0x4330  ldstr    aSiteid// "SiteId"
0x4335  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x433a  ldarg.1
0x433b  ldloc.0
0x433c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_SiteId()
0x4341  ldarg.3
0x4342  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4347  ldarg.3
0x4348  ldstr    aSiteid// "SiteId"
0x434d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4352  ldarg.0
0x4353  ldstr    aThumbnailurl// "ThumbnailUrl"
0x4358  ldarg.3
0x4359  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x435e  ldarg.1
0x435f  ldstr    aThumbnailurl// "ThumbnailUrl"
0x4364  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4369  ldarg.3
0x436a  ldstr    aThumbnailurl// "ThumbnailUrl"
0x436f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4374  ldarg.1
0x4375  ldloc.0
0x4376  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ThumbnailUrl()
0x437b  ldarg.3
0x437c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4381  ldarg.3
0x4382  ldstr    aThumbnailurl// "ThumbnailUrl"
0x4387  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x438c  ldarg.0
0x438d  ldstr    aTitle// "Title"
0x4392  ldarg.3
0x4393  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4398  ldarg.1
0x4399  ldstr    aTitle// "Title"
0x439e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43a3  ldarg.3
0x43a4  ldstr    aTitle// "Title"
0x43a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43ae  ldarg.1
0x43af  ldloc.0
0x43b0  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Title()
0x43b5  ldarg.3
0x43b6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43bb  ldarg.3
0x43bc  ldstr    aTitle// "Title"
0x43c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x43c6  ldarg.0
0x43c7  ldstr    aType// "Type"
0x43cc  ldarg.3
0x43cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43d2  ldarg.1
0x43d3  ldstr    aType// "Type"
0x43d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x43dd  ldarg.3
0x43de  ldstr    aType// "Type"
0x43e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x43e8  ldarg.1
0x43e9  ldloc.0
0x43ea  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Type()
0x43ef  ldarg.3
0x43f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43f5  ldarg.3
0x43f6  ldstr    aType// "Type"
0x43fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4400  ldarg.0
0x4401  ldstr    aUniqueid// "UniqueId"
0x4406  ldarg.3
0x4407  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x440c  ldarg.1
0x440d  ldstr    aUniqueid// "UniqueId"
0x4412  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4417  ldarg.3
0x4418  ldstr    aUniqueid// "UniqueId"
0x441d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4422  ldarg.1
0x4423  ldloc.0
0x4424  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_UniqueId()
0x4429  ldarg.3
0x442a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x442f  ldarg.3
0x4430  ldstr    aUniqueid// "UniqueId"
0x4435  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x443a  ldarg.0
0x443b  ldstr    aUrl// "Url"
0x4440  ldarg.3
0x4441  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4446  ldarg.1
0x4447  ldstr    aUrl// "Url"
0x444c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4451  ldarg.3
0x4452  ldstr    aUrl// "Url"
0x4457  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x445c  ldarg.1
0x445d  ldloc.0
0x445e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Url()
0x4463  ldarg.3
0x4464  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4469  ldarg.3
0x446a  ldstr    aUrl// "Url"
0x446f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4474  ldarg.0
  ... truncated ...
```
