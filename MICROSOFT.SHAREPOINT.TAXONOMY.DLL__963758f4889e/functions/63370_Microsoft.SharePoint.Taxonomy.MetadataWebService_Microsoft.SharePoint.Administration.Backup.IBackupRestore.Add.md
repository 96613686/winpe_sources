# Microsoft.SharePoint.Taxonomy.MetadataWebService::Microsoft.SharePoint.Administration.Backup.IBackupRestore.AddBackupObjects

- ea: `0x63370`
- end: `0x63490`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebService::Microsoft.SharePoint.Administration.Backup.IBackupRestore.AddBackupObjects`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x2acd0`
- `0x2ad40`
- `0x63370`

## string_xrefs

- `0x633b2`: `ServiceName`
- `0x633dc`: `ServiceName`
- `0x63394`: `MetadataWebService does not have any application in the farm; so it does not have objects to back up`
- `0x633cc`: `ServiceOrProxyBRDescription`

## pseudocode

```c

```

## disassembly

```asm
0x63370  ldarg.1
0x63371  ldstr    aParent// "parent"
0x63376  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x6337b  ldarg.0
0x6337c  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_Applications()
0x63381  callvirt instance int32 class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication>::get_Count()
0x63386  brtrue.s loc_6339F
0x63388  ldc.i4   0x387A3033
0x6338d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63392  ldc.i4.s 0x64
0x63394  ldstr    aMetadatawebser_23// "MetadataWebService does not have any ap"...
0x63399  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6339e  ret
0x6339f  ldarg.1
0x633a0  ldarg.0
0x633a1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::AddChild(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore)
0x633a6  stloc.0
0x633a7  ldloc.0
0x633a8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x633ad  ldstr    aSptypename// "SPTypeName"
0x633b2  ldstr    aServicename// "ServiceName"
0x633b7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x633bc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x633c1  ldloc.0
0x633c2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x633c7  ldstr    aSpdescription// "SPDescription"
0x633cc  ldstr    aServiceorproxy// "ServiceOrProxyBRDescription"
0x633d1  ldc.i4.1
0x633d2  newarr   [mscorlib]System.Object
0x633d7  stloc.s  7
0x633d9  ldloc.s  7
0x633db  ldc.i4.0
0x633dc  ldstr    aServicename// "ServiceName"
0x633e1  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x633e6  stelem.ref
0x633e7  ldloc.s  7
0x633e9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x633ee  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x633f3  ldarg.0
0x633f4  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_Applications()
0x633f9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication>::GetEnumerator()
0x633fe  stloc.s  8
0x63400  br.s     loc_63426
0x63402  ldloc.s  8
0x63404  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication>::get_Current()
0x63409  stloc.1
0x6340a  ldloc.1
0x6340b  isinst   Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication
0x63410  stloc.2
0x63411  ldloc.2
0x63412  ldnull
0x63413  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x63418  brfalse.s loc_63426
0x6341a  ldloc.2
0x6341b  stloc.3
0x6341c  ldloc.3
0x6341d  brfalse.s loc_63426
0x6341f  ldloc.3
0x63420  ldloc.0
0x63421  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore::AddBackupObjects(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject)
0x63426  ldloc.s  8
0x63428  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6342d  brtrue.s loc_63402
0x6342f  leave.s  loc_6343D
0x63431  ldloc.s  8
0x63433  brfalse.s loc_6343C
0x63435  ldloc.s  8
0x63437  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6343c  endfinally
0x6343d  ldarg.0
0x6343e  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x63443  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition>::GetEnumerator()
0x63448  stloc.s  9
0x6344a  br.s     loc_63478
0x6344c  ldloc.s  9
0x6344e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition>::get_Current()
0x63453  stloc.s  4
0x63455  ldloc.s  4
0x63457  isinst   Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition
0x6345c  stloc.s  5
0x6345e  ldloc.s  5
0x63460  ldnull
0x63461  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x63466  brfalse.s loc_63478
0x63468  ldloc.s  5
0x6346a  stloc.s  6
0x6346c  ldloc.s  6
0x6346e  brfalse.s loc_63478
0x63470  ldloc.s  6
0x63472  ldloc.0
0x63473  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore::AddBackupObjects(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject)
0x63478  ldloc.s  9
0x6347a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6347f  brtrue.s loc_6344C
0x63481  leave.s  loc_6348F
0x63483  ldloc.s  9
0x63485  brfalse.s loc_6348E
0x63487  ldloc.s  9
0x63489  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6348e  endfinally
0x6348f  ret
```
