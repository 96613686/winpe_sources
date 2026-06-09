# Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::MapErrorMessage

- ea: `0x37730`
- end: `0x378eb`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::MapErrorMessage`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x378f0`

## callees

- `0x2acd0`
- `0x37730`

## string_xrefs

- `0x3778b`: `Sql exception readable message: `
- `0x37899`: `Sql exception readable message: `
- `0x37882`: `ErrorFailedToReadOrWriteDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x37730  ldstr    aSqlerror// "SqlError_"
0x37735  ldarg.0
0x37736  box      [mscorlib]System.Int32
0x3773b  call     string [mscorlib]System.String::Concat(object, object)
0x37740  stloc.0
0x37741  ldstr    asc_794BA// ""
0x37746  stloc.1
0x37747  ldarg.0
0x37748  ldc.i4.s 0x16
0x3774a  beq.s    loc_37751
0x3774c  ldarg.0
0x3774d  ldc.i4.s 0x17
0x3774f  bne.un.s loc_377A6
0x37751  ldloc.0
0x37752  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x37757  stloc.1
0x37758  ldarg.1
0x37759  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3775e  brtrue.s loc_3777F
0x37760  ldarg.1
0x37761  callvirt instance string [mscorlib]System.String::Trim()
0x37766  starg.s  1
0x37768  ldarg.1
0x37769  ldstr    asc_7CB8A// ";"
0x3776e  ldc.i4.4
0x3776f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x37774  brfalse.s loc_3777F
0x37776  ldarg.1
0x37777  ldc.i4.1
0x37778  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3777d  starg.s  1
0x3777f  ldc.i4   0x6638726D
0x37784  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x37789  ldc.i4.s 0x14
0x3778b  ldstr    aSqlExceptionRe// "Sql exception readable message: "
0x37790  ldloc.1
0x37791  ldstr    aThoseObjectsNa// " Those objects(name(Guid)) are: "
0x37796  ldarg.1
0x37797  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3779c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x377a1  br       loc_378A9
0x377a6  ldarg.0
0x377a7  ldc.i4.s 0x1C
0x377a9  bne.un   loc_37857
0x377ae  ldarg.1
0x377af  ldloca.s 2
0x377b1  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x377b6  brfalse.s loc_37830
0x377b8  ldloc.2
0x377b9  stloc.3
0x377ba  ldloc.3
0x377bb  ldc.i4.1
0x377bc  sub
0x377bd  switch   loc_377E3, loc_377F3, loc_37803, loc_378A9, loc_378A9, loc_37813, loc_37823
0x377de  br       loc_378A9
0x377e3  ldstr    aSqlerror28Term// "SqlError_28_Term"
0x377e8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x377ed  stloc.1
0x377ee  br       loc_378A9
0x377f3  ldstr    aSqlerror28Term_0// "SqlError_28_TermSet"
0x377f8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x377fd  stloc.1
0x377fe  br       loc_378A9
0x37803  ldstr    aSqlerror28Grou// "SqlError_28_Group"
0x37808  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3780d  stloc.1
0x3780e  br       loc_378A9
0x37813  ldstr    aSqlerror28Labe// "SqlError_28_Label"
0x37818  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3781d  stloc.1
0x3781e  br       loc_378A9
0x37823  ldstr    aSqlerror28Prop// "SqlError_28_Property"
0x37828  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3782d  stloc.1
0x3782e  br.s     loc_378A9
0x37830  ldc.i4   0x1DB457
0x37835  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3783a  ldc.i4.s 0xA
0x3783c  ldstr    aInvalidSqlQuot// "Invalid sql quota error message {0}"
0x37841  ldc.i4.1
0x37842  newarr   [mscorlib]System.Object
0x37847  stloc.s  4
0x37849  ldloc.s  4
0x3784b  ldc.i4.0
0x3784c  ldarg.1
0x3784d  stelem.ref
0x3784e  ldloc.s  4
0x37850  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x37855  br.s     loc_378A9
0x37857  ldloc.0
0x37858  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3785d  stloc.1
0x3785e  ldloc.1
0x3785f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37864  brfalse.s loc_3788D
0x37866  ldc.i4   0x786F7A64
0x3786b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x37870  ldc.i4.s 0xA
0x37872  ldstr    aInvalidSqlErro// "Invalid sql error message Id: "
0x37877  ldloc.0
0x37878  call     string [mscorlib]System.String::Concat(string, string)
0x3787d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x37882  ldstr    aErrorfailedtor// "ErrorFailedToReadOrWriteDatabase"
0x37887  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3788c  stloc.1
0x3788d  ldc.i4   0x786F7A65
0x37892  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x37897  ldc.i4.s 0xA
0x37899  ldstr    aSqlExceptionRe// "Sql exception readable message: "
0x3789e  ldloc.1
0x3789f  call     string [mscorlib]System.String::Concat(string, string)
0x378a4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x378a9  leave.s  loc_378E9
0x378ab  pop
0x378ac  ldc.i4   0x786F7A68
0x378b1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x378b6  ldc.i4.s 0xA
0x378b8  ldstr    aInvalidSqlErro// "Invalid sql error message Id: "
0x378bd  ldloc.0
0x378be  call     string [mscorlib]System.String::Concat(string, string)
0x378c3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x378c8  leave.s  loc_378E9
0x378ca  pop
0x378cb  ldc.i4   0x786F7A69
0x378d0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x378d5  ldc.i4.s 0xA
0x378d7  ldstr    aInvalidSqlErro// "Invalid sql error message Id: "
0x378dc  ldloc.0
0x378dd  call     string [mscorlib]System.String::Concat(string, string)
0x378e2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x378e7  leave.s  loc_378E9
0x378e9  ldloc.1
0x378ea  ret
```
