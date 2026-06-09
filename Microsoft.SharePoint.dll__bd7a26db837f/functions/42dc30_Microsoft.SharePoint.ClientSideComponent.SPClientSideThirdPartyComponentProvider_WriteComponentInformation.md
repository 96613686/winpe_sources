# Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponentInformation

- ea: `0x42dc30`
- end: `0x42e0e6`
- name: `Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponentInformation`
- size: `1206`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x42d570`

## callees

- `0x1b5530`
- `0x1b57a0`
- `0x26f690`
- `0x3192a0`
- `0x342f00`
- `0x343350`
- `0x3e9a20`
- `0x42cfe0`
- `0x42dc30`
- `0x42e7a0`
- `0x42f350`
- `0x431dc0`
- `0x436b20`
- `0x5076d0`
- `0x53e2d0`
- `0x53e2f0`
- `0x54cf40`
- `0x577070`
- `0x5c24f0`
- `0x6c9890`

## string_xrefs

- `0x42dced`: `featureName`
- `0x42dcfa`: `featureName`
- `0x42de5d`: `Cannot find Client Component Manifest List`
- `0x42dd8f`: `clientComponentName`
- `0x42dd9c`: `clientComponentName`
- `0x42ddce`: `clientComponentId`
- `0x42dddb`: `clientComponentId`
- `0x42de04`: `clientComponentManifest`
- `0x42de11`: `clientComponentManifest`
- `0x42de35`: `previousComponents`
- `0x42de42`: `previousComponents`
- `0x42deb8`: `UpdateComponent`
- `0x42ded3`: `ClientComponentId`
- `0x42dfc6`: `ClientComponentId`
- `0x42df22`: `Kill switch for client side component manifest cache management refactor.`
- `0x42dfab`: `NewComponent`

## pseudocode

```c

