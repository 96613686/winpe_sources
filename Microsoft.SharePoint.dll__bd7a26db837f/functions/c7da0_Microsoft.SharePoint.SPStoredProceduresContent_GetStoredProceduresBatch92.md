# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch92

- ea: `0xc7da0`
- end: `0xc84df`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch92`
- size: `1855`
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

- `0xc83fd`: `@ComplianceTag`
- `0xc8416`: `@ComplianceFlags`
- `0xc7fa4`: `@DeferUpdate`
- `0xc7da7`: `proc_SecUpdateAnonymousPermMask`
- `0xc7e35`: `proc_SecUpdateDomainGroupMapData`
- `0xc7e6a`: `@CacheVersion`
- `0xc7e7e`: `@DomainGroupMapCache`
- `0xc7ec2`: `proc_SecUpdateRoleDef`
- `0xc7fd2`: `proc_SecUpdateUser`
- `0xc802f`: `@UserIdToUpdate`
- `0xc80d1`: `proc_SecUpdateUserActiveStatus`
- `0xc8135`: `proc_SecUpdateUserActiveStatusBulk`
- `0xc82fd`: `proc_SetCommentFlags`
- `0xc838a`: `proc_SetComplianceTag`
- `0xc843e`: `@CheckComplianceTagUserId`
- `0xc8452`: `@ComplianceTagWrittenTime`
- `0xc8466`: `@ComplianceFlagsToReset`
- `0xc847a`: `@KeepOldComplianceTag`

## pseudocode

```c

