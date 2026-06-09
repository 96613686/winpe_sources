# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ScheduleDocscetUpdate

- ea: `0x11fb0`
- end: `0x12036`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ScheduleDocscetUpdate`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11ea0`

## callees

- `0xf5b0`
- `0x11fb0`

## string_xrefs

- `0x11fc4`: `UpdateSyndicatedCt`
- `0x1200f`: `Document Set Template Update on Syndicated Site Scheduled`

## pseudocode

```c

```

## disassembly

```asm
0x11fb0  ldarg.2
0x11fb1  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo::get_DocSetTemplateType()
0x11fb6  ldnull
0x11fb7  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11fbc  brfalse.s loc_12019
0x11fbe  ldarg.2
0x11fbf  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo::get_DocSetTemplateType()
0x11fc4  ldstr    aUpdatesyndicat// "UpdateSyndicatedCt"
0x11fc9  ldc.i4   0x168
0x11fce  ldnull
0x11fcf  ldnull
0x11fd0  ldc.i4.3
0x11fd1  newarr   [mscorlib]System.Object
0x11fd6  stloc.1
0x11fd7  ldloc.1
0x11fd8  ldc.i4.0
0x11fd9  ldarg.0
0x11fda  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::targetSite
0x11fdf  stelem.ref
0x11fe0  ldloc.1
0x11fe1  ldc.i4.1
0x11fe2  ldarg.1
0x11fe3  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x11fe8  stelem.ref
0x11fe9  ldloc.1
0x11fea  ldc.i4.2
0x11feb  ldarg.0
0x11fec  ldfld    bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::pushdown
0x11ff1  box      [mscorlib]System.Boolean
0x11ff6  stelem.ref
0x11ff7  ldloc.1
0x11ff8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11ffd  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[], class [mscorlib]System.Globalization.CultureInfo)
0x12002  pop
0x12003  ldc.i4   0x67317A69
0x12008  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_DLC_DocumentSets()
0x1200d  ldc.i4.s 0x32
0x1200f  ldstr    aDocumentSetTem// "Document Set Template Update on Syndica"...
0x12014  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x12019  leave.s  loc_12035
0x1201b  stloc.0
0x1201c  ldc.i4   0x6D666E36
0x12021  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_DLC_DocumentSets()
0x12026  ldc.i4.s 0xA
0x12028  ldloc.0
0x12029  callvirt instance string [mscorlib]System.Object::ToString()
0x1202e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x12033  leave.s  loc_12035
0x12035  ret
```
