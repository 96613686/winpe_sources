# Microsoft.SharePoint.SPChangeCollection::GetChanges

- ea: `0x4b2860`
- end: `0x4b3142`
- name: `Microsoft.SharePoint.SPChangeCollection::GetChanges`
- size: `2274`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4b32f0`

## callees

- `0x105820`
- `0x1b7df0`
- `0x1b8650`
- `0x1b8670`
- `0x1c89e0`
- `0x241d60`
- `0x242050`
- `0x2534b0`
- `0x25c8b0`
- `0x25c8d0`
- `0x25c9c0`
- `0x25c9e0`
- `0x25cb40`
- `0x25d9c0`
- `0x25dad0`
- `0x26b840`
- `0x26f6c0`
- `0x3428a0`
- `0x3428d0`
- `0x476c30`
- `0x477160`
- `0x4b23e0`
- `0x4b23f0`
- `0x4b2550`
- `0x4b2860`
- `0x4b3150`
- `0x4b38e0`
- `0x4b39c0`
- `0x4b3c30`
- `0x4b3c40`
- `0x4b3df0`
- `0x4b3e50`
- `0x4e76a0`
- `0x577060`
- `0x58dac0`
- `0x5c3eb0`
- `0x8e50a0`
- `0x8e5820`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x4b2c2a`: `@PathLike`
- `0x4b2c38`: `@PathLike`
- `0x4b2c8e`: `@PathLike`
- `0x4b2c9c`: `@PathLike`
- `0x4b2c44`: `@bReturnAcl`
- `0x4b2c52`: `@bReturnAcl`
- `0x4b2bed`: `@bFixTokenValidation`
- `0x4b2bfb`: `@bFixTokenValidation`
- `0x4b2e6e`: `ChangeToken is too early. ChangeTime={0}, ChangeNumber={1}, ChangeTimeFirst={2}, ChangeNumberFirst={3}`
- `0x4b2ec0`: `ChangeTokenTooEarly`
- `0x4b300f`: `ChangeTokenTooEarly`
- `0x4b2f3d`: `ChangeToken is from the future. ChangeTime={0}, ChangeNumber={1}, ChangeNumberActual={2}`
- `0x4b2f84`: `ChangeTokenFromFuture`
- `0x4b2fc5`: `ChangeToken [{0}] was not found or no changes are in the database. {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4b2860  ldarg.0
0x4b2861  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_readOnlyIntent
0x4b2866  brfalse.s loc_4B2871
0x4b2868  ldarg.1
0x4b2869  callvirt instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_ReadOnlyIntentSqlSession()
0x4b286e  stloc.0
0x4b286f  br.s     loc_4B2878
0x4b2871  ldarg.1
0x4b2872  callvirt instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_SqlSession()
0x4b2877  stloc.0
0x4b2878  ldnull
0x4b2879  stloc.1
0x4b287a  ldarg.1
0x4b287b  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsItemLevelChangeLogQuery()
0x4b2880  brtrue.s loc_4B289E
0x4b2882  ldarg.0
0x4b2883  ldfld    string Microsoft.SharePoint.SPChangeCollection::m_pathLike
0x4b2888  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b288d  brfalse.s loc_4B2898
0x4b288f  ldarg.0
0x4b2890  ldfld    int32 Microsoft.SharePoint.SPChangeCollection::m_itemId
0x4b2895  ldc.i4.0
0x4b2896  ble.s    loc_4B289E
0x4b2898  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x4b289d  throw
0x4b289e  ldarg.0
0x4b289f  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_bRequireTrimming
0x4b28a4  brfalse.s loc_4B28CA
0x4b28a6  ldarg.0
0x4b28a7  ldfld    valuetype CollectionScope Microsoft.SharePoint.SPChangeCollection::m_scope
0x4b28ac  ldc.i4.3
0x4b28ad  bne.un.s loc_4B28BC
0x4b28af  ldarg.0
0x4b28b0  ldfld    string Microsoft.SharePoint.SPChangeCollection::m_pathLike
0x4b28b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b28ba  brfalse.s loc_4B28C7
0x4b28bc  ldarg.0
0x4b28bd  ldfld    valuetype CollectionScope Microsoft.SharePoint.SPChangeCollection::m_scope
0x4b28c2  ldc.i4.2
0x4b28c3  ceq
0x4b28c5  br.s     loc_4B28CB
0x4b28c7  ldc.i4.1
0x4b28c8  br.s     loc_4B28CB
0x4b28ca  ldc.i4.0
0x4b28cb  stloc.2
0x4b28cc  ldarg.0
0x4b28cd  ldloc.2
0x4b28ce  stfld    bool Microsoft.SharePoint.SPChangeCollection::m_bSecurityTrimmed
0x4b28d3  ldloc.2
0x4b28d4  brfalse.s loc_4B28E6
0x4b28d6  ldstr    aMicrosoftShare_7// "Microsoft.SharePoint.Internal.Activitie"...
0x4b28db  call     object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.CompMgrRoot::CreateInstance(string)
0x4b28e0  isinst   Microsoft.SharePoint.Internal.Activities.IListItemsProcessor
0x4b28e5  stloc.1
0x4b28e6  ldc.i4.s 0xF
0x4b28e8  newobj   instance void Microsoft.SharePoint.SPNoCheckSecurableObject::.ctor()
0x4b28ed  newobj   instance void Microsoft.SharePoint.SPSecurityOnOperationScope::.ctor(valuetype SPOperationCode code, class Microsoft.SharePoint.SPSecurableObject obj)
0x4b28f2  stloc.s  0xF
0x4b28f4  ldarg.0
0x4b28f5  ldfld    class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPChangeCollection::m_site
0x4b28fa  brfalse.s loc_4B290E
0x4b28fc  ldarg.0
0x4b28fd  ldfld    class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPChangeCollection::m_site
0x4b2902  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x4b2907  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x4b290c  br.s     loc_4B2918
0x4b290e  ldloca.s 0x10
0x4b2910  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x4b2916  ldloc.s  0x10
0x4b2918  ldarg.0
0x4b2919  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPChangeCollection::m_web
0x4b291e  brfalse.s loc_4B2932
0x4b2920  ldarg.0
0x4b2921  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPChangeCollection::m_web
0x4b2926  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x4b292b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x4b2930  br.s     loc_4B293C
0x4b2932  ldloca.s 0x11
0x4b2934  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x4b293a  ldloc.s  0x11
0x4b293c  ldarg.0
0x4b293d  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPChangeCollection::m_listID
0x4b2942  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b2947  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4b294c  brtrue.s loc_4B295B
0x4b294e  ldarg.0
0x4b294f  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPChangeCollection::m_listID
0x4b2954  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x4b2959  br.s     loc_4B2965
0x4b295b  ldloca.s 0x12
0x4b295d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x4b2963  ldloc.s  0x12
0x4b2965  ldarg.0
0x4b2966  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b296b  ldnull
0x4b296c  call     bool Microsoft.SharePoint.SPChangeToken::op_Equality(class Microsoft.SharePoint.SPChangeToken changeToken1, class Microsoft.SharePoint.SPChangeToken changeToken2)
0x4b2971  brtrue.s loc_4B29A8
0x4b2973  ldarg.0
0x4b2974  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b2979  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::get_ChangeTime()
0x4b297e  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::InvalidChangeTime
0x4b2983  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4b2988  brtrue.s loc_4B299C
0x4b298a  ldarg.0
0x4b298b  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b2990  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::get_ChangeTime()
0x4b2995  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x4b299a  br.s     loc_4B29B2
0x4b299c  ldloca.s 0x13
0x4b299e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x4b29a4  ldloc.s  0x13
0x4b29a6  br.s     loc_4B29B2
0x4b29a8  ldloca.s 0x14
0x4b29aa  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x4b29b0  ldloc.s  0x14
0x4b29b2  ldarg.0
0x4b29b3  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b29b8  ldnull
0x4b29b9  call     bool Microsoft.SharePoint.SPChangeToken::op_Equality(class Microsoft.SharePoint.SPChangeToken changeToken1, class Microsoft.SharePoint.SPChangeToken changeToken2)
0x4b29be  brtrue.s loc_4B29F0
0x4b29c0  ldarg.0
0x4b29c1  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b29c6  callvirt instance int64 Microsoft.SharePoint.SPChangeToken::get_ChangeNumber()
0x4b29cb  ldsfld   int64 Microsoft.SharePoint.SPChangeToken::InvalidChangeNumber
0x4b29d0  beq.s    loc_4B29E4
0x4b29d2  ldarg.0
0x4b29d3  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeToken
0x4b29d8  callvirt instance int64 Microsoft.SharePoint.SPChangeToken::get_ChangeNumber()
0x4b29dd  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x4b29e2  br.s     loc_4B29FA
0x4b29e4  ldloca.s 0x15
0x4b29e6  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x4b29ec  ldloc.s  0x15
0x4b29ee  br.s     loc_4B29FA
0x4b29f0  ldloca.s 0x16
0x4b29f2  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x4b29f8  ldloc.s  0x16
0x4b29fa  ldarg.0
0x4b29fb  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a00  ldnull
0x4b2a01  call     bool Microsoft.SharePoint.SPChangeToken::op_Equality(class Microsoft.SharePoint.SPChangeToken changeToken1, class Microsoft.SharePoint.SPChangeToken changeToken2)
0x4b2a06  brtrue.s loc_4B2A3D
0x4b2a08  ldarg.0
0x4b2a09  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a0e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::get_ChangeTime()
0x4b2a13  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::InvalidChangeTime
0x4b2a18  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4b2a1d  brtrue.s loc_4B2A31
0x4b2a1f  ldarg.0
0x4b2a20  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a25  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPChangeToken::get_ChangeTime()
0x4b2a2a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x4b2a2f  br.s     loc_4B2A47
0x4b2a31  ldloca.s 0x17
0x4b2a33  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x4b2a39  ldloc.s  0x17
0x4b2a3b  br.s     loc_4B2A47
0x4b2a3d  ldloca.s 0x18
0x4b2a3f  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x4b2a45  ldloc.s  0x18
0x4b2a47  ldarg.0
0x4b2a48  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a4d  ldnull
0x4b2a4e  call     bool Microsoft.SharePoint.SPChangeToken::op_Equality(class Microsoft.SharePoint.SPChangeToken changeToken1, class Microsoft.SharePoint.SPChangeToken changeToken2)
0x4b2a53  brtrue.s loc_4B2A85
0x4b2a55  ldarg.0
0x4b2a56  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a5b  callvirt instance int64 Microsoft.SharePoint.SPChangeToken::get_ChangeNumber()
0x4b2a60  ldsfld   int64 Microsoft.SharePoint.SPChangeToken::InvalidChangeNumber
0x4b2a65  beq.s    loc_4B2A79
0x4b2a67  ldarg.0
0x4b2a68  ldfld    class Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.SPChangeCollection::m_changeTokenEnd
0x4b2a6d  callvirt instance int64 Microsoft.SharePoint.SPChangeToken::get_ChangeNumber()
0x4b2a72  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x4b2a77  br.s     loc_4B2A8F
0x4b2a79  ldloca.s 0x19
0x4b2a7b  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x4b2a81  ldloc.s  0x19
0x4b2a83  br.s     loc_4B2A8F
0x4b2a85  ldloca.s 0x1A
0x4b2a87  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x4b2a8d  ldloc.s  0x1A
0x4b2a8f  ldarg.0
0x4b2a90  ldfld    int32 Microsoft.SharePoint.SPChangeCollection::m_objectTypeMask
0x4b2a95  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x4b2a9a  ldarg.0
0x4b2a9b  ldfld    int32 Microsoft.SharePoint.SPChangeCollection::m_changeTypeMaskSQL
0x4b2aa0  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x4b2aa5  ldarg.0
0x4b2aa6  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_ignoreStartTokenNotFoundError
0x4b2aab  brtrue.s loc_4B2AC0
0x4b2aad  ldarg.0
0x4b2aae  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_bTrackChangeTokenFromFuture
0x4b2ab3  brfalse.s loc_4B2ABD
0x4b2ab5  ldarg.1
0x4b2ab6  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsReturningActualChangeNumber()
0x4b2abb  br.s     loc_4B2AC1
0x4b2abd  ldc.i4.0
0x4b2abe  br.s     loc_4B2AC1
0x4b2ac0  ldc.i4.1
0x4b2ac1  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2ac6  stloc.s  0x1B
0x4b2ac8  ldarg.0
0x4b2ac9  ldfld    int64 Microsoft.SharePoint.SPChangeCollection::m_fetchLimit
0x4b2ace  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x4b2ad3  ldloc.s  0x1B
0x4b2ad5  ldarg.0
0x4b2ad6  ldfld    int32 Microsoft.SharePoint.SPChangeCollection::m_itemId
0x4b2adb  ldc.i4.0
0x4b2adc  ble.s    loc_4B2AEB
0x4b2ade  ldarg.0
0x4b2adf  ldfld    int32 Microsoft.SharePoint.SPChangeCollection::m_itemId
0x4b2ae4  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x4b2ae9  br.s     loc_4B2AF5
0x4b2aeb  ldloca.s 0x1C
0x4b2aed  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4b2af3  ldloc.s  0x1C
0x4b2af5  ldarg.0
0x4b2af6  ldfld    string Microsoft.SharePoint.SPChangeCollection::m_pathLike
0x4b2afb  ldloc.2
0x4b2afc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b01  ldarg.0
0x4b2b02  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_bLatestFirst
0x4b2b07  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b0c  ldc.i4.0
0x4b2b0d  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b12  ldarg.0
0x4b2b13  ldfld    bool Microsoft.SharePoint.SPChangeCollection::m_bRecursiveAll
0x4b2b18  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b1d  ldc.i4.1
0x4b2b1e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b23  ldarg.0
0x4b2b24  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPChangeCollection::m_optimizedSyncQueryList
0x4b2b29  ldnull
0x4b2b2a  ceq
0x4b2b2c  ldc.i4.0
0x4b2b2d  ceq
0x4b2b2f  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b34  ldarg.0
0x4b2b35  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPChangeCollection::m_optimizedSyncQueryList
0x4b2b3a  brtrue.s loc_4B2B3F
0x4b2b3c  ldc.i4.0
0x4b2b3d  br.s     loc_4B2B4A
0x4b2b3f  ldarg.0
0x4b2b40  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPChangeCollection::m_optimizedSyncQueryList
0x4b2b45  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::get_HasUniqueRoleAssignments()
0x4b2b4a  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b4f  ldarg.0
0x4b2b50  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPChangeCollection::m_optimizedSyncQueryList
0x4b2b55  brtrue.s loc_4B2B63
0x4b2b57  ldloca.s 0x1D
0x4b2b59  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x4b2b5f  ldloc.s  0x1D
0x4b2b61  br.s     loc_4B2B78
0x4b2b63  ldarg.0
0x4b2b64  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPChangeCollection::m_optimizedSyncQueryList
0x4b2b69  callvirt instance class Microsoft.SharePoint.SPSecurableObjectImpl Microsoft.SharePoint.SPSecurableObject::get_SecurableObjectImpl()
0x4b2b6e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSecurableObjectImpl::get_ScopeId()
0x4b2b73  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x4b2b78  ldarg.0
0x4b2b79  call     instance bool Microsoft.SharePoint.SPChangeCollection::get_IncludeUserInfo()
0x4b2b7e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4b2b83  call     class Microsoft.SharePoint.Utilities.SPSqlCommand Microsoft.SharePoint.SPStoredProceduresContent::proc_GetChanges(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> SiteId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> WebId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> ListId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> ChangeTime, valuetype [mscorlib]System.Nullable`1<int64> ChangeNumber, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> ChangeTimeEnd, valuetype [mscorlib]System.Nullable`1<int64> ChangeNumberEnd, valuetype [mscorlib]System.Nullable`1<int32> ObjectTypeMask, valuetype [mscorlib]System.Nullable`1<int32> EventTypeMask, valuetype [mscorlib]System.Nullable`1<int64> MaxChanges, valuetype [mscorlib]System.Nullable`1<bool> IgnoreChangeNumberIfNotFound, valuetype [mscorlib]System.Nullable`1<int32> ItemId, string PathLike, valuetype [mscorlib]System.Nullable`1<bool> bReturnAcl, valuetype [mscorlib]System.Nullable`1<bool> bLatestFirst, valuetype [mscorlib]System.Nullable`1<bool> ClearLastWnsMessageSentTime, valuetype [mscorlib]System.Nullable`1<bool> bRecursiveAll, valuetype [mscorlib]System.Nullable`1<bool> bFixTokenValidation, valuetype [mscorlib]System.Nullable`1<bool> bSyncQuery, valuetype [mscorlib]System.Nullable`1<bool> bListHasUniquePermissions, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> ListScopeId, valuetype [mscorlib]System.Nullable`1<bool> bIncludeUserInfo)
0x4b2b88  stloc.3
0x4b2b89  ldloc.3
0x4b2b8a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x4b2b8f  stloc.s  4
0x4b2b91  ldarg.0
0x4b2b92  ldfld    class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.SPChangeCollection::m_db
0x4b2b97  ldnull
0x4b2b98  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x4b2b9d  brtrue.s loc_4B2BB7
0x4b2b9f  ldarg.0
0x4b2ba0  ldfld    class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPChangeCollection::m_site
0x4b2ba5  brtrue.s loc_4B2BAA
0x4b2ba7  ldnull
0x4b2ba8  br.s     loc_4B2BBD
0x4b2baa  ldarg.0
0x4b2bab  ldfld    class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPChangeCollection::m_site
0x4b2bb0  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x4b2bb5  br.s     loc_4B2BBD
0x4b2bb7  ldarg.0
0x4b2bb8  ldfld    class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.SPChangeCollection::m_db
0x4b2bbd  stloc.s  5
0x4b2bbf  ldloc.s  5
0x4b2bc1  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsGetListWnsSubscriptions()
0x4b2bc6  brtrue.s loc_4B2BE2
0x4b2bc8  ldloc.s  4
0x4b2bca  ldstr    aClearlastwnsme// "@ClearLastWnsMessageSentTime"
0x4b2bcf  callvirt instance bool [System.Data]System.Data.Common.DbParameterCollection::Contains(string)
0x4b2bd4  brfalse.s loc_4B2BE2
0x4b2bd6  ldloc.s  4
0x4b2bd8  ldstr    aClearlastwnsme// "@ClearLastWnsMessageSentTime"
0x4b2bdd  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::RemoveAt(string)
0x4b2be2  ldloc.s  5
0x4b2be4  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsReturningActualChangeNumber()
0x4b2be9  brtrue.s loc_4B2C05
0x4b2beb  ldloc.s  4
0x4b2bed  ldstr    aBfixtokenvalid// "@bFixTokenValidation"
0x4b2bf2  callvirt instance bool [System.Data]System.Data.Common.DbParameterCollection::Contains(string)
  ... truncated ...
```
