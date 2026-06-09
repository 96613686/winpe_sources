# Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponents_1

- ea: `0x42d570`
- end: `0x42dac0`
- name: `Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponents_1`
- size: `1360`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x42d490`
- `0x42d560`

## callees

- `0x3192a0`
- `0x42ce40`
- `0x42ce60`
- `0x42d570`
- `0x42dac0`
- `0x42dc30`
- `0x42e700`
- `0x42e730`
- `0x42e7e0`
- `0x42e890`
- `0x42e8d0`
- `0x42e8e0`
- `0x434df0`
- `0x434e10`
- `0x434e30`
- `0x434e50`
- `0x434eb0`
- `0x434ee0`
- `0x436900`
- `0x436920`
- `0x436940`
- `0x436960`
- `0x4369a0`
- `0x6c9890`
- `0x6f96e0`
- `0x6f9780`
- `0x6f9880`
- `0x6f9900`
- `0x6fc310`
- `0x6fc470`
- `0x70c240`
- `0x93dab0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x42d5c4`: `http://schemas.microsoft.com/sharepoint/2012/app/relationships/manifest-feature`
- `0x42d5da`: `Ensure that packages can only be uploaded once for client side solutions`
- `0x42d6bc`: `WriteComponents`
- `0x42d7ed`: `WriteComponents`
- `0x42d925`: `WriteComponents`
- `0x42d6d7`: `NumberComponents`
- `0x42d808`: `NumberComponents`
- `0x42d940`: `NumberComponents`
- `0x42d8d1`: `Kill switch for the turn on the client side asset upload to app catalog.`
- `0x42d8e1`: `http://schemas.microsoft.com/sharepoint/2012/app/relationships/manifest-clientsideasset`
- `0x42d8f7`: `Kill switch logging client side asset info`
- `0x42d90d`: `Add client side asset kill switch.`
- `0x42d953`: `ClientSideAssets`
- `0x42d97e`: `Entering deployment of client side assets.  Will deploy {0} client side assets.`
- `0x42da5e`: `Wrote {0} client side assets`
- `0x42da8f`: `Client side assets library not found`

## pseudocode

```c

```

## disassembly

