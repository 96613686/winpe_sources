# Microsoft.SharePoint.Deployment.ListSerializer::UpdateListData

- ea: `0x5efa20`
- end: `0x5f0665`
- name: `Microsoft.SharePoint.Deployment.ListSerializer::UpdateListData`
- size: `3141`
- prototype: ``
- caller_count: `2`
- callee_count: `75`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5ed2e0`
- `0x5f1f00`

## callees

- `0x1c8850`
- `0x26f650`
- `0x2a1220`
- `0x342e60`
- `0x343230`
- `0x3439f0`
- `0x343ef0`
- `0x3440b0`
- `0x344680`
- `0x3447e0`
- `0x344880`
- `0x3449c0`
- `0x344a50`
- `0x344ae0`
- `0x345650`
- `0x345700`
- `0x3457f0`
- `0x345950`
- `0x345980`
- `0x345c30`
- `0x345c60`
- `0x345d40`
- `0x345ea0`
- `0x345f90`
- `0x345fd0`
- `0x3460a0`
- `0x3461b0`
- `0x346390`
- `0x346590`
- `0x346800`
- `0x346900`
- `0x3469e0`
- `0x346b40`
- `0x346be0`
- `0x346c80`
- `0x346d40`
- `0x346ea0`
- `0x346f30`
- `0x347020`
- `0x3470f0`
- `0x347200`
- `0x347260`
- `0x347320`
- `0x3473c0`
- `0x347460`
- `0x3475b0`
- `0x3476d0`
- `0x347790`
- `0x347850`
- `0x347920`

## string_xrefs

- `0x5eff2a`: `DefaultItemOpen`
- `0x5eff42`: `DefaultItemOpen`
- `0x5eff64`: `DefaultItemOpen`
- `0x5eff7b`: `DefaultItemOpen`
- `0x5efef3`: `DefaultItemOpenUseListSetting`
- `0x5eff00`: `DefaultItemOpenUseListSetting`
- `0x5eff14`: `DefaultItemOpenUseListSetting`
- `0x5efd5e`: `ReadSecurity`
- `0x5efd6c`: `ReadSecurity`
- `0x5efd81`: `WriteSecurity`
- `0x5efd8f`: `WriteSecurity`
- `0x5efe40`: `NeedUpdateSiteClientTag`
- `0x5efe4e`: `NeedUpdateSiteClientTag`
- `0x5f05eb`: `ReadOnlyUI`
- `0x5f0603`: `RestrictUserUpdates`
- `0x5efb90`: `RequestAccessEnabled`
- `0x5efba3`: `RequestAccessEnabled`
- `0x5efbc3`: `RequestAccessEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x5efa20  ldarg.2
0x5efa21  ldstr    aTitle_0// "Title"
0x5efa26  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efa2b  brfalse.s loc_5EFA43
0x5efa2d  ldarg.1
0x5efa2e  ldarg.2
0x5efa2f  ldstr    aTitle_0// "Title"
0x5efa34  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efa39  castclass [mscorlib]System.String
0x5efa3e  callvirt instance void Microsoft.SharePoint.SPList::set_Title(string value)
0x5efa43  ldarg.2
0x5efa44  ldstr    aDescription// "Description"
0x5efa49  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efa4e  brfalse.s loc_5EFA66
0x5efa50  ldarg.1
0x5efa51  ldarg.2
0x5efa52  ldstr    aDescription// "Description"
0x5efa57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efa5c  castclass [mscorlib]System.String
0x5efa61  callvirt instance void Microsoft.SharePoint.SPList::set_Description(string value)
0x5efa66  ldarg.2
0x5efa67  ldstr    aDirection_0// "Direction"
0x5efa6c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efa71  brfalse.s loc_5EFA89
0x5efa73  ldarg.1
0x5efa74  ldarg.2
0x5efa75  ldstr    aDirection_0// "Direction"
0x5efa7a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efa7f  castclass [mscorlib]System.String
0x5efa84  callvirt instance void Microsoft.SharePoint.SPList::set_Direction(string value)
0x5efa89  ldarg.2
0x5efa8a  ldstr    aEventsinkassem_0// "EventSinkAssembly"
0x5efa8f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efa94  brfalse.s loc_5EFAAC
0x5efa96  ldarg.1
0x5efa97  ldarg.2
0x5efa98  ldstr    aEventsinkassem_0// "EventSinkAssembly"
0x5efa9d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efaa2  castclass [mscorlib]System.String
0x5efaa7  callvirt instance void Microsoft.SharePoint.SPList::set_EventSinkAssembly(string value)
0x5efaac  ldarg.2
0x5efaad  ldstr    aEventsinkclass_0// "EventSinkClass"
0x5efab2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efab7  brfalse.s loc_5EFACF
0x5efab9  ldarg.1
0x5efaba  ldarg.2
0x5efabb  ldstr    aEventsinkclass_0// "EventSinkClass"
0x5efac0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efac5  castclass [mscorlib]System.String
0x5efaca  callvirt instance void Microsoft.SharePoint.SPList::set_EventSinkClass(string value)
0x5efacf  ldarg.2
0x5efad0  ldstr    aEventsinkdata_0// "EventSinkData"
0x5efad5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efada  brfalse.s loc_5EFAF2
0x5efadc  ldarg.1
0x5efadd  ldarg.2
0x5efade  ldstr    aEventsinkdata_0// "EventSinkData"
0x5efae3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efae8  castclass [mscorlib]System.String
0x5efaed  callvirt instance void Microsoft.SharePoint.SPList::set_EventSinkData(string value)
0x5efaf2  ldarg.2
0x5efaf3  ldstr    aAllowmultiresp// "AllowMultiResponses"
0x5efaf8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efafd  brfalse.s loc_5EFB15
0x5efaff  ldarg.1
0x5efb00  ldarg.2
0x5efb01  ldstr    aAllowmultiresp// "AllowMultiResponses"
0x5efb06  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efb0b  unbox.any [mscorlib]System.Boolean
0x5efb10  callvirt instance void Microsoft.SharePoint.SPList::set_AllowMultiResponses(bool value)
0x5efb15  ldarg.1
0x5efb16  callvirt instance bool Microsoft.SharePoint.SPList::get_HasExternalDataSource()
0x5efb1b  brtrue.s loc_5EFB8F
0x5efb1d  ldarg.2
0x5efb1e  ldstr    aEnableattachme_0// "EnableAttachments"
0x5efb23  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efb28  brfalse.s loc_5EFB40
0x5efb2a  ldarg.1
0x5efb2b  ldarg.2
0x5efb2c  ldstr    aEnableattachme_0// "EnableAttachments"
0x5efb31  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efb36  unbox.any [mscorlib]System.Boolean
0x5efb3b  callvirt instance void Microsoft.SharePoint.SPList::set_EnableAttachments(bool value)
0x5efb40  ldarg.2
0x5efb41  ldstr    aEnableversioni// "EnableVersioning"
0x5efb46  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efb4b  brfalse.s loc_5EFB6C
0x5efb4d  ldarg.1
0x5efb4e  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x5efb53  ldc.i4.4
0x5efb54  beq.s    loc_5EFB6C
0x5efb56  ldarg.1
0x5efb57  ldarg.2
0x5efb58  ldstr    aEnableversioni// "EnableVersioning"
0x5efb5d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efb62  unbox.any [mscorlib]System.Boolean
0x5efb67  callvirt instance void Microsoft.SharePoint.SPList::set_EnableVersioning(bool value)
0x5efb6c  ldarg.2
0x5efb6d  ldstr    aEnableminorver_0// "EnableMinorVersions"
0x5efb72  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efb77  brfalse.s loc_5EFB8F
0x5efb79  ldarg.1
0x5efb7a  ldarg.2
0x5efb7b  ldstr    aEnableminorver_0// "EnableMinorVersions"
0x5efb80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efb85  unbox.any [mscorlib]System.Boolean
0x5efb8a  callvirt instance void Microsoft.SharePoint.SPList::set_EnableMinorVersions(bool value)
0x5efb8f  ldarg.2
0x5efb90  ldstr    aRequestaccesse_3// "RequestAccessEnabled"
0x5efb95  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efb9a  brfalse.s loc_5EFBD7
0x5efb9c  ldarg.1
0x5efb9d  callvirt instance bool Microsoft.SharePoint.SPList::get_RequestAccessEnabled()
0x5efba2  ldarg.2
0x5efba3  ldstr    aRequestaccesse_3// "RequestAccessEnabled"
0x5efba8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efbad  unbox.any [mscorlib]System.Boolean
0x5efbb2  beq.s    loc_5EFBD7
0x5efbb4  ldarg.0
0x5efbb5  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x5efbba  callvirt instance valuetype Microsoft.SharePoint.Deployment.SPIncludeSecurity Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_IncludeSecurity()
0x5efbbf  brfalse.s loc_5EFBD7
0x5efbc1  ldarg.1
0x5efbc2  ldarg.2
0x5efbc3  ldstr    aRequestaccesse_3// "RequestAccessEnabled"
0x5efbc8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efbcd  unbox.any [mscorlib]System.Boolean
0x5efbd2  callvirt instance void Microsoft.SharePoint.SPList::SetRequestAccessOnImport(bool value)
0x5efbd7  ldarg.2
0x5efbd8  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x5efbdd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efbe2  brfalse.s loc_5EFC0E
0x5efbe4  ldarg.1
0x5efbe5  ldtoken  Microsoft.SharePoint.DraftVisibilityType
0x5efbea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5efbef  ldarg.2
0x5efbf0  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x5efbf5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efbfa  castclass [mscorlib]System.String
0x5efbff  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x5efc04  unbox.any Microsoft.SharePoint.DraftVisibilityType
0x5efc09  callvirt instance void Microsoft.SharePoint.SPList::set_DraftVersionVisibility(valuetype Microsoft.SharePoint.DraftVisibilityType value)
0x5efc0e  ldarg.1
0x5efc0f  callvirt instance bool Microsoft.SharePoint.SPList::get_HasExternalDataSource()
0x5efc14  brtrue.s loc_5EFC39
0x5efc16  ldarg.2
0x5efc17  ldstr    aForcecheckout// "ForceCheckout"
0x5efc1c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efc21  brfalse.s loc_5EFC39
0x5efc23  ldarg.1
0x5efc24  ldarg.2
0x5efc25  ldstr    aForcecheckout// "ForceCheckout"
0x5efc2a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efc2f  unbox.any [mscorlib]System.Boolean
0x5efc34  callvirt instance void Microsoft.SharePoint.SPList::set_ForceCheckout(bool value)
0x5efc39  ldarg.2
0x5efc3a  ldstr    aHidden_1// "Hidden"
0x5efc3f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efc44  brfalse.s loc_5EFC5C
0x5efc46  ldarg.1
0x5efc47  ldarg.2
0x5efc48  ldstr    aHidden_1// "Hidden"
0x5efc4d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efc52  unbox.any [mscorlib]System.Boolean
0x5efc57  callvirt instance void Microsoft.SharePoint.SPList::set_Hidden(bool value)
0x5efc5c  ldarg.2
0x5efc5d  ldstr    aOrdered// "Ordered"
0x5efc62  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efc67  brfalse.s loc_5EFC87
0x5efc69  ldarg.1
0x5efc6a  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x5efc6f  brtrue.s loc_5EFC87
0x5efc71  ldarg.1
0x5efc72  ldarg.2
0x5efc73  ldstr    aOrdered// "Ordered"
0x5efc78  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efc7d  unbox.any [mscorlib]System.Boolean
0x5efc82  callvirt instance void Microsoft.SharePoint.SPList::set_Ordered(bool value)
0x5efc87  ldarg.2
0x5efc88  ldstr    aShowuser// "ShowUser"
0x5efc8d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efc92  brfalse.s loc_5EFCAA
0x5efc94  ldarg.1
0x5efc95  ldarg.2
0x5efc96  ldstr    aShowuser// "ShowUser"
0x5efc9b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efca0  unbox.any [mscorlib]System.Boolean
0x5efca5  callvirt instance void Microsoft.SharePoint.SPList::set_ShowUser(bool value)
0x5efcaa  ldarg.2
0x5efcab  ldstr    aEnablepeoplese_0// "EnablePeopleSelector"
0x5efcb0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efcb5  brfalse.s loc_5EFCCD
0x5efcb7  ldarg.1
0x5efcb8  ldarg.2
0x5efcb9  ldstr    aEnablepeoplese_0// "EnablePeopleSelector"
0x5efcbe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efcc3  unbox.any [mscorlib]System.Boolean
0x5efcc8  callvirt instance void Microsoft.SharePoint.SPList::set_EnablePeopleSelector(bool value)
0x5efccd  ldarg.2
0x5efcce  ldstr    aEnableresource_0// "EnableResourceSelector"
0x5efcd3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efcd8  brfalse.s loc_5EFCF0
0x5efcda  ldarg.1
0x5efcdb  ldarg.2
0x5efcdc  ldstr    aEnableresource_0// "EnableResourceSelector"
0x5efce1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efce6  unbox.any [mscorlib]System.Boolean
0x5efceb  callvirt instance void Microsoft.SharePoint.SPList::set_EnableResourceSelector(bool value)
0x5efcf0  ldarg.2
0x5efcf1  ldstr    aNothrottlelist// "NoThrottleListOperations"
0x5efcf6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efcfb  brfalse.s loc_5EFD5D
0x5efcfd  ldarg.1
0x5efcfe  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x5efd03  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x5efd08  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x5efd0d  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x5efd12  callvirt instance bool Microsoft.SharePoint.Administration.SPFarm::CurrentUserIsAdministrator()
0x5efd17  brfalse.s loc_5EFD36
0x5efd19  ldarg.2
0x5efd1a  ldstr    aNothrottlelist// "NoThrottleListOperations"
0x5efd1f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efd24  unbox.any [mscorlib]System.Boolean
0x5efd29  stloc.0
0x5efd2a  ldarg.1
0x5efd2b  ldloc.0
0x5efd2c  ldc.i4.0
0x5efd2d  ceq
0x5efd2f  callvirt instance void Microsoft.SharePoint.SPList::set_EnableThrottling(bool value)
0x5efd34  br.s     loc_5EFD5D
0x5efd36  ldarg.0
0x5efd37  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x5efd3c  callvirt instance class Microsoft.SharePoint.Deployment.DeploymentLogger Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_Logger()
0x5efd41  ldc.i4.3
0x5efd42  ldarg.0
0x5efd43  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x5efd48  ldstr    aCannotsetenabl// "CannotSetEnableThrottle"
0x5efd4d  ldc.i4.0
0x5efd4e  newarr   [mscorlib]System.Object
0x5efd53  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x5efd58  callvirt instance void Microsoft.SharePoint.Deployment.DeploymentLogger::Log(valuetype Microsoft.SharePoint.Deployment.DeploymentLogSeverity severity, class Microsoft.SharePoint.Deployment.SPLoggerObject loggerObject, string message)
0x5efd5d  ldarg.2
0x5efd5e  ldstr    aReadsecurity_0// "ReadSecurity"
0x5efd63  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efd68  brfalse.s loc_5EFD80
0x5efd6a  ldarg.1
0x5efd6b  ldarg.2
0x5efd6c  ldstr    aReadsecurity_0// "ReadSecurity"
0x5efd71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efd76  unbox.any [mscorlib]System.Int32
0x5efd7b  callvirt instance void Microsoft.SharePoint.SPList::set_ReadSecurity(int32 value)
0x5efd80  ldarg.2
0x5efd81  ldstr    aWritesecurity_0// "WriteSecurity"
0x5efd86  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efd8b  brfalse.s loc_5EFDA3
0x5efd8d  ldarg.1
0x5efd8e  ldarg.2
0x5efd8f  ldstr    aWritesecurity_0// "WriteSecurity"
0x5efd94  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efd99  unbox.any [mscorlib]System.Int32
0x5efd9e  callvirt instance void Microsoft.SharePoint.SPList::set_WriteSecurity(int32 value)
0x5efda3  ldarg.1
0x5efda4  callvirt instance bool Microsoft.SharePoint.SPList::get_EnableVersioning()
0x5efda9  brfalse.s loc_5EFDCE
0x5efdab  ldarg.2
0x5efdac  ldstr    aMajorversionli// "MajorVersionLimit"
0x5efdb1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efdb6  brfalse.s loc_5EFDCE
0x5efdb8  ldarg.1
0x5efdb9  ldarg.2
0x5efdba  ldstr    aMajorversionli// "MajorVersionLimit"
0x5efdbf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efdc4  unbox.any [mscorlib]System.Int32
0x5efdc9  callvirt instance void Microsoft.SharePoint.SPList::set_MajorVersionLimit(int32 value)
0x5efdce  ldarg.1
0x5efdcf  callvirt instance bool Microsoft.SharePoint.SPList::get_EnableMinorVersions()
0x5efdd4  brfalse.s loc_5EFDF9
0x5efdd6  ldarg.2
0x5efdd7  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x5efddc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efde1  brfalse.s loc_5EFDF9
0x5efde3  ldarg.1
0x5efde4  ldarg.2
0x5efde5  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x5efdea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efdef  unbox.any [mscorlib]System.Int32
0x5efdf4  callvirt instance void Microsoft.SharePoint.SPList::set_MajorWithMinorVersionsLimit(int32 value)
0x5efdf9  ldarg.2
0x5efdfa  ldstr    aEnablecontentt// "EnableContentTypes"
0x5efdff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5efe04  brfalse.s loc_5EFE1C
0x5efe06  ldarg.1
0x5efe07  ldarg.2
0x5efe08  ldstr    aEnablecontentt// "EnableContentTypes"
0x5efe0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5efe12  unbox.any [mscorlib]System.Boolean
0x5efe17  callvirt instance void Microsoft.SharePoint.SPList::set_ContentTypesEnabled(bool value)
0x5efe1c  ldarg.2
0x5efe1d  ldstr    aNavigateforfor// "NavigateForFormsPages"
0x5efe22  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
  ... truncated ...
```
