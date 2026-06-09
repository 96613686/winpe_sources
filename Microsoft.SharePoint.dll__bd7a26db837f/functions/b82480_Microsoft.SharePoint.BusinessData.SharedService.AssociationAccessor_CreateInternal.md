# Microsoft.SharePoint.BusinessData.SharedService.AssociationAccessor::CreateInternal

- ea: `0xb82480`
- end: `0xb82a34`
- name: `Microsoft.SharePoint.BusinessData.SharedService.AssociationAccessor::CreateInternal`
- size: `1460`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb82410`
- `0xbf5cd0`

## callees

- `0xb096d0`
- `0xb47c60`
- `0xb47c80`
- `0xb47ce0`
- `0xb48ac0`
- `0xb48b20`
- `0xb48cc0`
- `0xb48ce0`
- `0xb48d00`
- `0xb48d20`
- `0xb49970`
- `0xb4a8a0`
- `0xb4b140`
- `0xb69610`
- `0xb7a1f0`
- `0xb7a9c0`
- `0xb7aec0`
- `0xb7d100`
- `0xb82480`
- `0xb8c600`
- `0xb8c800`
- `0xb8c890`
- `0xb8cd20`
- `0xb8d330`
- `0xb93fe0`
- `0xb94fc0`

## string_xrefs

- `0xb8278a`: `ApplicationRegistry_MethodInstanceAdmin_BadReturnTypeDescriptor`
- `0xb827d9`: `ApplicationRegistry_MethodInstanceAdmin_BadDirection`
- `0xb824ea`: `ApplicationRegistry_Association_NSourceEntities`
- `0xb827ae`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb82767`: `ApplicationRegistry_Association_DuplicateSourceEntity`
- `0xb827c0`: `rawValues.ReturnTypeDescriptorId`
- `0xb827e3`: `rawValues.ReturnTypeDescriptorId`
- `0xb8284e`: `rawValues.ReturnTypeDescriptorId`
- `0xb82936`: `rawValues.ReturnTypeDescriptorId`
- `0xb829a1`: `rawValues.ReturnTypeDescriptorId`
- `0xb82a17`: `rawValues.ReturnTypeDescriptorId`
- `0xb82649`: `@ReturnTypeDescriptorId`
- `0xb82801`: `ApplicationRegistry_MethodInstanceAdmin_MissingReturnTypeDescriptor`
- `0xb8286c`: `ApplicationRegistry_MethodInstanceAdmin_NoInputParameter`
- `0xb828e9`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldBeCollection`
- `0xb82954`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorShouldNotBeCollection`
- `0xb829bf`: `ApplicationRegistry_MethodInstanceAdmin_ReturnTypeDescriptorParameterRootTypeDescriptorShouldBeCollection`
- `0xb82506`: `proc_ar_CreateAssociation`

## pseudocode

```c

```

## disassembly

