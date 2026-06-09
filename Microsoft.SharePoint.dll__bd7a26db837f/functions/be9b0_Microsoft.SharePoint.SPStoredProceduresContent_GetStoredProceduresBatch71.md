# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch71

- ea: `0xbe9b0`
- end: `0xbf55f`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch71`
- size: `2991`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0xbee6e`: `@AlertTemplateName`
- `0xbf162`: `@DeleteTransactionId`
- `0xbf257`: `@DeleteTransactionId`
- `0xbf3cf`: `@DeleteTransactionId`
- `0xbf0d3`: `@DeleteUserId`
- `0xbf178`: `@ChildDeleteTransactionId`
- `0xbf50b`: `@DeleteTransactionData`
- `0xbf51f`: `tvpDeleteTransactionData`
- `0xbf534`: `@FailedDeleteTransactionId`
- `0xbec04`: `@DGCacheVersion`
- `0xbec73`: `@SharingLinkSessionId`
- `0xbec89`: `@ReturnSharingLinkSessionClaims`
- `0xbf05a`: `@CreateOrphaned`
- `0xbea2a`: `@ItemsToBeUpdated`
- `0xbeacc`: `@ItemsToBeUpdated`
- `0xbea53`: `@ItemsToBeDeleted`
- `0xbeaf5`: `@ItemsToBeDeleted`
- `0xbef57`: `proc_MoveDataToOccurrence`
- `0xbf01e`: `@OverwriteToInstance`
- `0xbf032`: `@CreateMeetingEntry`
- `0xbf089`: `proc_MoveOneRecycleBinItemToThirdStage`
- `0xbf1d1`: `proc_MoveRecycleBinItemToSecondStage`
- `0xbf35d`: `proc_MoveRecycleBinItemToThirdStage`
- `0xbf485`: `proc_MoveRecycleBinItemTVPToThirdStage`

## pseudocode

```c

```

## disassembly

