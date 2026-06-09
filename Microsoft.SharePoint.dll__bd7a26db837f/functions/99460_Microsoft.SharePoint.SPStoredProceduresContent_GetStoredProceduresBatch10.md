# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch10

- ea: `0x99460`
- end: `0x99953`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch10`
- size: `1267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0x998c9`: `@InstallationId`
- `0x997b7`: `@AppInstallationId`
- `0x9981d`: `@AppInstallationId`
- `0x9952e`: `@TaskId`
- `0x9963c`: `@TaskId`
- `0x995a8`: `@TaskType`
- `0x998de`: `@TaskType`
- `0x99543`: `@DependsOnTaskId`
- `0x99573`: `proc_App_RegisterTask`
- `0x995c1`: `@TaskData`
- `0x995ff`: `@TaskOperation`
- `0x99613`: `@IsRollback`
- `0x99657`: `proc_App_RemoveAppRuntimeMetadata`
- `0x996a7`: `proc_App_RemoveInactiveRuntimeIcons`
- `0x996f7`: `proc_App_RemoveRuntimeIcon`
- `0x99797`: `proc_App_SetAppDatabaseLastAccessedDate`
- `0x997e1`: `@LastAccessedDate`
- `0x998a9`: `proc_App_SetAppInstallationProperty`

## pseudocode

```c

