# Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::CreateInternal

- ea: `0xb964a0`
- end: `0xb96be6`
- name: `Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::CreateInternal`
- size: `1862`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0xb96440`
- `0xbfc1b0`

## callees

- `0xb08310`
- `0xb47c60`
- `0xb47c80`
- `0xb47ce0`
- `0xb48670`
- `0xb49970`
- `0xb49f50`
- `0xb4a8a0`
- `0xb4aa70`
- `0xb4b0a0`
- `0xb4b0b0`
- `0xb4b0c0`
- `0xb4b0e0`
- `0xb4b120`
- `0xb4b140`
- `0xb69610`
- `0xb7a1f0`
- `0xb7a9c0`
- `0xb7aec0`
- `0xb7d100`
- `0xb7d110`
- `0xb8c600`
- `0xb8c800`
- `0xb8c890`
- `0xb8cd20`
- `0xb8d330`
- `0xb8f5f0`
- `0xb90840`
- `0xb911e0`
- `0xb92850`
- `0xb93fe0`
- `0xb96480`
- `0xb964a0`
- `0xb972e0`
- `0xb97390`

## string_xrefs

- `0xb96525`: `ApplicationRegistry_Admin_BadMetadataObjectNameLength`
- `0xb965c6`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb9698c`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb96a65`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb96ad2`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb96b93`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb96b41`: `FilterDescriptor`
- `0xb964c0`: `ApplicationRegistry_TypeDescriptor_BadTypeName`
- `0xb964ec`: `ApplicationRegistry_TypeDescriptor_TypeNameTooLong`
- `0xb969ef`: `ApplicationRegistry_TypeDescriptor_BadFilterDescriptor`
- `0xb9653a`: `TypeDescriptor`
- `0xb96b38`: `TypeDescriptor`
- `0xb96589`: `ApplicationRegistry_TypeDescriptor_ParentFromSameParameter`
- `0xb96680`: `ApplicationRegistry_TypeDescriptor_TypeLoadDetailed`
- `0xb96722`: `ApplicationRegistry_TypeDescriptor_TypeFileNotFoundDetailed`
- `0xb967c4`: `ApplicationRegistry_TypeDescriptor_TypeFileLoadDetailed`
- `0xb96aae`: `ApplicationRegistry_TypeDescriptor_IsCollectionHasMultipleChildren`
- `0xb96b18`: `ApplicationRegistry_Admin_ExceededMetadataObjectLimit`
- `0xb968f4`: `@ParentTypeDescriptorId`
- `0xb968c6`: `@FilterDescriptorId`
- `0xb965d8`: `rawValues.ParentTypeDescriptorId`
- `0xb969b7`: `rawValues.ParentTypeDescriptorId`
- `0xb96838`: `proc_ar_CreateTypeDescriptor`
- `0xb96968`: `ApplicationRegistry_TypeDescriptor_MultipleRoots`
- `0xb96a23`: `rawValues.FilterDescriptorId`
- `0xb96a41`: `ApplicationRegistry_TypeDescriptor_ConsecutiveIsCollections`
- `0xb96b6f`: `ApplicationRegistry_TypeDescriptor_ReadonlyTypeDescriptorOnInParameter`

## pseudocode

```c

```

## disassembly

