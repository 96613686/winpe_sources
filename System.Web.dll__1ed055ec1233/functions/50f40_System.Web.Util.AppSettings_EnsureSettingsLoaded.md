# System.Web.Util.AppSettings::EnsureSettingsLoaded

- ea: `0x50f40`
- end: `0x5166e`
- name: `System.Web.Util.AppSettings::EnsureSettingsLoaded`
- size: `1838`
- prototype: ``
- caller_count: `48`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x51710`
- `0x51720`
- `0x51730`
- `0x51740`
- `0x51750`
- `0x51760`
- `0x51770`
- `0x51780`
- `0x51790`
- `0x517a0`
- `0x517b0`
- `0x517c0`
- `0x517d0`
- `0x517e0`
- `0x517f0`
- `0x51800`
- `0x51810`
- `0x51820`
- `0x51830`
- `0x51840`
- `0x51850`
- `0x51860`
- `0x51870`
- `0x51880`
- `0x51890`
- `0x518a0`
- `0x518b0`
- `0x518c0`
- `0x518d0`
- `0x518e0`
- `0x518f0`
- `0x51900`
- `0x51910`
- `0x51920`
- `0x51930`
- `0x51940`
- `0x51950`
- `0x51960`
- `0x51970`
- `0x51980`
- `0x51990`
- `0x519a0`
- `0x519b0`
- `0x519c0`
- `0x519d0`
- `0x519e0`
- `0x519f0`
- `0x51a00`

## callees

- `0x4ee60`
- `0x4eea0`
- `0x4eec0`
- `0x4ef00`
- `0x4ef40`
- `0x50f40`
- `0x51670`
- `0x516b0`
- `0x516e0`
- `0x130a40`
- `0x130e90`
- `0x142830`
- `0x156580`
- `0x156680`
- `0x1566c0`
- `0x1569e0`
- `0x156b70`
- `0x157780`

## string_xrefs

- `0x50f99`: `aspnet:AllowAnonymousImpersonation`
- `0x51019`: `aspnet:UseLegacyFormsAuthenticationTicketCompatibility`
- `0x51039`: `aspnet:UseLegacyEventValidationCompatibility`
- `0x510c9`: `aspnet:UseTaskFriendlySynchronizationContext`
- `0x510f8`: `aspnet:AllowAsyncDuringSyncStages`
- `0x51144`: `aspnet:MaxJsonDeserializerMembers`
- `0x511a3`: `aspnet:RestrictXmlControls`
- `0x5126c`: `aspnet:UpdatePanelMaxScriptLength`
- `0x51291`: `aspnet:MaxConcurrentCompilations`
- `0x512cc`: `aspnet:PortableCompilationOutput`
- `0x512ec`: `aspnet:PortableCompilationOutputSnapshotType`
- `0x5130d`: `aspnet:PortableCompilationOutputSnapshotTypeOptions`
- `0x51433`: `aspnet:UseLegacyClientServicesJsonHandling`
- `0x514bf`: `aspnet:VerifyVirtualPathFromDiskCache`
- `0x514ff`: `aspnet:DisableAppPathModifier`
- `0x515dc`: `aspnet:RestoreAggressiveCookielessPathRemoval`
- `0x515fc`: `aspnet:JsonDeserializerLimitedDate`
- `0x5163c`: `aspnet:UseLegacyCacheKeyHash`

## pseudocode

```c

