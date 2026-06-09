# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ImportWorkflowAssociation

- ea: `0x118a0`
- end: `0x11a82`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::ImportWorkflowAssociation`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11650`

## callees

- `0x118a0`
- `0x11a90`
- `0x11b70`
- `0x130c0`
- `0x2ad40`

## string_xrefs

- `0x118c3`: `Found the workflow template {0} for the workflow association {1}`
- `0x1197b`: `The workflow association {0} for content type {1} does not need to be updated`
- `0x119f7`: `ErrorNoWorkflowTemplate`
- `0x11a49`: `Could not find the workflow template {0} for the workflow association {1}`

## pseudocode

```c

```

## disassembly

```asm
0x118a0  ldc.i4.0
0x118a1  stloc.0
0x118a2  ldarg.3
0x118a3  ldnull
0x118a4  stind.ref
0x118a5  ldc.i4.0
0x118a6  stloc.1
0x118a7  ldarg.0
0x118a8  ldarg.1
0x118a9  ldloca.s 1
0x118ab  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::LoadWorkflowAssociation(string workflowAssociationXml, [out] bool& templateExists)
0x118b0  stloc.2
0x118b1  ldloc.1
0x118b2  brfalse  loc_119F0
0x118b7  ldc.i4   0x63683661
0x118bc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x118c1  ldc.i4.s 0x64
0x118c3  ldstr    aFoundTheWorkfl// "Found the workflow template {0} for the"...
0x118c8  ldc.i4.2
0x118c9  newarr   [mscorlib]System.Object
0x118ce  stloc.s  4
0x118d0  ldloc.s  4
0x118d2  ldc.i4.0
0x118d3  ldloc.2
0x118d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0x118d9  stloc.s  5
0x118db  ldloca.s 5
0x118dd  constrained. [mscorlib]System.Guid
0x118e3  callvirt instance string [mscorlib]System.Object::ToString()
0x118e8  stelem.ref
0x118e9  ldloc.s  4
0x118eb  ldc.i4.1
0x118ec  ldloc.2
0x118ed  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x118f2  stelem.ref
0x118f3  ldloc.s  4
0x118f5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x118fa  ldarg.3
0x118fb  ldloc.2
0x118fc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x11901  stind.ref
0x11902  ldarg.2
0x11903  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x11908  ldloc.2
0x11909  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x1190e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11913  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection::GetAssociationByName(string, class [mscorlib]System.Globalization.CultureInfo)
0x11918  stloc.3
0x11919  ldloc.3
0x1191a  brfalse  loc_119A8
0x1191f  ldloc.3
0x11920  ldloc.2
0x11921  call     bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::IsDifferentWorkflowAssociation(class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation workflowAssociation1, class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation workflowAssociation2)
0x11926  brfalse.s loc_1196F
0x11928  ldc.i4   0x63683662
0x1192d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11932  ldc.i4.s 0x64
0x11934  ldstr    aUpdatingTheWor// "Updating the workflow association {0} f"...
0x11939  ldc.i4.2
0x1193a  newarr   [mscorlib]System.Object
0x1193f  stloc.s  6
0x11941  ldloc.s  6
0x11943  ldc.i4.0
0x11944  ldloc.2
0x11945  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x1194a  stelem.ref
0x1194b  ldloc.s  6
0x1194d  ldc.i4.1
0x1194e  ldarg.2
0x1194f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x11954  stelem.ref
0x11955  ldloc.s  6
0x11957  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1195c  ldarg.2
0x1195d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x11962  ldloc.2
0x11963  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection::Update(class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation)
0x11968  ldc.i4.1
0x11969  stloc.0
0x1196a  br       loc_11A80
0x1196f  ldc.i4   0x63683663
0x11974  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11979  ldc.i4.s 0x64
0x1197b  ldstr    aTheWorkflowAss// "The workflow association {0} for conten"...
0x11980  ldc.i4.2
0x11981  newarr   [mscorlib]System.Object
0x11986  stloc.s  7
0x11988  ldloc.s  7
0x1198a  ldc.i4.0
0x1198b  ldloc.2
0x1198c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x11991  stelem.ref
0x11992  ldloc.s  7
0x11994  ldc.i4.1
0x11995  ldarg.2
0x11996  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x1199b  stelem.ref
0x1199c  ldloc.s  7
0x1199e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x119a3  br       loc_11A80
0x119a8  ldc.i4   0x63683664
0x119ad  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x119b2  ldc.i4.s 0x64
0x119b4  ldstr    aAddingTheWorkf// "Adding the workflow association {0} for"...
0x119b9  ldc.i4.2
0x119ba  newarr   [mscorlib]System.Object
0x119bf  stloc.s  8
0x119c1  ldloc.s  8
0x119c3  ldc.i4.0
0x119c4  ldloc.2
0x119c5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x119ca  stelem.ref
0x119cb  ldloc.s  8
0x119cd  ldc.i4.1
0x119ce  ldarg.2
0x119cf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x119d4  stelem.ref
0x119d5  ldloc.s  8
0x119d7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x119dc  ldarg.2
0x119dd  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_WorkflowAssociations()
0x119e2  ldloc.2
0x119e3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation)
0x119e8  pop
0x119e9  ldc.i4.1
0x119ea  stloc.0
0x119eb  br       loc_11A80
0x119f0  ldarg.0
0x119f1  ldfld    class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberImport::result
0x119f6  ldc.i4.2
0x119f7  ldstr    aErrornoworkflo// "ErrorNoWorkflowTemplate"
0x119fc  ldc.i4.3
0x119fd  newarr   [mscorlib]System.Object
0x11a02  stloc.s  9
0x11a04  ldloc.s  9
0x11a06  ldc.i4.0
0x11a07  ldloc.2
0x11a08  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x11a0d  stelem.ref
0x11a0e  ldloc.s  9
0x11a10  ldc.i4.1
0x11a11  ldarg.2
0x11a12  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x11a17  stelem.ref
0x11a18  ldloc.s  9
0x11a1a  ldc.i4.2
0x11a1b  ldloc.2
0x11a1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0x11a21  stloc.s  0xA
0x11a23  ldloca.s 0xA
0x11a25  constrained. [mscorlib]System.Guid
0x11a2b  callvirt instance string [mscorlib]System.Object::ToString()
0x11a30  stelem.ref
0x11a31  ldloc.s  9
0x11a33  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x11a38  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult::AddMessage(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationMessageType messageType, string errorMessage)
0x11a3d  ldc.i4   0x63683665
0x11a42  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x11a47  ldc.i4.s 0x32
0x11a49  ldstr    aCouldNotFindTh// "Could not find the workflow template {0"...
0x11a4e  ldc.i4.2
0x11a4f  newarr   [mscorlib]System.Object
0x11a54  stloc.s  0xB
0x11a56  ldloc.s  0xB
0x11a58  ldc.i4.0
0x11a59  ldloc.2
0x11a5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0x11a5f  stloc.s  0xC
0x11a61  ldloca.s 0xC
0x11a63  constrained. [mscorlib]System.Guid
0x11a69  callvirt instance string [mscorlib]System.Object::ToString()
0x11a6e  stelem.ref
0x11a6f  ldloc.s  0xB
0x11a71  ldc.i4.1
0x11a72  ldloc.2
0x11a73  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0x11a78  stelem.ref
0x11a79  ldloc.s  0xB
0x11a7b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x11a80  ldloc.0
0x11a81  ret
```