```asm
0xb964a0  ldarg.3
0xb964a1  brtrue.s loc_B964AE
0xb964a3  ldstr    aParameterstruc// "parameterStruct"
0xb964a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb964ad  throw
0xb964ae  ldarg.1
0xb964af  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb964b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb964b9  brfalse.s loc_B964D5
0xb964bb  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb964c0  ldstr    aApplicationreg_92// "ApplicationRegistry_TypeDescriptor_BadT"...
0xb964c5  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb964ca  ldstr    aRawvaluesTypen// "rawValues.TypeName"
0xb964cf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb964d4  throw
0xb964d5  ldarg.1
0xb964d6  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb964db  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb964e0  ldc.i4   0xFF
0xb964e5  ble.s    loc_B96501
0xb964e7  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb964ec  ldstr    aApplicationreg_93// "ApplicationRegistry_TypeDescriptor_Type"...
0xb964f1  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb964f6  ldstr    aRawvaluesTypen// "rawValues.TypeName"
0xb964fb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb96500  throw
0xb96501  ldarg.1
0xb96502  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_LobName()
0xb96507  brfalse.s loc_B96552
0xb96509  ldarg.1
0xb9650a  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_LobName()
0xb9650f  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb96514  ldc.i4   0xFF
0xb96519  ble.s    loc_B96552
0xb9651b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb96520  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96525  ldstr    aApplicationreg_0// "ApplicationRegistry_Admin_BadMetadataOb"...
0xb9652a  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb9652f  ldc.i4.1
0xb96530  newarr   [mscorlib]System.Object
0xb96535  stloc.s  0x10
0xb96537  ldloc.s  0x10
0xb96539  ldc.i4.0
0xb9653a  ldstr    aTypedescriptor// "TypeDescriptor"
0xb9653f  stelem.ref
0xb96540  ldloc.s  0x10
0xb96542  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb96547  ldstr    aRawvaluesLobna// "rawValues.LobName"
0xb9654c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb96551  throw
0xb96552  ldarg.2
0xb96553  brfalse  loc_B965E3
0xb96558  call     class Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor Microsoft.SharePoint.BusinessData.SharedService.ParameterAccessor::get_Value()
0xb9655d  ldarg.2
0xb9655e  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_ParameterId()
0xb96563  ldarg.2
0xb96564  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96569  ldarg.s  5
0xb9656b  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96570  stloc.0
0xb96571  ldloc.0
0xb96572  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb96577  ldarg.3
0xb96578  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb9657d  beq.s    loc_B965E3
0xb9657f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb96584  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96589  ldstr    aApplicationreg_98// "ApplicationRegistry_TypeDescriptor_Pare"...
0xb9658e  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb96593  ldc.i4.4
0xb96594  newarr   [mscorlib]System.Object
0xb96599  stloc.s  0x11
0xb9659b  ldloc.s  0x11
0xb9659d  ldc.i4.0
0xb9659e  ldarg.2
0xb9659f  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb965a4  stelem.ref
0xb965a5  ldloc.s  0x11
0xb965a7  ldc.i4.1
0xb965a8  ldarg.2
0xb965a9  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Id()
0xb965ae  box      [mscorlib]System.UInt32
0xb965b3  stelem.ref
0xb965b4  ldloc.s  0x11
0xb965b6  ldc.i4.2
0xb965b7  ldarg.1
0xb965b8  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb965bd  stelem.ref
0xb965be  ldloc.s  0x11
0xb965c0  ldc.i4.3
0xb965c1  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb965c6  ldstr    aApplicationreg_49// "ApplicationRegistry_MetadataException_U"...
0xb965cb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb965d0  stelem.ref
0xb965d1  ldloc.s  0x11
0xb965d3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb965d8  ldstr    aRawvaluesParen// "rawValues.ParentTypeDescriptorId"
0xb965dd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb965e2  throw
0xb965e3  ldarg.0
0xb965e4  ldarg.3
0xb965e5  ldarg.s  5
0xb965e7  call     instance class Microsoft.SharePoint.BusinessData.SharedService.LobSystemStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetLobSystemStructForParameterStruct(class Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct parameterStruct, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb965ec  stloc.1
0xb965ed  ldloc.1
0xb965ee  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.SystemType Microsoft.SharePoint.BusinessData.SharedService.LobSystemStruct::get_SystemType()
0xb965f3  ldc.i4.s 9
0xb965f5  beq      loc_B9681A
0xb965fa  ldarg.0
0xb965fb  ldarg.3
0xb965fc  ldarg.s  5
0xb965fe  call     instance class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorAccessor::GetTypeReflector(class Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct ps, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96603  stloc.2
0xb96604  ldloc.1
0xb96605  call     class Microsoft.SharePoint.BusinessData.SharedService.LobSystemAccessor Microsoft.SharePoint.BusinessData.SharedService.LobSystemAccessor::get_Value()
0xb9660a  ldloc.1
0xb9660b  ldarg.s  5
0xb9660d  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.LobSystemAccessor::GetSystemUtilityTypeNameForLobSystem(class Microsoft.SharePoint.BusinessData.SharedService.LobSystemStruct lobSystemStruct, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96612  ldc.i4.1
0xb96613  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0xb96618  ldnull
0xb96619  ldarg.s  4
0xb9661b  newobj   instance void Microsoft.SharePoint.BusinessData.SharedService.ApplicationServerLobSystemStruct::.ctor(class Microsoft.SharePoint.BusinessData.SharedService.LobSystemStruct lobSystemStruct, class [mscorlib]System.Type systemUtilityType, class [mscorlib]System.Type connectionManagerType, class Microsoft.SharePoint.BusinessData.SharedService.BdcServiceApplication bdcServiceApplication)
0xb96620  stloc.3
0xb96621  ldloc.2
0xb96622  ldarg.1
0xb96623  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb96628  ldloc.3
0xb96629  callvirt instance class [mscorlib]System.Type [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector::ResolveDotNetType(string, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ILobSystemStruct)
0xb9662e  pop
0xb9662f  leave    loc_B9681A
0xb96634  stloc.s  4
0xb96636  call     class Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor::get_Value()
0xb9663b  ldarg.3
0xb9663c  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct::get_MethodId()
0xb96641  ldarg.3
0xb96642  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96647  ldarg.s  5
0xb96649  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb9664e  castclass Microsoft.SharePoint.BusinessData.SharedService.MethodStruct
0xb96653  stloc.s  5
0xb96655  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb9665a  ldloc.s  5
0xb9665c  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodStruct::get_EntityId()
0xb96661  ldloc.s  5
0xb96663  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb96668  ldarg.s  5
0xb9666a  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb9666f  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb96674  stloc.s  6
0xb96676  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb9667b  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96680  ldstr    aApplicationreg_123// "ApplicationRegistry_TypeDescriptor_Type"...
0xb96685  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb9668a  ldc.i4.5
0xb9668b  newarr   [mscorlib]System.Object
0xb96690  stloc.s  0x12
0xb96692  ldloc.s  0x12
0xb96694  ldc.i4.0
0xb96695  ldarg.1
0xb96696  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb9669b  stelem.ref
0xb9669c  ldloc.s  0x12
0xb9669e  ldc.i4.1
0xb9669f  ldarg.3
0xb966a0  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb966a5  stelem.ref
0xb966a6  ldloc.s  0x12
0xb966a8  ldc.i4.2
0xb966a9  ldloc.s  5
0xb966ab  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb966b0  stelem.ref
0xb966b1  ldloc.s  0x12
0xb966b3  ldc.i4.3
0xb966b4  ldloc.s  6
0xb966b6  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb966bb  stelem.ref
0xb966bc  ldloc.s  0x12
0xb966be  ldc.i4.4
0xb966bf  ldloc.s  6
0xb966c1  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb966c6  stelem.ref
0xb966c7  ldloc.s  0x12
0xb966c9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb966ce  ldloc.s  4
0xb966d0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0xb966d5  throw
0xb966d6  stloc.s  7
0xb966d8  call     class Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor::get_Value()
0xb966dd  ldarg.3
0xb966de  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct::get_MethodId()
0xb966e3  ldarg.3
0xb966e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb966e9  ldarg.s  5
0xb966eb  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb966f0  castclass Microsoft.SharePoint.BusinessData.SharedService.MethodStruct
0xb966f5  stloc.s  8
0xb966f7  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb966fc  ldloc.s  8
0xb966fe  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodStruct::get_EntityId()
0xb96703  ldloc.s  8
0xb96705  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb9670a  ldarg.s  5
0xb9670c  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96711  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb96716  stloc.s  9
0xb96718  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb9671d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb96722  ldstr    aApplicationreg_124// "ApplicationRegistry_TypeDescriptor_Type"...
0xb96727  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb9672c  ldc.i4.5
0xb9672d  newarr   [mscorlib]System.Object
0xb96732  stloc.s  0x13
0xb96734  ldloc.s  0x13
0xb96736  ldc.i4.0
0xb96737  ldarg.1
0xb96738  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb9673d  stelem.ref
0xb9673e  ldloc.s  0x13
0xb96740  ldc.i4.1
0xb96741  ldarg.3
0xb96742  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96747  stelem.ref
0xb96748  ldloc.s  0x13
0xb9674a  ldc.i4.2
0xb9674b  ldloc.s  8
0xb9674d  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb96752  stelem.ref
0xb96753  ldloc.s  0x13
0xb96755  ldc.i4.3
0xb96756  ldloc.s  9
0xb96758  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb9675d  stelem.ref
0xb9675e  ldloc.s  0x13
0xb96760  ldc.i4.4
0xb96761  ldloc.s  9
0xb96763  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb96768  stelem.ref
0xb96769  ldloc.s  0x13
0xb9676b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb96770  ldloc.s  7
0xb96772  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0xb96777  throw
0xb96778  stloc.s  0xA
0xb9677a  call     class Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor Microsoft.SharePoint.BusinessData.SharedService.MethodAccessor::get_Value()
0xb9677f  ldarg.3
0xb96780  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.ParameterStruct::get_MethodId()
0xb96785  ldarg.3
0xb96786  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb9678b  ldarg.s  5
0xb9678d  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb96792  castclass Microsoft.SharePoint.BusinessData.SharedService.MethodStruct
0xb96797  stloc.s  0xB
0xb96799  call     class Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor Microsoft.SharePoint.BusinessData.SharedService.EntityAccessor::get_Value()
0xb9679e  ldloc.s  0xB
0xb967a0  callvirt instance unsigned int32 Microsoft.SharePoint.BusinessData.SharedService.MethodStruct::get_EntityId()
0xb967a5  ldloc.s  0xB
0xb967a7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_PartitionId()
0xb967ac  ldarg.s  5
0xb967ae  callvirt instance class Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectAccessor::GetMetadataObjectById(unsigned int32 metadataObjectId, valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.BusinessData.SharedService.DbSessionWrapper dbSessionWrapper)
0xb967b3  castclass Microsoft.SharePoint.BusinessData.SharedService.EntityStruct
0xb967b8  stloc.s  0xC
0xb967ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb967bf  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb967c4  ldstr    aApplicationreg_125// "ApplicationRegistry_TypeDescriptor_Type"...
0xb967c9  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb967ce  ldc.i4.5
0xb967cf  newarr   [mscorlib]System.Object
0xb967d4  stloc.s  0x14
0xb967d6  ldloc.s  0x14
0xb967d8  ldc.i4.0
0xb967d9  ldarg.1
0xb967da  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.TypeDescriptorStruct::get_TypeName()
0xb967df  stelem.ref
0xb967e0  ldloc.s  0x14
0xb967e2  ldc.i4.1
0xb967e3  ldarg.3
0xb967e4  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb967e9  stelem.ref
0xb967ea  ldloc.s  0x14
0xb967ec  ldc.i4.2
0xb967ed  ldloc.s  0xB
0xb967ef  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb967f4  stelem.ref
0xb967f5  ldloc.s  0x14
0xb967f7  ldc.i4.3
0xb967f8  ldloc.s  0xC
0xb967fa  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.MetadataObjectStruct::get_Name()
0xb967ff  stelem.ref
0xb96800  ldloc.s  0x14
0xb96802  ldc.i4.4
0xb96803  ldloc.s  0xC
0xb96805  callvirt instance string Microsoft.SharePoint.BusinessData.SharedService.DataClassStruct::get_Namespace()
0xb9680a  stelem.ref
0xb9680b  ldloc.s  0x14
0xb9680d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb96812  ldloc.s  0xA
0xb96814  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0xb96819  throw
0xb9681a  ldarg.1
  ... truncated ...
```