```asm
0x42d570  ldarg.1
0x42d571  brtrue.s loc_42D57E
0x42d573  ldstr    aPackage_0// "package"
0x42d578  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42d57d  throw
0x42d57e  ldarg.1
0x42d57f  callvirt instance class Microsoft.SharePoint.Packaging.SPAppManifest Microsoft.SharePoint.Packaging.SPAppPackage::get_AppManifest()
0x42d584  callvirt instance bool Microsoft.SharePoint.Packaging.SPAppManifest::get_IsClientSideSolution()
0x42d589  brtrue.s loc_42D58C
0x42d58b  ret
0x42d58c  ldarg.1
0x42d58d  callvirt instance class Microsoft.SharePoint.Packaging.SPAppManifest Microsoft.SharePoint.Packaging.SPAppPackage::get_AppManifest()
0x42d592  stloc.0
0x42d593  ldloc.0
0x42d594  callvirt instance string Microsoft.SharePoint.Packaging.SPAppManifest::get_Name()
0x42d599  stloc.1
0x42d59a  ldloc.0
0x42d59b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Packaging.SPAppManifest::get_ProductID()
0x42d5a0  stloc.s  0x1F
0x42d5a2  ldloca.s 0x1F
0x42d5a4  constrained. [mscorlib]System.Guid
0x42d5aa  callvirt instance string [mscorlib]System.Object::ToString()
0x42d5af  stloc.2
0x42d5b0  ldloc.0
0x42d5b1  callvirt instance class [mscorlib]System.Version Microsoft.SharePoint.Packaging.SPAppManifest::get_Version()
0x42d5b6  callvirt instance string [mscorlib]System.Object::ToString()
0x42d5bb  stloc.3
0x42d5bc  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x42d5c1  stloc.s  4
0x42d5c3  ldarg.1
0x42d5c4  ldstr    aHttpSchemasMic_22// "http://schemas.microsoft.com/sharepoint"...
0x42d5c9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Packaging.SPAppPart> Microsoft.SharePoint.Packaging.SPAppPackage::GetAppParts(string manifestRelationshipType)
0x42d5ce  stloc.s  5
0x42d5d0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideFrameworkFlights::EnforceUniquePackagesKillSwitch
0x42d5d5  ldstr    a6292017// "6/29/2017"
0x42d5da  ldstr    aEnsureThatPack// "Ensure that packages can only be upload"...
0x42d5df  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x42d5e4  brtrue   loc_42D7AA
0x42d5e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata>::.ctor()
0x42d5ee  pop
0x42d5ef  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>::.ctor()
0x42d5f4  stloc.s  7
0x42d5f6  ldloc.s  5
0x42d5f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Packaging.SPAppPart>::GetEnumerator()
0x42d5fd  stloc.s  0x20
0x42d5ff  br.s     loc_42D679
0x42d601  ldloc.s  0x20
0x42d603  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Packaging.SPAppPart>::get_Current()
0x42d608  castclass Microsoft.SharePoint.Packaging.SPFeatureAppPart
0x42d60d  stloc.s  8
0x42d60f  ldarg.0
0x42d610  call     instance class Microsoft.SharePoint.ClientSideComponent.IFeatureMetadataBuilder Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::get_FeatureMetadataBuilder()
0x42d615  ldloc.s  8
0x42d617  callvirt instance class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata Microsoft.SharePoint.ClientSideComponent.IFeatureMetadataBuilder::BuildFromAppPart(class Microsoft.SharePoint.Packaging.SPAppPart feature)
0x42d61c  stloc.s  9
0x42d61e  ldarg.0
0x42d61f  call     instance class Microsoft.SharePoint.ClientSideComponent.IClientSideComponentMetadataExtractorInternal Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::get_ClientSideComponentMetadataExtractor()
0x42d624  ldloc.s  8
0x42d626  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata> Microsoft.SharePoint.ClientSideComponent.IClientSideComponentMetadataExtractorInternal::ExtractComponents(class Microsoft.SharePoint.Packaging.SPFeatureAppPart feature)
0x42d62b  stloc.s  0xA
0x42d62d  ldloc.s  7
0x42d62f  ldloc.s  9
0x42d631  ldloc.s  0xA
0x42d633  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::.ctor(var<u1>, !!T0)
0x42d638  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>::Add(var<u1>)
0x42d63d  ldloc.s  0xA
0x42d63f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::GetEnumerator()
0x42d644  stloc.s  0x21
0x42d646  br.s     loc_42D660
0x42d648  ldloca.s 0x21
0x42d64a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::get_Current()
0x42d64f  stloc.s  0xB
0x42d651  ldloc.s  4
0x42d653  ldloc.s  0xB
0x42d655  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Id()
0x42d65a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x42d65f  pop
0x42d660  ldloca.s 0x21
0x42d662  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::MoveNext()
0x42d667  brtrue.s loc_42D648
0x42d669  leave.s  loc_42D679
0x42d66b  ldloca.s 0x21
0x42d66d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>
0x42d673  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d678  endfinally
0x42d679  ldloc.s  0x20
0x42d67b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x42d680  brtrue   loc_42D601
0x42d685  leave.s  loc_42D693
0x42d687  ldloc.s  0x20
0x42d689  brfalse.s loc_42D692
0x42d68b  ldloc.s  0x20
0x42d68d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d692  endfinally
0x42d693  ldarg.0
0x42d694  ldloc.s  4
0x42d696  ldloc.2
0x42d697  call     instance void Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::EnsureComponentsDoNotExistInOtherPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> componentIds, string solutionId)
0x42d69c  ldarg.0
0x42d69d  ldloc.2
0x42d69e  call     instance class Microsoft.SharePoint.SPListItemCollection Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::GetComponentsOfSolution(string solutionId)
0x42d6a3  stloc.s  6
0x42d6a5  ldloc.s  7
0x42d6a7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>::GetEnumerator()
0x42d6ac  stloc.s  0x22
0x42d6ae  br       loc_42D78B
0x42d6b3  ldloca.s 0x22
0x42d6b5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>::get_Current()
0x42d6ba  stloc.s  0xC
0x42d6bc  ldstr    aWritecomponent_0// "WriteComponents"
0x42d6c1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x42d6c6  stloc.s  0xE
0x42d6c8  ldloc.s  0xE
0x42d6ca  ldstr    aProductid_0// "ProductId"
0x42d6cf  ldloc.2
0x42d6d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42d6d5  ldloc.s  0xE
0x42d6d7  ldstr    aNumbercomponen// "NumberComponents"
0x42d6dc  ldloca.s 0xC
0x42d6de  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Value()
0x42d6e3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::get_Count()
0x42d6e8  box      [mscorlib]System.Int32
0x42d6ed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42d6f2  ldloc.s  0xE
0x42d6f4  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x42d6f9  ldloca.s 0xC
0x42d6fb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Value()
0x42d700  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::GetEnumerator()
0x42d705  stloc.s  0x23
0x42d707  br.s     loc_42D772
0x42d709  ldloca.s 0x23
0x42d70b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::get_Current()
0x42d710  stloc.s  0xD
0x42d712  ldarg.0
0x42d713  ldloc.1
0x42d714  ldloc.2
0x42d715  ldloc.3
0x42d716  ldloca.s 0xC
0x42d718  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Key()
0x42d71d  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Name()
0x42d722  ldloca.s 0xC
0x42d724  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Key()
0x42d729  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Description()
0x42d72e  ldloca.s 0xC
0x42d730  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Key()
0x42d735  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Id()
0x42d73a  ldloca.s 0xC
0x42d73c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>::get_Key()
0x42d741  callvirt instance valuetype Microsoft.SharePoint.SPFeatureScope Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Scope()
0x42d746  ldloc.s  0xD
0x42d748  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Name()
0x42d74d  ldloc.s  0xD
0x42d74f  callvirt instance valuetype Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Type()
0x42d754  ldloc.s  0xD
0x42d756  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Id()
0x42d75b  ldloc.s  0xD
0x42d75d  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Manifest()
0x42d762  ldloc.s  6
0x42d764  ldarg.2
0x42d765  ldloc.s  0xD
0x42d767  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_ReturnIfCustomScriptDisabled()
0x42d76c  ldarg.3
0x42d76d  call     instance void Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponentInformation(string solutionName, string solutionId, string solutionVersion, string featureName, string featureDescription, string featureId, valuetype Microsoft.SharePoint.SPFeatureScope featureScope, string clientComponentName, valuetype Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType clientComponentType, valuetype [mscorlib]System.Guid clientComponentId, string clientComponentManifest, class Microsoft.SharePoint.SPListItemCollection previousComponents, bool isEnabled, bool returnIfCustomScriptDisabled, bool skipFeatureDeployment)
0x42d772  ldloca.s 0x23
0x42d774  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::MoveNext()
0x42d779  brtrue.s loc_42D709
0x42d77b  leave.s  loc_42D78B
0x42d77d  ldloca.s 0x23
0x42d77f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>
0x42d785  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d78a  endfinally
0x42d78b  ldloca.s 0x22
0x42d78d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>::MoveNext()
0x42d792  brtrue   loc_42D6B3
0x42d797  leave    loc_42D8C7
0x42d79c  ldloca.s 0x22
0x42d79e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>>>
0x42d7a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d7a9  endfinally
0x42d7aa  ldarg.0
0x42d7ab  ldloc.2
0x42d7ac  call     instance class Microsoft.SharePoint.SPListItemCollection Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::GetComponentsOfSolution(string solutionId)
0x42d7b1  stloc.s  6
0x42d7b3  ldloc.s  5
0x42d7b5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Packaging.SPAppPart>::GetEnumerator()
0x42d7ba  stloc.s  0x24
0x42d7bc  br       loc_42D8AD
0x42d7c1  ldloc.s  0x24
0x42d7c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Packaging.SPAppPart>::get_Current()
0x42d7c8  castclass Microsoft.SharePoint.Packaging.SPFeatureAppPart
0x42d7cd  stloc.s  0xF
0x42d7cf  ldarg.0
0x42d7d0  call     instance class Microsoft.SharePoint.ClientSideComponent.IFeatureMetadataBuilder Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::get_FeatureMetadataBuilder()
0x42d7d5  ldloc.s  0xF
0x42d7d7  callvirt instance class Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata Microsoft.SharePoint.ClientSideComponent.IFeatureMetadataBuilder::BuildFromAppPart(class Microsoft.SharePoint.Packaging.SPAppPart feature)
0x42d7dc  stloc.s  0x10
0x42d7de  ldarg.0
0x42d7df  call     instance class Microsoft.SharePoint.ClientSideComponent.IClientSideComponentMetadataExtractorInternal Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::get_ClientSideComponentMetadataExtractor()
0x42d7e4  ldloc.s  0xF
0x42d7e6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata> Microsoft.SharePoint.ClientSideComponent.IClientSideComponentMetadataExtractorInternal::ExtractComponents(class Microsoft.SharePoint.Packaging.SPFeatureAppPart feature)
0x42d7eb  stloc.s  0x11
0x42d7ed  ldstr    aWritecomponent_0// "WriteComponents"
0x42d7f2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x42d7f7  stloc.s  0x13
0x42d7f9  ldloc.s  0x13
0x42d7fb  ldstr    aProductid_0// "ProductId"
0x42d800  ldloc.2
0x42d801  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42d806  ldloc.s  0x13
0x42d808  ldstr    aNumbercomponen// "NumberComponents"
0x42d80d  ldloc.s  0x11
0x42d80f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::get_Count()
0x42d814  box      [mscorlib]System.Int32
0x42d819  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x42d81e  ldloc.s  0x13
0x42d820  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x42d825  ldloc.s  0x11
0x42d827  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::GetEnumerator()
0x42d82c  stloc.s  0x25
0x42d82e  br.s     loc_42D894
0x42d830  ldloca.s 0x25
0x42d832  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::get_Current()
0x42d837  stloc.s  0x12
0x42d839  ldloc.s  4
0x42d83b  ldloc.s  0x12
0x42d83d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Id()
0x42d842  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x42d847  pop
0x42d848  ldarg.0
0x42d849  ldloc.1
0x42d84a  ldloc.2
0x42d84b  ldloc.3
0x42d84c  ldloc.s  0x10
0x42d84e  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Name()
0x42d853  ldloc.s  0x10
0x42d855  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Description()
0x42d85a  ldloc.s  0x10
0x42d85c  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Id()
0x42d861  ldloc.s  0x10
0x42d863  callvirt instance valuetype Microsoft.SharePoint.SPFeatureScope Microsoft.SharePoint.ClientSideComponent.SPFeatureMetadata::get_Scope()
0x42d868  ldloc.s  0x12
0x42d86a  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Name()
0x42d86f  ldloc.s  0x12
0x42d871  callvirt instance valuetype Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Type()
0x42d876  ldloc.s  0x12
0x42d878  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Id()
0x42d87d  ldloc.s  0x12
0x42d87f  callvirt instance string Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_Manifest()
0x42d884  ldloc.s  6
0x42d886  ldarg.2
0x42d887  ldloc.s  0x12
0x42d889  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata::get_ReturnIfCustomScriptDisabled()
0x42d88e  ldarg.3
0x42d88f  call     instance void Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::WriteComponentInformation(string solutionName, string solutionId, string solutionVersion, string featureName, string featureDescription, string featureId, valuetype Microsoft.SharePoint.SPFeatureScope featureScope, string clientComponentName, valuetype Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType clientComponentType, valuetype [mscorlib]System.Guid clientComponentId, string clientComponentManifest, class Microsoft.SharePoint.SPListItemCollection previousComponents, bool isEnabled, bool returnIfCustomScriptDisabled, bool skipFeatureDeployment)
0x42d894  ldloca.s 0x25
0x42d896  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>::MoveNext()
0x42d89b  brtrue.s loc_42D830
0x42d89d  leave.s  loc_42D8AD
0x42d89f  ldloca.s 0x25
0x42d8a1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentMetadata>
0x42d8a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d8ac  endfinally
0x42d8ad  ldloc.s  0x24
0x42d8af  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x42d8b4  brtrue   loc_42D7C1
0x42d8b9  leave.s  loc_42D8C7
0x42d8bb  ldloc.s  0x24
0x42d8bd  brfalse.s loc_42D8C6
0x42d8bf  ldloc.s  0x24
0x42d8c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42d8c6  endfinally
0x42d8c7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideFrameworkFlights::ClientSideAssetUploadKillSwitch
0x42d8cc  ldstr    a982017// "9/8/2017"
0x42d8d1  ldstr    aKillSwitchForT_0// "Kill switch for the turn on the client "...
0x42d8d6  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x42d8db  brtrue   loc_42DAB5
0x42d8e0  ldarg.1
0x42d8e1  ldstr    aHttpSchemasMic_23// "http://schemas.microsoft.com/sharepoint"...
0x42d8e6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Packaging.SPAppPart> Microsoft.SharePoint.Packaging.SPAppPackage::GetAppParts(string manifestRelationshipType)
0x42d8eb  stloc.s  0x14
0x42d8ed  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::ClientSideAssetsLoggingKillSwitch
0x42d8f2  ldstr    a392018// "3/9/2018"
0x42d8f7  ldstr    aKillSwitchLogg// "Kill switch logging client side asset i"...
0x42d8fc  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x42d901  stloc.s  0x15
0x42d903  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::AddAssetPackagingEngagementLogKillSwitch
0x42d908  ldstr    a11132017// "11/13/2017"
0x42d90d  ldstr    aAddClientSideA// "Add client side asset kill switch."
0x42d912  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x42d917  brtrue   loc_42D99D
0x42d91c  ldloc.s  0x14
0x42d91e  call     T0x2B000361
0x42d923  stloc.s  0x16
0x42d925  ldstr    aWritecomponent_0// "WriteComponents"
0x42d92a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x42d92f  stloc.s  0x17
0x42d931  ldloc.s  0x17
0x42d933  ldstr    aProductid_0// "ProductId"
0x42d938  ldloc.2
0x42d939  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
  ... truncated ...
```
