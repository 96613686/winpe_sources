# Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceAccessor::CreateInternal

- ea: `0xb80bc0`
- end: `0xb8117f`
- name: `Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceAccessor::CreateInternal`
- size: `1471`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb80b80`
- `0xbf5a40`

## callees

- `0xb082e0`
- `0xb47c60`
- `0xb47c80`
- `0xb47ce0`
- `0xb48ac0`
- `0xb48ae0`
- `0xb48b20`
- `0xb49970`
- `0xb4a8a0`
- `0xb4aa50`
- `0xb4b140`
- `0xb69610`
- `0xb7a1f0`
- `0xb7a9c0`
- `0xb7aec0`
- `0xb80bc0`
- `0xb8c600`
- `0xb8c800`
- `0xb8c890`
- `0xb8cd20`
- `0xb8d330`
- `0xb93fe0`
- `0xb94fc0`

## string_xrefs

- `0xb80dba`: `ApplicationRegistry_MethodInstanceAdmin_BadReturnTypeDescriptor`
- `0xb80c22`: `ApplicationRegistry_MethodInstanceAdmin_BadDirection`
- `0xb80e08`: `ApplicationRegistry_MethodInstanceAdmin_BadDirection`
- `0xb80dde`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb80c2c`: `rawValues.ReturnTypeDescriptorId`
- `0xb80df0`: `rawValues.ReturnTypeDescriptorId`
- `0xb80e12`: `rawValues.ReturnTypeDescriptorId`
- `0xb80e7c`: `rawValues.ReturnTypeDescriptorId`
- `0xb80f4b`: `rawValues.ReturnTypeDescriptorId`
- `0xb80fb5`: `rawValues.ReturnTypeDescriptorId`
- `0xb81029`: `rawValues.ReturnTypeDescriptorId`
- `0xb81093`: `rawValues.ReturnTypeDescriptorId`
- `0xb810fd`: `rawValues.ReturnTypeDescriptorId`
- `0xb81167`: `rawValues.ReturnTypeDescriptorId`
- `0xb80c3c`: `proc_ar_CreateMethodInstance`
- `0xb80c73`: `@ReturnTypeDescriptorId`
- `0xb80d5a`: `ApplicationRegistry_MethodInstanceAdmin_MethodInstanceTypeExists`
- `0xb80e2f`: `ApplicationRegistry_MethodInstanceAdmin_MissingReturnTypeDescriptor`
- `0xb80e99`: `ApplicationRegistry_MethodInstanceAdmin_NoInputParameter`
- `0xb80efe`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldBeCollection`
- `0xb80f68`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldNotBeCollection`
- `0xb80fd2`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorParameterRootTypeDescriptorShouldBeCollection`
- `0xb81046`: `ApplicationRegistry_MethodInstanceAdmin_StreamAccessorReturnTypeDescriptorNotChildless`
- `0xb810b0`: `ApplicationRegistry_MethodInstanceAdmin_StreamAccessorReturnTypeDescriptorNotOnlyChild`
- `0xb8111a`: `ApplicationRegistry_MethodInstanceAdmin_IncorrectTimestampFilters`

## pseudocode

```c

