# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::SetProperty

- ea: `0x3610`
- end: `0x39bb`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::SetProperty`
- size: `939`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3610`

## string_xrefs

- `0x3699`: `EmbedServiceResponseCode`
- `0x3828`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x3610  ldarg.s  4
0x3612  brtrue.s loc_361F
0x3614  ldstr    aProxycontext// "proxyContext"
0x3619  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x361e  throw
0x361f  ldarg.1
0x3620  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x3625  stloc.0
0x3626  ldloc.0
0x3627  brtrue.s loc_3634
0x3629  ldstr    aTarget// "target"
0x362e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3633  throw
0x3634  ldarg.2
0x3635  brtrue.s loc_3642
0x3637  ldstr    aPropname// "propName"
0x363c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3641  throw
0x3642  ldarg.0
0x3643  ldarg.2
0x3644  ldarg.s  4
0x3646  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x364b  starg.s  2
0x364d  ldarg.2
0x364e  dup
0x364f  stloc.1
0x3650  brfalse  loc_39AF
0x3655  volatile.
0x3657  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000095-1
0x365c  brtrue   loc_3750
0x3661  ldc.i4.s 0x12
0x3663  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3668  dup
0x3669  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x366e  ldc.i4.0
0x366f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3674  dup
0x3675  ldstr    aCreatorname// "CreatorName"
0x367a  ldc.i4.1
0x367b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3680  dup
0x3681  ldstr    aDatepublisheda// "DatePublishedAt"
0x3686  ldc.i4.2
0x3687  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x368c  dup
0x368d  ldstr    aDescription// "Description"
0x3692  ldc.i4.3
0x3693  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3698  dup
0x3699  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x369e  ldc.i4.4
0x369f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36a4  dup
0x36a5  ldstr    aErrormessage// "ErrorMessage"
0x36aa  ldc.i4.5
0x36ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36b0  dup
0x36b1  ldstr    aHtml// "Html"
0x36b6  ldc.i4.6
0x36b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36bc  dup
0x36bd  ldstr    aListid// "ListId"
0x36c2  ldc.i4.7
0x36c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36c8  dup
0x36c9  ldstr    aPublishername// "PublisherName"
0x36ce  ldc.i4.8
0x36cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36d4  dup
0x36d5  ldstr    aResponsecode// "ResponseCode"
0x36da  ldc.i4.s 9
0x36dc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36e1  dup
0x36e2  ldstr    aSiteid// "SiteId"
0x36e7  ldc.i4.s 0xA
0x36e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36ee  dup
0x36ef  ldstr    aThumbnailurl// "ThumbnailUrl"
0x36f4  ldc.i4.s 0xB
0x36f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x36fb  dup
0x36fc  ldstr    aTitle// "Title"
0x3701  ldc.i4.s 0xC
0x3703  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3708  dup
0x3709  ldstr    aType// "Type"
0x370e  ldc.i4.s 0xD
0x3710  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3715  dup
0x3716  ldstr    aUniqueid// "UniqueId"
0x371b  ldc.i4.s 0xE
0x371d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3722  dup
0x3723  ldstr    aUrl// "Url"
0x3728  ldc.i4.s 0xF
0x372a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x372f  dup
0x3730  ldstr    aVideoid// "VideoId"
0x3735  ldc.i4.s 0x10
0x3737  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x373c  dup
0x373d  ldstr    aWebid// "WebId"
0x3742  ldc.i4.s 0x11
0x3744  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3749  volatile.
0x374b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000095-1
0x3750  volatile.
0x3752  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000095-1
0x3757  ldloc.1
0x3758  ldloca.s 2
0x375a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x375f  brfalse  loc_39AF
0x3764  ldloc.2
0x3765  switch   loc_37B7, loc_37D3, loc_37EF, loc_380B, loc_3827, loc_3843, loc_385F, loc_387B, loc_3897, loc_38B3, loc_38CF, loc_38EB, loc_3907, loc_3923, loc_393F, loc_395B, loc_3977, loc_3993
0x37b2  br       loc_39AF
0x37b7  ldarg.0
0x37b8  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x37bd  ldarg.s  4
0x37bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x37c4  ldloc.0
0x37c5  ldarg.3
0x37c6  ldarg.s  4
0x37c8  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x37cd  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_AllowHttpsEmbed(bool)
0x37d2  ret
0x37d3  ldarg.0
0x37d4  ldstr    aCreatorname// "CreatorName"
0x37d9  ldarg.s  4
0x37db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x37e0  ldloc.0
0x37e1  ldarg.3
0x37e2  ldarg.s  4
0x37e4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x37e9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_CreatorName(string)
0x37ee  ret
0x37ef  ldarg.0
0x37f0  ldstr    aDatepublisheda// "DatePublishedAt"
0x37f5  ldarg.s  4
0x37f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x37fc  ldloc.0
0x37fd  ldarg.3
0x37fe  ldarg.s  4
0x3800  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3805  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_DatePublishedAt(string)
0x380a  ret
0x380b  ldarg.0
0x380c  ldstr    aDescription// "Description"
0x3811  ldarg.s  4
0x3813  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3818  ldloc.0
0x3819  ldarg.3
0x381a  ldarg.s  4
0x381c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3821  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Description(string)
0x3826  ret
0x3827  ldarg.0
0x3828  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x382d  ldarg.s  4
0x382f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3834  ldloc.0
0x3835  ldarg.3
0x3836  ldarg.s  4
0x3838  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x383d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_EmbedServiceResponseCode(int32)
0x3842  ret
0x3843  ldarg.0
0x3844  ldstr    aErrormessage// "ErrorMessage"
0x3849  ldarg.s  4
0x384b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3850  ldloc.0
0x3851  ldarg.3
0x3852  ldarg.s  4
0x3854  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3859  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ErrorMessage(string)
0x385e  ret
0x385f  ldarg.0
0x3860  ldstr    aHtml// "Html"
0x3865  ldarg.s  4
0x3867  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x386c  ldloc.0
0x386d  ldarg.3
0x386e  ldarg.s  4
0x3870  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3875  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Html(string)
0x387a  ret
0x387b  ldarg.0
0x387c  ldstr    aListid// "ListId"
0x3881  ldarg.s  4
0x3883  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3888  ldloc.0
0x3889  ldarg.3
0x388a  ldarg.s  4
0x388c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3891  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ListId(string)
0x3896  ret
0x3897  ldarg.0
0x3898  ldstr    aPublishername// "PublisherName"
0x389d  ldarg.s  4
0x389f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38a4  ldloc.0
0x38a5  ldarg.3
0x38a6  ldarg.s  4
0x38a8  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38ad  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_PublisherName(string)
0x38b2  ret
0x38b3  ldarg.0
0x38b4  ldstr    aResponsecode// "ResponseCode"
0x38b9  ldarg.s  4
0x38bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38c0  ldloc.0
0x38c1  ldarg.3
0x38c2  ldarg.s  4
0x38c4  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38c9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ResponseCode(int32)
0x38ce  ret
0x38cf  ldarg.0
0x38d0  ldstr    aSiteid// "SiteId"
0x38d5  ldarg.s  4
0x38d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38dc  ldloc.0
0x38dd  ldarg.3
0x38de  ldarg.s  4
0x38e0  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38e5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_SiteId(string)
0x38ea  ret
0x38eb  ldarg.0
0x38ec  ldstr    aThumbnailurl// "ThumbnailUrl"
0x38f1  ldarg.s  4
0x38f3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38f8  ldloc.0
0x38f9  ldarg.3
0x38fa  ldarg.s  4
0x38fc  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3901  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ThumbnailUrl(string)
0x3906  ret
0x3907  ldarg.0
0x3908  ldstr    aTitle// "Title"
0x390d  ldarg.s  4
0x390f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3914  ldloc.0
0x3915  ldarg.3
0x3916  ldarg.s  4
0x3918  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x391d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Title(string)
0x3922  ret
0x3923  ldarg.0
0x3924  ldstr    aType// "Type"
0x3929  ldarg.s  4
0x392b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3930  ldloc.0
0x3931  ldarg.3
0x3932  ldarg.s  4
0x3934  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3939  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Type(string)
0x393e  ret
0x393f  ldarg.0
0x3940  ldstr    aUniqueid// "UniqueId"
0x3945  ldarg.s  4
0x3947  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x394c  ldloc.0
0x394d  ldarg.3
0x394e  ldarg.s  4
0x3950  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3955  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_UniqueId(string)
0x395a  ret
0x395b  ldarg.0
0x395c  ldstr    aUrl// "Url"
0x3961  ldarg.s  4
0x3963  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3968  ldloc.0
0x3969  ldarg.3
0x396a  ldarg.s  4
0x396c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3971  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Url(string)
0x3976  ret
0x3977  ldarg.0
0x3978  ldstr    aVideoid// "VideoId"
0x397d  ldarg.s  4
0x397f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3984  ldloc.0
0x3985  ldarg.3
0x3986  ldarg.s  4
0x3988  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x398d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_VideoId(string)
0x3992  ret
0x3993  ldarg.0
0x3994  ldstr    aWebid// "WebId"
0x3999  ldarg.s  4
0x399b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x39a0  ldloc.0
0x39a1  ldarg.3
0x39a2  ldarg.s  4
0x39a4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x39a9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_WebId(string)
0x39ae  ret
0x39af  ldarg.0
0x39b0  ldarg.1
0x39b1  ldarg.2
0x39b2  ldarg.3
0x39b3  ldarg.s  4
  ... truncated ...
```
