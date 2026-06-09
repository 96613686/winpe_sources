# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch5

- ea: `0x98100`
- end: `0x98624`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch5`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x983b2`: `@InstallationId`
- `0x98402`: `@InstallationId`
- `0x9847a`: `@InstallationId`
- `0x98107`: `proc_App_CommitJob`
- `0x98157`: `proc_App_CommitPackage`
- `0x981a5`: `@TitleToken`
- `0x981be`: `@Manifest`
- `0x981ee`: `proc_App_CreateApp`
- `0x982e2`: `@TempIconUrl`
- `0x98316`: `proc_App_CreateAppInstallation`
- `0x9839e`: `@InstallationLocale`
- `0x983cd`: `proc_App_CreateJob`
- `0x9845a`: `proc_App_DeleteAppInstallation`
- `0x984aa`: `proc_App_DeleteInvalidatedDownloadApp`
- `0x985c6`: `proc_App_FinishTask`
- `0x985e6`: `@TaskId`

## pseudocode

```c

```

## disassembly

```asm
0x98100  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x98105  stloc.0
0x98106  ldarg.0
0x98107  ldstr    aProcAppCommitj// "proc_App_CommitJob"
0x9810c  ldloc.0
0x9810d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x98112  ldloc.0
0x98113  ldstr    aReturnValue// "@RETURN_VALUE"
0x98118  ldc.i4.8
0x98119  ldc.i4.0
0x9811a  ldc.i4.1
0x9811b  ldc.i4.0
0x9811c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98121  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98126  ldloc.0
0x98127  ldstr    aJobid// "@JobId"
0x9812c  ldc.i4.s 0xE
0x9812e  ldc.i4.0
0x9812f  ldc.i4.0
0x98130  ldc.i4.0
0x98131  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98136  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9813b  ldloc.0
0x9813c  ldstr    aSiteid_1// "@SiteId"
0x98141  ldc.i4.s 0xE
0x98143  ldc.i4.0
0x98144  ldc.i4.0
0x98145  ldc.i4.0
0x98146  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9814b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98150  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x98155  stloc.0
0x98156  ldarg.0
0x98157  ldstr    aProcAppCommitp// "proc_App_CommitPackage"
0x9815c  ldloc.0
0x9815d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x98162  ldloc.0
0x98163  ldstr    aReturnValue// "@RETURN_VALUE"
0x98168  ldc.i4.8
0x98169  ldc.i4.0
0x9816a  ldc.i4.1
0x9816b  ldc.i4.0
0x9816c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98171  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98176  ldloc.0
0x98177  ldstr    aPackagefingerp// "@PackageFingerprint"
0x9817c  ldc.i4.1
0x9817d  ldc.i4.s 0x40
0x9817f  ldc.i4.0
0x98180  ldc.i4.0
0x98181  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98186  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9818b  ldloc.0
0x9818c  ldstr    aTitle// "@Title"
0x98191  ldc.i4.s 0xC
0x98193  ldc.i4   0x200
0x98198  ldc.i4.0
0x98199  ldc.i4.0
0x9819a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9819f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x981a4  ldloc.0
0x981a5  ldstr    aTitletoken// "@TitleToken"
0x981aa  ldc.i4.s 0xC
0x981ac  ldc.i4   0x208
0x981b1  ldc.i4.0
0x981b2  ldc.i4.0
0x981b3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x981b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x981bd  ldloc.0
0x981be  ldstr    aManifest// "@Manifest"
0x981c3  ldc.i4.s 0x15
0x981c5  ldc.i4.m1
0x981c6  ldc.i4.0
0x981c7  ldc.i4.0
0x981c8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x981cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x981d2  ldloc.0
0x981d3  ldstr    aSiteid_1// "@SiteId"
0x981d8  ldc.i4.s 0xE
0x981da  ldc.i4.0
0x981db  ldc.i4.0
0x981dc  ldc.i4.0
0x981dd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x981e2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x981e7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x981ec  stloc.0
0x981ed  ldarg.0
0x981ee  ldstr    aProcAppCreatea// "proc_App_CreateApp"
0x981f3  ldloc.0
0x981f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x981f9  ldloc.0
0x981fa  ldstr    aReturnValue// "@RETURN_VALUE"
0x981ff  ldc.i4.8
0x98200  ldc.i4.0
0x98201  ldc.i4.1
0x98202  ldc.i4.0
0x98203  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98208  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9820d  ldloc.0
0x9820e  ldstr    aPackagefingerp// "@PackageFingerprint"
0x98213  ldc.i4.1
0x98214  ldc.i4.s 0x40
0x98216  ldc.i4.0
0x98217  ldc.i4.0
0x98218  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9821d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98222  ldloc.0
0x98223  ldstr    aProductid// "@ProductId"
0x98228  ldc.i4.s 0xE
0x9822a  ldc.i4.0
0x9822b  ldc.i4.0
0x9822c  ldc.i4.0
0x9822d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98232  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98237  ldloc.0
0x98238  ldstr    aVersionmajor// "@VersionMajor"
0x9823d  ldc.i4.8
0x9823e  ldc.i4.0
0x9823f  ldc.i4.0
0x98240  ldc.i4.0
0x98241  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98246  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9824b  ldloc.0
0x9824c  ldstr    aVersionminor// "@VersionMinor"
0x98251  ldc.i4.8
0x98252  ldc.i4.0
0x98253  ldc.i4.0
0x98254  ldc.i4.0
0x98255  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9825a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9825f  ldloc.0
0x98260  ldstr    aVersionbuild// "@VersionBuild"
0x98265  ldc.i4.8
0x98266  ldc.i4.0
0x98267  ldc.i4.0
0x98268  ldc.i4.0
0x98269  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9826e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98273  ldloc.0
0x98274  ldstr    aVersionrevisio// "@VersionRevision"
0x98279  ldc.i4.8
0x9827a  ldc.i4.0
0x9827b  ldc.i4.0
0x9827c  ldc.i4.0
0x9827d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98282  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98287  ldloc.0
0x98288  ldstr    aTitle// "@Title"
0x9828d  ldc.i4.s 0xC
0x9828f  ldc.i4   0x200
0x98294  ldc.i4.0
0x98295  ldc.i4.0
0x98296  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9829b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x982a0  ldloc.0
0x982a1  ldstr    aAppsource// "@AppSource"
0x982a6  ldc.i4.s 0x14
0x982a8  ldc.i4.0
0x982a9  ldc.i4.0
0x982aa  ldc.i4.0
0x982ab  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x982b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x982b5  ldloc.0
0x982b6  ldstr    aContentmarket// "@ContentMarket"
0x982bb  ldc.i4.s 0xC
0x982bd  ldc.i4.s 0xA
0x982bf  ldc.i4.0
0x982c0  ldc.i4.0
0x982c1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x982c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x982cb  ldloc.0
0x982cc  ldstr    aAssetid// "@AssetId"
0x982d1  ldc.i4.s 0xC
0x982d3  ldc.i4.s 0x10
0x982d5  ldc.i4.0
0x982d6  ldc.i4.0
0x982d7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x982dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x982e1  ldloc.0
0x982e2  ldstr    aTempiconurl// "@TempIconUrl"
0x982e7  ldc.i4.s 0xC
0x982e9  ldc.i4   0x820
0x982ee  ldc.i4.0
0x982ef  ldc.i4.0
0x982f0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x982f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x982fa  ldloc.0
0x982fb  ldstr    aSiteid_1// "@SiteId"
0x98300  ldc.i4.s 0xE
0x98302  ldc.i4.0
0x98303  ldc.i4.0
0x98304  ldc.i4.0
0x98305  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9830a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9830f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x98314  stloc.0
0x98315  ldarg.0
0x98316  ldstr    aProcAppCreatea_0// "proc_App_CreateAppInstallation"
0x9831b  ldloc.0
0x9831c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x98321  ldloc.0
0x98322  ldstr    aReturnValue// "@RETURN_VALUE"
0x98327  ldc.i4.8
0x98328  ldc.i4.0
0x98329  ldc.i4.1
0x9832a  ldc.i4.0
0x9832b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98330  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98335  ldloc.0
0x98336  ldstr    aSourceinfoid// "@SourceInfoId"
0x9833b  ldc.i4.s 0xE
0x9833d  ldc.i4.0
0x9833e  ldc.i4.0
0x9833f  ldc.i4.0
0x98340  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98345  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9834a  ldloc.0
0x9834b  ldstr    aWebid_0// "@WebId"
0x98350  ldc.i4.s 0xE
0x98352  ldc.i4.0
0x98353  ldc.i4.0
0x98354  ldc.i4.0
0x98355  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9835a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9835f  ldloc.0
0x98360  ldstr    aSiteid_1// "@SiteId"
0x98365  ldc.i4.s 0xE
0x98367  ldc.i4.0
0x98368  ldc.i4.0
0x98369  ldc.i4.0
0x9836a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9836f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98374  ldloc.0
0x98375  ldstr    aSitesubscripti_2// "@SiteSubscriptionId"
0x9837a  ldc.i4.s 0xE
0x9837c  ldc.i4.0
0x9837d  ldc.i4.0
0x9837e  ldc.i4.0
0x9837f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98384  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98389  ldloc.0
0x9838a  ldstr    aCreatorid// "@CreatorId"
0x9838f  ldc.i4.8
0x98390  ldc.i4.0
0x98391  ldc.i4.0
0x98392  ldc.i4.0
0x98393  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98398  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9839d  ldloc.0
0x9839e  ldstr    aInstallationlo// "@InstallationLocale"
0x983a3  ldc.i4.8
0x983a4  ldc.i4.0
0x983a5  ldc.i4.0
0x983a6  ldc.i4.0
0x983a7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x983ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x983b1  ldloc.0
0x983b2  ldstr    aInstallationid// "@InstallationId"
0x983b7  ldc.i4.s 0xE
0x983b9  ldc.i4.0
0x983ba  ldc.i4.1
0x983bb  ldc.i4.0
0x983bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x983c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x983c6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x983cb  stloc.0
0x983cc  ldarg.0
0x983cd  ldstr    aProcAppCreatej// "proc_App_CreateJob"
0x983d2  ldloc.0
0x983d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x983d8  ldloc.0
0x983d9  ldstr    aReturnValue// "@RETURN_VALUE"
0x983de  ldc.i4.8
0x983df  ldc.i4.0
0x983e0  ldc.i4.1
0x983e1  ldc.i4.0
0x983e2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x983e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x983ec  ldloc.0
0x983ed  ldstr    aSiteid_1// "@SiteId"
0x983f2  ldc.i4.s 0xE
0x983f4  ldc.i4.0
0x983f5  ldc.i4.0
0x983f6  ldc.i4.0
0x983f7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x983fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98401  ldloc.0
0x98402  ldstr    aInstallationid// "@InstallationId"
0x98407  ldc.i4.s 0xE
0x98409  ldc.i4.0
0x9840a  ldc.i4.0
0x9840b  ldc.i4.0
0x9840c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x98411  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x98416  ldloc.0
0x98417  ldstr    aJobid// "@JobId"
0x9841c  ldc.i4.s 0xE
0x9841e  ldc.i4.0
0x9841f  ldc.i4.1
0x98420  ldc.i4.0
  ... truncated ...
```
