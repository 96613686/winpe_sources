# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::SetProperty_0

- ea: `0x4550`
- end: `0x48d7`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::SetProperty_0`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4550`

## string_xrefs

- `0x45d9`: `EmbedServiceResponseCode`
- `0x4760`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x4550  ldarg.s  4
0x4552  brtrue.s loc_455F
0x4554  ldstr    aProxycontext// "proxyContext"
0x4559  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x455e  throw
0x455f  ldarg.1
0x4560  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x4565  stloc.0
0x4566  ldloc.0
0x4567  brtrue.s loc_4574
0x4569  ldstr    aTarget// "target"
0x456e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4573  throw
0x4574  ldarg.2
0x4575  brtrue.s loc_4582
0x4577  ldstr    aPropname// "propName"
0x457c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4581  throw
0x4582  ldarg.0
0x4583  ldarg.2
0x4584  ldarg.s  4
0x4586  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x458b  starg.s  2
0x458d  ldarg.2
0x458e  dup
0x458f  stloc.1
0x4590  brfalse  loc_48CB
0x4595  volatile.
0x4597  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600009c-1
0x459c  brtrue   loc_4690
0x45a1  ldc.i4.s 0x12
0x45a3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x45a8  dup
0x45a9  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x45ae  ldc.i4.0
0x45af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45b4  dup
0x45b5  ldstr    aCreatorname// "CreatorName"
0x45ba  ldc.i4.1
0x45bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45c0  dup
0x45c1  ldstr    aDatepublisheda// "DatePublishedAt"
0x45c6  ldc.i4.2
0x45c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45cc  dup
0x45cd  ldstr    aDescription// "Description"
0x45d2  ldc.i4.3
0x45d3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45d8  dup
0x45d9  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x45de  ldc.i4.4
0x45df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45e4  dup
0x45e5  ldstr    aErrormessage// "ErrorMessage"
0x45ea  ldc.i4.5
0x45eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45f0  dup
0x45f1  ldstr    aHtml// "Html"
0x45f6  ldc.i4.6
0x45f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x45fc  dup
0x45fd  ldstr    aListid// "ListId"
0x4602  ldc.i4.7
0x4603  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4608  dup
0x4609  ldstr    aPublishername// "PublisherName"
0x460e  ldc.i4.8
0x460f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4614  dup
0x4615  ldstr    aResponsecode// "ResponseCode"
0x461a  ldc.i4.s 9
0x461c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4621  dup
0x4622  ldstr    aSiteid// "SiteId"
0x4627  ldc.i4.s 0xA
0x4629  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x462e  dup
0x462f  ldstr    aThumbnailurl// "ThumbnailUrl"
0x4634  ldc.i4.s 0xB
0x4636  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x463b  dup
0x463c  ldstr    aTitle// "Title"
0x4641  ldc.i4.s 0xC
0x4643  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4648  dup
0x4649  ldstr    aType// "Type"
0x464e  ldc.i4.s 0xD
0x4650  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4655  dup
0x4656  ldstr    aUniqueid// "UniqueId"
0x465b  ldc.i4.s 0xE
0x465d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4662  dup
0x4663  ldstr    aUrl// "Url"
0x4668  ldc.i4.s 0xF
0x466a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x466f  dup
0x4670  ldstr    aVideoid// "VideoId"
0x4675  ldc.i4.s 0x10
0x4677  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x467c  dup
0x467d  ldstr    aWebid// "WebId"
0x4682  ldc.i4.s 0x11
0x4684  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4689  volatile.
0x468b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600009c-1
0x4690  volatile.
0x4692  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600009c-1
0x4697  ldloc.1
0x4698  ldloca.s 2
0x469a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x469f  brfalse  loc_48CB
0x46a4  ldloc.2
0x46a5  switch   loc_46F7, loc_4711, loc_472B, loc_4745, loc_475F, loc_4779, loc_4793, loc_47AD, loc_47C7, loc_47E1, loc_47FB, loc_4815, loc_482F, loc_4849, loc_4863, loc_487D, loc_4897, loc_48B1
0x46f2  br       loc_48CB
0x46f7  ldarg.0
0x46f8  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x46fd  ldarg.s  4
0x46ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4704  ldloc.0
0x4705  ldarg.3
0x4706  callvirt T0x2B000007
0x470b  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_AllowHttpsEmbed(bool)
0x4710  ret
0x4711  ldarg.0
0x4712  ldstr    aCreatorname// "CreatorName"
0x4717  ldarg.s  4
0x4719  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x471e  ldloc.0
0x471f  ldarg.3
0x4720  callvirt T0x2B000001
0x4725  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_CreatorName(string)
0x472a  ret
0x472b  ldarg.0
0x472c  ldstr    aDatepublisheda// "DatePublishedAt"
0x4731  ldarg.s  4
0x4733  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4738  ldloc.0
0x4739  ldarg.3
0x473a  callvirt T0x2B000001
0x473f  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_DatePublishedAt(string)
0x4744  ret
0x4745  ldarg.0
0x4746  ldstr    aDescription// "Description"
0x474b  ldarg.s  4
0x474d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4752  ldloc.0
0x4753  ldarg.3
0x4754  callvirt T0x2B000001
0x4759  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Description(string)
0x475e  ret
0x475f  ldarg.0
0x4760  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x4765  ldarg.s  4
0x4767  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x476c  ldloc.0
0x476d  ldarg.3
0x476e  callvirt T0x2B000002
0x4773  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_EmbedServiceResponseCode(int32)
0x4778  ret
0x4779  ldarg.0
0x477a  ldstr    aErrormessage// "ErrorMessage"
0x477f  ldarg.s  4
0x4781  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4786  ldloc.0
0x4787  ldarg.3
0x4788  callvirt T0x2B000001
0x478d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ErrorMessage(string)
0x4792  ret
0x4793  ldarg.0
0x4794  ldstr    aHtml// "Html"
0x4799  ldarg.s  4
0x479b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47a0  ldloc.0
0x47a1  ldarg.3
0x47a2  callvirt T0x2B000001
0x47a7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Html(string)
0x47ac  ret
0x47ad  ldarg.0
0x47ae  ldstr    aListid// "ListId"
0x47b3  ldarg.s  4
0x47b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47ba  ldloc.0
0x47bb  ldarg.3
0x47bc  callvirt T0x2B000001
0x47c1  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ListId(string)
0x47c6  ret
0x47c7  ldarg.0
0x47c8  ldstr    aPublishername// "PublisherName"
0x47cd  ldarg.s  4
0x47cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47d4  ldloc.0
0x47d5  ldarg.3
0x47d6  callvirt T0x2B000001
0x47db  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_PublisherName(string)
0x47e0  ret
0x47e1  ldarg.0
0x47e2  ldstr    aResponsecode// "ResponseCode"
0x47e7  ldarg.s  4
0x47e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47ee  ldloc.0
0x47ef  ldarg.3
0x47f0  callvirt T0x2B000002
0x47f5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ResponseCode(int32)
0x47fa  ret
0x47fb  ldarg.0
0x47fc  ldstr    aSiteid// "SiteId"
0x4801  ldarg.s  4
0x4803  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4808  ldloc.0
0x4809  ldarg.3
0x480a  callvirt T0x2B000001
0x480f  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_SiteId(string)
0x4814  ret
0x4815  ldarg.0
0x4816  ldstr    aThumbnailurl// "ThumbnailUrl"
0x481b  ldarg.s  4
0x481d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4822  ldloc.0
0x4823  ldarg.3
0x4824  callvirt T0x2B000001
0x4829  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_ThumbnailUrl(string)
0x482e  ret
0x482f  ldarg.0
0x4830  ldstr    aTitle// "Title"
0x4835  ldarg.s  4
0x4837  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x483c  ldloc.0
0x483d  ldarg.3
0x483e  callvirt T0x2B000001
0x4843  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Title(string)
0x4848  ret
0x4849  ldarg.0
0x484a  ldstr    aType// "Type"
0x484f  ldarg.s  4
0x4851  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4856  ldloc.0
0x4857  ldarg.3
0x4858  callvirt T0x2B000001
0x485d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Type(string)
0x4862  ret
0x4863  ldarg.0
0x4864  ldstr    aUniqueid// "UniqueId"
0x4869  ldarg.s  4
0x486b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4870  ldloc.0
0x4871  ldarg.3
0x4872  callvirt T0x2B000001
0x4877  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_UniqueId(string)
0x487c  ret
0x487d  ldarg.0
0x487e  ldstr    aUrl// "Url"
0x4883  ldarg.s  4
0x4885  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x488a  ldloc.0
0x488b  ldarg.3
0x488c  callvirt T0x2B000001
0x4891  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_Url(string)
0x4896  ret
0x4897  ldarg.0
0x4898  ldstr    aVideoid// "VideoId"
0x489d  ldarg.s  4
0x489f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48a4  ldloc.0
0x48a5  ldarg.3
0x48a6  callvirt T0x2B000001
0x48ab  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_VideoId(string)
0x48b0  ret
0x48b1  ldarg.0
0x48b2  ldstr    aWebid// "WebId"
0x48b7  ldarg.s  4
0x48b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48be  ldloc.0
0x48bf  ldarg.3
0x48c0  callvirt T0x2B000001
0x48c5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::set_WebId(string)
0x48ca  ret
0x48cb  ldarg.0
0x48cc  ldarg.1
0x48cd  ldarg.2
0x48ce  ldarg.3
0x48cf  ldarg.s  4
0x48d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48d6  ret
```
