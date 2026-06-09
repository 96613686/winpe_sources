# Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::ProcessSite

- ea: `0x3da70`
- end: `0x3ddc4`
- name: `Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::ProcessSite`
- size: `852`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x242a0`
- `0x3da20`
- `0x3da70`
- `0x4baa0`
- `0x4cc10`
- `0x55560`
- `0x55d60`
- `0x56c60`

## string_xrefs

- `0x3db7e`: `HiddenListFullSync timer job found service application restore or language add.  Syncing all terms for site {0}.`
- `0x3dc07`: `Failed to get update hidden list for site {0} and proxy {1}, error was {2}.`
- `0x3dcf5`: `Failed to get update hidden list for site {0} and termstore id {1}, error was {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x3da70  ldc.i4   0x66367775
0x3da75  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3da7a  ldc.i4.s 0x32
0x3da7c  ldstr    aHiddenlistfull_1// "HiddenListFullSync timer job started up"...
0x3da81  ldc.i4.1
0x3da82  newarr   [mscorlib]System.Object
0x3da87  stloc.s  0xC
0x3da89  ldloc.s  0xC
0x3da8b  ldc.i4.0
0x3da8c  ldarg.1
0x3da8d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3da92  stelem.ref
0x3da93  ldloc.s  0xC
0x3da95  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3da9a  ldarg.1
0x3da9b  ldstr    aSite// "site"
0x3daa0  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3daa5  ldarg.2
0x3daa6  ldstr    aJobstate// "jobState"
0x3daab  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3dab0  ldnull
0x3dab1  stloc.0
0x3dab2  ldarg.1
0x3dab3  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3dab8  stloc.1
0x3dab9  ldarg.0
0x3daba  ldfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3dabf  brfalse  loc_3DB56
0x3dac4  ldc.i4   0x66633379
0x3dac9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3dace  ldc.i4.s 0x14
0x3dad0  ldstr    aHiddenlistfull_2// "HiddenListFullSync timer job encountere"...
0x3dad5  ldc.i4.2
0x3dad6  newarr   [mscorlib]System.Object
0x3dadb  stloc.s  0xD
0x3dadd  ldloc.s  0xD
0x3dadf  ldc.i4.0
0x3dae0  ldarg.1
0x3dae1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x3dae6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3daeb  box      [mscorlib]System.Guid
0x3daf0  stelem.ref
0x3daf1  ldloc.s  0xD
0x3daf3  ldc.i4.1
0x3daf4  ldarg.1
0x3daf5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x3dafa  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3daff  stelem.ref
0x3db00  ldloc.s  0xD
0x3db02  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3db07  ldarg.1
0x3db08  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3db0d  stloc.2
0x3db0e  ldloc.0
0x3db0f  brtrue.s loc_3DB18
0x3db11  ldarg.1
0x3db12  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::TryGetHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3db17  stloc.0
0x3db18  ldloc.0
0x3db19  brfalse  loc_3DD5E
0x3db1e  ldloc.2
0x3db1f  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x3db24  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x3db29  stloc.s  0xE
0x3db2b  br.s     loc_3DB3C
0x3db2d  ldloc.s  0xE
0x3db2f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x3db34  stloc.3
0x3db35  ldloc.3
0x3db36  ldloc.0
0x3db37  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ResyncHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList hiddenList)
0x3db3c  ldloc.s  0xE
0x3db3e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3db43  brtrue.s loc_3DB2D
0x3db45  leave    loc_3DD5E
0x3db4a  ldloc.s  0xE
0x3db4c  brfalse.s loc_3DB55
0x3db4e  ldloc.s  0xE
0x3db50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3db55  endfinally
0x3db56  ldarg.0
0x3db57  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3db5c  brfalse  loc_3DC70
0x3db61  ldarg.0
0x3db62  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3db67  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3db6c  ldc.i4.0
0x3db6d  ble      loc_3DC70
0x3db72  ldc.i4   0x66367776
0x3db77  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3db7c  ldc.i4.s 0x14
0x3db7e  ldstr    aHiddenlistfull_3// "HiddenListFullSync timer job found serv"...
0x3db83  ldc.i4.1
0x3db84  newarr   [mscorlib]System.Object
0x3db89  stloc.s  0xF
0x3db8b  ldloc.s  0xF
0x3db8d  ldc.i4.0
0x3db8e  ldarg.1
0x3db8f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3db94  stelem.ref
0x3db95  ldloc.s  0xF
0x3db97  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3db9c  ldloc.0
0x3db9d  brtrue.s loc_3DBA6
0x3db9f  ldarg.1
0x3dba0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::TryGetHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3dba5  stloc.0
0x3dba6  ldloc.0
0x3dba7  brfalse  loc_3DC70
0x3dbac  ldarg.0
0x3dbad  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3dbb2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x3dbb7  stloc.s  0x10
0x3dbb9  br       loc_3DC54
0x3dbbe  ldloca.s 0x10
0x3dbc0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x3dbc5  stloc.s  4
0x3dbc7  ldloc.1
0x3dbc8  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x3dbcd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x3dbd2  stloc.s  0x11
0x3dbd4  br.s     loc_3DC3D
0x3dbd6  ldloc.s  0x11
0x3dbd8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x3dbdd  stloc.s  5
0x3dbdf  ldloc.s  5
0x3dbe1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x3dbe6  ldloc.s  4
0x3dbe8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3dbed  brfalse.s loc_3DC3D
0x3dbef  ldloc.s  5
0x3dbf1  ldloc.0
0x3dbf2  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ResyncHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList hiddenList)
0x3dbf7  leave.s  loc_3DC3D
0x3dbf9  stloc.s  6
0x3dbfb  ldc.i4   0x66367777
0x3dc00  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3dc05  ldc.i4.s 0xA
0x3dc07  ldstr    aFailedToGetUpd// "Failed to get update hidden list for si"...
0x3dc0c  ldc.i4.3
0x3dc0d  newarr   [mscorlib]System.Object
0x3dc12  stloc.s  0x12
0x3dc14  ldloc.s  0x12
0x3dc16  ldc.i4.0
0x3dc17  ldarg.1
0x3dc18  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3dc1d  stelem.ref
0x3dc1e  ldloc.s  0x12
0x3dc20  ldc.i4.1
0x3dc21  ldloc.s  4
0x3dc23  box      [mscorlib]System.Guid
0x3dc28  stelem.ref
0x3dc29  ldloc.s  0x12
0x3dc2b  ldc.i4.2
0x3dc2c  ldloc.s  6
0x3dc2e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3dc33  stelem.ref
0x3dc34  ldloc.s  0x12
0x3dc36  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3dc3b  leave.s  loc_3DC3D
0x3dc3d  ldloc.s  0x11
0x3dc3f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3dc44  brtrue.s loc_3DBD6
0x3dc46  leave.s  loc_3DC54
0x3dc48  ldloc.s  0x11
0x3dc4a  brfalse.s loc_3DC53
0x3dc4c  ldloc.s  0x11
0x3dc4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dc53  endfinally
0x3dc54  ldloca.s 0x10
0x3dc56  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x3dc5b  brtrue   loc_3DBBE
0x3dc60  leave.s  loc_3DC70
0x3dc62  ldloca.s 0x10
0x3dc64  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x3dc6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dc6f  endfinally
0x3dc70  ldarg.0
0x3dc71  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3dc76  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3dc7b  ldc.i4.0
0x3dc7c  ble      loc_3DD5E
0x3dc81  ldloc.0
0x3dc82  brtrue.s loc_3DC8B
0x3dc84  ldarg.1
0x3dc85  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::TryGetHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3dc8a  stloc.0
0x3dc8b  ldloc.0
0x3dc8c  brfalse  loc_3DD5E
0x3dc91  ldarg.0
0x3dc92  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3dc97  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x3dc9c  stloc.s  0x13
0x3dc9e  br       loc_3DD42
0x3dca3  ldloca.s 0x13
0x3dca5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x3dcaa  stloc.s  7
0x3dcac  ldarg.1
0x3dcad  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x3dcb2  stloc.s  8
0x3dcb4  ldloc.s  8
0x3dcb6  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x3dcbb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x3dcc0  stloc.s  0x14
0x3dcc2  br.s     loc_3DD2B
0x3dcc4  ldloc.s  0x14
0x3dcc6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x3dccb  stloc.s  9
0x3dccd  ldloc.s  9
0x3dccf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x3dcd4  ldloc.s  7
0x3dcd6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3dcdb  brfalse.s loc_3DD2B
0x3dcdd  ldloc.s  9
0x3dcdf  ldloc.0
0x3dce0  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ResyncHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList hiddenList)
0x3dce5  leave.s  loc_3DD34
0x3dce7  stloc.s  0xA
0x3dce9  ldc.i4   0x6DB41A
0x3dcee  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3dcf3  ldc.i4.s 0xA
0x3dcf5  ldstr    aFailedToGetUpd_0// "Failed to get update hidden list for si"...
0x3dcfa  ldc.i4.3
0x3dcfb  newarr   [mscorlib]System.Object
0x3dd00  stloc.s  0x15
0x3dd02  ldloc.s  0x15
0x3dd04  ldc.i4.0
0x3dd05  ldarg.1
0x3dd06  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3dd0b  stelem.ref
0x3dd0c  ldloc.s  0x15
0x3dd0e  ldc.i4.1
0x3dd0f  ldloc.s  7
0x3dd11  box      [mscorlib]System.Guid
0x3dd16  stelem.ref
0x3dd17  ldloc.s  0x15
0x3dd19  ldc.i4.2
0x3dd1a  ldloc.s  0xA
0x3dd1c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3dd21  stelem.ref
0x3dd22  ldloc.s  0x15
0x3dd24  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3dd29  leave.s  loc_3DD34
0x3dd2b  ldloc.s  0x14
0x3dd2d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3dd32  brtrue.s loc_3DCC4
0x3dd34  leave.s  loc_3DD42
0x3dd36  ldloc.s  0x14
0x3dd38  brfalse.s loc_3DD41
0x3dd3a  ldloc.s  0x14
0x3dd3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dd41  endfinally
0x3dd42  ldloca.s 0x13
0x3dd44  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x3dd49  brtrue   loc_3DCA3
0x3dd4e  leave.s  loc_3DD5E
0x3dd50  ldloca.s 0x13
0x3dd52  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x3dd58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dd5d  endfinally
0x3dd5e  leave.s  loc_3DD99
0x3dd60  stloc.s  0xB
0x3dd62  ldc.i4   0x66367778
0x3dd67  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3dd6c  ldc.i4.s 0xA
0x3dd6e  ldstr    aHiddenlistfull_4// "HiddenListFullSync timer job encountere"...
0x3dd73  ldc.i4.2
0x3dd74  newarr   [mscorlib]System.Object
0x3dd79  stloc.s  0x16
0x3dd7b  ldloc.s  0x16
0x3dd7d  ldc.i4.0
0x3dd7e  ldarg.1
0x3dd7f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3dd84  stelem.ref
0x3dd85  ldloc.s  0x16
0x3dd87  ldc.i4.1
0x3dd88  ldloc.s  0xB
0x3dd8a  callvirt instance string [mscorlib]System.Object::ToString()
0x3dd8f  stelem.ref
0x3dd90  ldloc.s  0x16
0x3dd92  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3dd97  leave.s  loc_3DD99
0x3dd99  ldc.i4   0x67326F68
0x3dd9e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3dda3  ldc.i4.s 0x32
0x3dda5  ldstr    aHiddenlistfull_5// "HiddenListFullSync timer job finished u"...
0x3ddaa  ldc.i4.1
0x3ddab  newarr   [mscorlib]System.Object
0x3ddb0  stloc.s  0x17
0x3ddb2  ldloc.s  0x17
0x3ddb4  ldc.i4.0
0x3ddb5  ldarg.1
0x3ddb6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x3ddbb  stelem.ref
0x3ddbc  ldloc.s  0x17
0x3ddbe  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3ddc3  ret
```
