# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::GetProperty

- ea: `0x32f0`
- end: `0x3604`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::GetProperty`
- size: `788`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x32f0`

## string_xrefs

- `0x3377`: `EmbedServiceResponseCode`
- `0x34e7`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x32f0  ldarg.2
0x32f1  brtrue.s loc_32FE
0x32f3  ldstr    aPropname// "propName"
0x32f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32fd  throw
0x32fe  ldarg.3
0x32ff  brtrue.s loc_330C
0x3301  ldstr    aProxycontext// "proxyContext"
0x3306  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x330b  throw
0x330c  ldarg.1
0x330d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x3312  stloc.0
0x3313  ldloc.0
0x3314  brtrue.s loc_3321
0x3316  ldstr    aTarget// "target"
0x331b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3320  throw
0x3321  ldarg.0
0x3322  ldarg.2
0x3323  ldarg.3
0x3324  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3329  starg.s  2
0x332b  ldarg.2
0x332c  dup
0x332d  stloc.1
0x332e  brfalse  loc_35FA
0x3333  volatile.
0x3335  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000094-1
0x333a  brtrue   loc_342E
0x333f  ldc.i4.s 0x12
0x3341  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3346  dup
0x3347  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x334c  ldc.i4.0
0x334d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3352  dup
0x3353  ldstr    aCreatorname// "CreatorName"
0x3358  ldc.i4.1
0x3359  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x335e  dup
0x335f  ldstr    aDatepublisheda// "DatePublishedAt"
0x3364  ldc.i4.2
0x3365  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x336a  dup
0x336b  ldstr    aDescription// "Description"
0x3370  ldc.i4.3
0x3371  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3376  dup
0x3377  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x337c  ldc.i4.4
0x337d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3382  dup
0x3383  ldstr    aErrormessage// "ErrorMessage"
0x3388  ldc.i4.5
0x3389  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x338e  dup
0x338f  ldstr    aHtml// "Html"
0x3394  ldc.i4.6
0x3395  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x339a  dup
0x339b  ldstr    aListid// "ListId"
0x33a0  ldc.i4.7
0x33a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33a6  dup
0x33a7  ldstr    aPublishername// "PublisherName"
0x33ac  ldc.i4.8
0x33ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33b2  dup
0x33b3  ldstr    aResponsecode// "ResponseCode"
0x33b8  ldc.i4.s 9
0x33ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33bf  dup
0x33c0  ldstr    aSiteid// "SiteId"
0x33c5  ldc.i4.s 0xA
0x33c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33cc  dup
0x33cd  ldstr    aThumbnailurl// "ThumbnailUrl"
0x33d2  ldc.i4.s 0xB
0x33d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33d9  dup
0x33da  ldstr    aTitle// "Title"
0x33df  ldc.i4.s 0xC
0x33e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33e6  dup
0x33e7  ldstr    aType// "Type"
0x33ec  ldc.i4.s 0xD
0x33ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x33f3  dup
0x33f4  ldstr    aUniqueid// "UniqueId"
0x33f9  ldc.i4.s 0xE
0x33fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3400  dup
0x3401  ldstr    aUrl// "Url"
0x3406  ldc.i4.s 0xF
0x3408  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x340d  dup
0x340e  ldstr    aVideoid// "VideoId"
0x3413  ldc.i4.s 0x10
0x3415  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x341a  dup
0x341b  ldstr    aWebid// "WebId"
0x3420  ldc.i4.s 0x11
0x3422  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3427  volatile.
0x3429  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000094-1
0x342e  volatile.
0x3430  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000094-1
0x3435  ldloc.1
0x3436  ldloca.s 2
0x3438  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x343d  brfalse  loc_35FA
0x3442  ldloc.2
0x3443  switch   loc_3495, loc_34AD, loc_34C0, loc_34D3, loc_34E6, loc_34FE, loc_3511, loc_3524, loc_3537, loc_354A, loc_3562, loc_3575, loc_3588, loc_359B, loc_35AE, loc_35C1, loc_35D4, loc_35E7
0x3490  br       loc_35FA
0x3495  ldarg.0
0x3496  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x349b  ldarg.3
0x349c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x34a1  ldloc.0
0x34a2  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_AllowHttpsEmbed()
0x34a7  box      [mscorlib]System.Boolean
0x34ac  ret
0x34ad  ldarg.0
0x34ae  ldstr    aCreatorname// "CreatorName"
0x34b3  ldarg.3
0x34b4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x34b9  ldloc.0
0x34ba  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_CreatorName()
0x34bf  ret
0x34c0  ldarg.0
0x34c1  ldstr    aDatepublisheda// "DatePublishedAt"
0x34c6  ldarg.3
0x34c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x34cc  ldloc.0
0x34cd  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_DatePublishedAt()
0x34d2  ret
0x34d3  ldarg.0
0x34d4  ldstr    aDescription// "Description"
0x34d9  ldarg.3
0x34da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x34df  ldloc.0
0x34e0  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Description()
0x34e5  ret
0x34e6  ldarg.0
0x34e7  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x34ec  ldarg.3
0x34ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x34f2  ldloc.0
0x34f3  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_EmbedServiceResponseCode()
0x34f8  box      [mscorlib]System.Int32
0x34fd  ret
0x34fe  ldarg.0
0x34ff  ldstr    aErrormessage// "ErrorMessage"
0x3504  ldarg.3
0x3505  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x350a  ldloc.0
0x350b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ErrorMessage()
0x3510  ret
0x3511  ldarg.0
0x3512  ldstr    aHtml// "Html"
0x3517  ldarg.3
0x3518  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x351d  ldloc.0
0x351e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Html()
0x3523  ret
0x3524  ldarg.0
0x3525  ldstr    aListid// "ListId"
0x352a  ldarg.3
0x352b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3530  ldloc.0
0x3531  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ListId()
0x3536  ret
0x3537  ldarg.0
0x3538  ldstr    aPublishername// "PublisherName"
0x353d  ldarg.3
0x353e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3543  ldloc.0
0x3544  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_PublisherName()
0x3549  ret
0x354a  ldarg.0
0x354b  ldstr    aResponsecode// "ResponseCode"
0x3550  ldarg.3
0x3551  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3556  ldloc.0
0x3557  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ResponseCode()
0x355c  box      [mscorlib]System.Int32
0x3561  ret
0x3562  ldarg.0
0x3563  ldstr    aSiteid// "SiteId"
0x3568  ldarg.3
0x3569  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x356e  ldloc.0
0x356f  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_SiteId()
0x3574  ret
0x3575  ldarg.0
0x3576  ldstr    aThumbnailurl// "ThumbnailUrl"
0x357b  ldarg.3
0x357c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3581  ldloc.0
0x3582  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ThumbnailUrl()
0x3587  ret
0x3588  ldarg.0
0x3589  ldstr    aTitle// "Title"
0x358e  ldarg.3
0x358f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3594  ldloc.0
0x3595  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Title()
0x359a  ret
0x359b  ldarg.0
0x359c  ldstr    aType// "Type"
0x35a1  ldarg.3
0x35a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35a7  ldloc.0
0x35a8  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Type()
0x35ad  ret
0x35ae  ldarg.0
0x35af  ldstr    aUniqueid// "UniqueId"
0x35b4  ldarg.3
0x35b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35ba  ldloc.0
0x35bb  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_UniqueId()
0x35c0  ret
0x35c1  ldarg.0
0x35c2  ldstr    aUrl// "Url"
0x35c7  ldarg.3
0x35c8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35cd  ldloc.0
0x35ce  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Url()
0x35d3  ret
0x35d4  ldarg.0
0x35d5  ldstr    aVideoid// "VideoId"
0x35da  ldarg.3
0x35db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35e0  ldloc.0
0x35e1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_VideoId()
0x35e6  ret
0x35e7  ldarg.0
0x35e8  ldstr    aWebid// "WebId"
0x35ed  ldarg.3
0x35ee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35f3  ldloc.0
0x35f4  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_WebId()
0x35f9  ret
0x35fa  ldarg.0
0x35fb  ldarg.1
0x35fc  ldarg.2
0x35fd  ldarg.3
0x35fe  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3603  ret
```
