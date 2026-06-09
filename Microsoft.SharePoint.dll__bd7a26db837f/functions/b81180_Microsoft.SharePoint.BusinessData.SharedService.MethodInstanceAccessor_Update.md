# Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceAccessor::Update

- ea: `0xb81180`
- end: `0xb81816`
- name: `Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceAccessor::Update`
- size: `1686`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xb82a40`

## callees

- `0xb082e0`
- `0xb096d0`
- `0xb47c60`
- `0xb47c80`
- `0xb47ce0`
- `0xb48ac0`
- `0xb48ae0`
- `0xb48b00`
- `0xb48b20`
- `0xb49970`
- `0xb4b140`
- `0xb69610`
- `0xb7a1f0`
- `0xb7ab80`
- `0xb7afe0`
- `0xb7d100`
- `0xb7d1f0`
- `0xb7d630`
- `0xb81180`
- `0xb8c600`
- `0xb8c800`
- `0xb8c890`
- `0xb8cd20`
- `0xb8d330`
- `0xb92850`
- `0xb93fe0`
- `0xb94fc0`

## string_xrefs

- `0xb813c1`: `ReturnTypeDescriptor`
- `0xb81473`: `ReturnTypeDescriptor`
- `0xb814f0`: `ReturnTypeDescriptor`
- `0xb8156d`: `ReturnTypeDescriptor`
- `0xb815ea`: `ReturnTypeDescriptor`
- `0xb816f6`: `ReturnTypeDescriptor`
- `0xb81773`: `ReturnTypeDescriptor`
- `0xb817f0`: `ReturnTypeDescriptor`
- `0xb81383`: `ApplicationRegistry_MethodInstanceAdmin_BadReturnTypeDescriptor`
- `0xb8145d`: `ApplicationRegistry_MethodInstanceAdmin_BadDirection`
- `0xb81202`: `@ReturnTypeDescriptorId`
- `0xb81322`: `ApplicationRegistry_MethodInstanceAdmin_MethodInstanceTypeExists`
- `0xb81497`: `ApplicationRegistry_MethodInstanceAdmin_MissingReturnTypeDescriptor`
- `0xb813e5`: `ApplicationRegistry_MethodInstanceAdmin_NoInputParameter`
- `0xb81514`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldBeCollection`
- `0xb81591`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldNotBeCollection`
- `0xb81611`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorParameterRootTypeDescriptorShouldBeCollection`
- `0xb8169d`: `ApplicationRegistry_MethodInstanceAdmin_StreamAccessorReturnTypeDescriptorNotChildless`
- `0xb8171a`: `ApplicationRegistry_MethodInstanceAdmin_StreamAccessorReturnTypeDescriptorNotOnlyChild`
- `0xb81797`: `ApplicationRegistry_MethodInstanceAdmin_IncorrectTimestampFilters`
- `0xb811e9`: `proc_ar_UpdateMethodInstanceById`
- `0xb81675`: `RootTypeDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0xb81180  ldarg.1
0xb81181  brtrue.s loc_B8118E
0xb81183  ldstr    aMetadataobject_0// "metadataObjectStruct"
0xb81188  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb8118d  throw
0xb8118e  ldarg.1
0xb8118f  isinst   Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct
0xb81194  stloc.0
0xb81195  ldarg.0
0xb81196  ldloc.0
0xb81197  ldarg.2
0xb81198  call     instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.AccessControlledMetadataObjectAccessor::Update(class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct metadataObjectStruct, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb8119d  pop
0xb8119e  ldnull
0xb8119f  stloc.1
0xb811a0  ldnull
0xb811a1  stloc.2
0xb811a2  ldloc.0
0xb811a3  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb811a8  brfalse.s loc_B811E4
0xb811aa  call     class Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::get_Value()
0xb811af  ldloc.0
0xb811b0  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb811b5  ldloc.0
0xb811b6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb811bb  ldarg.2
0xb811bc  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb811c1  castclass Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct
0xb811c6  stloc.1
0xb811c7  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb811cc  ldloc.1
0xb811cd  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb811d2  ldloc.1
0xb811d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb811d8  ldarg.2
0xb811d9  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb811de  castclass Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct
0xb811e3  stloc.2
0xb811e4  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb811e9  ldstr    aProcArUpdateme// "proc_ar_UpdateMethodInstanceById"
0xb811ee  ldarg.2
0xb811ef  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderCommand(string commandText, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper sessionWrapper)
0xb811f4  stloc.3
0xb811f5  ldarg.0
0xb811f6  ldloc.3
0xb811f7  ldloc.0
0xb811f8  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::UpdateCommon(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct metadataObjectStruct)
0xb811fd  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb81202  ldstr    aReturntypedesc_4// "@ReturnTypeDescriptorId"
0xb81207  ldc.i4.s 0xB
0xb81209  ldloc.0
0xb8120a  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb8120f  brtrue.s loc_B81218
0xb81211  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb81216  br.s     loc_B81223
0xb81218  ldloc.0
0xb81219  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb8121e  box      [mscorlib]System.UInt32
0xb81223  ldloc.3
0xb81224  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb81229  pop
0xb8122a  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb8122f  ldstr    aIsdefault_1// "@IsDefault"
0xb81234  ldc.i4.3
0xb81235  ldloc.0
0xb81236  callvirt instance bool Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_IsDefault()
0xb8123b  box      [mscorlib]System.Boolean
0xb81240  ldloc.3
0xb81241  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb81246  pop
0xb81247  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb8124c  ldstr    aType_2// "@Type"
0xb81251  ldc.i4.2
0xb81252  ldloc.0
0xb81253  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb81258  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb8125d  ldloc.3
0xb8125e  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb81263  pop
0xb81264  ldarg.2
0xb81265  ldloc.3
0xb81266  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xb8126b  ldarg.0
0xb8126c  ldloc.3
0xb8126d  ldc.i4.s 0xF
0xb8126f  ldloc.0
0xb81270  ldstr    aMethod// "Method"
0xb81275  ldarg.2
0xb81276  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::PostUpdate(class [System.Data]System.Data.IDbCommand cmd, int32 limit, class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct updateStruct, string parentStructName, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb8127b  ldloc.3
0xb8127c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb81281  ldstr    aErrorcode_0// "@ErrorCode"
0xb81286  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb8128b  castclass [System.Data]System.Data.IDbDataParameter
0xb81290  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb81295  unbox.any [mscorlib]System.Int32
0xb8129a  stloc.s  4
0xb8129c  ldnull
0xb8129d  stloc.s  5
0xb8129f  ldnull
0xb812a0  stloc.s  6
0xb812a2  ldloc.s  4
0xb812a4  brfalse.s loc_B812E2
0xb812a6  call     class Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor::get_Value()
0xb812ab  ldloc.0
0xb812ac  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodId()
0xb812b1  ldloc.0
0xb812b2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb812b7  ldarg.2
0xb812b8  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb812bd  castclass Microsoft.SharePoint.BusinessData.SharedService.MethodStruct
0xb812c2  stloc.s  6
0xb812c4  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb812c9  ldloc.0
0xb812ca  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb812cf  ldloc.0
0xb812d0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb812d5  ldarg.2
0xb812d6  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb812db  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb812e0  stloc.s  5
0xb812e2  ldloc.s  4
0xb812e4  ldc.i4   0xFFFFFF36
0xb812e9  beq.s    loc_B81318
0xb812eb  ldloc.s  4
0xb812ed  ldc.i4   0xFFFFFF33
0xb812f2  beq.s    loc_B81318
0xb812f4  ldloc.s  4
0xb812f6  ldc.i4   0xFFFFFF2F
0xb812fb  beq.s    loc_B81318
0xb812fd  ldloc.s  4
0xb812ff  ldc.i4   0xFFFFFF2E
0xb81304  beq.s    loc_B81318
0xb81306  ldloc.s  4
0xb81308  ldc.i4   0xFFFFFF2D
0xb8130d  beq.s    loc_B81318
0xb8130f  ldloc.s  4
0xb81311  ldc.i4   0xFFFFFF28
0xb81316  bne.un.s loc_B81370
0xb81318  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb8131d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb81322  ldstr    aApplicationreg_702// "ApplicationRegistry_MethodInstanceAdmin"...
0xb81327  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb8132c  ldc.i4.3
0xb8132d  newarr   [mscorlib]System.Object
0xb81332  stloc.s  7
0xb81334  ldloc.s  7
0xb81336  ldc.i4.0
0xb81337  ldloc.0
0xb81338  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb8133d  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb81342  callvirt instance string [mscorlib]System.Object::ToString()
0xb81347  stelem.ref
0xb81348  ldloc.s  7
0xb8134a  ldc.i4.1
0xb8134b  ldloc.s  5
0xb8134d  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb81352  stelem.ref
0xb81353  ldloc.s  7
0xb81355  ldc.i4.2
0xb81356  ldloc.s  5
0xb81358  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb8135d  box      [mscorlib]System.UInt32
0xb81362  stelem.ref
0xb81363  ldloc.s  7
0xb81365  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb8136a  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.ExceededMetadataObjectLimitException::.ctor(string message)
0xb8136f  throw
0xb81370  ldloc.s  4
0xb81372  ldc.i4   0xFFFFFF35
0xb81377  bne.un.s loc_B813D2
0xb81379  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb8137e  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb81383  ldstr    aApplicationreg_39// "ApplicationRegistry_MethodInstanceAdmin"...
0xb81388  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb8138d  ldc.i4.2
0xb8138e  newarr   [mscorlib]System.Object
0xb81393  stloc.s  8
0xb81395  ldloc.s  8
0xb81397  ldc.i4.0
0xb81398  ldloc.0
0xb81399  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb8139e  stelem.ref
0xb8139f  ldloc.s  8
0xb813a1  ldc.i4.1
0xb813a2  ldloc.0
0xb813a3  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb813a8  box      [mscorlib]System.UInt32
0xb813ad  stelem.ref
0xb813ae  ldloc.s  8
0xb813b0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb813b5  ldloc.0
0xb813b6  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb813bb  ldloc.0
0xb813bc  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb813c1  ldstr    aReturntypedesc// "ReturnTypeDescriptor"
0xb813c6  ldarg.0
0xb813c7  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb813cc  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
0xb813d1  throw
0xb813d2  ldloc.s  4
0xb813d4  ldc.i4   0xFFFFFF27
0xb813d9  bne.un.s loc_B8144F
0xb813db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb813e0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb813e5  ldstr    aApplicationreg_704// "ApplicationRegistry_MethodInstanceAdmin"...
0xb813ea  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb813ef  ldc.i4.4
0xb813f0  newarr   [mscorlib]System.Object
0xb813f5  stloc.s  9
0xb813f7  ldloc.s  9
0xb813f9  ldc.i4.0
0xb813fa  ldloc.0
0xb813fb  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb81400  stelem.ref
0xb81401  ldloc.s  9
0xb81403  ldc.i4.1
0xb81404  ldloc.s  5
0xb81406  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb8140b  stelem.ref
0xb8140c  ldloc.s  9
0xb8140e  ldc.i4.2
0xb8140f  ldloc.s  5
0xb81411  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb81416  stelem.ref
0xb81417  ldloc.s  9
0xb81419  ldc.i4.3
0xb8141a  ldloc.0
0xb8141b  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb81420  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb81425  callvirt instance string [mscorlib]System.Object::ToString()
0xb8142a  stelem.ref
0xb8142b  ldloc.s  9
0xb8142d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb81432  ldloc.0
0xb81433  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb81438  ldloc.0
0xb81439  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb8143e  ldstr    aMethodinstance_2// "MethodInstanceType"
0xb81443  ldarg.0
0xb81444  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb81449  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
0xb8144e  throw
0xb8144f  ldloc.s  4
0xb81451  ldc.i4   0xFFFFFF34
0xb81456  bne.un.s loc_B81484
0xb81458  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb8145d  ldstr    aApplicationreg_40// "ApplicationRegistry_MethodInstanceAdmin"...
0xb81462  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb81467  ldloc.0
0xb81468  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb8146d  ldloc.0
0xb8146e  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb81473  ldstr    aReturntypedesc// "ReturnTypeDescriptor"
0xb81478  ldarg.0
0xb81479  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb8147e  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
0xb81483  throw
0xb81484  ldloc.s  4
0xb81486  ldc.i4   0xFFFFFF32
0xb8148b  bne.un.s loc_B81501
0xb8148d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb81492  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb81497  ldstr    aApplicationreg_703// "ApplicationRegistry_MethodInstanceAdmin"...
0xb8149c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb814a1  ldc.i4.4
0xb814a2  newarr   [mscorlib]System.Object
0xb814a7  stloc.s  0xA
0xb814a9  ldloc.s  0xA
0xb814ab  ldc.i4.0
0xb814ac  ldloc.0
0xb814ad  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb814b2  stelem.ref
0xb814b3  ldloc.s  0xA
0xb814b5  ldc.i4.1
0xb814b6  ldloc.s  5
0xb814b8  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb814bd  stelem.ref
0xb814be  ldloc.s  0xA
0xb814c0  ldc.i4.2
0xb814c1  ldloc.s  5
0xb814c3  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb814c8  stelem.ref
0xb814c9  ldloc.s  0xA
0xb814cb  ldc.i4.3
0xb814cc  ldloc.0
0xb814cd  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb814d2  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb814d7  callvirt instance string [mscorlib]System.Object::ToString()
0xb814dc  stelem.ref
0xb814dd  ldloc.s  0xA
0xb814df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb814e4  ldloc.0
0xb814e5  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb814ea  ldloc.0
0xb814eb  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb814f0  ldstr    aReturntypedesc// "ReturnTypeDescriptor"
0xb814f5  ldarg.0
0xb814f6  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::get_MetadataObjectType()
0xb814fb  newobj   instance void Microsoft.SharePoint.BusinessData.Administration.InvalidMetadataObjectException::.ctor(string message, unsigned int32 invalidMetadataObjectId, string invalidMetadataObjectName, string invalidFieldName, class [mscorlib]System.Type metadataObjectType)
  ... truncated ...
```
