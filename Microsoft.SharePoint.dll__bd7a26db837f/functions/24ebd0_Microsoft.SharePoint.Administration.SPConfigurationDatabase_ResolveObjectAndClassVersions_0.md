# Microsoft.SharePoint.Administration.SPConfigurationDatabase::ResolveObjectAndClassVersions_0

- ea: `0x24ebd0`
- end: `0x24f3e9`
- name: `Microsoft.SharePoint.Administration.SPConfigurationDatabase::ResolveObjectAndClassVersions_0`
- size: `2073`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x24ebc0`

## callees

- `0x1c8490`
- `0x1c8540`
- `0x1c8680`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a80`
- `0x2271c0`
- `0x242050`
- `0x249d80`
- `0x249d90`
- `0x24a050`
- `0x24d7b0`
- `0x24eae0`
- `0x24ebd0`
- `0x24f3f0`
- `0x24f430`
- `0x24f4c0`
- `0x2529a0`
- `0x252fc0`
- `0x253480`
- `0x285d10`
- `0x29ae90`
- `0x6c9890`
- `0x7cb310`
- `0xa4f180`
- `0xa4f270`

## string_xrefs

- `0x24ebdd`: `Update classes and persisted objects so that the assembly qualified names in the serialized XML are referencing to the latest version found in the farm.`
- `0x24ebf2`: `Parameters to the function. handleTypesWithPathChanges={0},deleteObjectsOfUnresolvedType={1}`
- `0x24ecf9`: `UPDATE Classes SET FullName = '{0}' WHERE Id = '{1}';`
- `0x24ed87`: `Cannot deserialize type {0} (id = {1}).`
- `0x24ee22`: `\n                DECLARE @ObjectLevelTbl TABLE (Id uniqueidentifier PRIMARY KEY, ClassId uniqueidentifier, Level int)\n                INSERT INTO @ObjectLevelTbl SELECT Id, ClassId, NULL FROM Objects\n\n                UPDATE \n                    @ObjectLevelTbl \n                SET \n                    Level=0 \n                FROM \n                    @ObjectLevelTbl AS O\n                LEFT OUTER JOIN\n                    Dependencies AS D\n                ON\n          `
- `0x24ee33`: `useGetConfigObjectsInOrderNew`
- `0x24ee3f`: `            \n                DECLARE @ObjectLevelTbl TABLE (Id uniqueidentifier PRIMARY KEY, ClassId uniqueidentifier, Level int)\n                INSERT INTO @ObjectLevelTbl SELECT Id, ClassId, NULL FROM Objects\n\n                UPDATE \n                    @ObjectLevelTbl \n                SET \n                    Level=0 \n                FROM \n                    @ObjectLevelTbl AS O\n                LEFT OUTER JOIN\n                    Dependencies AS D\n                ON`
- `0x24eeb7`: `Retrieving and updating object {0} because its class id {1} is also being updated.`
- `0x24ef1b`: `Object with Id {0} and class id {1} could not be deserialized. Most likely its type is no longer a sub class of SPPersistedObject.`
- `0x24efd9`: `SPProcessIdentity object {0} is not updated because its parent's type cannot be resolved yet.`
- `0x24f09f`: `Object {0} is deleted because its class id {1} does not load and no other objects depend on it.`
- `0x24f11b`: `Object {0} is not updated because its class id {1} is not being updated either.`
- `0x24f183`: `[{0}] objects are updated, and [{1}] objects are skipped.`
- `0x24f1bd`: `[{0}] SPProcessIdentify objects needs to be updated.`
- `0x24f240`: `Upgrading SPProcessIdentity Object id = [{0}]`
- `0x24f382`: `{0} objects of unresolved types have been deleted. {1} objects of unresolved types are not deleted because of dependencies.`
- `0x24f3c1`: `Will make one more pass of the objects to see if any of the unresolved objects could be deleted because their dependencies are removed.`

## pseudocode

```c

```

## disassembly

