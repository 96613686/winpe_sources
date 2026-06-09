# Microsoft.VisualStudio.Setup.Serialization.DependencyConverter::WriteJson

- ea: `0xe8d0`
- end: `0xeb1e`
- name: `Microsoft.VisualStudio.Setup.Serialization.DependencyConverter::WriteJson`
- size: `590`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4160`
- `0x4180`
- `0x41a0`
- `0x41c0`
- `0x41e0`
- `0x4200`
- `0x4220`
- `0x4240`
- `0x4260`
- `0x42a0`
- `0x4340`
- `0xc1a0`
- `0xe8d0`

## string_xrefs

- `0xe8d1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xe8d0  ldarg.1
0xe8d1  ldstr    aWriter// "writer"
0xe8d6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe8db  ldarg.3
0xe8dc  ldstr    aSerializer// "serializer"
0xe8e1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe8e6  ldarg.2
0xe8e7  isinst   Microsoft.VisualStudio.Setup.Dependency
0xe8ec  stloc.0
0xe8ed  ldloc.0
0xe8ee  brtrue.s loc_E8F7
0xe8f0  ldarg.1
0xe8f1  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteNull()
0xe8f6  ret
0xe8f7  ldloc.0
0xe8f8  callvirt instance bool Microsoft.VisualStudio.Setup.Dependency::get_IsSimple()
0xe8fd  brfalse.s loc_E916
0xe8ff  ldarg.3
0xe900  ldarg.1
0xe901  ldloc.0
0xe902  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Dependency::get_Version()
0xe907  dup
0xe908  brtrue.s loc_E910
0xe90a  pop
0xe90b  ldsfld   object Microsoft.VisualStudio.Setup.Serialization.DependencyConverter::EmptyObject
0xe910  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xe915  ret
0xe916  ldarg.3
0xe917  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_ContractResolver()
0xe91c  isinst   [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver
0xe921  stloc.1
0xe922  ldarg.1
0xe923  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0xe928  ldloc.0
0xe929  call     bool Microsoft.VisualStudio.Setup.DependencyCollection::HasIdentityKey(class Microsoft.VisualStudio.Setup.Dependency item)
0xe92e  brtrue.s loc_E95D
0xe930  ldarg.1
0xe931  ldloc.1
0xe932  brtrue.s loc_E937
0xe934  ldnull
0xe935  br.s     loc_E942
0xe937  ldloc.1
0xe938  ldstr    aId// "Id"
0xe93d  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xe942  dup
0xe943  brtrue.s loc_E94B
0xe945  pop
0xe946  ldstr    aId// "Id"
0xe94b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xe950  ldarg.3
0xe951  ldarg.1
0xe952  ldloc.0
0xe953  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Id()
0xe958  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xe95d  ldloc.0
0xe95e  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Dependency::get_Version()
0xe963  brfalse.s loc_E992
0xe965  ldarg.1
0xe966  ldloc.1
0xe967  brtrue.s loc_E96C
0xe969  ldnull
0xe96a  br.s     loc_E977
0xe96c  ldloc.1
0xe96d  ldstr    aVersion_1// "Version"
0xe972  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xe977  dup
0xe978  brtrue.s loc_E980
0xe97a  pop
0xe97b  ldstr    aVersion_1// "Version"
0xe980  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xe985  ldarg.3
0xe986  ldarg.1
0xe987  ldloc.0
0xe988  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Dependency::get_Version()
0xe98d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xe992  ldloc.0
0xe993  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Chip()
0xe998  brfalse.s loc_E9C7
0xe99a  ldarg.1
0xe99b  ldloc.1
0xe99c  brtrue.s loc_E9A1
0xe99e  ldnull
0xe99f  br.s     loc_E9AC
0xe9a1  ldloc.1
0xe9a2  ldstr    aChip_1// "Chip"
0xe9a7  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xe9ac  dup
0xe9ad  brtrue.s loc_E9B5
0xe9af  pop
0xe9b0  ldstr    aChip_1// "Chip"
0xe9b5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xe9ba  ldarg.3
0xe9bb  ldarg.1
0xe9bc  ldloc.0
0xe9bd  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Chip()
0xe9c2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xe9c7  ldloc.0
0xe9c8  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_MachineArch()
0xe9cd  brfalse.s loc_E9FC
0xe9cf  ldarg.1
0xe9d0  ldloc.1
0xe9d1  brtrue.s loc_E9D6
0xe9d3  ldnull
0xe9d4  br.s     loc_E9E1
0xe9d6  ldloc.1
0xe9d7  ldstr    aMachinearch_1// "MachineArch"
0xe9dc  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xe9e1  dup
0xe9e2  brtrue.s loc_E9EA
0xe9e4  pop
0xe9e5  ldstr    aMachinearch_1// "MachineArch"
0xe9ea  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xe9ef  ldarg.3
0xe9f0  ldarg.1
0xe9f1  ldloc.0
0xe9f2  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_MachineArch()
0xe9f7  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xe9fc  ldloc.0
0xe9fd  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Language()
0xea02  brfalse.s loc_EA31
0xea04  ldarg.1
0xea05  ldloc.1
0xea06  brtrue.s loc_EA0B
0xea08  ldnull
0xea09  br.s     loc_EA16
0xea0b  ldloc.1
0xea0c  ldstr    aLanguage_1// "Language"
0xea11  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xea16  dup
0xea17  brtrue.s loc_EA1F
0xea19  pop
0xea1a  ldstr    aLanguage_1// "Language"
0xea1f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xea24  ldarg.3
0xea25  ldarg.1
0xea26  ldloc.0
0xea27  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Language()
0xea2c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xea31  ldloc.0
0xea32  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Branch()
0xea37  brfalse.s loc_EA66
0xea39  ldarg.1
0xea3a  ldloc.1
0xea3b  brtrue.s loc_EA40
0xea3d  ldnull
0xea3e  br.s     loc_EA4B
0xea40  ldloc.1
0xea41  ldstr    aBranch_1// "Branch"
0xea46  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xea4b  dup
0xea4c  brtrue.s loc_EA54
0xea4e  pop
0xea4f  ldstr    aBranch_1// "Branch"
0xea54  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xea59  ldarg.3
0xea5a  ldarg.1
0xea5b  ldloc.0
0xea5c  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Branch()
0xea61  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xea66  ldloc.0
0xea67  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyType Microsoft.VisualStudio.Setup.Dependency::get_Type()
0xea6c  brfalse.s loc_EAA0
0xea6e  ldarg.1
0xea6f  ldloc.1
0xea70  brtrue.s loc_EA75
0xea72  ldnull
0xea73  br.s     loc_EA80
0xea75  ldloc.1
0xea76  ldstr    aType_1// "Type"
0xea7b  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xea80  dup
0xea81  brtrue.s loc_EA89
0xea83  pop
0xea84  ldstr    aType_1// "Type"
0xea89  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xea8e  ldarg.3
0xea8f  ldarg.1
0xea90  ldloc.0
0xea91  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyType Microsoft.VisualStudio.Setup.Dependency::get_Type()
0xea96  box      Microsoft.VisualStudio.Setup.DependencyType
0xea9b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xeaa0  ldloc.0
0xeaa1  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyBehaviors Microsoft.VisualStudio.Setup.Dependency::get_Behaviors()
0xeaa6  brfalse.s loc_EADA
0xeaa8  ldarg.1
0xeaa9  ldloc.1
0xeaaa  brtrue.s loc_EAAF
0xeaac  ldnull
0xeaad  br.s     loc_EABA
0xeaaf  ldloc.1
0xeab0  ldstr    aBehaviors// "Behaviors"
0xeab5  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xeaba  dup
0xeabb  brtrue.s loc_EAC3
0xeabd  pop
0xeabe  ldstr    aBehaviors// "Behaviors"
0xeac3  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xeac8  ldarg.3
0xeac9  ldarg.1
0xeaca  ldloc.0
0xeacb  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyBehaviors Microsoft.VisualStudio.Setup.Dependency::get_Behaviors()
0xead0  box      Microsoft.VisualStudio.Setup.DependencyBehaviors
0xead5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xeada  ldloc.0
0xeadb  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependency::get_When()
0xeae0  call     T0x2B00000E
0xeae5  brtrue.s loc_EB14
0xeae7  ldarg.1
0xeae8  ldloc.1
0xeae9  brtrue.s loc_EAEE
0xeaeb  ldnull
0xeaec  br.s     loc_EAF9
0xeaee  ldloc.1
0xeaef  ldstr    aWhen// "When"
0xeaf4  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xeaf9  dup
0xeafa  brtrue.s loc_EB02
0xeafc  pop
0xeafd  ldstr    aWhen// "When"
0xeb02  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xeb07  ldarg.3
0xeb08  ldarg.1
0xeb09  ldloc.0
0xeb0a  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependency::get_When()
0xeb0f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xeb14  leave.s  loc_EB1D
0xeb16  ldarg.1
0xeb17  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0xeb1c  endfinally
0xeb1d  ret
```