```

## disassembly

```asm
0xb80bc0  ldarg.2
0xb80bc1  brtrue.s loc_B80BCE
0xb80bc3  ldstr    aMethodstruct// "methodStruct"
0xb80bc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb80bcd  throw
0xb80bce  ldnull
0xb80bcf  stloc.0
0xb80bd0  ldnull
0xb80bd1  stloc.1
0xb80bd2  ldarg.1
0xb80bd3  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb80bd8  brfalse.s loc_B80C37
0xb80bda  call     class Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::get_Value()
0xb80bdf  ldarg.1
0xb80be0  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb80be5  ldarg.2
0xb80be6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb80beb  ldarg.3
0xb80bec  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb80bf1  castclass Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct
0xb80bf6  stloc.0
0xb80bf7  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb80bfc  ldloc.0
0xb80bfd  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb80c02  ldloc.0
0xb80c03  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb80c08  ldarg.3
0xb80c09  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb80c0e  castclass Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct
0xb80c13  stloc.1
0xb80c14  ldloc.1
0xb80c15  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.DirectionType Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct::get_Direction()
0xb80c1a  ldc.i4.1
0xb80c1b  bne.un.s loc_B80C37
0xb80c1d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80c22  ldstr    aApplicationreg_40// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80c27  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80c2c  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb80c31  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb80c36  throw
0xb80c37  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb80c3c  ldstr    aProcArCreateme// "proc_ar_CreateMethodInstance"
0xb80c41  ldarg.3
0xb80c42  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderCommand(string commandText, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper sessionWrapper)
0xb80c47  stloc.2
0xb80c48  ldarg.0
0xb80c49  ldloc.2
0xb80c4a  ldarg.1
0xb80c4b  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::CreateCommon(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct rawValues)
0xb80c50  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb80c55  ldstr    aMethodid_1// "@MethodId"
0xb80c5a  ldc.i4.s 0xB
0xb80c5c  ldarg.2
0xb80c5d  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb80c62  box      [mscorlib]System.UInt32
0xb80c67  ldloc.2
0xb80c68  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb80c6d  pop
0xb80c6e  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb80c73  ldstr    aReturntypedesc_4// "@ReturnTypeDescriptorId"
0xb80c78  ldc.i4.s 0xB
0xb80c7a  ldarg.1
0xb80c7b  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb80c80  brtrue.s loc_B80C89
0xb80c82  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb80c87  br.s     loc_B80C94
0xb80c89  ldarg.1
0xb80c8a  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb80c8f  box      [mscorlib]System.UInt32
0xb80c94  ldloc.2
0xb80c95  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb80c9a  pop
0xb80c9b  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb80ca0  ldstr    aType_2// "@Type"
0xb80ca5  ldc.i4.2
0xb80ca6  ldarg.1
0xb80ca7  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb80cac  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb80cb1  ldloc.2
0xb80cb2  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb80cb7  pop
0xb80cb8  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb80cbd  ldstr    aIsdefault_1// "@IsDefault"
0xb80cc2  ldc.i4.3
0xb80cc3  ldarg.1
0xb80cc4  callvirt instance bool Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_IsDefault()
0xb80cc9  box      [mscorlib]System.Boolean
0xb80cce  ldloc.2
0xb80ccf  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb80cd4  pop
0xb80cd5  ldarg.3
0xb80cd6  ldloc.2
0xb80cd7  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xb80cdc  ldloc.2
0xb80cdd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb80ce2  ldstr    aErrorcode_0// "@ErrorCode"
0xb80ce7  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb80cec  castclass [System.Data]System.Data.IDbDataParameter
0xb80cf1  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb80cf6  unbox.any [mscorlib]System.Int32
0xb80cfb  stloc.3
0xb80cfc  ldnull
0xb80cfd  stloc.s  4
0xb80cff  ldloc.3
0xb80d00  brfalse.s loc_B80D20
0xb80d02  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb80d07  ldarg.2
0xb80d08  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodStruct::get_EntityId()
0xb80d0d  ldarg.2
0xb80d0e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb80d13  ldarg.3
0xb80d14  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb80d19  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb80d1e  stloc.s  4
0xb80d20  ldloc.3
0xb80d21  ldc.i4   0xFFFFFF36
0xb80d26  beq.s    loc_B80D50
0xb80d28  ldloc.3
0xb80d29  ldc.i4   0xFFFFFF33
0xb80d2e  beq.s    loc_B80D50
0xb80d30  ldloc.3
0xb80d31  ldc.i4   0xFFFFFF2F
0xb80d36  beq.s    loc_B80D50
0xb80d38  ldloc.3
0xb80d39  ldc.i4   0xFFFFFF2E
0xb80d3e  beq.s    loc_B80D50
0xb80d40  ldloc.3
0xb80d41  ldc.i4   0xFFFFFF2D
0xb80d46  beq.s    loc_B80D50
0xb80d48  ldloc.3
0xb80d49  ldc.i4   0xFFFFFF28
0xb80d4e  bne.un.s loc_B80DA8
0xb80d50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb80d55  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80d5a  ldstr    aApplicationreg_702// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80d5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80d64  ldc.i4.3
0xb80d65  newarr   [mscorlib]System.Object
0xb80d6a  stloc.s  5
0xb80d6c  ldloc.s  5
0xb80d6e  ldc.i4.0
0xb80d6f  ldarg.1
0xb80d70  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb80d75  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb80d7a  callvirt instance string [mscorlib]System.Object::ToString()
0xb80d7f  stelem.ref
0xb80d80  ldloc.s  5
0xb80d82  ldc.i4.1
0xb80d83  ldloc.s  4
0xb80d85  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80d8a  stelem.ref
0xb80d8b  ldloc.s  5
0xb80d8d  ldc.i4.2
0xb80d8e  ldloc.s  4
0xb80d90  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb80d95  box      [mscorlib]System.UInt32
0xb80d9a  stelem.ref
0xb80d9b  ldloc.s  5
0xb80d9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb80da2  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.ExceededMetadataObjectLimitException::.ctor(string message)
0xb80da7  throw
0xb80da8  ldloc.3
0xb80da9  ldc.i4   0xFFFFFF35
0xb80dae  bne.un.s loc_B80DFB
0xb80db0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb80db5  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80dba  ldstr    aApplicationreg_39// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80dbf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80dc4  ldc.i4.2
0xb80dc5  newarr   [mscorlib]System.Object
0xb80dca  stloc.s  6
0xb80dcc  ldloc.s  6
0xb80dce  ldc.i4.0
0xb80dcf  ldarg.1
0xb80dd0  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80dd5  stelem.ref
0xb80dd6  ldloc.s  6
0xb80dd8  ldc.i4.1
0xb80dd9  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80dde  ldstr    aApplicationreg_49// "ApplicationRegistry_MetadataException_U"...
0xb80de3  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80de8  stelem.ref
0xb80de9  ldloc.s  6
0xb80deb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb80df0  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb80df5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb80dfa  throw
0xb80dfb  ldloc.3
0xb80dfc  ldc.i4   0xFFFFFF34
0xb80e01  bne.un.s loc_B80E1D
0xb80e03  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80e08  ldstr    aApplicationreg_40// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80e0d  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80e12  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb80e17  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb80e1c  throw
0xb80e1d  ldloc.3
0xb80e1e  ldc.i4   0xFFFFFF32
0xb80e23  bne.un.s loc_B80E87
0xb80e25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb80e2a  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80e2f  ldstr    aApplicationreg_703// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80e34  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80e39  ldc.i4.4
0xb80e3a  newarr   [mscorlib]System.Object
0xb80e3f  stloc.s  7
0xb80e41  ldloc.s  7
0xb80e43  ldc.i4.0
0xb80e44  ldarg.1
0xb80e45  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80e4a  stelem.ref
0xb80e4b  ldloc.s  7
0xb80e4d  ldc.i4.1
0xb80e4e  ldloc.s  4
0xb80e50  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80e55  stelem.ref
0xb80e56  ldloc.s  7
0xb80e58  ldc.i4.2
0xb80e59  ldloc.s  4
0xb80e5b  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb80e60  stelem.ref
0xb80e61  ldloc.s  7
0xb80e63  ldc.i4.3
0xb80e64  ldarg.1
0xb80e65  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb80e6a  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb80e6f  callvirt instance string [mscorlib]System.Object::ToString()
0xb80e74  stelem.ref
0xb80e75  ldloc.s  7
0xb80e77  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb80e7c  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb80e81  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb80e86  throw
0xb80e87  ldloc.3
0xb80e88  ldc.i4   0xFFFFFF27
0xb80e8d  bne.un.s loc_B80EEC
0xb80e8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb80e94  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80e99  ldstr    aApplicationreg_704// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80e9e  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80ea3  ldc.i4.4
0xb80ea4  newarr   [mscorlib]System.Object
0xb80ea9  stloc.s  8
0xb80eab  ldloc.s  8
0xb80ead  ldc.i4.0
0xb80eae  ldarg.1
0xb80eaf  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80eb4  stelem.ref
0xb80eb5  ldloc.s  8
0xb80eb7  ldc.i4.1
0xb80eb8  ldloc.s  4
0xb80eba  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80ebf  stelem.ref
0xb80ec0  ldloc.s  8
0xb80ec2  ldc.i4.2
0xb80ec3  ldloc.s  4
0xb80ec5  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb80eca  stelem.ref
0xb80ecb  ldloc.s  8
0xb80ecd  ldc.i4.3
0xb80ece  ldarg.1
0xb80ecf  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb80ed4  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb80ed9  callvirt instance string [mscorlib]System.Object::ToString()
0xb80ede  stelem.ref
0xb80edf  ldloc.s  8
0xb80ee1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb80ee6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb80eeb  throw
0xb80eec  ldloc.3
0xb80eed  ldc.i4   0xFFFFFF31
0xb80ef2  bne.un.s loc_B80F56
0xb80ef4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb80ef9  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb80efe  ldstr    aApplicationreg_705// "ApplicationRegistry_MethodInstanceAdmin"...
0xb80f03  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb80f08  ldc.i4.4
0xb80f09  newarr   [mscorlib]System.Object
0xb80f0e  stloc.s  9
0xb80f10  ldloc.s  9
0xb80f12  ldc.i4.0
0xb80f13  ldarg.1
0xb80f14  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80f19  stelem.ref
0xb80f1a  ldloc.s  9
0xb80f1c  ldc.i4.1
0xb80f1d  ldloc.s  4
0xb80f1f  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb80f24  stelem.ref
0xb80f25  ldloc.s  9
0xb80f27  ldc.i4.2
0xb80f28  ldloc.s  4
0xb80f2a  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb80f2f  stelem.ref
0xb80f30  ldloc.s  9
0xb80f32  ldc.i4.3
0xb80f33  ldarg.1
0xb80f34  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb80f39  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb80f3e  callvirt instance string [mscorlib]System.Object::ToString()
  ... truncated ...
```
