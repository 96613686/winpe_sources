# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::EnsureHiddenListFullSyncTimerJob

- ea: `0x46b90`
- end: `0x46c59`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::EnsureHiddenListFullSyncTimerJob`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x46a10`

## callees

- `0x3d400`
- `0x46b90`

## string_xrefs

- `0x46b9c`: `Hidden list full sync timer job is being created and associated with the web application {0}.`
- `0x46c12`: `Hidden list full sync timer job is created and associated with the web application {0}.`
- `0x46c3a`: `Hidden list full sync timer job was not created and associated with the web application {0}.  jobDefinition was already set.`

## pseudocode

```c

```

## disassembly

```asm
0x46b90  ldc.i4   0x66756331
0x46b95  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x46b9a  ldc.i4.s 0x32
0x46b9c  ldstr    aHiddenListFull_3// "Hidden list full sync timer job is bein"...
0x46ba1  ldc.i4.1
0x46ba2  newarr   [mscorlib]System.Object
0x46ba7  stloc.2
0x46ba8  ldloc.2
0x46ba9  ldc.i4.0
0x46baa  ldarg.0
0x46bab  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x46bb0  stelem.ref
0x46bb1  ldloc.2
0x46bb2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x46bb7  ldarg.0
0x46bb8  ldnull
0x46bb9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46bbe  brfalse  loc_46C58
0x46bc3  ldarg.0
0x46bc4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x46bc9  ldstr    aHiddenlistfull// "HiddenListFullSyncTimerJob"
0x46bce  callvirt T0x2B000063
0x46bd3  stloc.0
0x46bd4  ldloc.0
0x46bd5  ldnull
0x46bd6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46bdb  brfalse.s loc_46C2E
0x46bdd  ldarg.0
0x46bde  newobj   instance void Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x46be3  stloc.0
0x46be4  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPHourlySchedule::.ctor()
0x46be9  stloc.1
0x46bea  ldloc.1
0x46beb  ldc.i4.0
0x46bec  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPHourlySchedule::set_BeginMinute(int32)
0x46bf1  ldloc.1
0x46bf2  ldc.i4.s 0x3B
0x46bf4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPHourlySchedule::set_EndMinute(int32)
0x46bf9  ldloc.0
0x46bfa  ldloc.1
0x46bfb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule)
0x46c00  ldloc.0
0x46c01  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x46c06  ldc.i4   0x66756332
0x46c0b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x46c10  ldc.i4.s 0x32
0x46c12  ldstr    aHiddenListFull_4// "Hidden list full sync timer job is crea"...
0x46c17  ldc.i4.1
0x46c18  newarr   [mscorlib]System.Object
0x46c1d  stloc.3
0x46c1e  ldloc.3
0x46c1f  ldc.i4.0
0x46c20  ldarg.0
0x46c21  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x46c26  stelem.ref
0x46c27  ldloc.3
0x46c28  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x46c2d  ret
0x46c2e  ldc.i4   0x66756333
0x46c33  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x46c38  ldc.i4.s 0x32
0x46c3a  ldstr    aHiddenListFull_5// "Hidden list full sync timer job was not"...
0x46c3f  ldc.i4.1
0x46c40  newarr   [mscorlib]System.Object
0x46c45  stloc.s  4
0x46c47  ldloc.s  4
0x46c49  ldc.i4.0
0x46c4a  ldarg.0
0x46c4b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x46c50  stelem.ref
0x46c51  ldloc.s  4
0x46c53  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x46c58  ret
```
