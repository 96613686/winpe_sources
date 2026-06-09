# Microsoft.SharePoint.Taxonomy.MetadataWebServiceProxy::Microsoft.SharePoint.Administration.Backup.IBackupRestore.AddBackupObjects

- ea: `0x671c0`
- end: `0x6728e`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceProxy::Microsoft.SharePoint.Administration.Backup.IBackupRestore.AddBackupObjects`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x2acd0`
- `0x2ad40`
- `0x671c0`

## string_xrefs

- `0x6721c`: `ServiceOrProxyBRDescription`
- `0x67202`: `ServiceProxyName`
- `0x6722c`: `ServiceProxyName`
- `0x671e4`: `MetadataWebServiceProxy does not have any application proxy in the farm; so it does not have objects to back up`

## pseudocode

```c

```

## disassembly

```asm
0x671c0  ldarg.1
0x671c1  ldstr    aParent// "parent"
0x671c6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x671cb  ldarg.0
0x671cc  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceProxy::get_ApplicationProxies()
0x671d1  callvirt instance int32 class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Count()
0x671d6  brtrue.s loc_671EF
0x671d8  ldc.i4   0x61347868
0x671dd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x671e2  ldc.i4.s 0x64
0x671e4  ldstr    aMetadatawebser_69// "MetadataWebServiceProxy does not have a"...
0x671e9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x671ee  ret
0x671ef  ldarg.1
0x671f0  ldarg.0
0x671f1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::AddChild(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore)
0x671f6  stloc.0
0x671f7  ldloc.0
0x671f8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x671fd  ldstr    aSptypename// "SPTypeName"
0x67202  ldstr    aServiceproxyna// "ServiceProxyName"
0x67207  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6720c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x67211  ldloc.0
0x67212  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x67217  ldstr    aSpdescription// "SPDescription"
0x6721c  ldstr    aServiceorproxy// "ServiceOrProxyBRDescription"
0x67221  ldc.i4.1
0x67222  newarr   [mscorlib]System.Object
0x67227  stloc.s  4
0x67229  ldloc.s  4
0x6722b  ldc.i4.0
0x6722c  ldstr    aServiceproxyna// "ServiceProxyName"
0x67231  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x67236  stelem.ref
0x67237  ldloc.s  4
0x67239  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6723e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x67243  ldarg.0
0x67244  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceProxy::get_ApplicationProxies()
0x67249  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::GetEnumerator()
0x6724e  stloc.s  5
0x67250  br.s     loc_67276
0x67252  ldloc.s  5
0x67254  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Current()
0x67259  stloc.1
0x6725a  ldloc.1
0x6725b  isinst   Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x67260  stloc.2
0x67261  ldloc.2
0x67262  ldnull
0x67263  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x67268  brfalse.s loc_67276
0x6726a  ldloc.2
0x6726b  stloc.3
0x6726c  ldloc.3
0x6726d  brfalse.s loc_67276
0x6726f  ldloc.3
0x67270  ldloc.0
0x67271  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore::AddBackupObjects(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject)
0x67276  ldloc.s  5
0x67278  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6727d  brtrue.s loc_67252
0x6727f  leave.s  loc_6728D
0x67281  ldloc.s  5
0x67283  brfalse.s loc_6728C
0x67285  ldloc.s  5
0x67287  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6728c  endfinally
0x6728d  ret
```