```asm
0xbe9b0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xbe9b5  stloc.0
0xbe9b6  ldarg.0
0xbe9b7  ldstr    aProcMergesites// "proc_MergeSiteSession"
0xbe9bc  ldloc.0
0xbe9bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xbe9c2  ldloc.0
0xbe9c3  ldstr    aReturnValue// "@RETURN_VALUE"
0xbe9c8  ldc.i4.8
0xbe9c9  ldc.i4.0
0xbe9ca  ldc.i4.1
0xbe9cb  ldc.i4.0
0xbe9cc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbe9d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbe9d6  ldloc.0
0xbe9d7  ldstr    aSiteid_1// "@SiteId"
0xbe9dc  ldc.i4.s 0xE
0xbe9de  ldc.i4.0
0xbe9df  ldc.i4.0
0xbe9e0  ldc.i4.0
0xbe9e1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbe9e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbe9eb  ldloc.0
0xbe9ec  ldstr    aSessionid_0// "@SessionId"
0xbe9f1  ldc.i4.s 0xC
0xbe9f3  ldc.i4.s 0x64
0xbe9f5  ldc.i4.0
0xbe9f6  ldc.i4.0
0xbe9f7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbe9fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbea01  ldloc.0
0xbea02  ldstr    aExpiration// "@Expiration"
0xbea07  ldc.i4.4
0xbea08  ldc.i4.0
0xbea09  ldc.i4.0
0xbea0a  ldc.i4.0
0xbea0b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbea10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbea15  ldloc.0
0xbea16  ldstr    aSessionslimit// "@SessionsLimit"
0xbea1b  ldc.i4.8
0xbea1c  ldc.i4.0
0xbea1d  ldc.i4.0
0xbea1e  ldc.i4.1
0xbea1f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbea24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbea29  ldloc.0
0xbea2a  ldstr    aItemstobeupdat// "@ItemsToBeUpdated"
0xbea2f  ldstr    aContent// "Content"
0xbea34  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xbea39  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xbea3e  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xbea43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xbea48  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xbea4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbea52  ldloc.0
0xbea53  ldstr    aItemstobedelet// "@ItemsToBeDeleted"
0xbea58  ldstr    aContent// "Content"
0xbea5d  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xbea62  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xbea67  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xbea6c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xbea71  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xbea76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbea7b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xbea80  stloc.0
0xbea81  ldarg.0
0xbea82  ldstr    aProcMergesites_0// "proc_MergeSiteSessionData"
0xbea87  ldloc.0
0xbea88  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xbea8d  ldloc.0
0xbea8e  ldstr    aReturnValue// "@RETURN_VALUE"
0xbea93  ldc.i4.8
0xbea94  ldc.i4.0
0xbea95  ldc.i4.1
0xbea96  ldc.i4.0
0xbea97  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbea9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeaa1  ldloc.0
0xbeaa2  ldstr    aSiteid_1// "@SiteId"
0xbeaa7  ldc.i4.s 0xE
0xbeaa9  ldc.i4.0
0xbeaaa  ldc.i4.0
0xbeaab  ldc.i4.0
0xbeaac  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeab1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeab6  ldloc.0
0xbeab7  ldstr    aSessiondataid// "@SessionDataId"
0xbeabc  ldc.i4.s 0xE
0xbeabe  ldc.i4.0
0xbeabf  ldc.i4.0
0xbeac0  ldc.i4.0
0xbeac1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeac6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeacb  ldloc.0
0xbeacc  ldstr    aItemstobeupdat// "@ItemsToBeUpdated"
0xbead1  ldstr    aContent// "Content"
0xbead6  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xbeadb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xbeae0  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xbeae5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xbeaea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xbeaef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeaf4  ldloc.0
0xbeaf5  ldstr    aItemstobedelet// "@ItemsToBeDeleted"
0xbeafa  ldstr    aContent// "Content"
0xbeaff  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xbeb04  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xbeb09  ldstr    aTvparrayofsess// "tvpArrayOfSessionItems"
0xbeb0e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xbeb13  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xbeb18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb1d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xbeb22  stloc.0
0xbeb23  ldarg.0
0xbeb24  ldstr    aProcMergeweb// "proc_MergeWeb"
0xbeb29  ldloc.0
0xbeb2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xbeb2f  ldloc.0
0xbeb30  ldstr    aReturnValue// "@RETURN_VALUE"
0xbeb35  ldc.i4.8
0xbeb36  ldc.i4.0
0xbeb37  ldc.i4.1
0xbeb38  ldc.i4.0
0xbeb39  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeb3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb43  ldloc.0
0xbeb44  ldstr    aWebsiteid// "@WebSiteId"
0xbeb49  ldc.i4.s 0xE
0xbeb4b  ldc.i4.0
0xbeb4c  ldc.i4.0
0xbeb4d  ldc.i4.0
0xbeb4e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeb53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb58  ldloc.0
0xbeb59  ldstr    aWeburl_0// "@WebUrl"
0xbeb5e  ldc.i4.s 0xC
0xbeb60  ldc.i4   0x190
0xbeb65  ldc.i4.0
0xbeb66  ldc.i4.0
0xbeb67  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeb6c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb71  ldloc.0
0xbeb72  ldstr    aThresholdrowco// "@ThresholdRowCount"
0xbeb77  ldc.i4.8
0xbeb78  ldc.i4.0
0xbeb79  ldc.i4.0
0xbeb7a  ldc.i4.1
0xbeb7b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeb80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb85  ldloc.0
0xbeb86  ldstr    aRequestguid// "@RequestGuid"
0xbeb8b  ldc.i4.s 0xE
0xbeb8d  ldc.i4.0
0xbeb8e  ldc.i4.1
0xbeb8f  ldc.i4.1
0xbeb90  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbeb95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbeb9a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xbeb9f  stloc.0
0xbeba0  ldarg.0
0xbeba1  ldstr    aProcMinisproc// "proc_MiniSproc"
0xbeba6  ldloc.0
0xbeba7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xbebac  ldloc.0
0xbebad  ldstr    aReturnValue// "@RETURN_VALUE"
0xbebb2  ldc.i4.8
0xbebb3  ldc.i4.0
0xbebb4  ldc.i4.1
0xbebb5  ldc.i4.0
0xbebb6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbebbb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbebc0  ldloc.0
0xbebc1  ldstr    aWebsiteid// "@WebSiteId"
0xbebc6  ldc.i4.s 0xE
0xbebc8  ldc.i4.0
0xbebc9  ldc.i4.0
0xbebca  ldc.i4.0
0xbebcb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbebd0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbebd5  ldloc.0
0xbebd6  ldstr    aWebid_0// "@WebId"
0xbebdb  ldc.i4.s 0xE
0xbebdd  ldc.i4.0
0xbebde  ldc.i4.0
0xbebdf  ldc.i4.0
0xbebe0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbebe5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbebea  ldloc.0
0xbebeb  ldstr    aUrl_0// "@Url"
0xbebf0  ldc.i4.s 0xC
0xbebf2  ldc.i4   0x190
0xbebf7  ldc.i4.0
0xbebf8  ldc.i4.0
0xbebf9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbebfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec03  ldloc.0
0xbec04  ldstr    aDgcacheversion// "@DGCacheVersion"
0xbec09  ldc.i4.0
0xbec0a  ldc.i4.0
0xbec0b  ldc.i4.0
0xbec0c  ldc.i4.0
0xbec0d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec17  ldloc.0
0xbec18  ldstr    aSystemid// "@SystemId"
0xbec1d  ldc.i4.s 0x15
0xbec1f  ldc.i4   0x200
0xbec24  ldc.i4.0
0xbec25  ldc.i4.1
0xbec26  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec2b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec30  ldloc.0
0xbec31  ldstr    aAppprincipalna// "@AppPrincipalName"
0xbec36  ldc.i4.s 0xC
0xbec38  ldc.i4   0x100
0xbec3d  ldc.i4.0
0xbec3e  ldc.i4.0
0xbec3f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec49  ldloc.0
0xbec4a  ldstr    aIshostheaderap// "@IsHostHeaderAppPrincipalName"
0xbec4f  ldc.i4.2
0xbec50  ldc.i4.0
0xbec51  ldc.i4.0
0xbec52  ldc.i4.0
0xbec53  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec5d  ldloc.0
0xbec5e  ldstr    aRequestguid// "@RequestGuid"
0xbec63  ldc.i4.s 0xE
0xbec65  ldc.i4.0
0xbec66  ldc.i4.1
0xbec67  ldc.i4.1
0xbec68  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec72  ldloc.0
0xbec73  ldstr    aSharinglinkses// "@SharingLinkSessionId"
0xbec78  ldc.i4.s 0xC
0xbec7a  ldc.i4.s 0x64
0xbec7c  ldc.i4.0
0xbec7d  ldc.i4.1
0xbec7e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec88  ldloc.0
0xbec89  ldstr    aReturnsharingl// "@ReturnSharingLinkSessionClaims"
0xbec8e  ldc.i4.2
0xbec8f  ldc.i4.0
0xbec90  ldc.i4.0
0xbec91  ldc.i4.1
0xbec92  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbec97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbec9c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xbeca1  stloc.0
0xbeca2  ldarg.0
0xbeca3  ldstr    aProcModifysubs// "proc_ModifySubscription"
0xbeca8  ldloc.0
0xbeca9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xbecae  ldloc.0
0xbecaf  ldstr    aReturnValue// "@RETURN_VALUE"
0xbecb4  ldc.i4.8
0xbecb5  ldc.i4.0
0xbecb6  ldc.i4.1
0xbecb7  ldc.i4.0
0xbecb8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbecbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbecc2  ldloc.0
0xbecc3  ldstr    aSiteid_1// "@SiteId"
0xbecc8  ldc.i4.s 0xE
0xbecca  ldc.i4.0
0xbeccb  ldc.i4.0
0xbeccc  ldc.i4.0
0xbeccd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbecd2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbecd7  ldloc.0
0xbecd8  ldstr    aSubid// "@SubId"
0xbecdd  ldc.i4.s 0xE
0xbecdf  ldc.i4.0
0xbece0  ldc.i4.0
0xbece1  ldc.i4.0
0xbece2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbece7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbecec  ldloc.0
0xbeced  ldstr    aNotifyfreq// "@NotifyFreq"
0xbecf2  ldc.i4.8
0xbecf3  ldc.i4.0
0xbecf4  ldc.i4.0
0xbecf5  ldc.i4.0
0xbecf6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbecfb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbed00  ldloc.0
0xbed01  ldstr    aNotifytime_0// "@NotifyTime"
0xbed06  ldc.i4.4
0xbed07  ldc.i4.0
0xbed08  ldc.i4.0
0xbed09  ldc.i4.0
0xbed0a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xbed0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xbed14  ldloc.0
0xbed15  ldstr    aNotifytimeutc// "@NotifyTimeUTC"
  ... truncated ...
```
