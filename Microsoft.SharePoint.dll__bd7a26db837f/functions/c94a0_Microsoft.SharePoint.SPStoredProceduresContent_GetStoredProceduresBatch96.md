# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch96

- ea: `0xc94a0`
- end: `0xca3d9`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch96`
- size: `3897`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0xc9759`: `proc_SetSitesHighWriteVolumeFlag`
- `0xc97a1`: `@IncJobRewindPosTokenName`
- `0xc97f6`: `@HVRewindPosTokenName`
- `0xc9a0b`: `@DeleteAllStreams`
- `0xca256`: `@DeleteAllStreams`
- `0xca373`: `@DeleteAllStreams`
- `0xc9fd6`: `@BSNToDelete0`
- `0xc9fea`: `@BSNToDelete1`
- `0xc9ffe`: `@BSNToDelete2`
- `0xca012`: `@BSNToDelete3`
- `0xca026`: `@BSNToDelete4`
- `0xca03a`: `@BSNToDelete5`
- `0xca04e`: `@BSNToDelete6`
- `0xca062`: `@BSNToDelete7`
- `0xca076`: `@BSNToDelete8`
- `0xca08a`: `@BSNToDelete9`
- `0xca09e`: `@BSNToDelete10`
- `0xca0b2`: `@BSNToDelete11`
- `0xca0c6`: `@BSNToDelete12`
- `0xca0da`: `@BSNToDelete13`
- `0xca0ee`: `@BSNToDelete14`
- `0xca102`: `@BSNToDelete15`
- `0xca116`: `@BSNToDelete16`
- `0xca12a`: `@BSNToDelete17`
- `0xca13e`: `@BSNToDelete18`
- `0xca152`: `@BSNToDelete19`
- `0xca166`: `@BSNToDelete20`
- `0xca17a`: `@BSNToDelete21`
- `0xca18e`: `@BSNToDelete22`
- `0xca1a2`: `@BSNToDelete23`
- `0xca1b6`: `@BSNToDelete24`
- `0xca1ca`: `@BSNToDelete25`
- `0xca1de`: `@BSNToDelete26`
- `0xca1f2`: `@BSNToDelete27`
- `0xca206`: `@BSNToDelete28`
- `0xca21a`: `@BSNToDelete29`
- `0xca22e`: `@BSNToDelete30`
- `0xca242`: `@BSNToDelete31`
- `0xca3b0`: `@StreamsToMoveFromContentAlloc`

## pseudocode

```c

```

## disassembly

