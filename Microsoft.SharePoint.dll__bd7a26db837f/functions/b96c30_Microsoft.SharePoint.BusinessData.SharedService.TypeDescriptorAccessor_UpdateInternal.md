# Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::UpdateInternal

- ea: `0xb96c30`
- end: `0xb97255`
- name: `Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::UpdateInternal`
- size: `1573`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xb96bf0`
- `0xbfc370`

## callees

- `0xb096d0`
- `0xb47c60`
- `0xb47c80`
- `0xb47ce0`
- `0xb4b050`
- `0xb4b070`
- `0xb4b090`
- `0xb4b0a0`
- `0xb4b0c0`
- `0xb4b0e0`
- `0xb4b120`
- `0xb4b140`
- `0xb4b160`
- `0xb4b260`
- `0xb4b290`
- `0xb69610`
- `0xb7a1f0`
- `0xb7ab80`
- `0xb7afe0`
- `0xb7d100`
- `0xb8c600`
- `0xb8c800`
- `0xb8c890`
- `0xb8c8a0`
- `0xb8cd20`
- `0xb8f5f0`
- `0xb93fe0`
- `0xb96c30`
- `0xb972e0`
- `0xb97390`

## string_xrefs

- `0xb9706f`: `FilterDescriptor`
- `0xb97249`: `FilterDescriptor`
- `0xb9702f`: `ApplicationRegistry_TypeDescriptor_BadFilterDescriptor`
- `0xb970aa`: `ApplicationRegistry_TypeDescriptor_ParentFromSameParameter`
- `0xb97142`: `ApplicationRegistry_TypeDescriptor_NestDepth`
- `0xb96f9a`: `ApplicationRegistry_TypeDescriptor_IsCollectionHasMultipleChildren`
- `0xb96ce4`: `@ParentTypeDescriptorId`
- `0xb96cb7`: `@FilterDescriptorId`
- `0xb96e6f`: `ApplicationRegistry_TypeDescriptor_MultipleRoots`
- `0xb96f04`: `ApplicationRegistry_TypeDescriptor_ConsecutiveIsCollections`
- `0xb971da`: `ApplicationRegistry_TypeDescriptor_ReadonlyTypeDescriptorOnInParameter`
- `0xb96c35`: `proc_ar_UpdateTypeDescriptorById`
- `0xb96d21`: `@ContainsFilterDescriptor`
- `0xb96db0`: `@ContainsFilterDescriptor`
- `0xb96d39`: `@ContainsIdentifier`
- `0xb96dd5`: `@ContainsIdentifier`
- `0xb96d51`: `@ContainsReadOnly`
- `0xb96dfa`: `@ContainsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xb96c30  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96c35  ldstr    aProcArUpdatety// "proc_ar_UpdateTypeDescriptorById"
0xb96c3a  ldarg.2
0xb96c3b  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderCommand(string commandText, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper sessionWrapper)
0xb96c40  stloc.0
0xb96c41  ldarg.0
0xb96c42  ldloc.0
0xb96c43  ldarg.1
0xb96c44  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::UpdateCommon(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct metadataObjectStruct)
0xb96c49  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96c4e  ldstr    aTypename_1// "@TypeName"
0xb96c53  ldc.i4.s 0x10
0xb96c55  ldarg.1
0xb96c56  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb96c5b  ldloc.0
0xb96c5c  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96c61  pop
0xb96c62  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96c67  ldstr    aLobname_1// "@LobName"
0xb96c6c  ldc.i4.s 0x10
0xb96c6e  ldarg.1
0xb96c6f  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_LobName()
0xb96c74  ldloc.0
0xb96c75  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96c7a  pop
0xb96c7b  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96c80  ldstr    aRules_3// "@Rules"
0xb96c85  ldc.i4.s 0x10
0xb96c87  ldarg.1
0xb96c88  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_SerializedRules()
0xb96c8d  ldloc.0
0xb96c8e  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96c93  pop
0xb96c94  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96c99  ldstr    aFlags_0// "@Flags"
0xb96c9e  ldc.i4.s 0xA
0xb96ca0  ldarg.1
0xb96ca1  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.TypeDescriptorFlags Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_Flags()
0xb96ca6  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.TypeDescriptorFlags
0xb96cab  ldloc.0
0xb96cac  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96cb1  pop
0xb96cb2  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96cb7  ldstr    aFilterdescript_5// "@FilterDescriptorId"
0xb96cbc  ldc.i4.s 0xB
0xb96cbe  ldarg.1
0xb96cbf  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_FilterDescriptorId()
0xb96cc4  brtrue.s loc_B96CCD
0xb96cc6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96ccb  br.s     loc_B96CD8
0xb96ccd  ldarg.1
0xb96cce  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_FilterDescriptorId()
0xb96cd3  box      [mscorlib]System.UInt32
0xb96cd8  ldloc.0
0xb96cd9  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96cde  pop
0xb96cdf  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96ce4  ldstr    aParenttypedesc_3// "@ParentTypeDescriptorId"
0xb96ce9  ldc.i4.s 0xB
0xb96ceb  ldarg.1
0xb96cec  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParentTypeDescriptorId()
0xb96cf1  brtrue.s loc_B96CFA
0xb96cf3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96cf8  br.s     loc_B96D05
0xb96cfa  ldarg.1
0xb96cfb  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParentTypeDescriptorId()
0xb96d00  box      [mscorlib]System.UInt32
0xb96d05  ldloc.0
0xb96d06  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb96d0b  pop
0xb96d0c  ldarg.0
0xb96d0d  ldloc.0
0xb96d0e  ldarg.1
0xb96d0f  call     instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::ConstructIdentifierParameters(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct rawValues)
0xb96d14  ldarg.0
0xb96d15  ldloc.0
0xb96d16  ldarg.1
0xb96d17  call     instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::ConstructAssociationParameters(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct rawValues)
0xb96d1c  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96d21  ldstr    aContainsfilter_0// "@ContainsFilterDescriptor"
0xb96d26  ldc.i4.3
0xb96d27  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96d2c  ldc.i4.2
0xb96d2d  ldloc.0
0xb96d2e  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, valuetype [System.Data]System.Data.ParameterDirection direction, class [System.Data]System.Data.IDbCommand cmd)
0xb96d33  pop
0xb96d34  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96d39  ldstr    aContainsidenti_0// "@ContainsIdentifier"
0xb96d3e  ldc.i4.3
0xb96d3f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96d44  ldc.i4.2
0xb96d45  ldloc.0
0xb96d46  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, valuetype [System.Data]System.Data.ParameterDirection direction, class [System.Data]System.Data.IDbCommand cmd)
0xb96d4b  pop
0xb96d4c  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96d51  ldstr    aContainsreadon// "@ContainsReadOnly"
0xb96d56  ldc.i4.3
0xb96d57  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96d5c  ldc.i4.2
0xb96d5d  ldloc.0
0xb96d5e  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, valuetype [System.Data]System.Data.ParameterDirection direction, class [System.Data]System.Data.IDbCommand cmd)
0xb96d63  pop
0xb96d64  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb96d69  ldstr    aChildrencontai// "@ChildrenContainRules"
0xb96d6e  ldc.i4.3
0xb96d6f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb96d74  ldc.i4.2
0xb96d75  ldloc.0
0xb96d76  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, valuetype [System.Data]System.Data.ParameterDirection direction, class [System.Data]System.Data.IDbCommand cmd)
0xb96d7b  pop
0xb96d7c  ldarg.2
0xb96d7d  ldloc.0
0xb96d7e  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xb96d83  ldloc.0
0xb96d84  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb96d89  ldstr    aErrorcode_0// "@ErrorCode"
0xb96d8e  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb96d93  castclass [System.Data]System.Data.IDbDataParameter
0xb96d98  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb96d9d  unbox.any [mscorlib]System.Int32
0xb96da2  stloc.1
0xb96da3  ldloc.1
0xb96da4  brtrue   loc_B96E42
0xb96da9  ldarg.1
0xb96daa  ldloc.0
0xb96dab  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb96db0  ldstr    aContainsfilter_0// "@ContainsFilterDescriptor"
0xb96db5  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb96dba  castclass [System.Data]System.Data.IDbDataParameter
0xb96dbf  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb96dc4  unbox.any [mscorlib]System.Boolean
0xb96dc9  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::set_ContainsFilterDescriptor(bool value)
0xb96dce  ldarg.1
0xb96dcf  ldloc.0
0xb96dd0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb96dd5  ldstr    aContainsidenti_0// "@ContainsIdentifier"
0xb96dda  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb96ddf  castclass [System.Data]System.Data.IDbDataParameter
0xb96de4  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb96de9  unbox.any [mscorlib]System.Boolean
0xb96dee  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::set_ContainsIdentifier(bool value)
0xb96df3  ldarg.1
0xb96df4  ldloc.0
0xb96df5  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb96dfa  ldstr    aContainsreadon// "@ContainsReadOnly"
0xb96dff  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb96e04  castclass [System.Data]System.Data.IDbDataParameter
0xb96e09  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb96e0e  unbox.any [mscorlib]System.Boolean
0xb96e13  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::set_ContainsReadOnly(bool value)
0xb96e18  ldarg.1
0xb96e19  ldloc.0
0xb96e1a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb96e1f  ldstr    aChildrencontai// "@ChildrenContainRules"
0xb96e24  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb96e29  castclass [System.Data]System.Data.IDbDataParameter
0xb96e2e  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb96e33  unbox.any [mscorlib]System.Boolean
0xb96e38  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::set_ChildrenContainRules(bool value)
0xb96e3d  br       loc_B97244
0xb96e42  ldloc.1
0xb96e43  ldc.i4   0xFFFFFED2
0xb96e48  bne.un   loc_B96ED7
0xb96e4d  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb96e52  ldarg.1
0xb96e53  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb96e58  ldarg.1
0xb96e59  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96e5e  ldarg.2
0xb96e5f  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96e64  stloc.2
0xb96e65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb96e6a  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96e6f  ldstr    aApplicationreg_755// "ApplicationRegistry_TypeDescriptor_Mult"...
0xb96e74  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb96e79  ldc.i4.4
0xb96e7a  newarr   [mscorlib]System.Object
0xb96e7f  stloc.s  9
0xb96e81  ldloc.s  9
0xb96e83  ldc.i4.0
0xb96e84  ldarg.1
0xb96e85  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96e8a  stelem.ref
0xb96e8b  ldloc.s  9
0xb96e8d  ldc.i4.1
0xb96e8e  ldarg.1
0xb96e8f  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96e94  box      [mscorlib]System.UInt32
0xb96e99  stelem.ref
0xb96e9a  ldloc.s  9
0xb96e9c  ldc.i4.2
0xb96e9d  ldloc.2
0xb96e9e  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96ea3  stelem.ref
0xb96ea4  ldloc.s  9
0xb96ea6  ldc.i4.3
0xb96ea7  ldloc.2
0xb96ea8  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96ead  box      [mscorlib]System.UInt32
0xb96eb2  stelem.ref
0xb96eb3  ldloc.s  9
0xb96eb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb96eba  ldarg.1
0xb96ebb  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96ec0  ldarg.1
0xb96ec1  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96ec6  ldstr    aFlags_1// "Flags"
0xb96ecb  ldarg.0
0xb96ecc  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb96ed1  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
0xb96ed6  throw
0xb96ed7  ldloc.1
0xb96ed8  ldc.i4   0xFFFFFECF
0xb96edd  bne.un   loc_B96F6C
0xb96ee2  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb96ee7  ldarg.1
0xb96ee8  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb96eed  ldarg.1
0xb96eee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96ef3  ldarg.2
0xb96ef4  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96ef9  stloc.3
0xb96efa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb96eff  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96f04  ldstr    aApplicationreg_756// "ApplicationRegistry_TypeDescriptor_Cons"...
0xb96f09  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb96f0e  ldc.i4.4
0xb96f0f  newarr   [mscorlib]System.Object
0xb96f14  stloc.s  0xA
0xb96f16  ldloc.s  0xA
0xb96f18  ldc.i4.0
0xb96f19  ldarg.1
0xb96f1a  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96f1f  stelem.ref
0xb96f20  ldloc.s  0xA
0xb96f22  ldc.i4.1
0xb96f23  ldarg.1
0xb96f24  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96f29  box      [mscorlib]System.UInt32
0xb96f2e  stelem.ref
0xb96f2f  ldloc.s  0xA
0xb96f31  ldc.i4.2
0xb96f32  ldloc.3
0xb96f33  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96f38  stelem.ref
0xb96f39  ldloc.s  0xA
0xb96f3b  ldc.i4.3
0xb96f3c  ldloc.3
0xb96f3d  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96f42  box      [mscorlib]System.UInt32
0xb96f47  stelem.ref
0xb96f48  ldloc.s  0xA
0xb96f4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb96f4f  ldarg.1
0xb96f50  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96f55  ldarg.1
0xb96f56  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96f5b  ldstr    aFlags_1// "Flags"
0xb96f60  ldarg.0
0xb96f61  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb96f66  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
0xb96f6b  throw
0xb96f6c  ldloc.1
0xb96f6d  ldc.i4   0xFFFFFECE
0xb96f72  bne.un   loc_B97004
0xb96f77  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb96f7c  ldarg.1
0xb96f7d  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb96f82  ldarg.1
0xb96f83  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96f88  ldarg.2
0xb96f89  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96f8e  stloc.s  4
0xb96f90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb96f95  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96f9a  ldstr    aApplicationreg_367// "ApplicationRegistry_TypeDescriptor_IsCo"...
0xb96f9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb96fa4  ldc.i4.4
0xb96fa5  newarr   [mscorlib]System.Object
0xb96faa  stloc.s  0xB
0xb96fac  ldloc.s  0xB
0xb96fae  ldc.i4.0
0xb96faf  ldarg.1
0xb96fb0  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96fb5  stelem.ref
0xb96fb6  ldloc.s  0xB
0xb96fb8  ldc.i4.1
0xb96fb9  ldarg.1
0xb96fba  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96fbf  box      [mscorlib]System.UInt32
0xb96fc4  stelem.ref
0xb96fc5  ldloc.s  0xB
0xb96fc7  ldc.i4.2
0xb96fc8  ldloc.s  4
0xb96fca  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96fcf  stelem.ref
0xb96fd0  ldloc.s  0xB
0xb96fd2  ldc.i4.3
0xb96fd3  ldloc.s  4
0xb96fd5  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
  ... truncated ...
```
