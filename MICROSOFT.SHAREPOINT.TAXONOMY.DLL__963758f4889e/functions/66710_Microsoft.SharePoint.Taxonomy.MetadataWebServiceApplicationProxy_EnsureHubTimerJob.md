# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::EnsureHubTimerJob

- ea: `0x66710`
- end: `0x66842`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::EnsureHubTimerJob`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x46a10`

## callees

- `0xddf0`
- `0x66710`

## string_xrefs

- `0x66783`: `Found and deleted a metadata hub timer job from an older installation.`
- `0x667ee`: `Created the metadata hub timer job for this farm.`
- `0x66837`: `Verified that the metadata hub timer job already exists for this farm.`

## pseudocode

```c

```

## disassembly

```asm
0x66710  ldarg.0
0x66711  ldtoken  Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x66716  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6671b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy> [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetProxies(class [mscorlib]System.Type)
0x66720  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x66725  stloc.0
0x66726  ldloc.0
0x66727  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Count()
0x6672c  brtrue.s loc_66745
0x6672e  ldc.i4   0x4B399
0x66733  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66738  ldc.i4.s 0x32
0x6673a  ldstr    aSkippingCheckF_0// "Skipping check for the metadata hub tim"...
0x6673f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66744  ret
0x66745  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x6674a  stloc.1
0x6674b  ldloc.1
0x6674c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x66751  callvirt T0x2B000011
0x66756  stloc.2
0x66757  ldloc.2
0x66758  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x6675d  ldstr    aMetadatahubtim// "MetadataHubTimerJob"
0x66762  callvirt T0x2B0000AA
0x66767  stloc.3
0x66768  ldloc.3
0x66769  ldnull
0x6676a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x6676f  brfalse.s loc_6678D
0x66771  ldloc.3
0x66772  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x66777  ldc.i4   0x4B39A
0x6677c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66781  ldc.i4.s 0x32
0x66783  ldstr    aFoundAndDelete// "Found and deleted a metadata hub timer "...
0x66788  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6678d  ldloc.1
0x6678e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPTimerService [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_TimerService()
0x66793  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x66798  ldstr    aMetadatahubtim// "MetadataHubTimerJob"
0x6679d  callvirt T0x2B0000AA
0x667a2  stloc.3
0x667a3  ldloc.3
0x667a4  ldnull
0x667a5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x667aa  brfalse.s loc_667F9
0x667ac  ldstr    aMetadatahubtim// "MetadataHubTimerJob"
0x667b1  ldloc.1
0x667b2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPTimerService [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_TimerService()
0x667b7  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::.ctor(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService service)
0x667bc  stloc.3
0x667bd  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::.ctor()
0x667c2  stloc.s  4
0x667c4  ldloc.s  4
0x667c6  ldc.i4.1
0x667c7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginHour(int32)
0x667cc  ldloc.s  4
0x667ce  ldc.i4.2
0x667cf  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndHour(int32)
0x667d4  ldloc.3
0x667d5  ldloc.s  4
0x667d7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule)
0x667dc  ldloc.3
0x667dd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x667e2  ldc.i4   0x66356464
0x667e7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x667ec  ldc.i4.s 0x32
0x667ee  ldstr    aCreatedTheMeta// "Created the metadata hub timer job for "...
0x667f3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x667f8  ret
0x667f9  ldloc.3
0x667fa  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_Schedule()
0x667ff  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule
0x66804  brtrue.s loc_6682B
0x66806  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::.ctor()
0x6680b  stloc.s  5
0x6680d  ldloc.s  5
0x6680f  ldc.i4.1
0x66810  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginHour(int32)
0x66815  ldloc.s  5
0x66817  ldc.i4.2
0x66818  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndHour(int32)
0x6681d  ldloc.3
0x6681e  ldloc.s  5
0x66820  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule)
0x66825  ldloc.3
0x66826  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x6682b  ldc.i4   0x66356465
0x66830  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66835  ldc.i4.s 0x32
0x66837  ldstr    aVerifiedThatTh// "Verified that the metadata hub timer jo"...
0x6683c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66841  ret
```
