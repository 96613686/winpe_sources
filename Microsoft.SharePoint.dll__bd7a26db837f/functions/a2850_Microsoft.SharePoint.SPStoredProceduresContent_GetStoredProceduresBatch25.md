# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch25

- ea: `0xa2850`
- end: `0xa2f2e`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch25`
- size: `1758`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0xa2983`: `@DeleteTransactionId`
- `0xa29b2`: `@DeleteFlags`
- `0xa2857`: `proc_DeleteView`
- `0xa2921`: `proc_DeleteWeb`
- `0xa29c6`: `@WebIdDelete`
- `0xa29f6`: `proc_DeleteWebPart`
- `0xa2ab6`: `proc_DeleteWebPartPersonalization`
- `0xa2b61`: `proc_DeleteWebPartWhileSaving`
- `0xa2c0d`: `proc_DeleteZoneWebPartsWhileSaving`
- `0xa2d70`: `@IsLink`
- `0xa2dfe`: `@LinksOnly`
- `0xa2e8b`: `@LinksOnly`
- `0xa2e42`: `proc_DeplAddExportObjectDependenciesForCopyJob`
- `0xa2ecf`: `proc_DeplAddExportObjectLinks`

## pseudocode

```c

```

## disassembly

```asm
0xa2850  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xa2855  stloc.0
0xa2856  ldarg.0
0xa2857  ldstr    aProcDeleteview// "proc_DeleteView"
0xa285c  ldloc.0
0xa285d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xa2862  ldloc.0
0xa2863  ldstr    aReturnValue// "@RETURN_VALUE"
0xa2868  ldc.i4.8
0xa2869  ldc.i4.0
0xa286a  ldc.i4.1
0xa286b  ldc.i4.0
0xa286c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2871  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2876  ldloc.0
0xa2877  ldstr    aSiteid_1// "@SiteId"
0xa287c  ldc.i4.s 0xE
0xa287e  ldc.i4.0
0xa287f  ldc.i4.0
0xa2880  ldc.i4.0
0xa2881  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2886  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa288b  ldloc.0
0xa288c  ldstr    aListid_0// "@ListId"
0xa2891  ldc.i4.s 0xE
0xa2893  ldc.i4.0
0xa2894  ldc.i4.0
0xa2895  ldc.i4.0
0xa2896  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa289b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa28a0  ldloc.0
0xa28a1  ldstr    aViewid// "@ViewId"
0xa28a6  ldc.i4.s 0xE
0xa28a8  ldc.i4.0
0xa28a9  ldc.i4.0
0xa28aa  ldc.i4.0
0xa28ab  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa28b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa28b5  ldloc.0
0xa28b6  ldstr    aCanmanageperso// "@CanManagePersonalViews"
0xa28bb  ldc.i4.2
0xa28bc  ldc.i4.0
0xa28bd  ldc.i4.0
0xa28be  ldc.i4.0
0xa28bf  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa28c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa28c9  ldloc.0
0xa28ca  ldstr    aCanmanagelists// "@CanManageLists"
0xa28cf  ldc.i4.2
0xa28d0  ldc.i4.0
0xa28d1  ldc.i4.0
0xa28d2  ldc.i4.0
0xa28d3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa28d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa28dd  ldloc.0
0xa28de  ldstr    aUserid_1// "@UserId"
0xa28e3  ldc.i4.8
0xa28e4  ldc.i4.0
0xa28e5  ldc.i4.0
0xa28e6  ldc.i4.0
0xa28e7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa28ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa28f1  ldloc.0
0xa28f2  ldstr    aAppprincipalid// "@AppPrincipalId"
0xa28f7  ldc.i4.8
0xa28f8  ldc.i4.0
0xa28f9  ldc.i4.0
0xa28fa  ldc.i4.0
0xa28fb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2900  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2905  ldloc.0
0xa2906  ldstr    aRequestguid// "@RequestGuid"
0xa290b  ldc.i4.s 0xE
0xa290d  ldc.i4.0
0xa290e  ldc.i4.1
0xa290f  ldc.i4.1
0xa2910  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2915  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa291a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xa291f  stloc.0
0xa2920  ldarg.0
0xa2921  ldstr    aProcDeleteweb// "proc_DeleteWeb"
0xa2926  ldloc.0
0xa2927  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xa292c  ldloc.0
0xa292d  ldstr    aReturnValue// "@RETURN_VALUE"
0xa2932  ldc.i4.8
0xa2933  ldc.i4.0
0xa2934  ldc.i4.1
0xa2935  ldc.i4.0
0xa2936  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa293b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2940  ldloc.0
0xa2941  ldstr    aWebsiteid// "@WebSiteId"
0xa2946  ldc.i4.s 0xE
0xa2948  ldc.i4.0
0xa2949  ldc.i4.0
0xa294a  ldc.i4.0
0xa294b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2950  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2955  ldloc.0
0xa2956  ldstr    aWeburl_0// "@WebUrl"
0xa295b  ldc.i4.s 0xC
0xa295d  ldc.i4   0x190
0xa2962  ldc.i4.0
0xa2963  ldc.i4.0
0xa2964  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2969  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa296e  ldloc.0
0xa296f  ldstr    aThresholdrowco// "@ThresholdRowCount"
0xa2974  ldc.i4.8
0xa2975  ldc.i4.0
0xa2976  ldc.i4.0
0xa2977  ldc.i4.1
0xa2978  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa297d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2982  ldloc.0
0xa2983  ldstr    aDeletetransact_0// "@DeleteTransactionId"
0xa2988  ldc.i4.s 0x15
0xa298a  ldc.i4.s 0x10
0xa298c  ldc.i4.0
0xa298d  ldc.i4.1
0xa298e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2993  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2998  ldloc.0
0xa2999  ldstr    aFailedurl// "@FailedUrl"
0xa299e  ldc.i4.s 0xC
0xa29a0  ldc.i4   0x190
0xa29a5  ldc.i4.1
0xa29a6  ldc.i4.1
0xa29a7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa29ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa29b1  ldloc.0
0xa29b2  ldstr    aDeleteflags// "@DeleteFlags"
0xa29b7  ldc.i4.8
0xa29b8  ldc.i4.0
0xa29b9  ldc.i4.0
0xa29ba  ldc.i4.1
0xa29bb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa29c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa29c5  ldloc.0
0xa29c6  ldstr    aWebiddelete// "@WebIdDelete"
0xa29cb  ldc.i4.s 0xE
0xa29cd  ldc.i4.0
0xa29ce  ldc.i4.0
0xa29cf  ldc.i4.1
0xa29d0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa29d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa29da  ldloc.0
0xa29db  ldstr    aRequestguid// "@RequestGuid"
0xa29e0  ldc.i4.s 0xE
0xa29e2  ldc.i4.0
0xa29e3  ldc.i4.1
0xa29e4  ldc.i4.1
0xa29e5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa29ea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa29ef  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xa29f4  stloc.0
0xa29f5  ldarg.0
0xa29f6  ldstr    aProcDeletewebp// "proc_DeleteWebPart"
0xa29fb  ldloc.0
0xa29fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xa2a01  ldloc.0
0xa2a02  ldstr    aReturnValue// "@RETURN_VALUE"
0xa2a07  ldc.i4.8
0xa2a08  ldc.i4.0
0xa2a09  ldc.i4.1
0xa2a0a  ldc.i4.0
0xa2a0b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a15  ldloc.0
0xa2a16  ldstr    aSiteid_1// "@SiteId"
0xa2a1b  ldc.i4.s 0xE
0xa2a1d  ldc.i4.0
0xa2a1e  ldc.i4.0
0xa2a1f  ldc.i4.0
0xa2a20  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a2a  ldloc.0
0xa2a2b  ldstr    aDirname_0// "@DirName"
0xa2a30  ldc.i4.s 0xC
0xa2a32  ldc.i4   0x190
0xa2a37  ldc.i4.0
0xa2a38  ldc.i4.0
0xa2a39  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a43  ldloc.0
0xa2a44  ldstr    aLeafname// "@LeafName"
0xa2a49  ldc.i4.s 0xC
0xa2a4b  ldc.i4   0x190
0xa2a50  ldc.i4.0
0xa2a51  ldc.i4.0
0xa2a52  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a57  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a5c  ldloc.0
0xa2a5d  ldstr    aLevel_1// "@Level"
0xa2a62  ldc.i4.s 0x14
0xa2a64  ldc.i4.0
0xa2a65  ldc.i4.1
0xa2a66  ldc.i4.0
0xa2a67  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a6c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a71  ldloc.0
0xa2a72  ldstr    aUserid_1// "@UserId"
0xa2a77  ldc.i4.8
0xa2a78  ldc.i4.0
0xa2a79  ldc.i4.0
0xa2a7a  ldc.i4.0
0xa2a7b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a85  ldloc.0
0xa2a86  ldstr    aWebpartid// "@WebPartId"
0xa2a8b  ldc.i4.s 0xE
0xa2a8d  ldc.i4.0
0xa2a8e  ldc.i4.0
0xa2a8f  ldc.i4.0
0xa2a90  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2a95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2a9a  ldloc.0
0xa2a9b  ldstr    aRequestguid// "@RequestGuid"
0xa2aa0  ldc.i4.s 0xE
0xa2aa2  ldc.i4.0
0xa2aa3  ldc.i4.1
0xa2aa4  ldc.i4.1
0xa2aa5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2aaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2aaf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xa2ab4  stloc.0
0xa2ab5  ldarg.0
0xa2ab6  ldstr    aProcDeletewebp_0// "proc_DeleteWebPartPersonalization"
0xa2abb  ldloc.0
0xa2abc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xa2ac1  ldloc.0
0xa2ac2  ldstr    aReturnValue// "@RETURN_VALUE"
0xa2ac7  ldc.i4.8
0xa2ac8  ldc.i4.0
0xa2ac9  ldc.i4.1
0xa2aca  ldc.i4.0
0xa2acb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2ad0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2ad5  ldloc.0
0xa2ad6  ldstr    aSiteid_1// "@SiteId"
0xa2adb  ldc.i4.s 0xE
0xa2add  ldc.i4.0
0xa2ade  ldc.i4.0
0xa2adf  ldc.i4.0
0xa2ae0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2ae5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2aea  ldloc.0
0xa2aeb  ldstr    aDirname_0// "@DirName"
0xa2af0  ldc.i4.s 0xC
0xa2af2  ldc.i4   0x190
0xa2af7  ldc.i4.0
0xa2af8  ldc.i4.0
0xa2af9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2afe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2b03  ldloc.0
0xa2b04  ldstr    aLeafname// "@LeafName"
0xa2b09  ldc.i4.s 0xC
0xa2b0b  ldc.i4   0x190
0xa2b10  ldc.i4.0
0xa2b11  ldc.i4.0
0xa2b12  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2b17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2b1c  ldloc.0
0xa2b1d  ldstr    aUserid_1// "@UserId"
0xa2b22  ldc.i4.8
0xa2b23  ldc.i4.0
0xa2b24  ldc.i4.0
0xa2b25  ldc.i4.0
0xa2b26  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2b2b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2b30  ldloc.0
0xa2b31  ldstr    aWebpartid// "@WebPartId"
0xa2b36  ldc.i4.s 0xE
0xa2b38  ldc.i4.0
0xa2b39  ldc.i4.0
0xa2b3a  ldc.i4.0
0xa2b3b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2b40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2b45  ldloc.0
0xa2b46  ldstr    aRequestguid// "@RequestGuid"
0xa2b4b  ldc.i4.s 0xE
0xa2b4d  ldc.i4.0
0xa2b4e  ldc.i4.1
0xa2b4f  ldc.i4.1
0xa2b50  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xa2b55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xa2b5a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xa2b5f  stloc.0
0xa2b60  ldarg.0
0xa2b61  ldstr    aProcDeletewebp_1// "proc_DeleteWebPartWhileSaving"
0xa2b66  ldloc.0
0xa2b67  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xa2b6c  ldloc.0
0xa2b6d  ldstr    aReturnValue// "@RETURN_VALUE"
0xa2b72  ldc.i4.8
0xa2b73  ldc.i4.0
0xa2b74  ldc.i4.1
0xa2b75  ldc.i4.0
  ... truncated ...
```
