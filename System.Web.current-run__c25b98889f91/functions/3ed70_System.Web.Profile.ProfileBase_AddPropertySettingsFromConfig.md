# System.Web.Profile.ProfileBase::AddPropertySettingsFromConfig

- ea: `0x3ed70`
- end: `0x3f020`
- name: `System.Web.Profile.ProfileBase::AddPropertySettingsFromConfig`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x3e960`

## callees

- `0x34f20`
- `0x34fa0`
- `0x3ed70`
- `0x3f020`
- `0x3f590`
- `0x152b30`
- `0x152b60`
- `0x152ba0`
- `0x152c10`
- `0x152c20`
- `0x152c30`
- `0x152c60`
- `0x152c90`
- `0x152ca0`
- `0x152cb0`
- `0x152cf0`

## string_xrefs

- `0x3edc6`: `Profile_property_already_added`
- `0x3ee2f`: `Profile_could_not_create_type`

## pseudocode

```c

```

## disassembly

```asm
0x3ed70  ldarg.3
0x3ed71  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Configuration]System.Configuration.ConfigurationElementCollection::GetEnumerator()
0x3ed76  stloc.0
0x3ed77  br       loc_3EFFE
0x3ed7c  ldloc.0
0x3ed7d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3ed82  castclass System.Web.Configuration.ProfilePropertySettings
0x3ed87  stloc.1
0x3ed88  ldarg.s  4
0x3ed8a  brtrue.s loc_3ED94
0x3ed8c  ldloc.1
0x3ed8d  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_Name()
0x3ed92  br.s     loc_3EDA6
0x3ed94  ldarg.s  4
0x3ed96  ldstr    asc_1B2EDA// "."
0x3ed9b  ldloc.1
0x3ed9c  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_Name()
0x3eda1  call     string [mscorlib]System.String::Concat(string, string, string)
0x3eda6  stloc.2
0x3eda7  ldarg.0
0x3eda8  ldtoken  System.Web.Profile.ProfileBase
0x3edad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3edb2  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3edb7  brfalse.s loc_3EE0B
0x3edb9  ldsfld   class [System]System.Configuration.SettingsPropertyCollection System.Web.Profile.ProfileBase::s_Properties
0x3edbe  ldloc.2
0x3edbf  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyCollection::get_Item(string)
0x3edc4  brfalse.s loc_3EE0B
0x3edc6  ldstr    aProfilePropert// "Profile_property_already_added"
0x3edcb  call     string System.Web.SR::GetString(string name)
0x3edd0  ldnull
0x3edd1  ldloc.1
0x3edd2  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3edd7  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3eddc  ldstr    aName// "name"
0x3ede1  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ede6  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x3edeb  ldloc.1
0x3edec  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3edf1  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3edf6  ldstr    aName// "name"
0x3edfb  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ee00  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x3ee05  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x3ee0a  throw
0x3ee0b  nop
0x3ee0c  ldloc.1
0x3ee0d  callvirt instance class [mscorlib]System.Type System.Web.Configuration.ProfilePropertySettings::get_TypeInternal()
0x3ee12  ldnull
0x3ee13  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3ee18  brfalse.s loc_3EE2B
0x3ee1a  ldloc.1
0x3ee1b  ldloc.1
0x3ee1c  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_Type()
0x3ee21  call     class [mscorlib]System.Type System.Web.Profile.ProfileBase::ResolvePropertyType(string typeName)
0x3ee26  callvirt instance void System.Web.Configuration.ProfilePropertySettings::set_TypeInternal(class [mscorlib]System.Type value)
0x3ee2b  leave.s  loc_3EE85
0x3ee2d  stloc.s  6
0x3ee2f  ldstr    aProfileCouldNo// "Profile_could_not_create_type"
0x3ee34  ldc.i4.1
0x3ee35  newarr   [mscorlib]System.Object
0x3ee3a  dup
0x3ee3b  ldc.i4.0
0x3ee3c  ldloc.s  6
0x3ee3e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3ee43  stelem.ref
0x3ee44  call     string System.Web.SR::GetString(string name, object[] args)
0x3ee49  ldloc.s  6
0x3ee4b  ldloc.1
0x3ee4c  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3ee51  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3ee56  ldstr    aType// "type"
0x3ee5b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ee60  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x3ee65  ldloc.1
0x3ee66  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3ee6b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3ee70  ldstr    aType// "type"
0x3ee75  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ee7a  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x3ee7f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x3ee84  throw
0x3ee85  ldarg.1
0x3ee86  brtrue.s loc_3EEE7
0x3ee88  ldloc.1
0x3ee89  callvirt instance bool System.Web.Configuration.ProfilePropertySettings::get_AllowAnonymous()
0x3ee8e  stloc.s  7
0x3ee90  ldloc.s  7
0x3ee92  brfalse.s loc_3EEE7
0x3ee94  ldstr    aAnnoymousIdMod// "Annoymous_id_module_not_enabled"
0x3ee99  ldc.i4.1
0x3ee9a  newarr   [mscorlib]System.Object
0x3ee9f  dup
0x3eea0  ldc.i4.0
0x3eea1  ldloc.1
0x3eea2  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_Name()
0x3eea7  stelem.ref
0x3eea8  call     string System.Web.SR::GetString(string name, object[] args)
0x3eead  ldloc.1
0x3eeae  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3eeb3  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3eeb8  ldstr    aAllowanonymous_0// "allowAnonymous"
0x3eebd  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3eec2  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x3eec7  ldloc.1
0x3eec8  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3eecd  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3eed2  ldstr    aAllowanonymous_0// "allowAnonymous"
0x3eed7  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3eedc  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x3eee1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x3eee6  throw
0x3eee7  ldarg.2
0x3eee8  brfalse.s loc_3EEF2
0x3eeea  ldloc.1
0x3eeeb  call     void System.Web.Profile.ProfileBase::SetProviderForProperty(class System.Web.Configuration.ProfilePropertySettings pps)
0x3eef0  br.s     loc_3EEF9
0x3eef2  ldloc.1
0x3eef3  ldnull
0x3eef4  callvirt instance void System.Web.Configuration.ProfilePropertySettings::set_ProviderInternal(class [System]System.Configuration.SettingsProvider value)
0x3eef9  ldloc.1
0x3eefa  callvirt instance class [System]System.Configuration.SettingsProvider System.Web.Configuration.ProfilePropertySettings::get_ProviderInternal()
0x3eeff  brfalse.s loc_3EF1D
0x3ef01  ldloc.1
0x3ef02  callvirt instance class [System]System.Configuration.SettingsProvider System.Web.Configuration.ProfilePropertySettings::get_ProviderInternal()
0x3ef07  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ef0c  ldtoken  System.Web.Profile.SqlProfileProvider
0x3ef11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ef16  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3ef1b  br.s     loc_3EF1E
0x3ef1d  ldc.i4.1
0x3ef1e  stloc.3
0x3ef1f  ldloc.3
0x3ef20  brfalse.s loc_3EF8B
0x3ef22  ldloc.1
0x3ef23  callvirt instance valuetype System.Web.Configuration.SerializationMode System.Web.Configuration.ProfilePropertySettings::get_SerializeAs()
0x3ef28  ldc.i4.2
0x3ef29  bne.un.s loc_3EF8B
0x3ef2b  ldloc.1
0x3ef2c  callvirt instance class [mscorlib]System.Type System.Web.Configuration.ProfilePropertySettings::get_TypeInternal()
0x3ef31  callvirt instance bool [mscorlib]System.Type::get_IsSerializable()
0x3ef36  brtrue.s loc_3EF8B
0x3ef38  ldstr    aPropertyNotSer// "Property_not_serializable"
0x3ef3d  ldc.i4.1
0x3ef3e  newarr   [mscorlib]System.Object
0x3ef43  dup
0x3ef44  ldc.i4.0
0x3ef45  ldloc.1
0x3ef46  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_Name()
0x3ef4b  stelem.ref
0x3ef4c  call     string System.Web.SR::GetString(string name, object[] args)
0x3ef51  ldloc.1
0x3ef52  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3ef57  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3ef5c  ldstr    aSerializeas// "serializeAs"
0x3ef61  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ef66  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x3ef6b  ldloc.1
0x3ef6c  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x3ef71  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x3ef76  ldstr    aSerializeas// "serializeAs"
0x3ef7b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x3ef80  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x3ef85  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x3ef8a  throw
0x3ef8b  newobj   instance void [System]System.Configuration.SettingsAttributeDictionary::.ctor()
0x3ef90  stloc.s  4
0x3ef92  ldloc.s  4
0x3ef94  ldstr    aAllowanonymous// "AllowAnonymous"
0x3ef99  ldloc.1
0x3ef9a  callvirt instance bool System.Web.Configuration.ProfilePropertySettings::get_AllowAnonymous()
0x3ef9f  box      [mscorlib]System.Boolean
0x3efa4  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3efa9  ldloc.1
0x3efaa  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_CustomProviderData()
0x3efaf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3efb4  brtrue.s loc_3EFC8
0x3efb6  ldloc.s  4
0x3efb8  ldstr    aCustomprovider_0// "CustomProviderData"
0x3efbd  ldloc.1
0x3efbe  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_CustomProviderData()
0x3efc3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3efc8  ldloc.2
0x3efc9  ldloc.1
0x3efca  callvirt instance class [mscorlib]System.Type System.Web.Configuration.ProfilePropertySettings::get_TypeInternal()
0x3efcf  ldloc.1
0x3efd0  callvirt instance class [System]System.Configuration.SettingsProvider System.Web.Configuration.ProfilePropertySettings::get_ProviderInternal()
0x3efd5  ldloc.1
0x3efd6  callvirt instance bool System.Web.Configuration.ProfilePropertySettings::get_ReadOnly()
0x3efdb  ldloc.1
0x3efdc  callvirt instance string System.Web.Configuration.ProfilePropertySettings::get_DefaultValue()
0x3efe1  ldloc.1
0x3efe2  callvirt instance valuetype System.Web.Configuration.SerializationMode System.Web.Configuration.ProfilePropertySettings::get_SerializeAs()
0x3efe7  ldloc.s  4
0x3efe9  ldc.i4.0
0x3efea  ldc.i4.1
0x3efeb  newobj   instance void [System]System.Configuration.SettingsProperty::.ctor(string, class [mscorlib]System.Type, class [System]System.Configuration.SettingsProvider, bool, object, valuetype [System]System.Configuration.SettingsSerializeAs, class [System]System.Configuration.SettingsAttributeDictionary, bool, bool)
0x3eff0  stloc.s  5
0x3eff2  ldsfld   class [System]System.Configuration.SettingsPropertyCollection System.Web.Profile.ProfileBase::s_Properties
0x3eff7  ldloc.s  5
0x3eff9  callvirt instance void [System]System.Configuration.SettingsPropertyCollection::Add(class [System]System.Configuration.SettingsProperty)
0x3effe  ldloc.0
0x3efff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3f004  brtrue   loc_3ED7C
0x3f009  leave.s  loc_3F01F
0x3f00b  ldloc.0
0x3f00c  isinst   [mscorlib]System.IDisposable
0x3f011  stloc.s  8
0x3f013  ldloc.s  8
0x3f015  brfalse.s loc_3F01E
0x3f017  ldloc.s  8
0x3f019  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f01e  endfinally
0x3f01f  ret
```
