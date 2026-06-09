# System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::Initialize

- ea: `0xfec20`
- end: `0xfed9e`
- name: `System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::Initialize`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x24280`
- `0x34f20`
- `0x34fa0`
- `0x4c5e0`
- `0x58700`
- `0xfec20`

## string_xrefs

- `0xfed51`: `commandTimeout`
- `0xfed64`: `commandTimeout`
- `0xfec32`: `configSettings`

## pseudocode

```c

```

## disassembly

```asm
0xfec20  ldc.i4   0x12C
0xfec25  ldstr    aFeatureNotSupp// "Feature_not_supported_at_this_level"
0xfec2a  call     void System.Web.HttpRuntime::CheckAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level, string errorMessageId)
0xfec2f  ldarg.2
0xfec30  brtrue.s loc_FEC3D
0xfec32  ldstr    aConfigsettings// "configSettings"
0xfec37  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfec3c  throw
0xfec3d  ldarg.1
0xfec3e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfec43  brfalse.s loc_FEC4C
0xfec45  ldstr    aSqlpersonaliza// "SqlPersonalizationProvider"
0xfec4a  starg.s  1
0xfec4c  ldarg.2
0xfec4d  ldstr    aDescription// "description"
0xfec52  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfec57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfec5c  brfalse.s loc_FEC7E
0xfec5e  ldarg.2
0xfec5f  ldstr    aDescription// "description"
0xfec64  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0xfec69  ldarg.2
0xfec6a  ldstr    aDescription// "description"
0xfec6f  ldstr    aSqlpersonaliza_0// "SqlPersonalizationProvider_Description"
0xfec74  call     string System.Web.SR::GetString(string name)
0xfec79  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xfec7e  ldarg.0
0xfec7f  ldarg.1
0xfec80  ldarg.2
0xfec81  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0xfec86  ldarg.0
0xfec87  ldc.i4.0
0xfec88  stfld    int32 System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_SchemaVersionCheck
0xfec8d  ldarg.0
0xfec8e  ldarg.2
0xfec8f  ldstr    aApplicationnam// "applicationName"
0xfec94  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfec99  stfld    string System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_applicationName
0xfec9e  ldarg.0
0xfec9f  ldfld    string System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_applicationName
0xfeca4  brfalse.s loc_FECEE
0xfeca6  ldarg.2
0xfeca7  ldstr    aApplicationnam// "applicationName"
0xfecac  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0xfecb1  ldarg.0
0xfecb2  ldfld    string System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_applicationName
0xfecb7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xfecbc  ldc.i4   0x100
0xfecc1  ble.s    loc_FECEE
0xfecc3  ldstr    aPersonalizatio_20// "PersonalizationProvider_ApplicationName"...
0xfecc8  ldc.i4.1
0xfecc9  newarr   [mscorlib]System.Object
0xfecce  dup
0xfeccf  ldc.i4.0
0xfecd0  ldc.i4   0x100
0xfecd5  stloc.2
0xfecd6  ldloca.s 2
0xfecd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xfecdd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xfece2  stelem.ref
0xfece3  call     string System.Web.SR::GetString(string name, object[] args)
0xfece8  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0xfeced  throw
0xfecee  ldarg.2
0xfecef  ldstr    aConnectionstri// "connectionStringName"
0xfecf4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfecf9  stloc.0
0xfecfa  ldloc.0
0xfecfb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfed00  brfalse.s loc_FED12
0xfed02  ldstr    aPersonalizatio_22// "PersonalizationProvider_NoConnection"
0xfed07  call     string System.Web.SR::GetString(string name)
0xfed0c  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0xfed11  throw
0xfed12  ldarg.2
0xfed13  ldstr    aConnectionstri// "connectionStringName"
0xfed18  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0xfed1d  ldloc.0
0xfed1e  ldc.i4.1
0xfed1f  ldc.i4.1
0xfed20  call     string System.Web.DataAccess.SqlConnectionHelper::GetConnectionString(string specifiedConnectionString, bool lookupConnectionString, bool appLevel)
0xfed25  stloc.1
0xfed26  ldloc.1
0xfed27  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfed2c  brfalse.s loc_FED48
0xfed2e  ldstr    aPersonalizatio_23// "PersonalizationProvider_BadConnection"
0xfed33  ldc.i4.1
0xfed34  newarr   [mscorlib]System.Object
0xfed39  dup
0xfed3a  ldc.i4.0
0xfed3b  ldloc.0
0xfed3c  stelem.ref
0xfed3d  call     string System.Web.SR::GetString(string name, object[] args)
0xfed42  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0xfed47  throw
0xfed48  ldarg.0
0xfed49  ldloc.1
0xfed4a  stfld    string System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_connectionString
0xfed4f  ldarg.0
0xfed50  ldarg.2
0xfed51  ldstr    aCommandtimeout// "commandTimeout"
0xfed56  ldc.i4.m1
0xfed57  ldc.i4.1
0xfed58  ldc.i4.0
0xfed59  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0xfed5e  stfld    int32 System.Web.UI.WebControls.WebParts.SqlPersonalizationProvider::_commandTimeout
0xfed63  ldarg.2
0xfed64  ldstr    aCommandtimeout// "commandTimeout"
0xfed69  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0xfed6e  ldarg.2
0xfed6f  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xfed74  ldc.i4.0
0xfed75  ble.s    loc_FED9D
0xfed77  ldarg.2
0xfed78  ldc.i4.0
0xfed79  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0xfed7e  stloc.3
0xfed7f  ldstr    aPersonalizatio_24// "PersonalizationProvider_UnknownProp"
0xfed84  ldc.i4.2
0xfed85  newarr   [mscorlib]System.Object
0xfed8a  dup
0xfed8b  ldc.i4.0
0xfed8c  ldloc.3
0xfed8d  stelem.ref
0xfed8e  dup
0xfed8f  ldc.i4.1
0xfed90  ldarg.1
0xfed91  stelem.ref
0xfed92  call     string System.Web.SR::GetString(string name, object[] args)
0xfed97  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0xfed9c  throw
0xfed9d  ret
```
