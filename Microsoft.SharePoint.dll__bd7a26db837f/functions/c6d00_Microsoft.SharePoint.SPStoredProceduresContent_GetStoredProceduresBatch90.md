# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch90

- ea: `0xc6d00`
- end: `0xc73e4`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch90`
- size: `1764`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0xc6df1`: `@ExternalToken`
- `0xc6e06`: `@ExternalTokenTime`
- `0xc6da8`: `proc_SecRefreshToken`
- `0xc6e35`: `proc_SecRemoveAppInstancePerms`
- `0xc6e7f`: `@AllPermsRemoved`
- `0xc6eae`: `proc_SecRemoveAppPrincipalPerms`
- `0xc6f41`: `proc_SecRemoveExternalSecurityProvider`
- `0xc6fa6`: `proc_SecRemoveGroup`
- `0xc7090`: `@DeferAclUpdates`
- `0xc731c`: `@DeferAclUpdates`
- `0xc73bc`: `@DeferAclUpdates`
- `0xc70be`: `proc_SecRemovePrincipalFromScope`
- `0xc7132`: `@RemoveFromCurrentScopeOnly`
- `0xc72c6`: `@RemoveFromCurrentScopeOnly`
- `0xc7183`: `@DeferUpdate`
- `0xc7224`: `@DeferUpdate`
- `0xc71b1`: `proc_SecRemoveRoleDef`
- `0xc7252`: `proc_SecRemoveUserFromScopeByLogin`
- `0xc734a`: `proc_SecRemoveUserFromSite`

## pseudocode

```c

```

## disassembly

