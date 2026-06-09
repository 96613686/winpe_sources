# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::.cctor

- ea: `0x4920`
- end: `0x49e2`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::.cctor`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x494a`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x4920  ldc.i4.s 0x12
0x4922  newarr   [mscorlib]System.String
0x4927  stloc.0
0x4928  ldloc.0
0x4929  ldc.i4.0
0x492a  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x492f  stelem.ref
0x4930  ldloc.0
0x4931  ldc.i4.1
0x4932  ldstr    aCreatorname// "CreatorName"
0x4937  stelem.ref
0x4938  ldloc.0
0x4939  ldc.i4.2
0x493a  ldstr    aDatepublisheda// "DatePublishedAt"
0x493f  stelem.ref
0x4940  ldloc.0
0x4941  ldc.i4.3
0x4942  ldstr    aDescription// "Description"
0x4947  stelem.ref
0x4948  ldloc.0
0x4949  ldc.i4.4
0x494a  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x494f  stelem.ref
0x4950  ldloc.0
0x4951  ldc.i4.5
0x4952  ldstr    aErrormessage// "ErrorMessage"
0x4957  stelem.ref
0x4958  ldloc.0
0x4959  ldc.i4.6
0x495a  ldstr    aHtml// "Html"
0x495f  stelem.ref
0x4960  ldloc.0
0x4961  ldc.i4.7
0x4962  ldstr    aListid// "ListId"
0x4967  stelem.ref
0x4968  ldloc.0
0x4969  ldc.i4.8
0x496a  ldstr    aPublishername// "PublisherName"
0x496f  stelem.ref
0x4970  ldloc.0
0x4971  ldc.i4.s 9
0x4973  ldstr    aResponsecode// "ResponseCode"
0x4978  stelem.ref
0x4979  ldloc.0
0x497a  ldc.i4.s 0xA
0x497c  ldstr    aSiteid// "SiteId"
0x4981  stelem.ref
0x4982  ldloc.0
0x4983  ldc.i4.s 0xB
0x4985  ldstr    aThumbnailurl// "ThumbnailUrl"
0x498a  stelem.ref
0x498b  ldloc.0
0x498c  ldc.i4.s 0xC
0x498e  ldstr    aTitle// "Title"
0x4993  stelem.ref
0x4994  ldloc.0
0x4995  ldc.i4.s 0xD
0x4997  ldstr    aType// "Type"
0x499c  stelem.ref
0x499d  ldloc.0
0x499e  ldc.i4.s 0xE
0x49a0  ldstr    aUniqueid// "UniqueId"
0x49a5  stelem.ref
0x49a6  ldloc.0
0x49a7  ldc.i4.s 0xF
0x49a9  ldstr    aUrl// "Url"
0x49ae  stelem.ref
0x49af  ldloc.0
0x49b0  ldc.i4.s 0x10
0x49b2  ldstr    aVideoid// "VideoId"
0x49b7  stelem.ref
0x49b8  ldloc.0
0x49b9  ldc.i4.s 0x11
0x49bb  ldstr    aWebid// "WebId"
0x49c0  stelem.ref
0x49c1  ldloc.0
0x49c2  stsfld   string[] Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::s_valueProperties
0x49c7  ldc.i4.0
0x49c8  newarr   [mscorlib]System.String
0x49cd  stsfld   string[] Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::s_refProperties
0x49d2  ldstr    a67742ff385034e// "{67742ff3-8503-4ee9-9364-54673d9d73b4}"
0x49d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x49dc  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::s_targetTypeId
0x49e1  ret
```