```asm
0xc94a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc94a5  stloc.0
0xc94a6  ldarg.0
0xc94a7  ldstr    aProcSetsitequo// "proc_SetSiteQuota"
0xc94ac  ldloc.0
0xc94ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc94b2  ldloc.0
0xc94b3  ldstr    aReturnValue// "@RETURN_VALUE"
0xc94b8  ldc.i4.8
0xc94b9  ldc.i4.0
0xc94ba  ldc.i4.1
0xc94bb  ldc.i4.0
0xc94bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc94c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc94c6  ldloc.0
0xc94c7  ldstr    aWebsiteid// "@WebSiteId"
0xc94cc  ldc.i4.s 0xE
0xc94ce  ldc.i4.0
0xc94cf  ldc.i4.0
0xc94d0  ldc.i4.0
0xc94d1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc94d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc94db  ldloc.0
0xc94dc  ldstr    aQuotaid_0// "@quotaId"
0xc94e1  ldc.i4.s 0x10
0xc94e3  ldc.i4.0
0xc94e4  ldc.i4.0
0xc94e5  ldc.i4.0
0xc94e6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc94eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc94f0  ldloc.0
0xc94f1  ldstr    aDiskquota_0// "@diskQuota"
0xc94f6  ldc.i4.0
0xc94f7  ldc.i4.0
0xc94f8  ldc.i4.0
0xc94f9  ldc.i4.0
0xc94fa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc94ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9504  ldloc.0
0xc9505  ldstr    aDiskwarning_0// "@diskWarning"
0xc950a  ldc.i4.0
0xc950b  ldc.i4.0
0xc950c  ldc.i4.0
0xc950d  ldc.i4.0
0xc950e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9513  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9518  ldloc.0
0xc9519  ldstr    aUserquota_1// "@userQuota"
0xc951e  ldc.i4.8
0xc951f  ldc.i4.0
0xc9520  ldc.i4.0
0xc9521  ldc.i4.0
0xc9522  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9527  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc952c  ldloc.0
0xc952d  ldstr    aResourceusagem_0// "@resourceUsageMaximum"
0xc9532  ldc.i4.6
0xc9533  ldc.i4.0
0xc9534  ldc.i4.0
0xc9535  ldc.i4.0
0xc9536  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc953b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9540  ldloc.0
0xc9541  ldstr    aResourceusagew_0// "@resourceUsageWarning"
0xc9546  ldc.i4.6
0xc9547  ldc.i4.0
0xc9548  ldc.i4.0
0xc9549  ldc.i4.0
0xc954a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc954f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9554  ldloc.0
0xc9555  ldstr    aRequestguid// "@RequestGuid"
0xc955a  ldc.i4.s 0xE
0xc955c  ldc.i4.0
0xc955d  ldc.i4.1
0xc955e  ldc.i4.1
0xc955f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9564  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9569  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc956e  stloc.0
0xc956f  ldarg.0
0xc9570  ldstr    aProcSetsitered// "proc_SetSiteRedirectUrl"
0xc9575  ldloc.0
0xc9576  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc957b  ldloc.0
0xc957c  ldstr    aReturnValue// "@RETURN_VALUE"
0xc9581  ldc.i4.8
0xc9582  ldc.i4.0
0xc9583  ldc.i4.1
0xc9584  ldc.i4.0
0xc9585  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc958a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc958f  ldloc.0
0xc9590  ldstr    aSiteid_1// "@SiteId"
0xc9595  ldc.i4.s 0xE
0xc9597  ldc.i4.0
0xc9598  ldc.i4.0
0xc9599  ldc.i4.0
0xc959a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc959f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc95a4  ldloc.0
0xc95a5  ldstr    aRedirecturl// "@RedirectUrl"
0xc95aa  ldc.i4.s 0xC
0xc95ac  ldc.i4   0x190
0xc95b1  ldc.i4.0
0xc95b2  ldc.i4.0
0xc95b3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc95b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc95bd  ldloc.0
0xc95be  ldstr    aRequestguid// "@RequestGuid"
0xc95c3  ldc.i4.s 0xE
0xc95c5  ldc.i4.0
0xc95c6  ldc.i4.1
0xc95c7  ldc.i4.1
0xc95c8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc95cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc95d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc95d7  stloc.0
0xc95d8  ldarg.0
0xc95d9  ldstr    aProcSetsiteses// "proc_SetSiteSession"
0xc95de  ldloc.0
0xc95df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc95e4  ldloc.0
0xc95e5  ldstr    aReturnValue// "@RETURN_VALUE"
0xc95ea  ldc.i4.8
0xc95eb  ldc.i4.0
0xc95ec  ldc.i4.1
0xc95ed  ldc.i4.0
0xc95ee  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc95f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc95f8  ldloc.0
0xc95f9  ldstr    aSiteid_1// "@SiteId"
0xc95fe  ldc.i4.s 0xE
0xc9600  ldc.i4.0
0xc9601  ldc.i4.0
0xc9602  ldc.i4.0
0xc9603  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9608  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc960d  ldloc.0
0xc960e  ldstr    aSessionid_0// "@SessionId"
0xc9613  ldc.i4.s 0xC
0xc9615  ldc.i4.s 0x64
0xc9617  ldc.i4.0
0xc9618  ldc.i4.0
0xc9619  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc961e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9623  ldloc.0
0xc9624  ldstr    aExpiration// "@Expiration"
0xc9629  ldc.i4.4
0xc962a  ldc.i4.0
0xc962b  ldc.i4.0
0xc962c  ldc.i4.0
0xc962d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9632  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9637  ldloc.0
0xc9638  ldstr    aSessionitems// "@SessionItems"
0xc963d  ldstr    aContent// "Content"
0xc9642  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xc9647  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xc964c  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xc9651  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xc9656  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xc965b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9660  ldloc.0
0xc9661  ldstr    aSessionslimit// "@SessionsLimit"
0xc9666  ldc.i4.8
0xc9667  ldc.i4.0
0xc9668  ldc.i4.0
0xc9669  ldc.i4.1
0xc966a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc966f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9674  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc9679  stloc.0
0xc967a  ldarg.0
0xc967b  ldstr    aProcSetsiteses_0// "proc_SetSiteSessionData"
0xc9680  ldloc.0
0xc9681  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc9686  ldloc.0
0xc9687  ldstr    aReturnValue// "@RETURN_VALUE"
0xc968c  ldc.i4.8
0xc968d  ldc.i4.0
0xc968e  ldc.i4.1
0xc968f  ldc.i4.0
0xc9690  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9695  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc969a  ldloc.0
0xc969b  ldstr    aSiteid_1// "@SiteId"
0xc96a0  ldc.i4.s 0xE
0xc96a2  ldc.i4.0
0xc96a3  ldc.i4.0
0xc96a4  ldc.i4.0
0xc96a5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc96aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc96af  ldloc.0
0xc96b0  ldstr    aSessiondataid// "@SessionDataId"
0xc96b5  ldc.i4.s 0xE
0xc96b7  ldc.i4.0
0xc96b8  ldc.i4.0
0xc96b9  ldc.i4.0
0xc96ba  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc96bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc96c4  ldloc.0
0xc96c5  ldstr    aSessionitems// "@SessionItems"
0xc96ca  ldstr    aContent// "Content"
0xc96cf  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xc96d4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xc96d9  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xc96de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xc96e3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xc96e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc96ed  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc96f2  stloc.0
0xc96f3  ldarg.0
0xc96f4  ldstr    aProcSetsitesha// "proc_SetSiteSharingProperties"
0xc96f9  ldloc.0
0xc96fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc96ff  ldloc.0
0xc9700  ldstr    aReturnValue// "@RETURN_VALUE"
0xc9705  ldc.i4.8
0xc9706  ldc.i4.0
0xc9707  ldc.i4.1
0xc9708  ldc.i4.0
0xc9709  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc970e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9713  ldloc.0
0xc9714  ldstr    aSiteid_1// "@SiteId"
0xc9719  ldc.i4.s 0xE
0xc971b  ldc.i4.0
0xc971c  ldc.i4.0
0xc971d  ldc.i4.0
0xc971e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9723  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9728  ldloc.0
0xc9729  ldstr    aSharingpropert// "@SharingProperties"
0xc972e  ldc.i4.s 0xC
0xc9730  ldc.i4.m1
0xc9731  ldc.i4.0
0xc9732  ldc.i4.0
0xc9733  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9738  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc973d  ldloc.0
0xc973e  ldstr    aRequestguid// "@RequestGuid"
0xc9743  ldc.i4.s 0xE
0xc9745  ldc.i4.0
0xc9746  ldc.i4.1
0xc9747  ldc.i4.1
0xc9748  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc974d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9752  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc9757  stloc.0
0xc9758  ldarg.0
0xc9759  ldstr    aProcSetsiteshi// "proc_SetSitesHighWriteVolumeFlag"
0xc975e  ldloc.0
0xc975f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc9764  ldloc.0
0xc9765  ldstr    aReturnValue// "@RETURN_VALUE"
0xc976a  ldc.i4.8
0xc976b  ldc.i4.0
0xc976c  ldc.i4.1
0xc976d  ldc.i4.0
0xc976e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9773  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc9778  ldloc.0
0xc9779  ldstr    aDaystoanalyze// "@DaysToAnalyze"
0xc977e  ldc.i4.8
0xc977f  ldc.i4.0
0xc9780  ldc.i4.0
0xc9781  ldc.i4.0
0xc9782  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc9787  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc978c  ldloc.0
0xc978d  ldstr    aLastchangetime// "@LastChangeTime"
0xc9792  ldc.i4.4
0xc9793  ldc.i4.0
0xc9794  ldc.i4.0
0xc9795  ldc.i4.0
0xc9796  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc979b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc97a0  ldloc.0
0xc97a1  ldstr    aIncjobrewindpo// "@IncJobRewindPosTokenName"
0xc97a6  ldc.i4.s 0xC
0xc97a8  ldc.i4   0x104
0xc97ad  ldc.i4.0
0xc97ae  ldc.i4.0
0xc97af  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc97b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc97b9  ldloc.0
0xc97ba  ldstr    aThresholdevent// "@ThresholdEventCount"
0xc97bf  ldc.i4.8
0xc97c0  ldc.i4.0
0xc97c1  ldc.i4.0
0xc97c2  ldc.i4.0
0xc97c3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc97c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc97cd  ldloc.0
0xc97ce  ldstr    aMaxhvsiteperce// "@MaxHVSitePercentage"
0xc97d3  ldc.i4.8
0xc97d4  ldc.i4.0
0xc97d5  ldc.i4.0
0xc97d6  ldc.i4.0
  ... truncated ...
```
