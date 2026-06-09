# Microsoft.VisualStudio.Setup.WorkPrimaryProcess::RecordUpdateInformation

- ea: `0x2fc0`
- end: `0x34bf`
- name: `Microsoft.VisualStudio.Setup.WorkPrimaryProcess::RecordUpdateInformation`
- size: `1279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5f80`

## callees

- `0x2fc0`
- `0x34c0`
- `0x34e0`
- `0x5c10`

## string_xrefs

- `0x305e`: `Unable to get channel manifest for `
- `0x3155`: `The cache manifest and downloaded manifest had the same version for instance: `
- `0x315c`: `. Did not compute update information.`
- `0x331e`: `No update found for instance: `
- `0x335a`: `Failed to get channel product for instance. Falling back to using instance for update properties.`
- `0x349c`: `accountProfileService.UpdateUserProfile failed`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x2fc5  stloc.0
0x2fc6  ldloc.0
0x2fc7  ldarg.s  6
0x2fc9  stfld    string <>c__DisplayClass2_0::singleInstanceId
0x2fce  ldarg.1
0x2fcf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetAllInstances()
0x2fd4  stloc.1
0x2fd5  ldloc.0
0x2fd6  ldfld    string <>c__DisplayClass2_0::singleInstanceId
0x2fdb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fe0  brtrue.s loc_2FF5
0x2fe2  ldloc.1
0x2fe3  ldloc.0
0x2fe4  ldftn    instance bool <>c__DisplayClass2_0::<RecordUpdateInformation>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance i)
0x2fea  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool>::.ctor(object, native int)
0x2fef  call     T0x2B00000B
0x2ff4  stloc.1
0x2ff5  ldloc.1
0x2ff6  brfalse  loc_34BE
0x2ffb  ldloc.1
0x2ffc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetEnumerator()
0x3001  stloc.2
0x3002  br       loc_34A7
0x3007  ldloc.2
0x3008  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::get_Current()
0x300d  stloc.3
0x300e  ldnull
0x300f  stloc.s  4
0x3011  ldloc.3
0x3012  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x3017  stloc.s  5
0x3019  ldloc.3
0x301a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_CatalogInfo()
0x301f  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_BuildVersion()
0x3024  pop
0x3025  ldarg.2
0x3026  ldloc.3
0x3027  ldc.i4.0
0x3028  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::GetChannelForInstance(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool)
0x302d  stloc.s  6
0x302f  ldloc.s  6
0x3031  brtrue.s loc_3036
0x3033  ldnull
0x3034  br.s     loc_303D
0x3036  ldloc.s  6
0x3038  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x303d  dup
0x303e  brtrue.s loc_304F
0x3040  pop
0x3041  ldloc.s  6
0x3043  brtrue.s loc_3048
0x3045  ldnull
0x3046  br.s     loc_304F
0x3048  ldloc.s  6
0x304a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x304f  stloc.s  7
0x3051  ldloc.s  7
0x3053  brtrue.s loc_3079
0x3055  ldarg.s  4
0x3057  brfalse  loc_34A7
0x305c  ldarg.s  4
0x305e  ldstr    aUnableToGetCha// "Unable to get channel manifest for "
0x3063  ldloc.s  5
0x3065  call     string [mscorlib]System.String::Concat(string, string)
0x306a  call     T0x2B00000A
0x306f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x3074  br       loc_34A7
0x3079  ldloc.s  6
0x307b  brtrue.s loc_3080
0x307d  ldnull
0x307e  br.s     loc_3093
0x3080  ldloc.s  6
0x3082  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x3087  dup
0x3088  brtrue.s loc_308E
0x308a  pop
0x308b  ldnull
0x308c  br.s     loc_3093
0x308e  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x3093  stloc.s  8
0x3095  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x309a  dup
0x309b  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastSuccessfulCheckUTC
0x30a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x30a5  stloc.s  0xA
0x30a7  ldloca.s 0xA
0x30a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30ae  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x30b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x30b8  dup
0x30b9  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::HasUpdate
0x30be  ldc.i4.0
0x30bf  stloc.s  0xB
0x30c1  ldloca.s 0xB
0x30c3  call     instance string [mscorlib]System.Boolean::ToString()
0x30c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x30cd  dup
0x30ce  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UserPropertyNames::InstallChannelUriProperty
0x30d3  ldloc.s  8
0x30d5  brtrue.s loc_30DA
0x30d7  ldnull
0x30d8  br.s     loc_30E1
0x30da  ldloc.s  8
0x30dc  callvirt instance string [mscorlib]System.Object::ToString()
0x30e1  dup
0x30e2  brtrue.s loc_30EA
0x30e4  pop
0x30e5  ldsfld   string [mscorlib]System.String::Empty
0x30ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x30ef  stloc.s  4
0x30f1  ldarg.0
0x30f2  ldloc.3
0x30f3  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GetCacheChannelManifestVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance currentInstance)
0x30f8  ldloc.s  7
0x30fa  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x30ff  stloc.s  9
0x3101  ldloc.s  9
0x3103  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x3108  brfalse.s loc_3175
0x310a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x310f  dup
0x3110  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastSuccessfulCheckUTC
0x3115  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x311a  stloc.s  0xA
0x311c  ldloca.s 0xA
0x311e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3123  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x3128  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x312d  dup
0x312e  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::HasUpdate
0x3133  ldarg.1
0x3134  ldloc.3
0x3135  ldnull
0x3136  ldc.i4.0
0x3137  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::IsUpdateAvailable(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed, bool)
0x313c  stloc.s  0xB
0x313e  ldloca.s 0xB
0x3140  call     instance string [mscorlib]System.Boolean::ToString()
0x3145  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x314a  stloc.s  4
0x314c  ldarg.s  4
0x314e  brfalse  loc_3490
0x3153  ldarg.s  4
0x3155  ldstr    aTheCacheManife// "The cache manifest and downloaded manif"...
0x315a  ldloc.s  5
0x315c  ldstr    aDidNotComputeU// ". Did not compute update information."
0x3161  call     string [mscorlib]System.String::Concat(string, string, string)
0x3166  call     T0x2B00000A
0x316b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x3170  br       loc_3490
0x3175  ldarg.1
0x3176  ldloc.s  5
0x3178  ldnull
0x3179  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetUpdateInformation(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed)
0x317e  stloc.s  0xC
0x3180  ldloc.s  0xC
0x3182  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation::get_IsUpdateAvailable()
0x3187  brfalse  loc_3318
0x318c  ldloc.s  0xC
0x318e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation::get_UpdatedPackages()
0x3193  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__2_1
0x3198  dup
0x3199  brtrue.s loc_31B2
0x319b  pop
0x319c  ldsfld   class <>c <>c::<>9
0x31a1  ldftn    instance bool <>c::<RecordUpdateInformation>b__2_1(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package)
0x31a7  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x31ac  dup
0x31ad  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__2_1
0x31b2  call     T0x2B00003F
0x31b7  call     T0x2B000040
0x31bc  stloc.s  0xD
0x31be  ldloc.s  0xD
0x31c0  brtrue.s loc_31E6
0x31c2  ldarg.s  4
0x31c4  brfalse  loc_34A7
0x31c9  ldarg.s  4
0x31cb  ldstr    aUnableToGetPro// "Unable to get product for "
0x31d0  ldloc.s  5
0x31d2  call     string [mscorlib]System.String::Concat(string, string)
0x31d7  call     T0x2B00000A
0x31dc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x31e1  br       loc_34A7
0x31e6  ldloc.s  0xD
0x31e8  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x31ed  stloc.s  0xE
0x31ef  ldloc.s  0xD
0x31f1  castclass [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product
0x31f6  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product::get_ReleaseNotes()
0x31fb  stloc.s  0xF
0x31fd  ldarg.0
0x31fe  ldloc.s  0xC
0x3200  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation::get_AdvertisedPackages()
0x3205  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackage> Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GetAdvertisedPackageInfo(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> advertisedPackages)
0x320a  stloc.s  0x10
0x320c  ldloc.s  0x10
0x320e  call     T0x2B000041
0x3213  brtrue.s loc_321C
0x3215  ldsfld   string [mscorlib]System.String::Empty
0x321a  br.s     loc_3223
0x321c  ldloc.s  0x10
0x321e  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x3223  stloc.s  0x11
0x3225  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x322a  dup
0x322b  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadTotalSize
0x3230  ldloc.s  0xC
0x3232  callvirt instance int64 [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation::get_DownloadSize()
0x3237  stloc.s  0x12
0x3239  ldloca.s 0x12
0x323b  call     instance string [mscorlib]System.Int64::ToString()
0x3240  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3245  dup
0x3246  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductDisplayVersion
0x324b  ldloc.s  7
0x324d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest::get_Info()
0x3252  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_ProductDisplayVersion()
0x3257  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x325c  dup
0x325d  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelManifestBuildVersion
0x3262  ldloc.s  7
0x3264  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x3269  callvirt instance string [mscorlib]System.Object::ToString()
0x326e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3273  dup
0x3274  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastSuccessfulCheckUTC
0x3279  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x327e  stloc.s  0xA
0x3280  ldloca.s 0xA
0x3282  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3287  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x328c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3291  dup
0x3292  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelProductVersion
0x3297  ldloc.s  0xE
0x3299  callvirt instance string [mscorlib]System.Object::ToString()
0x329e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32a3  dup
0x32a4  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelReleasenoteUrl
0x32a9  ldloc.s  0xF
0x32ab  callvirt instance string [mscorlib]System.Object::ToString()
0x32b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32b5  dup
0x32b6  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::AdvertisedPackages
0x32bb  ldloc.s  0x11
0x32bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32c2  dup
0x32c3  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateRequiresInstallerUpdate
0x32c8  ldarga.s 5
0x32ca  call     instance string [mscorlib]System.Boolean::ToString()
0x32cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32d4  dup
0x32d5  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::HasUpdate
0x32da  ldloc.s  0xC
0x32dc  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IUpdateInformation::get_IsUpdateAvailable()
0x32e1  stloc.s  0xB
0x32e3  ldloca.s 0xB
0x32e5  call     instance string [mscorlib]System.Boolean::ToString()
0x32ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32ef  dup
0x32f0  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UserPropertyNames::InstallChannelUriProperty
0x32f5  ldloc.s  8
0x32f7  brtrue.s loc_32FC
0x32f9  ldnull
0x32fa  br.s     loc_3303
0x32fc  ldloc.s  8
0x32fe  callvirt instance string [mscorlib]System.Object::ToString()
0x3303  dup
0x3304  brtrue.s loc_330C
0x3306  pop
0x3307  ldsfld   string [mscorlib]System.String::Empty
0x330c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3311  stloc.s  4
0x3313  br       loc_3490
0x3318  ldarg.s  4
0x331a  brfalse.s loc_3339
0x331c  ldarg.s  4
0x331e  ldstr    aNoUpdateFoundF// "No update found for instance: "
0x3323  ldloc.s  5
0x3325  ldstr    aResettingPrope// ". Resetting properties."
0x332a  call     string [mscorlib]System.String::Concat(string, string, string)
0x332f  call     T0x2B00000A
0x3334  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x3339  ldnull
0x333a  stloc.s  0x13
0x333c  ldarg.2
0x333d  ldloc.3
0x333e  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::GetChannelProductForInstance(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance)
0x3343  dup
0x3344  brtrue.s loc_334A
0x3346  pop
0x3347  ldnull
0x3348  br.s     loc_334F
0x334a  call     instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>::get_Item()
0x334f  stloc.s  0x13
0x3351  leave.s  loc_336B
0x3353  pop
0x3354  ldarg.s  4
0x3356  brfalse.s loc_3369
  ... truncated ...
```
