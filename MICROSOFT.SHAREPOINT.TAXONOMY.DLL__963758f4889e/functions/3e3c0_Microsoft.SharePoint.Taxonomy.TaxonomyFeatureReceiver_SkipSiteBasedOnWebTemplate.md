# Microsoft.SharePoint.Taxonomy.TaxonomyFeatureReceiver::SkipSiteBasedOnWebTemplate

- ea: `0x3e3c0`
- end: `0x3e4ce`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyFeatureReceiver::SkipSiteBasedOnWebTemplate`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3e190`

## callees

- `0x3e3c0`
- `0x73be0`

## string_xrefs

- `0x3e4a3`: `Skipped content type syndication on site {0} because its web template is {1}`
- `0x3e3fe`: `TaxonomyFeatureReceiver:SkipSiteBasedOnWebTemplate started for web {0} site {1}, template {2} configuration {3}`

## pseudocode

```c

```

## disassembly

```asm
0x3e3c0  newobj   instance void <>c__DisplayClass2::.ctor()
0x3e3c5  stloc.s  4
0x3e3c7  ldloc.s  4
0x3e3c9  ldarg.0
0x3e3ca  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_WebTemplate()
0x3e3cf  ldstr    asc_98FFC// "#"
0x3e3d4  ldarg.0
0x3e3d5  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Configuration()
0x3e3da  stloc.s  5
0x3e3dc  ldloca.s 5
0x3e3de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3e3e3  call     instance string [mscorlib]System.Int16::ToString(class [mscorlib]System.IFormatProvider)
0x3e3e8  call     string [mscorlib]System.String::Concat(string, string, string)
0x3e3ed  stfld    string <>c__DisplayClass2::webTemplateConfiguration
0x3e3f2  ldc.i4   0x1487488
0x3e3f7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3e3fc  ldc.i4.s 0x32
0x3e3fe  ldstr    aTaxonomyfeatur_2// "TaxonomyFeatureReceiver:SkipSiteBasedOn"...
0x3e403  ldc.i4.4
0x3e404  newarr   [mscorlib]System.Object
0x3e409  stloc.s  6
0x3e40b  ldloc.s  6
0x3e40d  ldc.i4.0
0x3e40e  ldarg.0
0x3e40f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x3e414  box      [mscorlib]System.Guid
0x3e419  stelem.ref
0x3e41a  ldloc.s  6
0x3e41c  ldc.i4.1
0x3e41d  ldarg.0
0x3e41e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0x3e423  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x3e428  box      [mscorlib]System.Guid
0x3e42d  stelem.ref
0x3e42e  ldloc.s  6
0x3e430  ldc.i4.2
0x3e431  ldarg.0
0x3e432  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_WebTemplate()
0x3e437  stelem.ref
0x3e438  ldloc.s  6
0x3e43a  ldc.i4.3
0x3e43b  ldarg.0
0x3e43c  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Configuration()
0x3e441  box      [mscorlib]System.Int16
0x3e446  stelem.ref
0x3e447  ldloc.s  6
0x3e449  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3e44e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3e453  stloc.3
0x3e454  ldloc.3
0x3e455  ldstr    aGroup_1// "GROUP"
0x3e45a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3e45f  ldloc.3
0x3e460  ldstr    aSitepagepublis// "SITEPAGEPUBLISHING"
0x3e465  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3e46a  ldloc.3
0x3e46b  ldstr    aSts3// "STS#3"
0x3e470  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3e475  ldloc.3
0x3e476  stloc.0
0x3e477  ldc.i4.0
0x3e478  stloc.1
0x3e479  ldloc.0
0x3e47a  ldloc.s  4
0x3e47c  ldftn    instance bool <>c__DisplayClass2::<SkipSiteBasedOnWebTemplate>b__1(string template)
0x3e482  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x3e487  call     T0x2B000012
0x3e48c  stloc.2
0x3e48d  ldloc.2
0x3e48e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3e493  brtrue.s loc_3E4CC
0x3e495  ldc.i4.1
0x3e496  stloc.1
0x3e497  ldc.i4   0x1487489
0x3e49c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3e4a1  ldc.i4.s 0x32
0x3e4a3  ldstr    aSkippedContent// "Skipped content type syndication on sit"...
0x3e4a8  ldc.i4.2
0x3e4a9  newarr   [mscorlib]System.Object
0x3e4ae  stloc.s  7
0x3e4b0  ldloc.s  7
0x3e4b2  ldc.i4.0
0x3e4b3  ldarg.0
0x3e4b4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x3e4b9  stelem.ref
0x3e4ba  ldloc.s  7
0x3e4bc  ldc.i4.1
0x3e4bd  ldloc.s  4
0x3e4bf  ldfld    string <>c__DisplayClass2::webTemplateConfiguration
0x3e4c4  stelem.ref
0x3e4c5  ldloc.s  7
0x3e4c7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3e4cc  ldloc.1
0x3e4cd  ret
```
