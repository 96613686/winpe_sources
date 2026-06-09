# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::SkipSiteBasedOnWebTemplate

- ea: `0xff00`
- end: `0x1002d`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::SkipSiteBasedOnWebTemplate`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfdf0`

## callees

- `0xff00`
- `0x725f0`

## string_xrefs

- `0xff0c`: `ContentTypeSyndication:SkipSiteBasedOnWebTemplate started for {0}`
- `0xff83`: `ContentTypeSyndication:SkipSiteBasedOnWebTemplate looking for web template match: {0} in [{1}]`
- `0xffd9`: `Skipped content type syndication on site {0} because its web template is {1}`
- `0x1000d`: `ContentTypeSyndication:SkipSiteBasedOnWebTemplate ended for {0}`

## pseudocode

```c

```

## disassembly

```asm
0xff00  ldc.i4   0x889382
0xff05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xff0a  ldc.i4.s 0x32
0xff0c  ldstr    aContenttypesyn_2// "ContentTypeSyndication:SkipSiteBasedOnW"...
0xff11  ldc.i4.1
0xff12  newarr   [mscorlib]System.Object
0xff17  stloc.s  4
0xff19  ldloc.s  4
0xff1b  ldc.i4.0
0xff1c  ldarg.0
0xff1d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0xff22  stelem.ref
0xff23  ldloc.s  4
0xff25  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xff2a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xff2f  stloc.0
0xff30  ldc.i4.0
0xff31  stloc.1
0xff32  ldloc.0
0xff33  ldstr    aPointpublishin// "POINTPUBLISHING"
0xff38  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xff3d  ldc.i4   0xA9C
0xff42  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xff47  brfalse.s loc_FF54
0xff49  ldloc.0
0xff4a  ldstr    aSpspers// "SPSPERS"
0xff4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xff54  ldloc.0
0xff55  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0xff5a  ldc.i4.0
0xff5b  ble      loc_10001
0xff60  newobj   instance void <>c__DisplayClass1::.ctor()
0xff65  stloc.3
0xff66  ldloc.3
0xff67  ldarg.0
0xff68  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0xff6d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_WebTemplate()
0xff72  stfld    string <>c__DisplayClass1::webTemplate
0xff77  ldc.i4   0x889383
0xff7c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xff81  ldc.i4.s 0x32
0xff83  ldstr    aContenttypesyn_3// "ContentTypeSyndication:SkipSiteBasedOnW"...
0xff88  ldc.i4.2
0xff89  newarr   [mscorlib]System.Object
0xff8e  stloc.s  5
0xff90  ldloc.s  5
0xff92  ldc.i4.0
0xff93  ldloc.3
0xff94  ldfld    string <>c__DisplayClass1::webTemplate
0xff99  stelem.ref
0xff9a  ldloc.s  5
0xff9c  ldc.i4.1
0xff9d  ldstr    asc_7EF00// ","
0xffa2  ldloc.0
0xffa3  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xffa8  stelem.ref
0xffa9  ldloc.s  5
0xffab  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xffb0  ldloc.0
0xffb1  ldloc.3
0xffb2  ldftn    instance bool <>c__DisplayClass1::<SkipSiteBasedOnWebTemplate>b__0(string template)
0xffb8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xffbd  call     T0x2B000012
0xffc2  stloc.2
0xffc3  ldloc.2
0xffc4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xffc9  brtrue.s loc_10001
0xffcb  ldc.i4.1
0xffcc  stloc.1
0xffcd  ldc.i4   0x880223
0xffd2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xffd7  ldc.i4.s 0x32
0xffd9  ldstr    aSkippedContent// "Skipped content type syndication on sit"...
0xffde  ldc.i4.2
0xffdf  newarr   [mscorlib]System.Object
0xffe4  stloc.s  6
0xffe6  ldloc.s  6
0xffe8  ldc.i4.0
0xffe9  ldarg.0
0xffea  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0xffef  stelem.ref
0xfff0  ldloc.s  6
0xfff2  ldc.i4.1
0xfff3  ldloc.3
0xfff4  ldfld    string <>c__DisplayClass1::webTemplate
0xfff9  stelem.ref
0xfffa  ldloc.s  6
0xfffc  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x10001  ldc.i4   0x889384
0x10006  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1000b  ldc.i4.s 0x32
0x1000d  ldstr    aContenttypesyn_4// "ContentTypeSyndication:SkipSiteBasedOnW"...
0x10012  ldc.i4.1
0x10013  newarr   [mscorlib]System.Object
0x10018  stloc.s  7
0x1001a  ldloc.s  7
0x1001c  ldc.i4.0
0x1001d  ldarg.0
0x1001e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x10023  stelem.ref
0x10024  ldloc.s  7
0x10026  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1002b  ldloc.1
0x1002c  ret
```