```asm
0xb82480  ldarg.2
0xb82481  brtrue.s loc_B8248E
0xb82483  ldstr    aMethodstruct// "methodStruct"
0xb82488  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb8248d  throw
0xb8248e  ldarg.1
0xb8248f  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_DestinationEntityName()
0xb82494  brtrue.s loc_B824A1
0xb82496  ldstr    aRawvaluesDesti// "rawValues.DestinationEntityName"
0xb8249b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb824a0  throw
0xb824a1  ldarg.1
0xb824a2  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_DestinationEntityNamespace()
0xb824a7  brtrue.s loc_B824B4
0xb824a9  ldstr    aRawvaluesDesti_0// "rawValues.DestinationEntityNamespace"
0xb824ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb824b3  throw
0xb824b4  ldarg.1
0xb824b5  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNames()
0xb824ba  brtrue.s loc_B824C7
0xb824bc  ldstr    aRawvaluesSourc// "rawValues.SourceEntityNames"
0xb824c1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb824c6  throw
0xb824c7  ldarg.1
0xb824c8  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNamespaces()
0xb824cd  brtrue.s loc_B824DA
0xb824cf  ldstr    aRawvaluesSourc_0// "rawValues.SourceEntityNamespaces"
0xb824d4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb824d9  throw
0xb824da  ldarg.1
0xb824db  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNames()
0xb824e0  ldlen
0xb824e1  conv.i4
0xb824e2  ldc.i4.1
0xb824e3  bge.s    loc_B824FF
0xb824e5  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb824ea  ldstr    aApplicationreg_42// "ApplicationRegistry_Association_NSource"...
0xb824ef  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb824f4  ldstr    aRawvaluesSourc// "rawValues.SourceEntityNames"
0xb824f9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb824fe  throw
0xb824ff  ldarg.1
0xb82500  stloc.0
0xb82501  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb82506  ldstr    aProcArCreateas// "proc_ar_CreateAssociation"
0xb8250b  ldarg.3
0xb8250c  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderCommand(string commandText, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper sessionWrapper)
0xb82511  stloc.1
0xb82512  ldarg.0
0xb82513  ldloc.1
0xb82514  ldarg.1
0xb82515  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::CreateCommon(class [System.Data]System.Data.IDbCommand cmd, class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct rawValues)
0xb8251a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xb8251f  stloc.2
0xb82520  ldloc.2
0xb82521  ldloc.0
0xb82522  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_DestinationEntityNamespace()
0xb82527  ldstr    asc_CA2654// "\\"
0xb8252c  ldstr    asc_D00D32// "\\\\"
0xb82531  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb82536  ldstr    asc_C6AA4A// ","
0xb8253b  ldstr    asc_13AA8E2// "\\,"
0xb82540  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb82545  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb8254a  pop
0xb8254b  ldloc.2
0xb8254c  ldstr    asc_C6AA4A// ","
0xb82551  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb82556  pop
0xb82557  ldloc.2
0xb82558  ldloc.0
0xb82559  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_DestinationEntityName()
0xb8255e  ldstr    asc_CA2654// "\\"
0xb82563  ldstr    asc_D00D32// "\\\\"
0xb82568  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb8256d  ldstr    asc_C6AA4A// ","
0xb82572  ldstr    asc_13AA8E2// "\\,"
0xb82577  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb8257c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb82581  pop
0xb82582  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xb82587  stloc.3
0xb82588  ldc.i4.0
0xb82589  stloc.s  4
0xb8258b  br.s     loc_B82607
0xb8258d  ldloc.3
0xb8258e  ldloc.0
0xb8258f  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNamespaces()
0xb82594  ldloc.s  4
0xb82596  ldelem.ref
0xb82597  ldstr    asc_CA2654// "\\"
0xb8259c  ldstr    asc_D00D32// "\\\\"
0xb825a1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb825a6  ldstr    asc_C6AA4A// ","
0xb825ab  ldstr    asc_13AA8E2// "\\,"
0xb825b0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb825b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb825ba  pop
0xb825bb  ldloc.3
0xb825bc  ldstr    asc_C6AA4A// ","
0xb825c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb825c6  pop
0xb825c7  ldloc.3
0xb825c8  ldloc.0
0xb825c9  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNames()
0xb825ce  ldloc.s  4
0xb825d0  ldelem.ref
0xb825d1  ldstr    asc_CA2654// "\\"
0xb825d6  ldstr    asc_D00D32// "\\\\"
0xb825db  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb825e0  ldstr    asc_C6AA4A// ","
0xb825e5  ldstr    asc_13AA8E2// "\\,"
0xb825ea  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb825ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb825f4  pop
0xb825f5  ldloc.3
0xb825f6  ldstr    asc_C6AA4A// ","
0xb825fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb82600  pop
0xb82601  ldloc.s  4
0xb82603  ldc.i4.1
0xb82604  add
0xb82605  stloc.s  4
0xb82607  ldloc.s  4
0xb82609  ldloc.0
0xb8260a  callvirt instance string[] Microsoft.SharePoint.BusinessData.SharedService.AssociationStruct::get_SourceEntityNames()
0xb8260f  ldlen
0xb82610  conv.i4
0xb82611  blt      loc_B8258D
0xb82616  ldloc.3
0xb82617  ldloc.3
0xb82618  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0xb8261d  ldc.i4.1
0xb8261e  sub
0xb8261f  ldc.i4.1
0xb82620  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0xb82625  pop
0xb82626  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb8262b  ldstr    aMethodid_1// "@MethodId"
0xb82630  ldc.i4.s 0xB
0xb82632  ldarg.2
0xb82633  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb82638  box      [mscorlib]System.UInt32
0xb8263d  ldloc.1
0xb8263e  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb82643  pop
0xb82644  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb82649  ldstr    aReturntypedesc_4// "@ReturnTypeDescriptorId"
0xb8264e  ldc.i4.s 0xB
0xb82650  ldloc.0
0xb82651  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb82656  brtrue.s loc_B8265F
0xb82658  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb8265d  br.s     loc_B8266A
0xb8265f  ldloc.0
0xb82660  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb82665  box      [mscorlib]System.UInt32
0xb8266a  ldloc.1
0xb8266b  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb82670  pop
0xb82671  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb82676  ldstr    aType_2// "@Type"
0xb8267b  ldc.i4.2
0xb8267c  ldloc.0
0xb8267d  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_MethodInstanceType()
0xb82682  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb82687  ldloc.1
0xb82688  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb8268d  pop
0xb8268e  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb82693  ldstr    aSourceentities_0// "@SourceEntities"
0xb82698  ldc.i4.s 0x10
0xb8269a  ldloc.3
0xb8269b  callvirt instance string [mscorlib]System.Object::ToString()
0xb826a0  ldloc.1
0xb826a1  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb826a6  pop
0xb826a7  call     class Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::get_Value()
0xb826ac  ldstr    aDestinationent_3// "@DestinationEntity"
0xb826b1  ldc.i4.s 0x10
0xb826b3  ldloc.2
0xb826b4  callvirt instance string [mscorlib]System.Object::ToString()
0xb826b9  ldloc.1
0xb826ba  callvirt instance class [System.Data]System.Data.IDbDataParameter Microsoft.SharePoint.BusinessData.SharedService.DbObjectFactory::CreateProviderDataParameter(string name, valuetype [System.Data]System.Data.DbType type, object value, class [System.Data]System.Data.IDbCommand cmd)
0xb826bf  pop
0xb826c0  ldarg.3
0xb826c1  ldloc.1
0xb826c2  callvirt instance void Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xb826c7  ldloc.1
0xb826c8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb826cd  ldstr    aErrorcode_0// "@ErrorCode"
0xb826d2  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xb826d7  castclass [System.Data]System.Data.IDbDataParameter
0xb826dc  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xb826e1  unbox.any [mscorlib]System.Int32
0xb826e6  stloc.s  5
0xb826e8  ldnull
0xb826e9  stloc.s  6
0xb826eb  ldnull
0xb826ec  stloc.s  7
0xb826ee  ldnull
0xb826ef  stloc.s  8
0xb826f1  ldloc.s  5
0xb826f3  brfalse.s loc_B82759
0xb826f5  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb826fa  ldarg.2
0xb826fb  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodStruct::get_EntityId()
0xb82700  ldarg.2
0xb82701  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb82706  ldarg.3
0xb82707  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb8270c  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb82711  stloc.s  6
0xb82713  ldarg.1
0xb82714  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb82719  brfalse.s loc_B82759
0xb8271b  call     class Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::get_Value()
0xb82720  ldarg.1
0xb82721  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodInstanceStruct::get_ReturnTypeDescriptorId()
0xb82726  ldarg.2
0xb82727  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb8272c  ldarg.3
0xb8272d  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb82732  castclass Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct
0xb82737  stloc.s  7
0xb82739  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb8273e  ldloc.s  7
0xb82740  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb82745  ldloc.s  7
0xb82747  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb8274c  ldarg.3
0xb8274d  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb82752  castclass Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct
0xb82757  stloc.s  8
0xb82759  ldloc.s  5
0xb8275b  ldc.i4   0xFFFFFED4
0xb82760  bne.un.s loc_B82777
0xb82762  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb82767  ldstr    aApplicationreg_281// "ApplicationRegistry_Association_Duplica"...
0xb8276c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb82771  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb82776  throw
0xb82777  ldloc.s  5
0xb82779  ldc.i4   0xFFFFFF35
0xb8277e  bne.un.s loc_B827CB
0xb82780  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb82785  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb8278a  ldstr    aApplicationreg_39// "ApplicationRegistry_MethodInstanceAdmin"...
0xb8278f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb82794  ldc.i4.2
0xb82795  newarr   [mscorlib]System.Object
0xb8279a  stloc.s  9
0xb8279c  ldloc.s  9
0xb8279e  ldc.i4.0
0xb8279f  ldarg.1
0xb827a0  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb827a5  stelem.ref
0xb827a6  ldloc.s  9
0xb827a8  ldc.i4.1
0xb827a9  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb827ae  ldstr    aApplicationreg_49// "ApplicationRegistry_MetadataException_U"...
0xb827b3  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb827b8  stelem.ref
0xb827b9  ldloc.s  9
0xb827bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb827c0  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb827c5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb827ca  throw
0xb827cb  ldloc.s  5
0xb827cd  ldc.i4   0xFFFFFF34
0xb827d2  bne.un.s loc_B827EE
0xb827d4  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb827d9  ldstr    aApplicationreg_40// "ApplicationRegistry_MethodInstanceAdmin"...
0xb827de  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb827e3  ldstr    aRawvaluesRetur// "rawValues.ReturnTypeDescriptorId"
0xb827e8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb827ed  throw
0xb827ee  ldloc.s  5
0xb827f0  ldc.i4   0xFFFFFF32
0xb827f5  bne.un.s loc_B82859
0xb827f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb827fc  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb82801  ldstr    aApplicationreg_703// "ApplicationRegistry_MethodInstanceAdmin"...
0xb82806  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb8280b  ldc.i4.4
0xb8280c  newarr   [mscorlib]System.Object
0xb82811  stloc.s  0xA
0xb82813  ldloc.s  0xA
0xb82815  ldc.i4.0
0xb82816  ldarg.1
0xb82817  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb8281c  stelem.ref
0xb8281d  ldloc.s  0xA
0xb8281f  ldc.i4.1
0xb82820  ldloc.s  6
0xb82822  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb82827  stelem.ref
0xb82828  ldloc.s  0xA
0xb8282a  ldc.i4.2
0xb8282b  ldloc.s  6
  ... truncated ...
```