```asm
0x24ebd0  ldarg.0
0x24ebd1  call     instance bool Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_AutoResolveMissingTypes()
0x24ebd6  stloc.0
0x24ebd7  ldarg.1
0x24ebd8  ldc.i4   0x2603E1
0x24ebdd  ldstr    aUpdateClassesA// "Update classes and persisted objects so"...
0x24ebe2  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24ebe7  ldarg.1
0x24ebe8  ldc.i4   0x108A203
0x24ebed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ebf2  ldstr    aParametersToTh// "Parameters to the function. handleTypes"...
0x24ebf7  ldc.i4.2
0x24ebf8  newarr   [mscorlib]System.Object
0x24ebfd  stloc.s  0x21
0x24ebff  ldloc.s  0x21
0x24ec01  ldc.i4.0
0x24ec02  ldarg.2
0x24ec03  box      [mscorlib]System.Boolean
0x24ec08  stelem.ref
0x24ec09  ldloc.s  0x21
0x24ec0b  ldc.i4.1
0x24ec0c  ldarg.3
0x24ec0d  box      [mscorlib]System.Boolean
0x24ec12  stelem.ref
0x24ec13  ldloc.s  0x21
0x24ec15  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ec1a  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24ec1f  ldarg.0
0x24ec20  ldc.i4.1
0x24ec21  call     instance void Microsoft.SharePoint.Administration.SPConfigurationDatabase::set_AutoResolveMissingTypes(bool value)
0x24ec26  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x24ec2b  stloc.1
0x24ec2c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24ec31  stloc.2
0x24ec32  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24ec37  stloc.3
0x24ec38  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24ec3d  stloc.s  4
0x24ec3f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x24ec44  stloc.s  5
0x24ec46  ldc.i4.0
0x24ec47  stloc.s  6
0x24ec49  ldc.i4.0
0x24ec4a  stloc.s  7
0x24ec4c  ldstr    aSelectIdFullna// "SELECT Id, FullName FROM Classes"
0x24ec51  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string)
0x24ec56  stloc.s  8
0x24ec58  ldarg.0
0x24ec59  call     instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_SqlSession()
0x24ec5e  ldloc.s  8
0x24ec60  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader Microsoft.SharePoint.Utilities.SqlSession::ExecuteReader(class [System.Data]System.Data.SqlClient.SqlCommand command)
0x24ec65  stloc.s  9
0x24ec67  br       loc_24EDBA
0x24ec6c  ldloc.s  9
0x24ec6e  ldc.i4.0
0x24ec6f  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.Common.DbDataReader::GetGuid(int32)
0x24ec74  stloc.s  0xA
0x24ec76  ldloc.s  9
0x24ec78  ldc.i4.1
0x24ec79  callvirt instance string [System.Data]System.Data.Common.DbDataReader::GetString(int32)
0x24ec7e  stloc.s  0xB
0x24ec80  ldloc.s  0xB
0x24ec82  ldloc.s  0xA
0x24ec84  ldc.i4.1
0x24ec85  call     class [mscorlib]System.Type Microsoft.SharePoint.Utilities.SPTypeSerializer::DeserializeType(string typeName, valuetype [mscorlib]System.Guid classId, bool bResolveMissingTypes)
0x24ec8a  stloc.s  0xC
0x24ec8c  ldloc.s  0xC
0x24ec8e  ldnull
0x24ec8f  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x24ec94  brfalse  loc_24ED7C
0x24ec99  ldarg.2
0x24ec9a  brfalse  loc_24ED3D
0x24ec9f  ldloc.s  0xB
0x24eca1  ldloc.s  0xC
0x24eca3  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x24eca8  ldc.i4.4
0x24eca9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x24ecae  brfalse  loc_24ED3D
0x24ecb3  ldarg.1
0x24ecb4  ldc.i4   0x2603E2
0x24ecb9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ecbe  ldstr    aConvertingType// "Converting type (id = {0}) from {1} to "...
0x24ecc3  ldc.i4.3
0x24ecc4  newarr   [mscorlib]System.Object
0x24ecc9  stloc.s  0x22
0x24eccb  ldloc.s  0x22
0x24eccd  ldc.i4.0
0x24ecce  ldloc.s  0xA
0x24ecd0  box      [mscorlib]System.Guid
0x24ecd5  stelem.ref
0x24ecd6  ldloc.s  0x22
0x24ecd8  ldc.i4.1
0x24ecd9  ldloc.s  0xB
0x24ecdb  stelem.ref
0x24ecdc  ldloc.s  0x22
0x24ecde  ldc.i4.2
0x24ecdf  ldloc.s  0xC
0x24ece1  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x24ece6  stelem.ref
0x24ece7  ldloc.s  0x22
0x24ece9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ecee  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24ecf3  ldloc.1
0x24ecf4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ecf9  ldstr    aUpdateClassesS// "UPDATE Classes SET FullName = '{0}' WHE"...
0x24ecfe  ldc.i4.2
0x24ecff  newarr   [mscorlib]System.Object
0x24ed04  stloc.s  0x23
0x24ed06  ldloc.s  0x23
0x24ed08  ldc.i4.0
0x24ed09  ldloc.s  0xC
0x24ed0b  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x24ed10  stelem.ref
0x24ed11  ldloc.s  0x23
0x24ed13  ldc.i4.1
0x24ed14  ldloc.s  0xA
0x24ed16  box      [mscorlib]System.Guid
0x24ed1b  stelem.ref
0x24ed1c  ldloc.s  0x23
0x24ed1e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ed23  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x24ed28  pop
0x24ed29  ldloc.2
0x24ed2a  ldloc.s  0xA
0x24ed2c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x24ed31  ldarg.0
0x24ed32  ldloc.s  0xB
0x24ed34  ldloc.s  0xC
0x24ed36  call     instance void Microsoft.SharePoint.Administration.SPConfigurationDatabase::AddUpgradeConvertedType(string typeName, class [mscorlib]System.Type typeTo)
0x24ed3b  br.s     loc_24EDBA
0x24ed3d  ldarg.1
0x24ed3e  ldc.i4   0x2603E3
0x24ed43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ed48  ldstr    aType0NotChange// "Type {0} not changed (id = {1})."
0x24ed4d  ldc.i4.2
0x24ed4e  newarr   [mscorlib]System.Object
0x24ed53  stloc.s  0x24
0x24ed55  ldloc.s  0x24
0x24ed57  ldc.i4.0
0x24ed58  ldloc.s  0xB
0x24ed5a  stelem.ref
0x24ed5b  ldloc.s  0x24
0x24ed5d  ldc.i4.1
0x24ed5e  ldloc.s  0xA
0x24ed60  box      [mscorlib]System.Guid
0x24ed65  stelem.ref
0x24ed66  ldloc.s  0x24
0x24ed68  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ed6d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24ed72  ldloc.3
0x24ed73  ldloc.s  0xA
0x24ed75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x24ed7a  br.s     loc_24EDBA
0x24ed7c  ldarg.1
0x24ed7d  ldc.i4   0x260400
0x24ed82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ed87  ldstr    aCannotDeserial// "Cannot deserialize type {0} (id = {1})."
0x24ed8c  ldc.i4.2
0x24ed8d  newarr   [mscorlib]System.Object
0x24ed92  stloc.s  0x25
0x24ed94  ldloc.s  0x25
0x24ed96  ldc.i4.0
0x24ed97  ldloc.s  0xB
0x24ed99  stelem.ref
0x24ed9a  ldloc.s  0x25
0x24ed9c  ldc.i4.1
0x24ed9d  ldloc.s  0xA
0x24ed9f  box      [mscorlib]System.Guid
0x24eda4  stelem.ref
0x24eda5  ldloc.s  0x25
0x24eda7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24edac  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24edb1  ldloc.s  4
0x24edb3  ldloc.s  0xA
0x24edb5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x24edba  ldloc.s  9
0x24edbc  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x24edc1  brtrue   loc_24EC6C
0x24edc6  leave.s  loc_24EDD4
0x24edc8  ldloc.s  9
0x24edca  brfalse.s loc_24EDD3
0x24edcc  ldloc.s  9
0x24edce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24edd3  endfinally
0x24edd4  leave.s  loc_24EDE2
0x24edd6  ldloc.s  8
0x24edd8  brfalse.s loc_24EDE1
0x24edda  ldloc.s  8
0x24eddc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24ede1  endfinally
0x24ede2  ldc.i4.1
0x24ede3  call     void Microsoft.SharePoint.Administration.SPCredentialManager::set_FallBackToV3RegKey(bool value)
0x24ede8  ldarg.1
0x24ede9  ldc.i4   0x260401
0x24edee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24edf3  ldstr    aUpdatingObject// "Updating objects table with new type na"...
0x24edf8  ldc.i4.0
0x24edf9  newarr   [mscorlib]System.Object
0x24edfe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ee03  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24ee08  ldc.i4.0
0x24ee09  stloc.s  0xD
0x24ee0b  ldc.i4.0
0x24ee0c  stloc.s  0xE
0x24ee0e  ldc.i4.0
0x24ee0f  stloc.s  0xD
0x24ee11  ldc.i4.0
0x24ee12  stloc.s  0xE
0x24ee14  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPProcessIdentity>::.ctor()
0x24ee19  stloc.s  0xF
0x24ee1b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPEncryptedString>::.ctor()
0x24ee20  stloc.s  0x10
0x24ee22  ldstr    aDeclareObjectl// "\r\n                DECLARE @ObjectLeve"...
0x24ee27  stloc.s  0x11
0x24ee29  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_SPEED_ConfigDB_useGetConfigObjectsInOrderNew
0x24ee2e  ldstr    a03072016// "03/07/2016"
0x24ee33  ldstr    aUsegetconfigob// "useGetConfigObjectsInOrderNew"
0x24ee38  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x24ee3d  brfalse.s loc_24EE46
0x24ee3f  ldstr    aDeclareObjectl_0// "            \r\n                DECLARE"...
0x24ee44  stloc.s  0x11
0x24ee46  ldloc.s  0x11
0x24ee48  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string)
0x24ee4d  stloc.s  0x12
0x24ee4f  ldloc.s  0x12
0x24ee51  ldarg.0
0x24ee52  call     instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_SqlSession()
0x24ee57  callvirt instance int32 Microsoft.SharePoint.Utilities.SqlSession::get_MinimumCommandTimeout()
0x24ee5c  ldc.i4   0x384
0x24ee61  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x24ee66  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x24ee6b  ldarg.0
0x24ee6c  call     instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_SqlSession()
0x24ee71  ldloc.s  0x12
0x24ee73  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader Microsoft.SharePoint.Utilities.SqlSession::ExecuteReader(class [System.Data]System.Data.SqlClient.SqlCommand command)
0x24ee78  stloc.s  0x13
0x24ee7a  br       loc_24F14A
0x24ee7f  ldloc.s  0x13
0x24ee81  ldc.i4.0
0x24ee82  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.Common.DbDataReader::GetGuid(int32)
0x24ee87  stloc.s  0x14
0x24ee89  ldloc.s  0x13
0x24ee8b  ldc.i4.1
0x24ee8c  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.Common.DbDataReader::GetGuid(int32)
0x24ee91  stloc.s  0x15
0x24ee93  ldarg.2
0x24ee94  brfalse  loc_24F046
0x24ee99  ldloc.2
0x24ee9a  ldloc.s  0x15
0x24ee9c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x24eea1  brfalse  loc_24F046
0x24eea6  ldloc.s  6
0x24eea8  ldc.i4.1
0x24eea9  add
0x24eeaa  stloc.s  6
0x24eeac  ldarg.1
0x24eead  ldc.i4   0x260402
0x24eeb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24eeb7  ldstr    aRetrievingAndU// "Retrieving and updating object {0} beca"...
0x24eebc  ldc.i4.2
0x24eebd  newarr   [mscorlib]System.Object
0x24eec2  stloc.s  0x26
0x24eec4  ldloc.s  0x26
0x24eec6  ldc.i4.0
0x24eec7  ldloc.s  0x14
0x24eec9  box      [mscorlib]System.Guid
0x24eece  stelem.ref
0x24eecf  ldloc.s  0x26
0x24eed1  ldc.i4.1
0x24eed2  ldloc.s  0x15
0x24eed4  box      [mscorlib]System.Guid
0x24eed9  stelem.ref
0x24eeda  ldloc.s  0x26
0x24eedc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24eee1  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0x24eee6  ldarg.0
0x24eee7  ldloc.s  0x14
0x24eee9  call     instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPConfigurationDatabase::GetObject(valuetype [mscorlib]System.Guid id)
0x24eeee  stloc.s  0x16
0x24eef0  ldloc.s  0x16
0x24eef2  ldnull
0x24eef3  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x24eef8  brfalse.s loc_24EF4F
0x24eefa  ldloc.s  0x15
0x24eefc  ldstr    a49cd1407C4cd44// "49CD1407-C4CD-44a0-8E45-3E355107F9C9"
0x24ef01  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x24ef06  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x24ef0b  brfalse  loc_24F14A
0x24ef10  ldarg.1
0x24ef11  ldc.i4   0x260403
0x24ef16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ef1b  ldstr    aObjectWithId0A// "Object with Id {0} and class id {1} cou"...
0x24ef20  ldc.i4.2
0x24ef21  newarr   [mscorlib]System.Object
0x24ef26  stloc.s  0x27
0x24ef28  ldloc.s  0x27
0x24ef2a  ldc.i4.0
0x24ef2b  ldloc.s  0x14
0x24ef2d  box      [mscorlib]System.Guid
0x24ef32  stelem.ref
  ... truncated ...
```
