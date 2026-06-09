# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch19

- ea: `0x9c860`
- end: `0x9d8ac`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch19`
- size: `4172`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0x9d289`: `@ComplianceTag`
- `0x9d2a2`: `@ComplianceFlags`
- `0x9cfe5`: `@ServerTemplate`
- `0x9ca4c`: `proc_CreateDefaultRoles`
- `0x9cc92`: `proc_CreateDir`
- `0x9cd4b`: `@CreateDirFlags`
- `0x9ce46`: `@bAlreadyExists`
- `0x9ce8a`: `proc_CreateGB180302022NvpObjects`
- `0x9cec5`: `proc_CreateList`
- `0x9cfbc`: `@bCreateAttachmentsSubFolder`
- `0x9cff9`: `@DocLibTemplate`
- `0x9d040`: `@ReadSecurity`
- `0x9d054`: `@WriteSecurity`
- `0x9d24c`: `@TimeCreated`
- `0x9d2bc`: `proc_CreateListViewPart`
- `0x9d4c0`: `proc_CreateSite`
- `0x9d592`: `@OwnerSID`
- `0x9d5f6`: `@SecondaryContactSID`

## pseudocode

```c

```

## disassembly

```asm
0x9c860  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9c865  stloc.0
0x9c866  ldarg.0
0x9c867  ldstr    aProcCountchang// "proc_CountChanges"
0x9c86c  ldloc.0
0x9c86d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9c872  ldloc.0
0x9c873  ldstr    aReturnValue// "@RETURN_VALUE"
0x9c878  ldc.i4.8
0x9c879  ldc.i4.0
0x9c87a  ldc.i4.1
0x9c87b  ldc.i4.0
0x9c87c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c881  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c886  ldloc.0
0x9c887  ldstr    aOlderthandays// "@OlderThanDays"
0x9c88c  ldc.i4.8
0x9c88d  ldc.i4.0
0x9c88e  ldc.i4.0
0x9c88f  ldc.i4.0
0x9c890  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c895  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c89a  ldloc.0
0x9c89b  ldstr    aCountolder// "@CountOlder"
0x9c8a0  ldc.i4.8
0x9c8a1  ldc.i4.0
0x9c8a2  ldc.i4.1
0x9c8a3  ldc.i4.1
0x9c8a4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c8a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c8ae  ldloc.0
0x9c8af  ldstr    aRequestguid// "@RequestGuid"
0x9c8b4  ldc.i4.s 0xE
0x9c8b6  ldc.i4.0
0x9c8b7  ldc.i4.1
0x9c8b8  ldc.i4.1
0x9c8b9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c8be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c8c3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9c8c8  stloc.0
0x9c8c9  ldarg.0
0x9c8ca  ldstr    aProcCountworkf// "proc_CountWorkflowAssociations"
0x9c8cf  ldloc.0
0x9c8d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9c8d5  ldloc.0
0x9c8d6  ldstr    aReturnValue// "@RETURN_VALUE"
0x9c8db  ldc.i4.8
0x9c8dc  ldc.i4.0
0x9c8dd  ldc.i4.1
0x9c8de  ldc.i4.0
0x9c8df  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c8e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c8e9  ldloc.0
0x9c8ea  ldstr    aSiteid_1// "@SiteId"
0x9c8ef  ldc.i4.s 0xE
0x9c8f1  ldc.i4.0
0x9c8f2  ldc.i4.0
0x9c8f3  ldc.i4.0
0x9c8f4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c8f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c8fe  ldloc.0
0x9c8ff  ldstr    aBaseid_0// "@BaseId"
0x9c904  ldc.i4.s 0xE
0x9c906  ldc.i4.0
0x9c907  ldc.i4.0
0x9c908  ldc.i4.0
0x9c909  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c90e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c913  ldloc.0
0x9c914  ldstr    aRequestguid// "@RequestGuid"
0x9c919  ldc.i4.s 0xE
0x9c91b  ldc.i4.0
0x9c91c  ldc.i4.1
0x9c91d  ldc.i4.1
0x9c91e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c923  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c928  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9c92d  stloc.0
0x9c92e  ldarg.0
0x9c92f  ldstr    aProcCountworkf_0// "proc_CountWorkflows"
0x9c934  ldloc.0
0x9c935  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9c93a  ldloc.0
0x9c93b  ldstr    aReturnValue// "@RETURN_VALUE"
0x9c940  ldc.i4.8
0x9c941  ldc.i4.0
0x9c942  ldc.i4.1
0x9c943  ldc.i4.0
0x9c944  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c949  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c94e  ldloc.0
0x9c94f  ldstr    aAssociationid_0// "@AssociationId"
0x9c954  ldc.i4.s 0xE
0x9c956  ldc.i4.0
0x9c957  ldc.i4.0
0x9c958  ldc.i4.0
0x9c959  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c95e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c963  ldloc.0
0x9c964  ldstr    aSiteid_1// "@SiteId"
0x9c969  ldc.i4.s 0xE
0x9c96b  ldc.i4.0
0x9c96c  ldc.i4.0
0x9c96d  ldc.i4.0
0x9c96e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c973  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c978  ldloc.0
0x9c979  ldstr    aBaseid_0// "@BaseId"
0x9c97e  ldc.i4.s 0xE
0x9c980  ldc.i4.0
0x9c981  ldc.i4.0
0x9c982  ldc.i4.0
0x9c983  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c988  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c98d  ldloc.0
0x9c98e  ldstr    aRequestguid// "@RequestGuid"
0x9c993  ldc.i4.s 0xE
0x9c995  ldc.i4.0
0x9c996  ldc.i4.1
0x9c997  ldc.i4.1
0x9c998  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c99d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c9a2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9c9a7  stloc.0
0x9c9a8  ldarg.0
0x9c9a9  ldstr    aProcCountworkf_1// "proc_CountWorkflowsBatch"
0x9c9ae  ldloc.0
0x9c9af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9c9b4  ldloc.0
0x9c9b5  ldstr    aReturnValue// "@RETURN_VALUE"
0x9c9ba  ldc.i4.8
0x9c9bb  ldc.i4.0
0x9c9bc  ldc.i4.1
0x9c9bd  ldc.i4.0
0x9c9be  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c9c3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c9c8  ldloc.0
0x9c9c9  ldstr    aSiteid_1// "@SiteId"
0x9c9ce  ldc.i4.s 0xE
0x9c9d0  ldc.i4.0
0x9c9d1  ldc.i4.0
0x9c9d2  ldc.i4.0
0x9c9d3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c9d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c9dd  ldloc.0
0x9c9de  ldstr    aWebid_0// "@WebId"
0x9c9e3  ldc.i4.s 0xE
0x9c9e5  ldc.i4.0
0x9c9e6  ldc.i4.0
0x9c9e7  ldc.i4.0
0x9c9e8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9c9ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9c9f2  ldloc.0
0x9c9f3  ldstr    aListid_0// "@ListId"
0x9c9f8  ldc.i4.s 0xE
0x9c9fa  ldc.i4.0
0x9c9fb  ldc.i4.0
0x9c9fc  ldc.i4.0
0x9c9fd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca07  ldloc.0
0x9ca08  ldstr    aContenttypeid// "@ContentTypeId"
0x9ca0d  ldc.i4.s 0xE
0x9ca0f  ldc.i4.0
0x9ca10  ldc.i4.0
0x9ca11  ldc.i4.0
0x9ca12  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca1c  ldloc.0
0x9ca1d  ldstr    aInternalstate// "@InternalState"
0x9ca22  ldc.i4.8
0x9ca23  ldc.i4.0
0x9ca24  ldc.i4.0
0x9ca25  ldc.i4.0
0x9ca26  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca2b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca30  ldloc.0
0x9ca31  ldstr    aRequestguid// "@RequestGuid"
0x9ca36  ldc.i4.s 0xE
0x9ca38  ldc.i4.0
0x9ca39  ldc.i4.1
0x9ca3a  ldc.i4.1
0x9ca3b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca45  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9ca4a  stloc.0
0x9ca4b  ldarg.0
0x9ca4c  ldstr    aProcCreatedefa// "proc_CreateDefaultRoles"
0x9ca51  ldloc.0
0x9ca52  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9ca57  ldloc.0
0x9ca58  ldstr    aReturnValue// "@RETURN_VALUE"
0x9ca5d  ldc.i4.8
0x9ca5e  ldc.i4.0
0x9ca5f  ldc.i4.1
0x9ca60  ldc.i4.0
0x9ca61  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca66  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca6b  ldloc.0
0x9ca6c  ldstr    aSiteid_1// "@SiteId"
0x9ca71  ldc.i4.s 0xE
0x9ca73  ldc.i4.0
0x9ca74  ldc.i4.0
0x9ca75  ldc.i4.0
0x9ca76  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca80  ldloc.0
0x9ca81  ldstr    aWebid_0// "@WebId"
0x9ca86  ldc.i4.s 0xE
0x9ca88  ldc.i4.0
0x9ca89  ldc.i4.0
0x9ca8a  ldc.i4.0
0x9ca8b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ca90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ca95  ldloc.0
0x9ca96  ldstr    aScopeid// "@ScopeId"
0x9ca9b  ldc.i4.s 0xE
0x9ca9d  ldc.i4.0
0x9ca9e  ldc.i4.0
0x9ca9f  ldc.i4.0
0x9caa0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9caa5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9caaa  ldloc.0
0x9caab  ldstr    aUserid_1// "@UserId"
0x9cab0  ldc.i4.8
0x9cab1  ldc.i4.0
0x9cab2  ldc.i4.0
0x9cab3  ldc.i4.0
0x9cab4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cab9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cabe  ldloc.0
0x9cabf  ldstr    aSecondaryconta_0// "@SecondaryContactId"
0x9cac4  ldc.i4.8
0x9cac5  ldc.i4.0
0x9cac6  ldc.i4.0
0x9cac7  ldc.i4.0
0x9cac8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cacd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cad2  ldloc.0
0x9cad3  ldstr    aAdminsname// "@AdminsName"
0x9cad8  ldc.i4.s 0xC
0x9cada  ldc.i4   0xFF
0x9cadf  ldc.i4.0
0x9cae0  ldc.i4.0
0x9cae1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cae6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9caeb  ldloc.0
0x9caec  ldstr    aAdminsdescript// "@AdminsDescription"
0x9caf1  ldc.i4.s 0xC
0x9caf3  ldc.i4   0x200
0x9caf8  ldc.i4.0
0x9caf9  ldc.i4.0
0x9cafa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9caff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb04  ldloc.0
0x9cb05  ldstr    aAdminspermmask// "@AdminsPermMask"
0x9cb0a  ldc.i4.0
0x9cb0b  ldc.i4.0
0x9cb0c  ldc.i4.0
0x9cb0d  ldc.i4.0
0x9cb0e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cb13  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb18  ldloc.0
0x9cb19  ldstr    aAuthorsname// "@AuthorsName"
0x9cb1e  ldc.i4.s 0xC
0x9cb20  ldc.i4   0xFF
0x9cb25  ldc.i4.0
0x9cb26  ldc.i4.0
0x9cb27  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cb2c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb31  ldloc.0
0x9cb32  ldstr    aAuthorsdescrip// "@AuthorsDescription"
0x9cb37  ldc.i4.s 0xC
0x9cb39  ldc.i4   0x200
0x9cb3e  ldc.i4.0
0x9cb3f  ldc.i4.0
0x9cb40  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cb45  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb4a  ldloc.0
0x9cb4b  ldstr    aAuthorspermmas// "@AuthorsPermMask"
0x9cb50  ldc.i4.0
0x9cb51  ldc.i4.0
0x9cb52  ldc.i4.0
0x9cb53  ldc.i4.0
0x9cb54  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cb59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb5e  ldloc.0
0x9cb5f  ldstr    aEditorsname// "@EditorsName"
0x9cb64  ldc.i4.s 0xC
0x9cb66  ldc.i4   0xFF
0x9cb6b  ldc.i4.0
0x9cb6c  ldc.i4.0
0x9cb6d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9cb72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9cb77  ldloc.0
0x9cb78  ldstr    aEditorsdescrip// "@EditorsDescription"
0x9cb7d  ldc.i4.s 0xC
0x9cb7f  ldc.i4   0x200
0x9cb84  ldc.i4.0
0x9cb85  ldc.i4.0
  ... truncated ...
```