```

## disassembly

```asm
0xc7da0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc7da5  stloc.0
0xc7da6  ldarg.0
0xc7da7  ldstr    aProcSecupdatea// "proc_SecUpdateAnonymousPermMask"
0xc7dac  ldloc.0
0xc7dad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc7db2  ldloc.0
0xc7db3  ldstr    aReturnValue// "@RETURN_VALUE"
0xc7db8  ldc.i4.8
0xc7db9  ldc.i4.0
0xc7dba  ldc.i4.1
0xc7dbb  ldc.i4.0
0xc7dbc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7dc1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7dc6  ldloc.0
0xc7dc7  ldstr    aSiteid_1// "@SiteId"
0xc7dcc  ldc.i4.s 0xE
0xc7dce  ldc.i4.0
0xc7dcf  ldc.i4.0
0xc7dd0  ldc.i4.0
0xc7dd1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7dd6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ddb  ldloc.0
0xc7ddc  ldstr    aWebid_0// "@WebId"
0xc7de1  ldc.i4.s 0xE
0xc7de3  ldc.i4.0
0xc7de4  ldc.i4.0
0xc7de5  ldc.i4.0
0xc7de6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7deb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7df0  ldloc.0
0xc7df1  ldstr    aScopeid// "@ScopeId"
0xc7df6  ldc.i4.s 0xE
0xc7df8  ldc.i4.0
0xc7df9  ldc.i4.0
0xc7dfa  ldc.i4.0
0xc7dfb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e05  ldloc.0
0xc7e06  ldstr    aAnonymouspermm// "@AnonymousPermMask"
0xc7e0b  ldc.i4.0
0xc7e0c  ldc.i4.0
0xc7e0d  ldc.i4.0
0xc7e0e  ldc.i4.0
0xc7e0f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e14  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e19  ldloc.0
0xc7e1a  ldstr    aRequestguid// "@RequestGuid"
0xc7e1f  ldc.i4.s 0xE
0xc7e21  ldc.i4.0
0xc7e22  ldc.i4.1
0xc7e23  ldc.i4.1
0xc7e24  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e2e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc7e33  stloc.0
0xc7e34  ldarg.0
0xc7e35  ldstr    aProcSecupdated// "proc_SecUpdateDomainGroupMapData"
0xc7e3a  ldloc.0
0xc7e3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc7e40  ldloc.0
0xc7e41  ldstr    aReturnValue// "@RETURN_VALUE"
0xc7e46  ldc.i4.8
0xc7e47  ldc.i4.0
0xc7e48  ldc.i4.1
0xc7e49  ldc.i4.0
0xc7e4a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e54  ldloc.0
0xc7e55  ldstr    aSiteid_1// "@SiteId"
0xc7e5a  ldc.i4.s 0xE
0xc7e5c  ldc.i4.0
0xc7e5d  ldc.i4.0
0xc7e5e  ldc.i4.0
0xc7e5f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e69  ldloc.0
0xc7e6a  ldstr    aCacheversion// "@CacheVersion"
0xc7e6f  ldc.i4.0
0xc7e70  ldc.i4.0
0xc7e71  ldc.i4.0
0xc7e72  ldc.i4.0
0xc7e73  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e7d  ldloc.0
0xc7e7e  ldstr    aDomaingroupmap// "@DomainGroupMapCache"
0xc7e83  ldc.i4.s 0x15
0xc7e85  ldc.i4.m1
0xc7e86  ldc.i4.0
0xc7e87  ldc.i4.0
0xc7e88  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7e8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7e92  ldloc.0
0xc7e93  ldstr    aRequestguid// "@RequestGuid"
0xc7e98  ldc.i4.s 0xE
0xc7e9a  ldc.i4.0
0xc7e9b  ldc.i4.1
0xc7e9c  ldc.i4.1
0xc7e9d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7ea2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ea7  ldloc.0
0xc7ea8  ldstr    aRequireversion// "@RequireVersionMatch"
0xc7ead  ldc.i4.2
0xc7eae  ldc.i4.0
0xc7eaf  ldc.i4.0
0xc7eb0  ldc.i4.1
0xc7eb1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7eb6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ebb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc7ec0  stloc.0
0xc7ec1  ldarg.0
0xc7ec2  ldstr    aProcSecupdater// "proc_SecUpdateRoleDef"
0xc7ec7  ldloc.0
0xc7ec8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc7ecd  ldloc.0
0xc7ece  ldstr    aReturnValue// "@RETURN_VALUE"
0xc7ed3  ldc.i4.8
0xc7ed4  ldc.i4.0
0xc7ed5  ldc.i4.1
0xc7ed6  ldc.i4.0
0xc7ed7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7edc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ee1  ldloc.0
0xc7ee2  ldstr    aSiteid_1// "@SiteId"
0xc7ee7  ldc.i4.s 0xE
0xc7ee9  ldc.i4.0
0xc7eea  ldc.i4.0
0xc7eeb  ldc.i4.0
0xc7eec  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7ef1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ef6  ldloc.0
0xc7ef7  ldstr    aWebid_0// "@WebId"
0xc7efc  ldc.i4.s 0xE
0xc7efe  ldc.i4.0
0xc7eff  ldc.i4.0
0xc7f00  ldc.i4.0
0xc7f01  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f0b  ldloc.0
0xc7f0c  ldstr    aRoleid_0// "@RoleId"
0xc7f11  ldc.i4.8
0xc7f12  ldc.i4.0
0xc7f13  ldc.i4.0
0xc7f14  ldc.i4.0
0xc7f15  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f1a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f1f  ldloc.0
0xc7f20  ldstr    aTitle// "@Title"
0xc7f25  ldc.i4.s 0xC
0xc7f27  ldc.i4   0xFF
0xc7f2c  ldc.i4.0
0xc7f2d  ldc.i4.0
0xc7f2e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f38  ldloc.0
0xc7f39  ldstr    aDescription_0// "@Description"
0xc7f3e  ldc.i4.s 0xC
0xc7f40  ldc.i4   0x200
0xc7f45  ldc.i4.0
0xc7f46  ldc.i4.0
0xc7f47  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f4c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f51  ldloc.0
0xc7f52  ldstr    aOrder// "@Order"
0xc7f57  ldc.i4.8
0xc7f58  ldc.i4.0
0xc7f59  ldc.i4.0
0xc7f5a  ldc.i4.0
0xc7f5b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f65  ldloc.0
0xc7f66  ldstr    aType_2// "@Type"
0xc7f6b  ldc.i4.s 0x14
0xc7f6d  ldc.i4.0
0xc7f6e  ldc.i4.0
0xc7f6f  ldc.i4.0
0xc7f70  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f7a  ldloc.0
0xc7f7b  ldstr    aPermmask// "@PermMask"
0xc7f80  ldc.i4.0
0xc7f81  ldc.i4.0
0xc7f82  ldc.i4.0
0xc7f83  ldc.i4.0
0xc7f84  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f89  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7f8e  ldloc.0
0xc7f8f  ldstr    aRequestguid// "@RequestGuid"
0xc7f94  ldc.i4.s 0xE
0xc7f96  ldc.i4.0
0xc7f97  ldc.i4.1
0xc7f98  ldc.i4.1
0xc7f99  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7f9e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7fa3  ldloc.0
0xc7fa4  ldstr    aDeferupdate// "@DeferUpdate"
0xc7fa9  ldc.i4.2
0xc7faa  ldc.i4.0
0xc7fab  ldc.i4.0
0xc7fac  ldc.i4.1
0xc7fad  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7fb2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7fb7  ldloc.0
0xc7fb8  ldstr    aReturnwnssubs// "@ReturnWnsSubs"
0xc7fbd  ldc.i4.2
0xc7fbe  ldc.i4.0
0xc7fbf  ldc.i4.0
0xc7fc0  ldc.i4.1
0xc7fc1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7fc6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7fcb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xc7fd0  stloc.0
0xc7fd1  ldarg.0
0xc7fd2  ldstr    aProcSecupdateu// "proc_SecUpdateUser"
0xc7fd7  ldloc.0
0xc7fd8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xc7fdd  ldloc.0
0xc7fde  ldstr    aReturnValue// "@RETURN_VALUE"
0xc7fe3  ldc.i4.8
0xc7fe4  ldc.i4.0
0xc7fe5  ldc.i4.1
0xc7fe6  ldc.i4.0
0xc7fe7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc7fec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc7ff1  ldloc.0
0xc7ff2  ldstr    aSiteid_1// "@SiteId"
0xc7ff7  ldc.i4.s 0xE
0xc7ff9  ldc.i4.0
0xc7ffa  ldc.i4.0
0xc7ffb  ldc.i4.0
0xc7ffc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc8001  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc8006  ldloc.0
0xc8007  ldstr    aCurrentuserid// "@CurrentUserId"
0xc800c  ldc.i4.8
0xc800d  ldc.i4.0
0xc800e  ldc.i4.0
0xc800f  ldc.i4.0
0xc8010  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc8015  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc801a  ldloc.0
0xc801b  ldstr    aAppprincipalid// "@AppPrincipalId"
0xc8020  ldc.i4.8
0xc8021  ldc.i4.0
0xc8022  ldc.i4.0
0xc8023  ldc.i4.0
0xc8024  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc8029  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc802e  ldloc.0
0xc802f  ldstr    aUseridtoupdate// "@UserIdToUpdate"
0xc8034  ldc.i4.8
0xc8035  ldc.i4.0
0xc8036  ldc.i4.0
0xc8037  ldc.i4.0
0xc8038  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc803d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc8042  ldloc.0
0xc8043  ldstr    aTitle// "@Title"
0xc8048  ldc.i4.s 0xC
0xc804a  ldc.i4   0xFF
0xc804f  ldc.i4.0
0xc8050  ldc.i4.0
0xc8051  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc8056  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc805b  ldloc.0
0xc805c  ldstr    aEmail_0// "@Email"
0xc8061  ldc.i4.s 0xC
0xc8063  ldc.i4   0xFF
0xc8068  ldc.i4.0
0xc8069  ldc.i4.0
0xc806a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc806f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc8074  ldloc.0
0xc8075  ldstr    aNotes// "@Notes"
0xc807a  ldc.i4.s 0xC
0xc807c  ldc.i4   0x3FF
0xc8081  ldc.i4.0
0xc8082  ldc.i4.0
0xc8083  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc8088  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc808d  ldloc.0
0xc808e  ldstr    aSiteadmin// "@SiteAdmin"
0xc8093  ldc.i4.2
0xc8094  ldc.i4.0
0xc8095  ldc.i4.0
0xc8096  ldc.i4.0
0xc8097  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc809c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc80a1  ldloc.0
0xc80a2  ldstr    aFlags_0// "@Flags"
0xc80a7  ldc.i4.8
0xc80a8  ldc.i4.0
0xc80a9  ldc.i4.0
0xc80aa  ldc.i4.0
0xc80ab  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xc80b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xc80b5  ldloc.0
0xc80b6  ldstr    aRequestguid// "@RequestGuid"
0xc80bb  ldc.i4.s 0xE
0xc80bd  ldc.i4.0
  ... truncated ...
```
