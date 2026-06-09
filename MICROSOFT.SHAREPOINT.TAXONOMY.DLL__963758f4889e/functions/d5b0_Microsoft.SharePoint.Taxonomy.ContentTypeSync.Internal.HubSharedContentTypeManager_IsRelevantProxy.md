# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::IsRelevantProxy

- ea: `0xd5b0`
- end: `0xd6d1`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::IsRelevantProxy`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0xdb00`

## callees

- `0xd5b0`
- `0xdc30`
- `0xe9a0`
- `0x134b0`
- `0x13520`
- `0x2acd0`
- `0x65280`
- `0x65400`
- `0x66050`

## string_xrefs

- `0xd62d`: `A site {0} in a subscription cannot be used as a hub for non-partitioned service application {1}`
- `0xd67d`: `ErrorIncompatibleHub`

## pseudocode

```c

```

## disassembly

```asm
0xd5b0  ldc.i4.0
0xd5b1  stloc.0
0xd5b2  ldarg.1
0xd5b3  ldnull
0xd5b4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0xd5b9  brfalse  loc_D6CF
0xd5be  ldarg.1
0xd5bf  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0xd5c4  brtrue   loc_D6CF
0xd5c9  ldarg.1
0xd5ca  ldarg.0
0xd5cb  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_HubSite()
0xd5d0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetRawPartitionId(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0xd5d5  stloc.1
0xd5d6  ldarg.1
0xd5d7  ldloc.1
0xd5d8  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetContentTypeSyndicationHub(valuetype [mscorlib]System.Guid rawPartitionId)
0xd5dd  stloc.2
0xd5de  ldarg.0
0xd5df  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xd5e4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0xd5e9  newobj   instance void [System]System.Uri::.ctor(string)
0xd5ee  stloc.3
0xd5ef  ldloc.2
0xd5f0  ldnull
0xd5f1  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xd5f6  brfalse  loc_D69E
0xd5fb  ldloc.2
0xd5fc  ldloc.3
0xd5fd  call     bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::IsHubSite(class [System]System.Uri hubUri, class [System]System.Uri targetUri)
0xd602  brfalse  loc_D69E
0xd607  ldarg.0
0xd608  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_HubSite()
0xd60d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0xd612  brfalse  loc_D69C
0xd617  ldarg.1
0xd618  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceApplicationPartitioned()
0xd61d  brtrue.s loc_D69C
0xd61f  ldc.i4.0
0xd620  stloc.0
0xd621  ldc.i4   0x63386A61
0xd626  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd62b  ldc.i4.s 0xA
0xd62d  ldstr    aASite0InASubsc// "A site {0} in a subscription cannot be "...
0xd632  ldc.i4.2
0xd633  newarr   [mscorlib]System.Object
0xd638  stloc.s  5
0xd63a  ldloc.s  5
0xd63c  ldc.i4.0
0xd63d  ldloc.2
0xd63e  stelem.ref
0xd63f  ldloc.s  5
0xd641  ldc.i4.1
0xd642  ldarg.1
0xd643  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xd648  stelem.ref
0xd649  ldloc.s  5
0xd64b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd650  ldarg.0
0xd651  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xd656  ldarg.1
0xd657  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xd65c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd661  ldsfld   string [mscorlib]System.String::Empty
0xd666  ldarg.0
0xd667  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xd66c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0xd671  ldsfld   string [mscorlib]System.String::Empty
0xd676  ldnull
0xd677  ldc.i4.0
0xd678  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetReadableStatus(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.SyndicationStatus status)
0xd67d  ldstr    aErrorincompati// "ErrorIncompatibleHub"
0xd682  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xd687  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xd68c  stloc.s  6
0xd68e  ldloca.s 6
0xd690  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0xd695  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::AddLogItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string proxyName, valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string siteUrl, string objectName, string stage, string stageMessage, string message, valuetype [mscorlib]System.DateTime createdTime)
0xd69a  br.s     loc_D69E
0xd69c  ldc.i4.1
0xd69d  stloc.0
0xd69e  leave.s  loc_D6CF
0xd6a0  stloc.s  4
0xd6a2  ldc.i4   0x63683577
0xd6a7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd6ac  ldc.i4.s 0xA
0xd6ae  ldstr    aFailedToGetTer// "Failed to get term store {0}"
0xd6b3  ldc.i4.1
0xd6b4  newarr   [mscorlib]System.Object
0xd6b9  stloc.s  7
0xd6bb  ldloc.s  7
0xd6bd  ldc.i4.0
0xd6be  ldloc.s  4
0xd6c0  callvirt instance string [mscorlib]System.Object::ToString()
0xd6c5  stelem.ref
0xd6c6  ldloc.s  7
0xd6c8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd6cd  leave.s  loc_D6CF
0xd6cf  ldloc.0
0xd6d0  ret
```