```

## disassembly

```asm
0x42dc30  ldarg.1
0x42dc31  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dc36  brfalse.s loc_42DC65
0x42dc38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dc3d  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dc42  ldc.i4.1
0x42dc43  newarr   [mscorlib]System.Object
0x42dc48  stloc.s  7
0x42dc4a  ldloc.s  7
0x42dc4c  ldc.i4.0
0x42dc4d  ldstr    aSolutionname_0// "solutionName"
0x42dc52  stelem.ref
0x42dc53  ldloc.s  7
0x42dc55  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dc5a  ldstr    aSolutionname_0// "solutionName"
0x42dc5f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dc64  throw
0x42dc65  ldarg.2
0x42dc66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dc6b  brfalse.s loc_42DC9A
0x42dc6d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dc72  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dc77  ldc.i4.1
0x42dc78  newarr   [mscorlib]System.Object
0x42dc7d  stloc.s  8
0x42dc7f  ldloc.s  8
0x42dc81  ldc.i4.0
0x42dc82  ldstr    aSolutionid// "solutionId"
0x42dc87  stelem.ref
0x42dc88  ldloc.s  8
0x42dc8a  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dc8f  ldstr    aSolutionid// "solutionId"
0x42dc94  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dc99  throw
0x42dc9a  ldarg.3
0x42dc9b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dca0  brfalse.s loc_42DCCF
0x42dca2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dca7  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dcac  ldc.i4.1
0x42dcad  newarr   [mscorlib]System.Object
0x42dcb2  stloc.s  9
0x42dcb4  ldloc.s  9
0x42dcb6  ldc.i4.0
0x42dcb7  ldstr    aSolutionversio// "solutionVersion"
0x42dcbc  stelem.ref
0x42dcbd  ldloc.s  9
0x42dcbf  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dcc4  ldstr    aSolutionversio// "solutionVersion"
0x42dcc9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dcce  throw
0x42dccf  ldarg.s  4
0x42dcd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dcd6  brfalse.s loc_42DD05
0x42dcd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dcdd  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dce2  ldc.i4.1
0x42dce3  newarr   [mscorlib]System.Object
0x42dce8  stloc.s  0xA
0x42dcea  ldloc.s  0xA
0x42dcec  ldc.i4.0
0x42dced  ldstr    aFeaturename_0// "featureName"
0x42dcf2  stelem.ref
0x42dcf3  ldloc.s  0xA
0x42dcf5  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dcfa  ldstr    aFeaturename_0// "featureName"
0x42dcff  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dd04  throw
0x42dd05  ldarg.s  5
0x42dd07  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dd0c  brfalse.s loc_42DD3B
0x42dd0e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dd13  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dd18  ldc.i4.1
0x42dd19  newarr   [mscorlib]System.Object
0x42dd1e  stloc.s  0xB
0x42dd20  ldloc.s  0xB
0x42dd22  ldc.i4.0
0x42dd23  ldstr    aFeaturedescrip// "featureDescription"
0x42dd28  stelem.ref
0x42dd29  ldloc.s  0xB
0x42dd2b  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dd30  ldstr    aFeaturedescrip// "featureDescription"
0x42dd35  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dd3a  throw
0x42dd3b  ldarg.s  6
0x42dd3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dd42  brfalse.s loc_42DD71
0x42dd44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dd49  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dd4e  ldc.i4.1
0x42dd4f  newarr   [mscorlib]System.Object
0x42dd54  stloc.s  0xC
0x42dd56  ldloc.s  0xC
0x42dd58  ldc.i4.0
0x42dd59  ldstr    aFeatureid_2// "featureId"
0x42dd5e  stelem.ref
0x42dd5f  ldloc.s  0xC
0x42dd61  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dd66  ldstr    aFeatureid_2// "featureId"
0x42dd6b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dd70  throw
0x42dd71  ldarg.s  8
0x42dd73  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dd78  brfalse.s loc_42DDA7
0x42dd7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42dd7f  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42dd84  ldc.i4.1
0x42dd85  newarr   [mscorlib]System.Object
0x42dd8a  stloc.s  0xD
0x42dd8c  ldloc.s  0xD
0x42dd8e  ldc.i4.0
0x42dd8f  ldstr    aClientcomponen// "clientComponentName"
0x42dd94  stelem.ref
0x42dd95  ldloc.s  0xD
0x42dd97  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dd9c  ldstr    aClientcomponen// "clientComponentName"
0x42dda1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dda6  throw
0x42dda7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42ddac  stloc.s  0xE
0x42ddae  ldloca.s 0xE
0x42ddb0  ldarg.s  0xA
0x42ddb2  call     instance int32 [mscorlib]System.Guid::CompareTo(valuetype [mscorlib]System.Guid)
0x42ddb7  brtrue.s loc_42DDE6
0x42ddb9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42ddbe  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42ddc3  ldc.i4.1
0x42ddc4  newarr   [mscorlib]System.Object
0x42ddc9  stloc.s  0xF
0x42ddcb  ldloc.s  0xF
0x42ddcd  ldc.i4.0
0x42ddce  ldstr    aClientcomponen_0// "clientComponentId"
0x42ddd3  stelem.ref
0x42ddd4  ldloc.s  0xF
0x42ddd6  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42dddb  ldstr    aClientcomponen_0// "clientComponentId"
0x42dde0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42dde5  throw
0x42dde6  ldarg.s  0xB
0x42dde8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dded  brfalse.s loc_42DE1C
0x42ddef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42ddf4  ldstr    aStringnullorem// "StringNullOrEmptyMessage"
0x42ddf9  ldc.i4.1
0x42ddfa  newarr   [mscorlib]System.Object
0x42ddff  stloc.s  0x10
0x42de01  ldloc.s  0x10
0x42de03  ldc.i4.0
0x42de04  ldstr    aClientcomponen_1// "clientComponentManifest"
0x42de09  stelem.ref
0x42de0a  ldloc.s  0x10
0x42de0c  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42de11  ldstr    aClientcomponen_1// "clientComponentManifest"
0x42de16  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42de1b  throw
0x42de1c  ldarg.s  0xC
0x42de1e  brtrue.s loc_42DE4D
0x42de20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x42de25  ldstr    aArgumentnullte// "ArgumentNullText"
0x42de2a  ldc.i4.1
0x42de2b  newarr   [mscorlib]System.Object
0x42de30  stloc.s  0x11
0x42de32  ldloc.s  0x11
0x42de34  ldc.i4.0
0x42de35  ldstr    aPreviouscompon// "previousComponents"
0x42de3a  stelem.ref
0x42de3b  ldloc.s  0x11
0x42de3d  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x42de42  ldstr    aPreviouscompon// "previousComponents"
0x42de47  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42de4c  throw
0x42de4d  ldarg.0
0x42de4e  ldarg.0
0x42de4f  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::currentWeb
0x42de54  call     instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::GetComponentList(class Microsoft.SharePoint.SPWeb web)
0x42de59  stloc.0
0x42de5a  ldloc.0
0x42de5b  brtrue.s loc_42DE68
0x42de5d  ldstr    aCannotFindClie// "Cannot find Client Component Manifest L"...
0x42de62  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x42de67  throw
0x42de68  ldc.i4.1
0x42de69  stloc.1
0x42de6a  ldnull
0x42de6b  stloc.2
0x42de6c  ldarg.s  0xC
0x42de6e  callvirt instance int32 Microsoft.SharePoint.SPBaseCollection::get_Count()
0x42de73  ldc.i4.0
0x42de74  ble      loc_42DF0D
0x42de79  ldarg.s  0xC
0x42de7b  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x42de80  stloc.s  0x12
0x42de82  br.s     loc_42DEED
0x42de84  ldloc.s  0x12
0x42de86  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x42de8b  castclass Microsoft.SharePoint.SPListItem
0x42de90  stloc.s  4
0x42de92  ldloc.s  4
0x42de94  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.Constants::ClientComponentIdFieldId
0x42de99  callvirt instance object Microsoft.SharePoint.SPListItem::get_Item(valuetype [mscorlib]System.Guid fieldId)
0x42de9e  callvirt instance string [mscorlib]System.Object::ToString()
0x42dea3  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x42dea8  stloc.3
0x42dea9  ldloc.3
0x42deaa  ldarg.s  0xA
0x42deac  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x42deb1  brfalse.s loc_42DEED
0x42deb3  ldc.i4.0
0x42deb4  stloc.1
0x42deb5  ldloc.s  4
0x42deb7  stloc.2
0x42deb8  ldstr    aUpdatecomponen// "UpdateComponent"
0x42debd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x42dec2  stloc.s  5
0x42dec4  ldloc.s  5
0x42dec6  ldstr    aProductid_0// "ProductId"
0x42decb  ldarg.2
0x42decc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42ded1  ldloc.s  5
0x42ded3  ldstr    aClientcomponen_2// "ClientComponentId"
0x42ded8  ldarg.s  0xA
0x42deda  box      [mscorlib]System.Guid
0x42dedf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42dee4  ldloc.s  5
0x42dee6  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x42deeb  br.s     loc_42DEF6
0x42deed  ldloc.s  0x12
0x42deef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x42def4  brtrue.s loc_42DE84
0x42def6  leave.s  loc_42DF0D
0x42def8  ldloc.s  0x12
0x42defa  isinst   [mscorlib]System.IDisposable
0x42deff  stloc.s  0x13
0x42df01  ldloc.s  0x13
0x42df03  brfalse.s loc_42DF0C
0x42df05  ldloc.s  0x13
0x42df07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42df0c  endfinally
0x42df0d  ldloc.1
0x42df0e  brfalse.s loc_42DF18
0x42df10  ldarg.0
0x42df11  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::get_IsSiteCollectionScoped()
0x42df16  brfalse.s loc_42DF5F
0x42df18  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideFrameworkFlights::ClientSideManifestCacheManagementRefactorKillSwitch
0x42df1d  ldstr    a10252017// "10/25/2017"
0x42df22  ldstr    aKillSwitchForC// "Kill switch for client side component m"...
0x42df27  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x42df2c  brtrue.s loc_42DF4A
0x42df2e  call     class Microsoft.SharePoint.ClientSideComponent.IClientSideManifestCacheManager Microsoft.SharePoint.ClientSideComponent.SPClientSideManifestCacheManager::get_Instance()
0x42df33  ldarg.0
0x42df34  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::currentWeb
0x42df39  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x42df3e  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x42df43  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSideManifestCacheManager::ExpireManifestCache(class Microsoft.SharePoint.SPSiteSubscription subscription)
0x42df48  br.s     loc_42DF5F
0x42df4a  ldarg.0
0x42df4b  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::currentWeb
0x42df50  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x42df55  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x42df5a  call     void Microsoft.SharePoint.ClientSideComponent.SPClientSideCachedThirdPartyComponentProvider::UpdateTenantComponentUpdatedTime(class Microsoft.SharePoint.SPSiteSubscription subscription)
0x42df5f  ldloc.1
0x42df60  brfalse.s loc_42DFDE
0x42df62  ldloc.0
0x42df63  callvirt instance class Microsoft.SharePoint.SPListItemCollection Microsoft.SharePoint.SPList::get_Items()
0x42df68  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::Add()
0x42df6d  stloc.2
0x42df6e  ldloc.2
0x42df6f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.Constants::SolutionIdFieldId
0x42df74  ldarg.2
0x42df75  callvirt instance void Microsoft.SharePoint.SPListItem::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x42df7a  ldloc.2
0x42df7b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.Constants::FeatureIdFieldId
0x42df80  ldarg.s  6
0x42df82  callvirt instance void Microsoft.SharePoint.SPListItem::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x42df87  ldloc.2
0x42df88  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.Constants::ClientComponentIdFieldId
0x42df8d  ldarg.s  0xA
0x42df8f  box      [mscorlib]System.Guid
0x42df94  callvirt instance void Microsoft.SharePoint.SPListItem::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x42df99  ldloc.2
0x42df9a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.Constants::FeatureScopeFieldId
0x42df9f  ldarg.s  7
0x42dfa1  box      [mscorlib]System.Int32
0x42dfa6  callvirt instance void Microsoft.SharePoint.SPListItem::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x42dfab  ldstr    aNewcomponent// "NewComponent"
0x42dfb0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x42dfb5  stloc.s  6
0x42dfb7  ldloc.s  6
0x42dfb9  ldstr    aProductid_0// "ProductId"
0x42dfbe  ldarg.2
0x42dfbf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42dfc4  ldloc.s  6
0x42dfc6  ldstr    aClientcomponen_2// "ClientComponentId"
0x42dfcb  ldarg.s  0xA
0x42dfcd  box      [mscorlib]System.Guid
0x42dfd2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42dfd7  ldloc.s  6
0x42dfd9  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x42dfde  ldloc.2
  ... truncated ...
```