```asm
0xc6d00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6d05  stloc.0
0xc6d06  ldarg.0
0xc6d07  ldstr    aProcSecrefresh// "proc_SecRefreshDynamicClaims"
0xc6d0c  ldloc.0
0xc6d0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6d12  ldloc.0
0xc6d13  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6d18  ldc.i4.8
0xc6d19  ldc.i4.0
0xc6d1a  ldc.i4.1
0xc6d1b  ldc.i4.0
0xc6d1c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d26  ldloc.0
0xc6d27  ldstr    aSiteid_1// "@SiteId"
0xc6d2c  ldc.i4.s 0xE
0xc6d2e  ldc.i4.0
0xc6d2f  ldc.i4.0
0xc6d30  ldc.i4.0
0xc6d31  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d36  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d3b  ldloc.0
0xc6d3c  ldstr    aUserid_1// "@UserId"
0xc6d41  ldc.i4.8
0xc6d42  ldc.i4.0
0xc6d43  ldc.i4.0
0xc6d44  ldc.i4.0
0xc6d45  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d4a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d4f  ldloc.0
0xc6d50  ldstr    aDynamicclaims// "@DynamicClaims"
0xc6d55  ldc.i4.s 0x15
0xc6d57  ldc.i4.m1
0xc6d58  ldc.i4.0
0xc6d59  ldc.i4.0
0xc6d5a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d5f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d64  ldloc.0
0xc6d65  ldstr    aRefreshtime// "@RefreshTime"
0xc6d6a  ldc.i4.4
0xc6d6b  ldc.i4.0
0xc6d6c  ldc.i4.0
0xc6d6d  ldc.i4.0
0xc6d6e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d78  ldloc.0
0xc6d79  ldstr    aClaimmapversio// "@ClaimMapVersion"
0xc6d7e  ldc.i4.0
0xc6d7f  ldc.i4.0
0xc6d80  ldc.i4.0
0xc6d81  ldc.i4.0
0xc6d82  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6d8c  ldloc.0
0xc6d8d  ldstr    aRequestguid// "@RequestGuid"
0xc6d92  ldc.i4.s 0xE
0xc6d94  ldc.i4.0
0xc6d95  ldc.i4.1
0xc6d96  ldc.i4.1
0xc6d97  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6d9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6da1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6da6  stloc.0
0xc6da7  ldarg.0
0xc6da8  ldstr    aProcSecrefresh_0// "proc_SecRefreshToken"
0xc6dad  ldloc.0
0xc6dae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6db3  ldloc.0
0xc6db4  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6db9  ldc.i4.8
0xc6dba  ldc.i4.0
0xc6dbb  ldc.i4.1
0xc6dbc  ldc.i4.0
0xc6dbd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6dc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6dc7  ldloc.0
0xc6dc8  ldstr    aSiteid_1// "@SiteId"
0xc6dcd  ldc.i4.s 0xE
0xc6dcf  ldc.i4.0
0xc6dd0  ldc.i4.0
0xc6dd1  ldc.i4.0
0xc6dd2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6dd7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6ddc  ldloc.0
0xc6ddd  ldstr    aUserid_1// "@UserId"
0xc6de2  ldc.i4.8
0xc6de3  ldc.i4.0
0xc6de4  ldc.i4.0
0xc6de5  ldc.i4.0
0xc6de6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6deb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6df0  ldloc.0
0xc6df1  ldstr    aExternaltoken// "@ExternalToken"
0xc6df6  ldc.i4.s 0x15
0xc6df8  ldc.i4.m1
0xc6df9  ldc.i4.0
0xc6dfa  ldc.i4.0
0xc6dfb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e05  ldloc.0
0xc6e06  ldstr    aExternaltokent// "@ExternalTokenTime"
0xc6e0b  ldc.i4.4
0xc6e0c  ldc.i4.0
0xc6e0d  ldc.i4.0
0xc6e0e  ldc.i4.0
0xc6e0f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e14  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e19  ldloc.0
0xc6e1a  ldstr    aRequestguid// "@RequestGuid"
0xc6e1f  ldc.i4.s 0xE
0xc6e21  ldc.i4.0
0xc6e22  ldc.i4.1
0xc6e23  ldc.i4.1
0xc6e24  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e2e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6e33  stloc.0
0xc6e34  ldarg.0
0xc6e35  ldstr    aProcSecremovea// "proc_SecRemoveAppInstancePerms"
0xc6e3a  ldloc.0
0xc6e3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6e40  ldloc.0
0xc6e41  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6e46  ldc.i4.8
0xc6e47  ldc.i4.0
0xc6e48  ldc.i4.1
0xc6e49  ldc.i4.0
0xc6e4a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e54  ldloc.0
0xc6e55  ldstr    aSiteid_1// "@SiteId"
0xc6e5a  ldc.i4.s 0xE
0xc6e5c  ldc.i4.0
0xc6e5d  ldc.i4.0
0xc6e5e  ldc.i4.0
0xc6e5f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e69  ldloc.0
0xc6e6a  ldstr    aAppinstanceid// "@AppInstanceId"
0xc6e6f  ldc.i4.s 0xE
0xc6e71  ldc.i4.0
0xc6e72  ldc.i4.0
0xc6e73  ldc.i4.0
0xc6e74  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e79  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e7e  ldloc.0
0xc6e7f  ldstr    aAllpermsremove// "@AllPermsRemoved"
0xc6e84  ldc.i4.2
0xc6e85  ldc.i4.0
0xc6e86  ldc.i4.1
0xc6e87  ldc.i4.0
0xc6e88  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6e8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6e92  ldloc.0
0xc6e93  ldstr    aRequestguid// "@RequestGuid"
0xc6e98  ldc.i4.s 0xE
0xc6e9a  ldc.i4.0
0xc6e9b  ldc.i4.1
0xc6e9c  ldc.i4.1
0xc6e9d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6ea2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6ea7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6eac  stloc.0
0xc6ead  ldarg.0
0xc6eae  ldstr    aProcSecremovea_0// "proc_SecRemoveAppPrincipalPerms"
0xc6eb3  ldloc.0
0xc6eb4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6eb9  ldloc.0
0xc6eba  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6ebf  ldc.i4.8
0xc6ec0  ldc.i4.0
0xc6ec1  ldc.i4.1
0xc6ec2  ldc.i4.0
0xc6ec3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6ec8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6ecd  ldloc.0
0xc6ece  ldstr    aSiteid_1// "@SiteId"
0xc6ed3  ldc.i4.s 0xE
0xc6ed5  ldc.i4.0
0xc6ed6  ldc.i4.0
0xc6ed7  ldc.i4.0
0xc6ed8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6edd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6ee2  ldloc.0
0xc6ee3  ldstr    aAppprincipalna// "@AppPrincipalName"
0xc6ee8  ldc.i4.s 0xC
0xc6eea  ldc.i4   0x100
0xc6eef  ldc.i4.0
0xc6ef0  ldc.i4.0
0xc6ef1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6ef6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6efb  ldloc.0
0xc6efc  ldstr    aWebid_0// "@WebId"
0xc6f01  ldc.i4.s 0xE
0xc6f03  ldc.i4.0
0xc6f04  ldc.i4.0
0xc6f05  ldc.i4.0
0xc6f06  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f10  ldloc.0
0xc6f11  ldstr    aListid_0// "@ListId"
0xc6f16  ldc.i4.s 0xE
0xc6f18  ldc.i4.0
0xc6f19  ldc.i4.0
0xc6f1a  ldc.i4.0
0xc6f1b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f25  ldloc.0
0xc6f26  ldstr    aRequestguid// "@RequestGuid"
0xc6f2b  ldc.i4.s 0xE
0xc6f2d  ldc.i4.0
0xc6f2e  ldc.i4.1
0xc6f2f  ldc.i4.1
0xc6f30  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f3a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6f3f  stloc.0
0xc6f40  ldarg.0
0xc6f41  ldstr    aProcSecremovee// "proc_SecRemoveExternalSecurityProvider"
0xc6f46  ldloc.0
0xc6f47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6f4c  ldloc.0
0xc6f4d  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6f52  ldc.i4.8
0xc6f53  ldc.i4.0
0xc6f54  ldc.i4.1
0xc6f55  ldc.i4.0
0xc6f56  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f5b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f60  ldloc.0
0xc6f61  ldstr    aSiteid_1// "@SiteId"
0xc6f66  ldc.i4.s 0xE
0xc6f68  ldc.i4.0
0xc6f69  ldc.i4.0
0xc6f6a  ldc.i4.0
0xc6f6b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f75  ldloc.0
0xc6f76  ldstr    aWebid_0// "@WebId"
0xc6f7b  ldc.i4.s 0xE
0xc6f7d  ldc.i4.0
0xc6f7e  ldc.i4.0
0xc6f7f  ldc.i4.0
0xc6f80  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f8a  ldloc.0
0xc6f8b  ldstr    aRequestguid// "@RequestGuid"
0xc6f90  ldc.i4.s 0xE
0xc6f92  ldc.i4.0
0xc6f93  ldc.i4.1
0xc6f94  ldc.i4.1
0xc6f95  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6f9a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6f9f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc6fa4  stloc.0
0xc6fa5  ldarg.0
0xc6fa6  ldstr    aProcSecremoveg// "proc_SecRemoveGroup"
0xc6fab  ldloc.0
0xc6fac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc6fb1  ldloc.0
0xc6fb2  ldstr    aReturnValue// "@RETURN_VALUE"
0xc6fb7  ldc.i4.8
0xc6fb8  ldc.i4.0
0xc6fb9  ldc.i4.1
0xc6fba  ldc.i4.0
0xc6fbb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6fc0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6fc5  ldloc.0
0xc6fc6  ldstr    aSiteid_1// "@SiteId"
0xc6fcb  ldc.i4.s 0xE
0xc6fcd  ldc.i4.0
0xc6fce  ldc.i4.0
0xc6fcf  ldc.i4.0
0xc6fd0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6fd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6fda  ldloc.0
0xc6fdb  ldstr    aGroupid_0// "@GroupId"
0xc6fe0  ldc.i4.8
0xc6fe1  ldc.i4.0
0xc6fe2  ldc.i4.0
0xc6fe3  ldc.i4.0
0xc6fe4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6fe9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc6fee  ldloc.0
0xc6fef  ldstr    aUserid_1// "@UserId"
0xc6ff4  ldc.i4.8
0xc6ff5  ldc.i4.0
0xc6ff6  ldc.i4.0
0xc6ff7  ldc.i4.0
0xc6ff8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc6ffd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7002  ldloc.0
0xc7003  ldstr    aAppprincipalid// "@AppPrincipalId"
0xc7008  ldc.i4.8
0xc7009  ldc.i4.0
0xc700a  ldc.i4.0
0xc700b  ldc.i4.0
0xc700c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7011  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
  ... truncated ...
```