```

## disassembly

```asm
0x50f40  volatile.
0x50f42  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Web.Util.AppSettings::_settingsInitialized
0x50f47  brtrue   loc_5166D
0x50f4c  ldsfld   object System.Web.Util.AppSettings::_appSettingsLock
0x50f51  stloc.0
0x50f52  ldc.i4.0
0x50f53  stloc.1
0x50f54  ldloc.0
0x50f55  ldloca.s 1
0x50f57  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x50f5c  volatile.
0x50f5e  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Web.Util.AppSettings::_settingsInitialized
0x50f63  brtrue   loc_51661
0x50f68  ldnull
0x50f69  stloc.2
0x50f6a  call     class [System]System.Collections.Specialized.NameValueCollection System.Web.Util.AppSettings::GetAppSettingsSection()
0x50f6f  stloc.2
0x50f70  leave    loc_5166D
0x50f75  ldloc.2
0x50f76  brfalse.s loc_50F8F
0x50f78  ldloc.2
0x50f79  ldstr    aAspnetUsehosth// "aspnet:UseHostHeaderForRequestUrl"
0x50f7e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50f83  ldsflda  bool System.Web.Util.AppSettings::_useHostHeaderForRequestUrl
0x50f88  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x50f8d  brtrue.s loc_50F95
0x50f8f  ldc.i4.0
0x50f90  stsfld   bool System.Web.Util.AppSettings::_useHostHeaderForRequestUrl
0x50f95  ldloc.2
0x50f96  brfalse.s loc_50FAF
0x50f98  ldloc.2
0x50f99  ldstr    aAspnetAllowano// "aspnet:AllowAnonymousImpersonation"
0x50f9e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50fa3  ldsflda  bool System.Web.Util.AppSettings::_allowAnonymousImpersonation
0x50fa8  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x50fad  brtrue.s loc_50FB5
0x50faf  ldc.i4.0
0x50fb0  stsfld   bool System.Web.Util.AppSettings::_allowAnonymousImpersonation
0x50fb5  ldloc.2
0x50fb6  brfalse.s loc_50FCF
0x50fb8  ldloc.2
0x50fb9  ldstr    aAspnetScriptre// "aspnet:ScriptResourceAllowNonJsFiles"
0x50fbe  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50fc3  ldsflda  bool System.Web.Util.AppSettings::_scriptResourceAllowNonJsFiles
0x50fc8  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x50fcd  brtrue.s loc_50FD5
0x50fcf  ldc.i4.0
0x50fd0  stsfld   bool System.Web.Util.AppSettings::_scriptResourceAllowNonJsFiles
0x50fd5  ldloc.2
0x50fd6  brfalse.s loc_50FEF
0x50fd8  ldloc.2
0x50fd9  ldstr    aAspnetUselegac// "aspnet:UseLegacyEncryption"
0x50fde  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50fe3  ldsflda  bool System.Web.Util.AppSettings::_useLegacyEncryption
0x50fe8  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x50fed  brtrue.s loc_50FF5
0x50fef  ldc.i4.0
0x50ff0  stsfld   bool System.Web.Util.AppSettings::_useLegacyEncryption
0x50ff5  ldloc.2
0x50ff6  brfalse.s loc_5100F
0x50ff8  ldloc.2
0x50ff9  ldstr    aAspnetUselegac_0// "aspnet:UseLegacyMachineKeyEncryption"
0x50ffe  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51003  ldsflda  bool System.Web.Util.AppSettings::_useLegacyMachineKeyEncryption
0x51008  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5100d  brtrue.s loc_51015
0x5100f  ldc.i4.0
0x51010  stsfld   bool System.Web.Util.AppSettings::_useLegacyMachineKeyEncryption
0x51015  ldloc.2
0x51016  brfalse.s loc_5102F
0x51018  ldloc.2
0x51019  ldstr    aAspnetUselegac_1// "aspnet:UseLegacyFormsAuthenticationTick"...
0x5101e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51023  ldsflda  bool System.Web.Util.AppSettings::_useLegacyFormsAuthenticationTicketCompatibility
0x51028  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5102d  brtrue.s loc_51035
0x5102f  ldc.i4.0
0x51030  stsfld   bool System.Web.Util.AppSettings::_useLegacyFormsAuthenticationTicketCompatibility
0x51035  ldloc.2
0x51036  brfalse.s loc_5104F
0x51038  ldloc.2
0x51039  ldstr    aAspnetUselegac_2// "aspnet:UseLegacyEventValidationCompatib"...
0x5103e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51043  ldsflda  bool System.Web.Util.AppSettings::_useLegacyEventValidationCompatibility
0x51048  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5104d  brtrue.s loc_51055
0x5104f  ldc.i4.0
0x51050  stsfld   bool System.Web.Util.AppSettings::_useLegacyEventValidationCompatibility
0x51055  ldloc.2
0x51056  ldstr    aAspnetAllowins// "aspnet:AllowInsecureDeserialization"
0x5105b  call     valuetype [mscorlib]System.Nullable`1<bool> System.Web.Util.AppSettings::GetNullableBooleanValue(class [System]System.Collections.Specialized.NameValueCollection settings, string key)
0x51060  stsfld   valuetype [mscorlib]System.Nullable`1<bool> System.Web.Util.AppSettings::_allowInsecureDeserialization
0x51065  ldloc.2
0x51066  brfalse.s loc_5107F
0x51068  ldloc.2
0x51069  ldstr    aAspnetAlwaysig// "aspnet:AlwaysIgnoreViewStateValidationE"...
0x5106e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51073  ldsflda  bool System.Web.Util.AppSettings::_alwaysIgnoreViewStateValidationErrors
0x51078  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5107d  brtrue.s loc_51085
0x5107f  ldc.i4.0
0x51080  stsfld   bool System.Web.Util.AppSettings::_alwaysIgnoreViewStateValidationErrors
0x51085  ldloc.2
0x51086  brfalse.s loc_5109F
0x51088  ldloc.2
0x51089  ldstr    aAspnetAllowrel// "aspnet:AllowRelaxedHttpUserName"
0x5108e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51093  ldsflda  bool System.Web.Util.AppSettings::_allowRelaxedHttpUserName
0x51098  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5109d  brtrue.s loc_510A5
0x5109f  ldc.i4.0
0x510a0  stsfld   bool System.Web.Util.AppSettings::_allowRelaxedHttpUserName
0x510a5  ldloc.2
0x510a6  brfalse.s loc_510BF
0x510a8  ldloc.2
0x510a9  ldstr    aAspnetJavascri// "aspnet:JavaScriptDoNotEncodeAmpersand"
0x510ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x510b3  ldsflda  bool System.Web.Util.AppSettings::_javaScriptDoNotEncodeAmpersand
0x510b8  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x510bd  brtrue.s loc_510C5
0x510bf  ldc.i4.0
0x510c0  stsfld   bool System.Web.Util.AppSettings::_javaScriptDoNotEncodeAmpersand
0x510c5  ldloc.2
0x510c6  brfalse.s loc_510DF
0x510c8  ldloc.2
0x510c9  ldstr    aAspnetUsetaskf// "aspnet:UseTaskFriendlySynchronizationCo"...
0x510ce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x510d3  ldsflda  bool System.Web.Util.AppSettings::_useTaskFriendlySynchronizationContext
0x510d8  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x510dd  brtrue.s loc_510F4
0x510df  ldsfld   class System.Web.Util.BinaryCompatibility System.Web.Util.BinaryCompatibility::Current
0x510e4  callvirt instance bool System.Web.Util.BinaryCompatibility::get_TargetsAtLeastFramework45()
0x510e9  brtrue.s loc_510EE
0x510eb  ldc.i4.0
0x510ec  br.s     loc_510EF
0x510ee  ldc.i4.1
0x510ef  stsfld   bool System.Web.Util.AppSettings::_useTaskFriendlySynchronizationContext
0x510f4  ldloc.2
0x510f5  brfalse.s loc_5110E
0x510f7  ldloc.2
0x510f8  ldstr    aAspnetAllowasy// "aspnet:AllowAsyncDuringSyncStages"
0x510fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51102  ldsflda  bool System.Web.Util.AppSettings::_allowAsyncDuringSyncStages
0x51107  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5110c  brtrue.s loc_51114
0x5110e  ldc.i4.0
0x5110f  stsfld   bool System.Web.Util.AppSettings::_allowAsyncDuringSyncStages
0x51114  ldloc.2
0x51115  brfalse.s loc_51136
0x51117  ldloc.2
0x51118  ldstr    aAspnetMaxhttpc// "aspnet:MaxHttpCollectionKeys"
0x5111d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51122  ldsflda  int32 System.Web.Util.AppSettings::_maxHttpCollectionKeys
0x51127  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x5112c  brfalse.s loc_51136
0x5112e  ldsfld   int32 System.Web.Util.AppSettings::_maxHttpCollectionKeys
0x51133  ldc.i4.0
0x51134  bge.s    loc_51140
0x51136  ldc.i4   0x7FFFFFFF
0x5113b  stsfld   int32 System.Web.Util.AppSettings::_maxHttpCollectionKeys
0x51140  ldloc.2
0x51141  brfalse.s loc_51162
0x51143  ldloc.2
0x51144  ldstr    aAspnetMaxjsond// "aspnet:MaxJsonDeserializerMembers"
0x51149  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5114e  ldsflda  int32 System.Web.Util.AppSettings::_maxJsonDeserializerMembers
0x51153  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x51158  brfalse.s loc_51162
0x5115a  ldsfld   int32 System.Web.Util.AppSettings::_maxJsonDeserializerMembers
0x5115f  ldc.i4.0
0x51160  bge.s    loc_5116C
0x51162  ldc.i4   0x7FFFFFFF
0x51167  stsfld   int32 System.Web.Util.AppSettings::_maxJsonDeserializerMembers
0x5116c  ldloc.2
0x5116d  brfalse.s loc_51186
0x5116f  ldloc.2
0x51170  ldstr    aAspnetDonotdis// "aspnet:DoNotDisposeSpecialHttpApplicati"...
0x51175  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5117a  ldsflda  bool System.Web.Util.AppSettings::_doNotDisposeSpecialHttpApplicationInstances
0x5117f  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x51184  brtrue.s loc_5118C
0x51186  ldc.i4.0
0x51187  stsfld   bool System.Web.Util.AppSettings::_doNotDisposeSpecialHttpApplicationInstances
0x5118c  ldloc.2
0x5118d  brfalse.s loc_5119F
0x5118f  ldloc.2
0x51190  ldstr    aAspnetFormsaut// "aspnet:FormsAuthReturnUrlVar"
0x51195  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5119a  stsfld   string System.Web.Util.AppSettings::_formsAuthReturnUrlVar
0x5119f  ldloc.2
0x511a0  brfalse.s loc_511B9
0x511a2  ldloc.2
0x511a3  ldstr    aAspnetRestrict// "aspnet:RestrictXmlControls"
0x511a8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x511ad  ldsflda  bool System.Web.Util.AppSettings::_restrictXmlControls
0x511b2  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x511b7  brtrue.s loc_511BF
0x511b9  ldc.i4.0
0x511ba  stsfld   bool System.Web.Util.AppSettings::_restrictXmlControls
0x511bf  ldloc.2
0x511c0  brfalse.s loc_511D9
0x511c2  ldloc.2
0x511c3  ldstr    aAspnetAllowrel_0// "aspnet:AllowRelaxedRelativeUrl"
0x511c8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x511cd  ldsflda  bool System.Web.Util.AppSettings::_allowRelaxedRelativeUrl
0x511d2  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x511d7  brtrue.s loc_511DF
0x511d9  ldc.i4.0
0x511da  stsfld   bool System.Web.Util.AppSettings::_allowRelaxedRelativeUrl
0x511df  ldloc.2
0x511e0  brfalse.s loc_511F9
0x511e2  ldloc.2
0x511e3  ldstr    aAspnetUselegac_3// "aspnet:UseLegacyRequestUrlGeneration"
0x511e8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x511ed  ldsflda  bool System.Web.Util.AppSettings::_useLegacyRequestUrlGeneration
0x511f2  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x511f7  brtrue.s loc_511FF
0x511f9  ldc.i4.0
0x511fa  stsfld   bool System.Web.Util.AppSettings::_useLegacyRequestUrlGeneration
0x511ff  ldloc.2
0x51200  brfalse.s loc_51219
0x51202  ldloc.2
0x51203  ldstr    aAspnetAllowutf// "aspnet:AllowUtf7RequestContentEncoding"
0x51208  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5120d  ldsflda  bool System.Web.Util.AppSettings::_allowUtf7RequestContentEncoding
0x51212  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x51217  brtrue.s loc_5121F
0x51219  ldc.i4.0
0x5121a  stsfld   bool System.Web.Util.AppSettings::_allowUtf7RequestContentEncoding
0x5121f  ldloc.2
0x51220  brfalse.s loc_51239
0x51222  ldloc.2
0x51223  ldstr    aAspnetAllowrel_1// "aspnet:AllowRelaxedUnicodeDecoding"
0x51228  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5122d  ldsflda  bool System.Web.Util.AppSettings::_allowRelaxedUnicodeDecoding
0x51232  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x51237  brtrue.s loc_5123F
0x51239  ldc.i4.0
0x5123a  stsfld   bool System.Web.Util.AppSettings::_allowRelaxedUnicodeDecoding
0x5123f  ldloc.2
0x51240  brfalse.s loc_51259
0x51242  ldloc.2
0x51243  ldstr    aAspnetDontusep// "aspnet:DontUsePercentUUrlEncoding"
0x51248  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5124d  ldsflda  bool System.Web.Util.AppSettings::_dontUsePercentUUrlEncoding
0x51252  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x51257  brtrue.s loc_51268
0x51259  ldsfld   class System.Web.Util.BinaryCompatibility System.Web.Util.BinaryCompatibility::Current
0x5125e  callvirt instance bool System.Web.Util.BinaryCompatibility::get_TargetsAtLeastFramework452()
0x51263  stsfld   bool System.Web.Util.AppSettings::_dontUsePercentUUrlEncoding
0x51268  ldloc.2
0x51269  brfalse.s loc_5128A
0x5126b  ldloc.2
0x5126c  ldstr    aAspnetUpdatepa// "aspnet:UpdatePanelMaxScriptLength"
0x51271  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51276  ldsflda  int32 System.Web.Util.AppSettings::_updatePanelMaxScriptLength
0x5127b  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x51280  brfalse.s loc_5128A
0x51282  ldsfld   int32 System.Web.Util.AppSettings::_updatePanelMaxScriptLength
0x51287  ldc.i4.0
0x51288  bge.s    loc_51290
0x5128a  ldc.i4.0
0x5128b  stsfld   int32 System.Web.Util.AppSettings::_updatePanelMaxScriptLength
0x51290  ldloc.2
0x51291  ldstr    aAspnetMaxconcu// "aspnet:MaxConcurrentCompilations"
0x51296  call     valuetype [mscorlib]System.Nullable`1<int32> System.Web.Util.AppSettings::GetNullableIntegerValue(class [System]System.Collections.Specialized.NameValueCollection settings, string key)
0x5129b  stsfld   valuetype [mscorlib]System.Nullable`1<int32> System.Web.Util.AppSettings::_maxConcurrentCompilations
0x512a0  ldloc.2
0x512a1  brfalse.s loc_512C2
0x512a3  ldloc.2
0x512a4  ldstr    aAspnetMaxaccep// "aspnet:MaxAcceptLanguageFallbackCount"
0x512a9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x512ae  ldsflda  int32 System.Web.Util.AppSettings::_maxAcceptLanguageFallbackCount
0x512b3  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x512b8  brfalse.s loc_512C2
0x512ba  ldsfld   int32 System.Web.Util.AppSettings::_maxAcceptLanguageFallbackCount
0x512bf  ldc.i4.0
0x512c0  bgt.s    loc_512C8
0x512c2  ldc.i4.3
0x512c3  stsfld   int32 System.Web.Util.AppSettings::_maxAcceptLanguageFallbackCount
0x512c8  ldloc.2
0x512c9  brfalse.s loc_512E2
0x512cb  ldloc.2
0x512cc  ldstr    aAspnetPortable// "aspnet:PortableCompilationOutput"
0x512d1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x512d6  ldsflda  bool System.Web.Util.AppSettings::_portableCompilationOutput
0x512db  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x512e0  brtrue.s loc_512E8
0x512e2  ldc.i4.0
0x512e3  stsfld   bool System.Web.Util.AppSettings::_portableCompilationOutput
0x512e8  ldloc.2
0x512e9  brfalse.s loc_51303
0x512eb  ldloc.2
0x512ec  ldstr    aAspnetPortable_0// "aspnet:PortableCompilationOutputSnapsho"...
0x512f1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x512f6  dup
0x512f7  stsfld   string System.Web.Util.AppSettings::_portableCompilationOutputSnapshotType
0x512fc  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x51301  brfalse.s loc_51309
0x51303  ldnull
  ... truncated ...
```
