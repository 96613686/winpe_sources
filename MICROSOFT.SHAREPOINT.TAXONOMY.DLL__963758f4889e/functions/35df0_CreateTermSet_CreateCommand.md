# CreateTermSet::CreateCommand

- ea: `0x35df0`
- end: `0x35f73`
- name: `CreateTermSet::CreateCommand`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

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
- `0x35df0`

## string_xrefs

- `0x35dfd`: `proc_ECM_CreateTermSet`
- `0x35ea6`: `@IsOpen='{0}' `

## pseudocode

```c

```

## disassembly

```asm
0x35df0  ldarg.1
0x35df1  ldstr    aBuilder// "builder"
0x35df6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x35dfb  ldarg.1
0x35dfc  ldarg.0
0x35dfd  ldstr    aProcEcmCreatet// "proc_ECM_CreateTermSet"
0x35e02  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x35e07  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35e0c  pop
0x35e0d  ldarg.1
0x35e0e  ldstr    asc_7D394// " "
0x35e13  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35e18  pop
0x35e19  ldarg.1
0x35e1a  ldstr    aPartitionid0// "@PartitionId='{0}' "
0x35e1f  ldarg.3
0x35e20  box      [mscorlib]System.Guid
0x35e25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35e2a  pop
0x35e2b  ldarg.1
0x35e2c  ldc.i4.s 0x2C
0x35e2e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35e33  pop
0x35e34  ldarg.1
0x35e35  ldstr    aUniqueid0// "@UniqueId='{0}' "
0x35e3a  ldarg.s  4
0x35e3c  box      [mscorlib]System.Guid
0x35e41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35e46  pop
0x35e47  ldarg.1
0x35e48  ldarg.2
0x35e49  ldarg.s  5
0x35e4b  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendTermSetName(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string allNames)
0x35e50  ldarg.s  6
0x35e52  brfalse.s loc_35E5D
0x35e54  ldarg.1
0x35e55  ldarg.2
0x35e56  ldarg.s  6
0x35e58  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendDescription(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string description)
0x35e5d  ldarg.1
0x35e5e  ldarg.2
0x35e5f  ldarg.s  7
0x35e61  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendOwner(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string owner)
0x35e66  ldarg.s  8
0x35e68  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35e6d  brtrue.s loc_35E78
0x35e6f  ldarg.1
0x35e70  ldarg.2
0x35e71  ldarg.s  8
0x35e73  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendCustomSortOrder(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string customSortOrder)
0x35e78  ldarg.s  9
0x35e7a  brfalse.s loc_35E98
0x35e7c  ldarg.1
0x35e7d  ldc.i4.s 0x2C
0x35e7f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35e84  pop
0x35e85  ldarg.1
0x35e86  ldstr    aType0// "@Type='{0}' "
0x35e8b  ldarg.s  9
0x35e8d  box      [mscorlib]System.Int32
0x35e92  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35e97  pop
0x35e98  ldarg.s  0xA
0x35e9a  brfalse.s loc_35EBD
0x35e9c  ldarg.1
0x35e9d  ldc.i4.s 0x2C
0x35e9f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35ea4  pop
0x35ea5  ldarg.1
0x35ea6  ldstr    aIsopen0// "@IsOpen='{0}' "
0x35eab  ldarg.s  0xA
0x35ead  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x35eb2  box      [mscorlib]System.Int32
0x35eb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35ebc  pop
0x35ebd  ldarg.s  0xB
0x35ebf  brfalse.s loc_35EE2
0x35ec1  ldarg.1
0x35ec2  ldc.i4.s 0x2C
0x35ec4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35ec9  pop
0x35eca  ldarg.1
0x35ecb  ldstr    aAvailableforta// "@AvailableForTagging='{0}' "
0x35ed0  ldarg.s  0xB
0x35ed2  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x35ed7  box      [mscorlib]System.Int32
0x35edc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35ee1  pop
0x35ee2  ldarg.s  0xC
0x35ee4  brfalse.s loc_35EEF
0x35ee6  ldarg.1
0x35ee7  ldarg.2
0x35ee8  ldarg.s  0xC
0x35eea  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendStakeHolders(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string stakeholders)
0x35eef  ldarg.s  0xD
0x35ef1  brfalse.s loc_35EFC
0x35ef3  ldarg.1
0x35ef4  ldarg.2
0x35ef5  ldarg.s  0xD
0x35ef7  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDefinition::AppendContact(class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, string contact)
0x35efc  ldarg.1
0x35efd  ldc.i4.s 0x2C
0x35eff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35f04  pop
0x35f05  ldarg.1
0x35f06  ldstr    aGroupid0// "@GroupId='{0}' "
0x35f0b  ldarg.s  0xE
0x35f0d  box      [mscorlib]System.Int32
0x35f12  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35f17  pop
0x35f18  ldarg.1
0x35f19  ldc.i4.s 0x2C
0x35f1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35f20  pop
0x35f21  ldarg.1
0x35f22  ldstr    aOldid0// "@OldId='{0}' "
0x35f27  ldarg.s  0xF
0x35f29  box      [mscorlib]System.Int32
0x35f2e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35f33  pop
0x35f34  ldarg.s  0x10
0x35f36  stloc.0
0x35f37  ldloca.s 0
0x35f39  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x35f3e  brtrue.s loc_35F4C
0x35f40  ldloca.s 0
0x35f42  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x35f47  ldc.i4.0
0x35f48  ceq
0x35f4a  br.s     loc_35F4D
0x35f4c  ldc.i4.1
0x35f4d  brfalse.s loc_35F6B
0x35f4f  ldarg.1
0x35f50  ldc.i4.s 0x2C
0x35f52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x35f57  pop
0x35f58  ldarg.1
0x35f59  ldstr    aSourceid0// "@SourceId='{0}' "
0x35f5e  ldarg.s  0x10
0x35f60  box      valuetype [mscorlib]System.Nullable`1<int32>
0x35f65  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x35f6a  pop
0x35f6b  ldarg.1
0x35f6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x35f71  pop
0x35f72  ret
```
