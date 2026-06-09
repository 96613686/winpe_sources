# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::SearchTermByLabel_0

- ea: `0x18e10`
- end: `0x1925b`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::SearchTermByLabel_0`
- size: `1099`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18de0`
- `0x1d3a0`

## callees

- `0x178f0`
- `0x18e10`
- `0x19bd0`
- `0x19e40`
- `0x19fb0`
- `0x1a000`

## string_xrefs

- `0x18fbc`: `@IncludeIdPath`
- `0x18fd3`: `@IncludeIdPath`
- `0x1905b`: `@GetFullPath`
- `0x19072`: `@GetFullPath`

## pseudocode

```c

```

## disassembly

```asm
0x18e10  ldc.i4   0x3134396D
0x18e15  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x18e1a  ldc.i4.s 0x64
0x18e1c  ldstr    aFindingTermsBy// "Finding Terms by label"
0x18e21  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x18e26  ldnull
0x18e27  stloc.0
0x18e28  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x18e2d  stloc.1
0x18e2e  ldloc.1
0x18e2f  ldc.i4.4
0x18e30  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x18e35  ldloc.1
0x18e36  ldarg.0
0x18e37  ldstr    aProcEcmSearchb// "proc_ECM_SearchByLabel"
0x18e3c  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x18e41  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x18e46  ldloc.1
0x18e47  ldarg.0
0x18e48  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x18e4d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x18e52  ldloc.1
0x18e53  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18e58  ldstr    aPartitionid// "@PartitionId"
0x18e5d  ldc.i4.s 0xE
0x18e5f  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18e64  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18e69  pop
0x18e6a  ldloc.1
0x18e6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18e70  ldstr    aPartitionid// "@PartitionId"
0x18e75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18e7a  ldarg.1
0x18e7b  box      [mscorlib]System.Guid
0x18e80  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18e85  ldarga.s 2
0x18e87  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x18e8c  brfalse.s loc_18EC6
0x18e8e  ldloc.1
0x18e8f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18e94  ldstr    aTermsetid_0// "@TermSetId"
0x18e99  ldc.i4.8
0x18e9a  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18e9f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18ea4  pop
0x18ea5  ldloc.1
0x18ea6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18eab  ldstr    aTermsetid_0// "@TermSetId"
0x18eb0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18eb5  ldarga.s 2
0x18eb7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x18ebc  box      [mscorlib]System.Int32
0x18ec1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18ec6  ldarga.s 3
0x18ec8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x18ecd  brfalse.s loc_18F07
0x18ecf  ldloc.1
0x18ed0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18ed5  ldstr    aAnchorid_0// "@AnchorId"
0x18eda  ldc.i4.8
0x18edb  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18ee0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18ee5  pop
0x18ee6  ldloc.1
0x18ee7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18eec  ldstr    aAnchorid_0// "@AnchorId"
0x18ef1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18ef6  ldarga.s 3
0x18ef8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x18efd  box      [mscorlib]System.Int32
0x18f02  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18f07  ldloc.1
0x18f08  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18f0d  ldstr    aLabel// "@Label"
0x18f12  ldc.i4.s 0xC
0x18f14  ldc.i4   0xFF
0x18f19  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x18f1e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18f23  pop
0x18f24  ldloc.1
0x18f25  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18f2a  ldstr    aLabel// "@Label"
0x18f2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18f34  ldarg.s  4
0x18f36  ldarg.s  8
0x18f38  call     string Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetSQLEscapedString(string inputString, valuetype Microsoft.SharePoint.Taxonomy.StringMatchOption matchOption)
0x18f3d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18f42  ldarga.s 5
0x18f44  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x18f49  brfalse.s loc_18F83
0x18f4b  ldloc.1
0x18f4c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18f51  ldstr    aLcid// "@Lcid"
0x18f56  ldc.i4.8
0x18f57  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18f5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18f61  pop
0x18f62  ldloc.1
0x18f63  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18f68  ldstr    aLcid// "@Lcid"
0x18f6d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18f72  ldarga.s 5
0x18f74  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x18f79  box      [mscorlib]System.Int32
0x18f7e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18f83  ldloc.1
0x18f84  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18f89  ldstr    aDefaultlabelon// "@DefaultLabelOnly"
0x18f8e  ldc.i4.2
0x18f8f  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18f94  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18f99  pop
0x18f9a  ldloc.1
0x18f9b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18fa0  ldstr    aDefaultlabelon// "@DefaultLabelOnly"
0x18fa5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18faa  ldarg.s  6
0x18fac  box      [mscorlib]System.Boolean
0x18fb1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18fb6  ldloc.1
0x18fb7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18fbc  ldstr    aIncludeidpath// "@IncludeIdPath"
0x18fc1  ldc.i4.2
0x18fc2  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18fc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18fcc  pop
0x18fcd  ldloc.1
0x18fce  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18fd3  ldstr    aIncludeidpath// "@IncludeIdPath"
0x18fd8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x18fdd  ldarg.s  7
0x18fdf  box      [mscorlib]System.Boolean
0x18fe4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18fe9  ldloc.1
0x18fea  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18fef  ldstr    aMatchoption// "@MatchOption"
0x18ff4  ldc.i4.s 0x10
0x18ff6  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x18ffb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x19000  pop
0x19001  ldloc.1
0x19002  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19007  ldstr    aMatchoption// "@MatchOption"
0x1900c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x19011  ldarg.s  8
0x19013  conv.ovf.i1.un
0x19014  box      [mscorlib]System.Int16
0x19019  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1901e  ldloc.1
0x1901f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19024  ldstr    aResultsize// "@ResultSize"
0x19029  ldc.i4.8
0x1902a  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x1902f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x19034  pop
0x19035  ldloc.1
0x19036  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1903b  ldstr    aResultsize// "@ResultSize"
0x19040  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x19045  ldarg.s  9
0x19047  box      [mscorlib]System.Int32
0x1904c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19051  ldarg.s  0xA
0x19053  brfalse.s loc_19088
0x19055  ldloc.1
0x19056  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1905b  ldstr    aGetfullpath// "@GetFullPath"
0x19060  ldc.i4.2
0x19061  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x19066  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1906b  pop
0x1906c  ldloc.1
0x1906d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19072  ldstr    aGetfullpath// "@GetFullPath"
0x19077  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x1907c  ldarg.s  0xA
0x1907e  box      [mscorlib]System.Boolean
0x19083  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19088  ldarga.s 0xB
0x1908a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1908f  brfalse.s loc_190C9
0x19091  ldloc.1
0x19092  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19097  ldstr    aDefaultlcid// "@DefaultLcid"
0x1909c  ldc.i4.8
0x1909d  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x190a2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x190a7  pop
0x190a8  ldloc.1
0x190a9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x190ae  ldstr    aDefaultlcid// "@DefaultLcid"
0x190b3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x190b8  ldarga.s 0xB
0x190ba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x190bf  box      [mscorlib]System.Int32
0x190c4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x190c9  ldarg.s  0xC
0x190cb  brfalse.s loc_19100
0x190cd  ldloc.1
0x190ce  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x190d3  ldstr    aIsoptimized// "@IsOptimized"
0x190d8  ldc.i4.2
0x190d9  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x190de  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x190e3  pop
0x190e4  ldloc.1
0x190e5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x190ea  ldstr    aIsoptimized// "@IsOptimized"
0x190ef  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x190f4  ldarg.s  0xC
0x190f6  box      [mscorlib]System.Boolean
0x190fb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19100  ldarg.s  0xD
0x19102  brfalse.s loc_19137
0x19104  ldloc.1
0x19105  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1910a  ldstr    aGetalllocalter// "@GetAllLocalTermSets"
0x1910f  ldc.i4.2
0x19110  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x19115  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1911a  pop
0x1911b  ldloc.1
0x1911c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19121  ldstr    aGetalllocalter// "@GetAllLocalTermSets"
0x19126  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x1912b  ldarg.s  0xD
0x1912d  box      [mscorlib]System.Boolean
0x19132  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19137  ldarga.s 0xE
0x19139  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1913e  brfalse.s loc_19178
0x19140  ldloc.1
0x19141  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19146  ldstr    aSitegroupid// "SiteGroupId"
0x1914b  ldc.i4.8
0x1914c  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x19151  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x19156  pop
0x19157  ldloc.1
0x19158  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1915d  ldstr    aSitegroupid// "SiteGroupId"
0x19162  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x19167  ldarga.s 0xE
0x19169  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1916e  box      [mscorlib]System.Int32
0x19173  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19178  ldnull
0x19179  stloc.2
0x1917a  ldstr    aCollationforlc// "@CollationForLcid"
0x1917f  ldc.i4.s 0xC
0x19181  ldc.i4   0x80
0x19186  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x1918b  stloc.2
0x1918c  ldloc.2
0x1918d  ldc.i4.3
0x1918e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x19193  ldloc.2
0x19194  ldarg.s  0xF
0x19196  ldind.ref
0x19197  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1919c  ldloc.1
0x1919d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x191a2  ldloc.2
0x191a3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x191a8  pop
0x191a9  ldnull
0x191aa  stloc.3
0x191ab  ldstr    aCollationforde// "@CollationForDefaultLcid"
0x191b0  ldc.i4.s 0xC
0x191b2  ldc.i4   0x80
0x191b7  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x191bc  stloc.3
0x191bd  ldloc.3
0x191be  ldc.i4.3
0x191bf  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x191c4  ldloc.3
0x191c5  ldarg.s  0xF
0x191c7  ldind.ref
0x191c8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x191cd  ldloc.1
0x191ce  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x191d3  ldloc.3
0x191d4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x191d9  pop
0x191da  ldarga.s 2
0x191dc  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x191e1  ldarg.s  0xC
0x191e3  call     string[] Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetSearchedTermsTableNames(bool isTermSetScoped, bool isOptimized)
0x191e8  stloc.s  4
0x191ea  ldarg.0
0x191eb  ldloc.1
0x191ec  ldloc.s  4
0x191ee  ldc.i4.1
0x191ef  call     instance string Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetResultXML(class [System.Data]System.Data.SqlClient.SqlCommand command, string[] tableNameList, valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x191f4  stloc.0
0x191f5  ldloc.2
0x191f6  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x191fb  call     bool [mscorlib]System.Convert::IsDBNull(object)
0x19200  brtrue.s loc_19212
0x19202  ldarg.s  0xF
  ... truncated ...
```
