# UpdateTermSet::CreateCommand

- ea: `0x36750`
- end: `0x36894`
- name: `UpdateTermSet::CreateCommand`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x342e0`

## callees

- `0x178f0`
- `0x242a0`
- `0x35080`
- `0x350b0`
- `0x350d0`
- `0x35110`
- `0x35170`
- `0x35190`
- `0x36750`

## string_xrefs

- `0x367e6`: `@IsOpen='{0}' `
- `0x3675d`: `proc_ECM_UpdateTermSet`

## pseudocode

```c

```

## disassembly

```asm
0x36750  ldarg.1
0x36751  ldstr    aBuilder// "builder"
0x36756  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3675b  ldarg.1
0x3675c  ldarg.0
0x3675d  ldstr    aProcEcmUpdatet// "proc_ECM_UpdateTermSet"
0x36762  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x36767  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3676c  pop
0x3676d  ldarg.1
0x3676e  ldstr    asc_7D394// " "
0x36773  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36778  pop
0x36779  ldarg.1
0x3677a  ldstr    aPartitionid0// "@PartitionId='{0}' "
0x3677f  ldarg.3
0x36780  box      [mscorlib]System.Guid
0x36785  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3678a  pop
0x3678b  ldarg.1
0x3678c  ldc.i4.s 0x2C
0x3678e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x36793  pop
0x36794  ldarg.1
0x36795  ldstr    aId0_0// "@Id='{0}' "
0x3679a  ldarg.s  4
0x3679c  box      [mscorlib]System.Int32
0x367a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x367a6  pop
0x367a7  ldarg.1
0x367a8  ldarg.2
0x367a9  ldarg.s  5
0x367ab  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendTermSetName(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string allNames)
0x367b0  ldarg.s  6
0x367b2  brfalse.s loc_367BD
0x367b4  ldarg.1
0x367b5  ldarg.2
0x367b6  ldarg.s  6
0x367b8  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendDescription(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string description)
0x367bd  ldarg.1
0x367be  ldarg.2
0x367bf  ldarg.s  7
0x367c1  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendOwner(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string owner)
0x367c6  ldarg.s  8
0x367c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x367cd  brtrue.s loc_367D8
0x367cf  ldarg.1
0x367d0  ldarg.2
0x367d1  ldarg.s  8
0x367d3  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendCustomSortOrder(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string customSortOrder)
0x367d8  ldarg.s  9
0x367da  brfalse.s loc_367FD
0x367dc  ldarg.1
0x367dd  ldc.i4.s 0x2C
0x367df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x367e4  pop
0x367e5  ldarg.1
0x367e6  ldstr    aIsopen0// "@IsOpen='{0}' "
0x367eb  ldarg.s  9
0x367ed  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x367f2  box      [mscorlib]System.Int32
0x367f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x367fc  pop
0x367fd  ldarg.s  0xA
0x367ff  brfalse.s loc_36822
0x36801  ldarg.1
0x36802  ldc.i4.s 0x2C
0x36804  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x36809  pop
0x3680a  ldarg.1
0x3680b  ldstr    aAvailableforta// "@AvailableForTagging='{0}' "
0x36810  ldarg.s  0xA
0x36812  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x36817  box      [mscorlib]System.Int32
0x3681c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x36821  pop
0x36822  ldarg.s  0xB
0x36824  brfalse.s loc_3682F
0x36826  ldarg.1
0x36827  ldarg.2
0x36828  ldarg.s  0xB
0x3682a  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendStakeHolders(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string stakeholders)
0x3682f  ldarg.s  0xC
0x36831  brfalse.s loc_3683C
0x36833  ldarg.1
0x36834  ldarg.2
0x36835  ldarg.s  0xC
0x36837  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendContact(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string contact)
0x3683c  ldarg.1
0x3683d  ldc.i4.s 0x2C
0x3683f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x36844  pop
0x36845  ldarg.s  0xD
0x36847  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x3684c  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x36851  brfalse.s loc_36879
0x36853  ldarg.1
0x36854  ldstr    aLastmodifiedti_0// "@LastModifiedTime='{0}' "
0x36859  ldarga.s 0xD
0x3685b  ldstr    aYyyyMmDdthhMmS// "yyyy-MM-ddTHH:mm:ss.fff"
0x36860  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36865  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x3686a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3686f  pop
0x36870  ldarg.1
0x36871  ldc.i4.s 0x2C
0x36873  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x36878  pop
0x36879  ldarg.1
0x3687a  ldstr    aGroupid0// "@GroupId='{0}' "
0x3687f  ldarg.s  0xE
0x36881  box      [mscorlib]System.Int32
0x36886  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3688b  pop
0x3688c  ldarg.1
0x3688d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36892  pop
0x36893  ret
```
