# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ImportWorkflowAssociations

- ea: `0x11650`
- end: `0x11894`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ImportWorkflowAssociations`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11ea0`

## callees

- `0xb4d0`
- `0xb4e0`
- `0xb560`
- `0x11650`
- `0x118a0`
- `0x12630`
- `0x12c80`
- `0x130c0`
- `0x72620`

## string_xrefs

- `0x117de`: `Start to UpdateWorkflowAssociationsOnChildren`
- `0x1182f`: `Finished UpdateWorkflowAssociationsOnChildren.`

## pseudocode

```c

```

## disassembly

```asm
0x11650  ldc.i4   0x63683633
0x11655  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1165a  ldc.i4.s 0x64
0x1165c  ldstr    aImportingWorkf// "Importing workflow associations"
0x11661  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x11666  ldarg.1
0x11667  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_WorkflowAssociations()
0x1166c  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x11671  ldc.i4.0
0x11672  ble      loc_11867
0x11677  ldarg.0
0x11678  ldarg.1
0x11679  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_Id()
0x1167e  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::GetContentType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId contentTypeId)
0x11683  stloc.0
0x11684  ldloc.0
0x11685  brfalse  loc_1183B
0x1168a  ldc.i4.0
0x1168b  stloc.1
0x1168c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x11691  stloc.2
0x11692  ldloc.0
0x11693  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x11698  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x1169d  stloc.s  0xA
0x1169f  br.s     loc_116BA
0x116a1  ldloc.s  0xA
0x116a3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x116a8  castclass [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation
0x116ad  stloc.3
0x116ae  ldloc.2
0x116af  ldloc.3
0x116b0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x116b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x116ba  ldloc.s  0xA
0x116bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x116c1  brtrue.s loc_116A1
0x116c3  leave.s  loc_116DA
0x116c5  ldloc.s  0xA
0x116c7  isinst   [mscorlib]System.IDisposable
0x116cc  stloc.s  0xB
0x116ce  ldloc.s  0xB
0x116d0  brfalse.s loc_116D9
0x116d2  ldloc.s  0xB
0x116d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x116d9  endfinally
0x116da  ldarg.1
0x116db  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_WorkflowAssociations()
0x116e0  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x116e5  stloc.s  0xC
0x116e7  br.s     loc_1173F
0x116e9  ldloc.s  0xC
0x116eb  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x116f0  stloc.s  4
0x116f2  newobj   instance void <>c__DisplayClass1::.ctor()
0x116f7  stloc.s  6
0x116f9  ldloc.s  6
0x116fb  ldarg.0
0x116fc  stfld    class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport <>c__DisplayClass1::<>4__this
0x11701  ldarg.0
0x11702  ldloc.s  4
0x11704  ldloc.0
0x11705  ldloc.s  6
0x11707  ldflda   string <>c__DisplayClass1::workflowAssociationName
0x1170c  call     instance bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ImportWorkflowAssociation(string workflowAssociationXml, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType targetContentType, [out] string& workflowAssociationName)
0x11711  brtrue.s loc_11716
0x11713  ldloc.1
0x11714  br.s     loc_11717
0x11716  ldc.i4.1
0x11717  stloc.1
0x11718  ldloc.2
0x11719  ldloc.s  6
0x1171b  ldftn    instance bool <>c__DisplayClass1::<ImportWorkflowAssociations>b__0(string waname)
0x11721  newobj   instance void class [mscorlib]System.Predicate`1<string>::.ctor(object, native int)
0x11726  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::Find(!!T0)
0x1172b  stloc.s  5
0x1172d  ldloc.s  5
0x1172f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11734  brtrue.s loc_1173F
0x11736  ldloc.2
0x11737  ldloc.s  5
0x11739  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x1173e  pop
0x1173f  ldloc.s  0xC
0x11741  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x11746  brtrue.s loc_116E9
0x11748  leave.s  loc_1175F
0x1174a  ldloc.s  0xC
0x1174c  isinst   [mscorlib]System.IDisposable
0x11751  stloc.s  0xD
0x11753  ldloc.s  0xD
0x11755  brfalse.s loc_1175E
0x11757  ldloc.s  0xD
0x11759  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1175e  endfinally
0x1175f  ldloc.2
0x11760  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x11765  ldc.i4.0
0x11766  ble.s    loc_117C1
0x11768  ldloc.2
0x11769  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1176e  stloc.s  0xE
0x11770  br.s     loc_117A8
0x11772  ldloca.s 0xE
0x11774  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x11779  stloc.s  7
0x1177b  ldloc.0
0x1177c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x11781  ldloc.s  7
0x11783  ldarg.0
0x11784  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::get_RootWeb()
0x11789  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Locale()
0x1178e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection::GetAssociationByName(string, class [mscorlib]System.Globalization.CultureInfo)
0x11793  stloc.s  8
0x11795  ldloc.s  8
0x11797  brfalse.s loc_117A8
0x11799  ldloc.0
0x1179a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x1179f  ldloc.s  8
0x117a1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection::Remove(class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation)
0x117a6  ldc.i4.1
0x117a7  stloc.1
0x117a8  ldloca.s 0xE
0x117aa  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x117af  brtrue.s loc_11772
0x117b1  leave.s  loc_117C1
0x117b3  ldloca.s 0xE
0x117b5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x117bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x117c0  endfinally
0x117c1  ldloc.1
0x117c2  brfalse  loc_1187D
0x117c7  ldarg.0
0x117c8  ldfld    bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::pushdown
0x117cd  brfalse  loc_1187D
0x117d2  ldc.i4   0x63683634
0x117d7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x117dc  ldc.i4.s 0x64
0x117de  ldstr    aStartToUpdatew// "Start to UpdateWorkflowAssociationsOnCh"...
0x117e3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x117e8  ldloc.0
0x117e9  ldc.i4.0
0x117ea  ldc.i4.1
0x117eb  ldc.i4.1
0x117ec  ldc.i4.1
0x117ed  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::UpdateWorkflowAssociationsOnChildren(bool, bool, bool, bool)
0x117f2  leave.s  loc_11823
0x117f4  stloc.s  9
0x117f6  ldc.i4   0x63683635
0x117fb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11800  ldc.i4.s 0xA
0x11802  ldloc.s  9
0x11804  callvirt instance string [mscorlib]System.Exception::get_Message()
0x11809  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1180e  ldarg.0
0x1180f  ldfld    class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::result
0x11814  ldc.i4.2
0x11815  ldloc.s  9
0x11817  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1181c  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult::AddMessage(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationMessageType messageType, string errorMessage)
0x11821  leave.s  loc_11823
0x11823  ldc.i4   0x63683636
0x11828  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1182d  ldc.i4.s 0x64
0x1182f  ldstr    aFinishedUpdate// "Finished UpdateWorkflowAssociationsOnCh"...
0x11834  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x11839  br.s     loc_1187D
0x1183b  ldc.i4   0x63683637
0x11840  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11845  ldc.i4.s 0xA
0x11847  ldstr    aNoContentType0// "No content type {0} can be found for th"...
0x1184c  ldc.i4.1
0x1184d  newarr   [mscorlib]System.Object
0x11852  stloc.s  0xF
0x11854  ldloc.s  0xF
0x11856  ldc.i4.0
0x11857  ldarg.1
0x11858  callvirt instance string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_Name()
0x1185d  stelem.ref
0x1185e  ldloc.s  0xF
0x11860  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x11865  br.s     loc_1187D
0x11867  ldc.i4   0x63683638
0x1186c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11871  ldc.i4.s 0x64
0x11873  ldstr    aNoWorkflowAsso// "No workflow association for the importe"...
0x11878  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1187d  ldc.i4   0x63683639
0x11882  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11887  ldc.i4.s 0x64
0x11889  ldstr    aImportedWorkfl// "Imported workflow associations"
0x1188e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x11893  ret
```
