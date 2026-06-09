# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::CheckSite

- ea: `0xfdf0`
- end: `0xfefa`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::CheckSite`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10300`
- `0x106b0`

## callees

- `0xfdf0`
- `0xff00`

## string_xrefs

- `0xfe0d`: `Subscriber timer job skipped the readonly site {0}`
- `0xfe37`: `Failed to access site {0}. {1}`
- `0xfed7`: `Skipped calling ContentTypeSyndication:SkipSiteBasedOnWebTemplate for {0}`

## pseudocode

```c

```

## disassembly

```asm
0xfdf0  ldc.i4.0
0xfdf1  stloc.0
0xfdf2  ldarg.0
0xfdf3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0xfdf8  stloc.1
0xfdf9  ldarg.0
0xfdfa  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ReadOnly()
0xfdff  brfalse.s loc_FE28
0xfe01  ldc.i4   0x6539627A
0xfe06  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xfe0b  ldc.i4.s 0x64
0xfe0d  ldstr    aSubscriberTime// "Subscriber timer job skipped the readon"...
0xfe12  ldc.i4.1
0xfe13  newarr   [mscorlib]System.Object
0xfe18  stloc.s  4
0xfe1a  ldloc.s  4
0xfe1c  ldc.i4.0
0xfe1d  ldloc.1
0xfe1e  stelem.ref
0xfe1f  ldloc.s  4
0xfe21  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xfe26  ldc.i4.1
0xfe27  stloc.0
0xfe28  leave.s  loc_FE5E
0xfe2a  stloc.2
0xfe2b  ldc.i4   0x666D6938
0xfe30  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xfe35  ldc.i4.s 0x32
0xfe37  ldstr    aFailedToAccess// "Failed to access site {0}. {1}"
0xfe3c  ldc.i4.2
0xfe3d  newarr   [mscorlib]System.Object
0xfe42  stloc.s  5
0xfe44  ldloc.s  5
0xfe46  ldc.i4.0
0xfe47  ldloc.1
0xfe48  stelem.ref
0xfe49  ldloc.s  5
0xfe4b  ldc.i4.1
0xfe4c  ldloc.2
0xfe4d  callvirt instance string [mscorlib]System.Object::ToString()
0xfe52  stelem.ref
0xfe53  ldloc.s  5
0xfe55  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xfe5a  ldc.i4.1
0xfe5b  stloc.0
0xfe5c  leave.s  loc_FE5E
0xfe5e  ldloc.0
0xfe5f  brtrue.s loc_FEBF
0xfe61  ldc.i4   0x65396330
0xfe66  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xfe6b  ldc.i4.s 0x64
0xfe6d  ldstr    aContenttypesyn_1// "ContentTypeSynchronize starts for site "...
0xfe72  ldc.i4.1
0xfe73  newarr   [mscorlib]System.Object
0xfe78  stloc.s  6
0xfe7a  ldloc.s  6
0xfe7c  ldc.i4.0
0xfe7d  ldloc.1
0xfe7e  stelem.ref
0xfe7f  ldloc.s  6
0xfe81  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xfe86  ldarg.0
0xfe87  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Features()
0xfe8c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.FeatureIds::Taxonomy
0xfe91  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::get_Item(valuetype [mscorlib]System.Guid)
0xfe96  brtrue.s loc_FEBF
0xfe98  ldc.i4.1
0xfe99  stloc.0
0xfe9a  ldc.i4   0x65396331
0xfe9f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xfea4  ldc.i4.s 0x64
0xfea6  ldstr    aSkipSite0Becau// "Skip site {0} because it does not have "...
0xfeab  ldc.i4.1
0xfeac  newarr   [mscorlib]System.Object
0xfeb1  stloc.s  7
0xfeb3  ldloc.s  7
0xfeb5  ldc.i4.0
0xfeb6  ldloc.1
0xfeb7  stelem.ref
0xfeb8  ldloc.s  7
0xfeba  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xfebf  ldloc.0
0xfec0  brtrue.s loc_FECB
0xfec2  ldarg.0
0xfec3  call     bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::SkipSiteBasedOnWebTemplate(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0xfec8  stloc.0
0xfec9  br.s     loc_FEF0
0xfecb  ldc.i4   0x889381
0xfed0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xfed5  ldc.i4.s 0x32
0xfed7  ldstr    aSkippedCalling// "Skipped calling ContentTypeSyndication:"...
0xfedc  ldc.i4.1
0xfedd  newarr   [mscorlib]System.Object
0xfee2  stloc.s  8
0xfee4  ldloc.s  8
0xfee6  ldc.i4.0
0xfee7  ldloc.1
0xfee8  stelem.ref
0xfee9  ldloc.s  8
0xfeeb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xfef0  ldloc.0
0xfef1  brtrue.s loc_FEF6
0xfef3  ldc.i4.1
0xfef4  br.s     loc_FEF7
0xfef6  ldc.i4.2
0xfef7  stloc.3
0xfef8  ldloc.3
0xfef9  ret
```
