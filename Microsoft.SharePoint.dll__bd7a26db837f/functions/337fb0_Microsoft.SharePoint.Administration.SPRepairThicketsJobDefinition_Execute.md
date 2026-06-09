# Microsoft.SharePoint.Administration.SPRepairThicketsJobDefinition::Execute

- ea: `0x337fb0`
- end: `0x338720`
- name: `Microsoft.SharePoint.Administration.SPRepairThicketsJobDefinition::Execute`
- size: `1904`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c8480`
- `0x1c8540`
- `0x1c8720`
- `0x1c89e0`
- `0x1cafb0`
- `0x1cafc0`
- `0x263de0`
- `0x263e60`
- `0x266130`
- `0x266420`
- `0x269af0`
- `0x26b480`
- `0x26b840`
- `0x26e7a0`
- `0x29d070`
- `0x29d0f0`
- `0x2c4c60`
- `0x337fb0`
- `0x338730`
- `0x3387c0`
- `0x338840`
- `0x338a60`
- `0x338ad0`
- `0x338ae0`
- `0x338d10`
- `0x5c0850`
- `0x5c3eb0`
- `0x93dae0`
- `0x957470`
- `0x957490`

## string_xrefs

- `0x337fba`: `SPRepairThicketsJobDefinition`
- `0x33870f`: `SPRepairThicketsJobDefinition`
- `0x337fd7`: `Skipping SPRepairThicketsJobDefinition job for database {0}, because it was unable to acquire HighActivityLock.`
- `0x338005`: `RepairThicketsJobLastProcessedTime`
- `0x338600`: `RepairThicketsJobLastProcessedTime`
- `0x338047`: `RepairThicketsRefreshInternal`
- `0x33805a`: `RepairThicketsRefreshInternal`
- `0x3380c4`: `SPRepairThickets.Execute: Skipping database {0} Id: {1} because it was processed {2} days ago.`
- `0x338125`: `SPRepairThickets.Execute: QueryResults content database {0} Id: {1} File Count: {2}`
- `0x338188`: `SPRepairThickets.Execute: FetchLimit reached on content database {0} Id: {1} File Count: {2}`
- `0x33838c`: `SPRepairThickets.Execute. Failure during web initialization. SiteId: {0} WebId: {1} Exception: {2}`
- `0x33841c`: `SPRepairThickets.Execute: Tenant being skipped because it is not enabled. SubscriptionId: {0}`
- `0x33845d`: `SPRepairThickets.Execute: System asks for stop on content database {0} Id: {1} Sites Processed: {2} Files Repaired: {3} Errors: {4}`
- `0x3384ff`: `SPRepairThickets.Execute. Failure during orphan repair. SiteId: {0} WebId: {1} UniqueId: {2} Exception: {3}`
- `0x3385c1`: `SPRepairThickets.Execute: Completed content database {0} Id: {1}`
- `0x338634`: `SPRepairThickets.Execute: Not completed content database {0} Id: {1}`
- `0x338686`: `SPRepairThickets.Execute: Finished on content database {0} Id: {1} Sites Processed: {2} Files Repaired: {3} Errors: {4}`
- `0x3386eb`: `SPRepairThickets.Execute: Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x337fb0  ldarg.1
0x337fb1  call     bool Microsoft.SharePoint.Administration.SPContentDatabaseJobDefinition::CanProcessContentDatabase(class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x337fb6  brtrue.s loc_337FB9
0x337fb8  ret
0x337fb9  ldarg.1
0x337fba  ldstr    aSprepairthicke// "SPRepairThicketsJobDefinition"
0x337fbf  ldstr    aHighactivitylo_8// "HighActivityLock"
0x337fc4  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::AcquireUnsafeHighActivityLock(string activityName, [opt] string lockName)
0x337fc9  brtrue.s loc_337FF6
0x337fcb  ldc.i4   0x12A0094
0x337fd0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Health()
0x337fd5  ldc.i4.s 0x32
0x337fd7  ldstr    aSkippingSprepa// "Skipping SPRepairThicketsJobDefinition "...
0x337fdc  ldc.i4.1
0x337fdd  newarr   [mscorlib]System.Object
0x337fe2  stloc.s  0x20
0x337fe4  ldloc.s  0x20
0x337fe6  ldc.i4.0
0x337fe7  ldarg.1
0x337fe8  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x337fed  stelem.ref
0x337fee  ldloc.s  0x20
0x337ff0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x337ff5  ret
0x337ff6  ldc.i4.0
0x337ff7  stloc.0
0x337ff8  ldc.i4.0
0x337ff9  stloc.1
0x337ffa  ldc.i4.0
0x337ffb  stloc.2
0x337ffc  ldc.i4.0
0x337ffd  stloc.3
0x337ffe  ldc.i4.0
0x337fff  stloc.s  4
0x338001  ldc.i4.0
0x338002  stloc.s  5
0x338004  ldarg.1
0x338005  ldstr    aRepairthickets// "RepairThicketsJobLastProcessedTime"
0x33800a  callvirt instance string Microsoft.SharePoint.Administration.SPContentDatabase::GetDatabaseInformation(string name)
0x33800f  stloc.s  6
0x338011  ldc.i4.0
0x338012  conv.i8
0x338013  stloc.s  7
0x338015  ldloc.s  6
0x338017  ldloca.s 7
0x338019  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x33801e  pop
0x33801f  ldloc.s  7
0x338021  ldc.i4.0
0x338022  conv.i8
0x338023  beq      loc_338110
0x338028  ldc.i4   0xB4
0x33802d  stloc.s  8
0x33802f  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x338034  stloc.s  9
0x338036  ldloc.s  9
0x338038  ldnull
0x338039  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33803e  brfalse.s loc_33807E
0x338040  ldloc.s  9
0x338042  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x338047  ldstr    aRepairthickets_0// "RepairThicketsRefreshInternal"
0x33804c  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x338051  brfalse.s loc_33807E
0x338053  ldloc.s  9
0x338055  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x33805a  ldstr    aRepairthickets_0// "RepairThicketsRefreshInternal"
0x33805f  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x338064  isinst   [mscorlib]System.String
0x338069  stloc.s  0xA
0x33806b  ldloc.s  0xA
0x33806d  brfalse.s loc_33807E
0x33806f  ldloc.s  0xA
0x338071  ldloca.s 0xB
0x338073  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x338078  brfalse.s loc_33807E
0x33807a  ldloc.s  0xB
0x33807c  stloc.s  8
0x33807e  ldloca.s 0xC
0x338080  ldloc.s  7
0x338082  ldc.i4.1
0x338083  call     instance void [mscorlib]System.DateTime::.ctor(int64, valuetype [mscorlib]System.DateTimeKind)
0x338088  ldloca.s 0xC
0x33808a  ldloc.s  8
0x33808c  conv.r8
0x33808d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x338092  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x338097  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x33809c  brfalse.s loc_338110
0x33809e  ldc.i4   0x43B
0x3380a3  call     bool Microsoft.SharePoint.Administration.SPFarm::CheckFlag(valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ServerDebugFlags flag)
0x3380a8  brtrue.s loc_338110
0x3380aa  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3380af  ldloc.s  0xC
0x3380b1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3380b6  stloc.s  0xD
0x3380b8  ldc.i4   0x12A0095
0x3380bd  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x3380c2  ldc.i4.s 0x32
0x3380c4  ldstr    aSprepairthicke_0// "SPRepairThickets.Execute: Skipping data"...
0x3380c9  ldc.i4.3
0x3380ca  newarr   [mscorlib]System.Object
0x3380cf  stloc.s  0x21
0x3380d1  ldloc.s  0x21
0x3380d3  ldc.i4.0
0x3380d4  ldarg.1
0x3380d5  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3380da  stelem.ref
0x3380db  ldloc.s  0x21
0x3380dd  ldc.i4.1
0x3380de  ldarg.1
0x3380df  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3380e4  stloc.s  0x22
0x3380e6  ldloca.s 0x22
0x3380e8  constrained. [mscorlib]System.Guid
0x3380ee  callvirt instance string [mscorlib]System.Object::ToString()
0x3380f3  stelem.ref
0x3380f4  ldloc.s  0x21
0x3380f6  ldc.i4.2
0x3380f7  ldloca.s 0xD
0x3380f9  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x3380fe  box      [mscorlib]System.Int32
0x338103  stelem.ref
0x338104  ldloc.s  0x21
0x338106  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x33810b  leave    loc_33871F
0x338110  ldarg.0
0x338111  ldarg.1
0x338112  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.SharePoint.Administration.SPRepairThicketsJobDefinition::GetOrphanFileBatch(class Microsoft.SharePoint.Administration.SPContentDatabase db)
0x338117  stloc.s  0xE
0x338119  ldc.i4   0x12A0096
0x33811e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x338123  ldc.i4.s 0x32
0x338125  ldstr    aSprepairthicke_1// "SPRepairThickets.Execute: QueryResults "...
0x33812a  ldc.i4.3
0x33812b  newarr   [mscorlib]System.Object
0x338130  stloc.s  0x23
0x338132  ldloc.s  0x23
0x338134  ldc.i4.0
0x338135  ldarg.1
0x338136  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x33813b  stelem.ref
0x33813c  ldloc.s  0x23
0x33813e  ldc.i4.1
0x33813f  ldarg.1
0x338140  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x338145  stloc.s  0x24
0x338147  ldloca.s 0x24
0x338149  constrained. [mscorlib]System.Guid
0x33814f  callvirt instance string [mscorlib]System.Object::ToString()
0x338154  stelem.ref
0x338155  ldloc.s  0x23
0x338157  ldc.i4.2
0x338158  ldloc.s  0xE
0x33815a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x33815f  box      [mscorlib]System.Int32
0x338164  stelem.ref
0x338165  ldloc.s  0x23
0x338167  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x33816c  ldloc.s  0xE
0x33816e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x338173  conv.i8
0x338174  ldarg.0
0x338175  call     instance int64 Microsoft.SharePoint.Administration.SPContentDatabaseJobDefinition::get_FetchLimit()
0x33817a  blt.s    loc_3381CF
0x33817c  ldc.i4   0x12A0097
0x338181  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x338186  ldc.i4.s 0xA
0x338188  ldstr    aSprepairthicke_2// "SPRepairThickets.Execute: FetchLimit re"...
0x33818d  ldc.i4.3
0x33818e  newarr   [mscorlib]System.Object
0x338193  stloc.s  0x25
0x338195  ldloc.s  0x25
0x338197  ldc.i4.0
0x338198  ldarg.1
0x338199  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x33819e  stelem.ref
0x33819f  ldloc.s  0x25
0x3381a1  ldc.i4.1
0x3381a2  ldarg.1
0x3381a3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3381a8  stloc.s  0x26
0x3381aa  ldloca.s 0x26
0x3381ac  constrained. [mscorlib]System.Guid
0x3381b2  callvirt instance string [mscorlib]System.Object::ToString()
0x3381b7  stelem.ref
0x3381b8  ldloc.s  0x25
0x3381ba  ldc.i4.2
0x3381bb  ldloc.s  0xE
0x3381bd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x3381c2  box      [mscorlib]System.Int32
0x3381c7  stelem.ref
0x3381c8  ldloc.s  0x25
0x3381ca  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x3381cf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381d4  stloc.s  0x10
0x3381d6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381db  stloc.s  0x11
0x3381dd  ldc.i4.0
0x3381de  stloc.s  0x12
0x3381e0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381e5  stloc.s  0x13
0x3381e7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381ec  stloc.s  0x14
0x3381ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381f3  stloc.s  0x15
0x3381f5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3381fa  stloc.s  0x16
0x3381fc  ldnull
0x3381fd  stloc.s  0x17
0x3381ff  ldnull
0x338200  stloc.s  0x18
0x338202  ldc.i4.0
0x338203  stloc.s  0xF
0x338205  br       loc_338559
0x33820a  ldloc.s  0xE
0x33820c  ldloc.s  0xF
0x33820e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x338213  castclass object[]
0x338218  stloc.s  0x19
0x33821a  ldloc.s  0x19
0x33821c  ldc.i4.0
0x33821d  conv.u
0x33821e  ldelem.ref
0x33821f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x338224  ldtoken  [mscorlib]System.Guid
0x338229  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33822e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x338233  brfalse.s loc_338243
0x338235  ldloc.s  0x19
0x338237  ldc.i4.0
0x338238  conv.u
0x338239  ldelem.ref
0x33823a  unbox.any [mscorlib]System.Guid
0x33823f  stloc.s  0x10
0x338241  br.s     loc_33824A
0x338243  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x338248  stloc.s  0x10
0x33824a  ldloc.s  0x19
0x33824c  ldc.i4.1
0x33824d  conv.u
0x33824e  ldelem.ref
0x33824f  unbox.any [mscorlib]System.Guid
0x338254  stloc.s  0x13
0x338256  ldloc.s  0x19
0x338258  ldc.i4.2
0x338259  conv.u
0x33825a  ldelem.ref
0x33825b  unbox.any [mscorlib]System.Guid
0x338260  stloc.s  0x15
0x338262  ldloc.s  0x19
0x338264  ldc.i4.3
0x338265  conv.u
0x338266  ldelem.ref
0x338267  unbox.any [mscorlib]System.Guid
0x33826c  stloc.s  0x16
0x33826e  ldloc.s  0x18
0x338270  brfalse.s loc_33828C
0x338272  ldloc.s  0x18
0x338274  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x338279  ldloc.s  0x15
0x33827b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x338280  brfalse.s loc_33828C
0x338282  ldloc.s  0x18
0x338284  callvirt instance void Microsoft.SharePoint.SPWeb::Dispose()
0x338289  ldnull
0x33828a  stloc.s  0x18
0x33828c  ldloc.s  0x14
0x33828e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x338293  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x338298  brfalse.s loc_3382B6
0x33829a  ldloc.s  0x14
0x33829c  ldloc.s  0x13
0x33829e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3382a3  brfalse.s loc_3382B6
0x3382a5  ldloc.s  0x17
0x3382a7  ldloc.s  0x14
0x3382a9  ldloc.3
0x3382aa  ldloc.s  5
0x3382ac  call     void Microsoft.SharePoint.Administration.SPRepairThicketsJobDefinition::LogSiteResults(class Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid siteId, int32 cFilesInSite, int32 cErrorsInSite)
0x3382b1  ldc.i4.0
0x3382b2  stloc.3
0x3382b3  ldc.i4.0
0x3382b4  stloc.s  5
0x3382b6  ldloc.s  0x12
0x3382b8  brfalse.s loc_3382D3
0x3382ba  ldloc.s  0x11
0x3382bc  ldloc.s  0x10
0x3382be  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3382c3  brfalse.s loc_3382D3
0x3382c5  ldloc.s  0x17
0x3382c7  ldloc.s  0x11
0x3382c9  ldloc.s  4
0x3382cb  call     void Microsoft.SharePoint.Administration.SPRepairThicketsJobDefinition::LogTenantResults(class Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid subscriptionId, int32 cFilesInTenant)
0x3382d0  ldc.i4.0
0x3382d1  stloc.s  4
0x3382d3  ldloc.s  0x17
0x3382d5  brfalse.s loc_3382FF
0x3382d7  ldloc.s  0x17
0x3382d9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
  ... truncated ...
```