```

## disassembly

```asm
0x99460  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x99465  stloc.0
0x99466  ldarg.0
0x99467  ldstr    aProcAppRecycle// "proc_App_Recycle"
0x9946c  ldloc.0
0x9946d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x99472  ldloc.0
0x99473  ldstr    aReturnValue// "@RETURN_VALUE"
0x99478  ldc.i4.8
0x99479  ldc.i4.0
0x9947a  ldc.i4.1
0x9947b  ldc.i4.0
0x9947c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99481  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99486  ldloc.0
0x99487  ldstr    aAppinstanceid// "@AppInstanceId"
0x9948c  ldc.i4.s 0xE
0x9948e  ldc.i4.0
0x9948f  ldc.i4.0
0x99490  ldc.i4.0
0x99491  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99496  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9949b  ldloc.0
0x9949c  ldstr    aTitle// "@Title"
0x994a1  ldc.i4.s 0xC
0x994a3  ldc.i4   0x200
0x994a8  ldc.i4.0
0x994a9  ldc.i4.0
0x994aa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x994af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x994b4  ldloc.0
0x994b5  ldstr    aSiteid_1// "@SiteId"
0x994ba  ldc.i4.s 0xE
0x994bc  ldc.i4.0
0x994bd  ldc.i4.0
0x994be  ldc.i4.0
0x994bf  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x994c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x994c9  ldloc.0
0x994ca  ldstr    aWebid_0// "@WebId"
0x994cf  ldc.i4.s 0xE
0x994d1  ldc.i4.0
0x994d2  ldc.i4.0
0x994d3  ldc.i4.0
0x994d4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x994d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x994de  ldloc.0
0x994df  ldstr    aUserid_1// "@UserId"
0x994e4  ldc.i4.8
0x994e5  ldc.i4.0
0x994e6  ldc.i4.0
0x994e7  ldc.i4.0
0x994e8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x994ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x994f2  ldloc.0
0x994f3  ldstr    aRecyclebinitem// "@RecycleBinItemId"
0x994f8  ldc.i4.s 0xE
0x994fa  ldc.i4.0
0x994fb  ldc.i4.1
0x994fc  ldc.i4.0
0x994fd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99502  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99507  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9950c  stloc.0
0x9950d  ldarg.0
0x9950e  ldstr    aProcAppRegiste// "proc_App_RegisterDependency"
0x99513  ldloc.0
0x99514  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x99519  ldloc.0
0x9951a  ldstr    aReturnValue// "@RETURN_VALUE"
0x9951f  ldc.i4.8
0x99520  ldc.i4.0
0x99521  ldc.i4.1
0x99522  ldc.i4.0
0x99523  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99528  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9952d  ldloc.0
0x9952e  ldstr    aTaskid// "@TaskId"
0x99533  ldc.i4.s 0xE
0x99535  ldc.i4.0
0x99536  ldc.i4.0
0x99537  ldc.i4.0
0x99538  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9953d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99542  ldloc.0
0x99543  ldstr    aDependsontaski// "@DependsOnTaskId"
0x99548  ldc.i4.s 0xE
0x9954a  ldc.i4.0
0x9954b  ldc.i4.0
0x9954c  ldc.i4.0
0x9954d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99552  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99557  ldloc.0
0x99558  ldstr    aSiteid_1// "@SiteId"
0x9955d  ldc.i4.s 0xE
0x9955f  ldc.i4.0
0x99560  ldc.i4.0
0x99561  ldc.i4.0
0x99562  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99567  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9956c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x99571  stloc.0
0x99572  ldarg.0
0x99573  ldstr    aProcAppRegiste_0// "proc_App_RegisterTask"
0x99578  ldloc.0
0x99579  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9957e  ldloc.0
0x9957f  ldstr    aReturnValue// "@RETURN_VALUE"
0x99584  ldc.i4.8
0x99585  ldc.i4.0
0x99586  ldc.i4.1
0x99587  ldc.i4.0
0x99588  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9958d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99592  ldloc.0
0x99593  ldstr    aJobid// "@JobId"
0x99598  ldc.i4.s 0xE
0x9959a  ldc.i4.0
0x9959b  ldc.i4.0
0x9959c  ldc.i4.0
0x9959d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x995a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x995a7  ldloc.0
0x995a8  ldstr    aTasktype// "@TaskType"
0x995ad  ldc.i4.s 0xC
0x995af  ldc.i4   0xFF
0x995b4  ldc.i4.0
0x995b5  ldc.i4.0
0x995b6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x995bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x995c0  ldloc.0
0x995c1  ldstr    aTaskdata// "@TaskData"
0x995c6  ldc.i4.s 0x15
0x995c8  ldc.i4.m1
0x995c9  ldc.i4.0
0x995ca  ldc.i4.0
0x995cb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x995d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x995d5  ldloc.0
0x995d6  ldstr    aEstimateddurat// "@EstimatedDurationMinutes"
0x995db  ldc.i4.8
0x995dc  ldc.i4.0
0x995dd  ldc.i4.0
0x995de  ldc.i4.0
0x995df  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x995e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x995e9  ldloc.0
0x995ea  ldstr    aSiteid_1// "@SiteId"
0x995ef  ldc.i4.s 0xE
0x995f1  ldc.i4.0
0x995f2  ldc.i4.0
0x995f3  ldc.i4.0
0x995f4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x995f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x995fe  ldloc.0
0x995ff  ldstr    aTaskoperation// "@TaskOperation"
0x99604  ldc.i4.8
0x99605  ldc.i4.0
0x99606  ldc.i4.0
0x99607  ldc.i4.0
0x99608  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9960d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99612  ldloc.0
0x99613  ldstr    aIsrollback// "@IsRollback"
0x99618  ldc.i4.2
0x99619  ldc.i4.0
0x9961a  ldc.i4.0
0x9961b  ldc.i4.0
0x9961c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99621  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99626  ldloc.0
0x99627  ldstr    aIsolationkey// "@IsolationKey"
0x9962c  ldc.i4.s 0xE
0x9962e  ldc.i4.0
0x9962f  ldc.i4.0
0x99630  ldc.i4.0
0x99631  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99636  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9963b  ldloc.0
0x9963c  ldstr    aTaskid// "@TaskId"
0x99641  ldc.i4.s 0xE
0x99643  ldc.i4.0
0x99644  ldc.i4.1
0x99645  ldc.i4.0
0x99646  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9964b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99650  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x99655  stloc.0
0x99656  ldarg.0
0x99657  ldstr    aProcAppRemovea// "proc_App_RemoveAppRuntimeMetadata"
0x9965c  ldloc.0
0x9965d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x99662  ldloc.0
0x99663  ldstr    aReturnValue// "@RETURN_VALUE"
0x99668  ldc.i4.8
0x99669  ldc.i4.0
0x9966a  ldc.i4.1
0x9966b  ldc.i4.0
0x9966c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99671  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99676  ldloc.0
0x99677  ldstr    aAppinstanceid// "@AppInstanceId"
0x9967c  ldc.i4.s 0xE
0x9967e  ldc.i4.0
0x9967f  ldc.i4.0
0x99680  ldc.i4.0
0x99681  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99686  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9968b  ldloc.0
0x9968c  ldstr    aSiteid_1// "@SiteId"
0x99691  ldc.i4.s 0xE
0x99693  ldc.i4.0
0x99694  ldc.i4.0
0x99695  ldc.i4.0
0x99696  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9969b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x996a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x996a5  stloc.0
0x996a6  ldarg.0
0x996a7  ldstr    aProcAppRemovei// "proc_App_RemoveInactiveRuntimeIcons"
0x996ac  ldloc.0
0x996ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x996b2  ldloc.0
0x996b3  ldstr    aReturnValue// "@RETURN_VALUE"
0x996b8  ldc.i4.8
0x996b9  ldc.i4.0
0x996ba  ldc.i4.1
0x996bb  ldc.i4.0
0x996bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x996c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x996c6  ldloc.0
0x996c7  ldstr    aSiteid_1// "@SiteId"
0x996cc  ldc.i4.s 0xE
0x996ce  ldc.i4.0
0x996cf  ldc.i4.0
0x996d0  ldc.i4.0
0x996d1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x996d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x996db  ldloc.0
0x996dc  ldstr    aAppinstanceid// "@AppInstanceId"
0x996e1  ldc.i4.s 0xE
0x996e3  ldc.i4.0
0x996e4  ldc.i4.0
0x996e5  ldc.i4.0
0x996e6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x996eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x996f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x996f5  stloc.0
0x996f6  ldarg.0
0x996f7  ldstr    aProcAppRemover// "proc_App_RemoveRuntimeIcon"
0x996fc  ldloc.0
0x996fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x99702  ldloc.0
0x99703  ldstr    aReturnValue// "@RETURN_VALUE"
0x99708  ldc.i4.8
0x99709  ldc.i4.0
0x9970a  ldc.i4.1
0x9970b  ldc.i4.0
0x9970c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99711  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99716  ldloc.0
0x99717  ldstr    aSiteid_1// "@SiteId"
0x9971c  ldc.i4.s 0xE
0x9971e  ldc.i4.0
0x9971f  ldc.i4.0
0x99720  ldc.i4.0
0x99721  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99726  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9972b  ldloc.0
0x9972c  ldstr    aIconid// "@IconId"
0x99731  ldc.i4.s 0xE
0x99733  ldc.i4.0
0x99734  ldc.i4.0
0x99735  ldc.i4.0
0x99736  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9973b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99740  ldloc.0
0x99741  ldstr    aAppinstanceid// "@AppInstanceId"
0x99746  ldc.i4.s 0xE
0x99748  ldc.i4.0
0x99749  ldc.i4.0
0x9974a  ldc.i4.0
0x9974b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99750  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x99755  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9975a  stloc.0
0x9975b  ldarg.0
0x9975c  ldstr    aProcAppRestore// "proc_App_RestoreFromRecycleBin"
0x99761  ldloc.0
0x99762  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x99767  ldloc.0
0x99768  ldstr    aReturnValue// "@RETURN_VALUE"
0x9976d  ldc.i4.8
0x9976e  ldc.i4.0
0x9976f  ldc.i4.1
0x99770  ldc.i4.0
0x99771  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x99776  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9977b  ldloc.0
0x9977c  ldstr    aRecyclebinitem// "@RecycleBinItemId"
  ... truncated ...
```
