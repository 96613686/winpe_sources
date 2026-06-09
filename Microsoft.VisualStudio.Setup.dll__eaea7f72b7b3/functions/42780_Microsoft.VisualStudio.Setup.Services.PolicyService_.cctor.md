# Microsoft.VisualStudio.Setup.Services.PolicyService::.cctor

- ea: `0x42780`
- end: `0x42989`
- name: `Microsoft.VisualStudio.Setup.Services.PolicyService::.cctor`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x427f4`: `AdministratorUpdatesEnabled`
- `0x427f9`: `AdministratorUpdatesEnabled`
- `0x42814`: `AdministratorUpdatesOptOut`
- `0x42819`: `AdministratorUpdatesOptOut`
- `0x428a4`: `RemoveOos`
- `0x428a9`: `RemoveOos`
- `0x42874`: `DisableRollback`
- `0x42879`: `DisableRollback`
- `0x427a4`: `SharedInstallationPath`
- `0x427a9`: `SharedInstallationPath`
- `0x427c4`: `CompatibilityInstallationPath`
- `0x427c9`: `CompatibilityInstallationPath`
- `0x427b4`: `CachePath`
- `0x427b9`: `CachePath`
- `0x42834`: `ChannelUpdateDisabled`
- `0x42839`: `ChannelUpdateDisabled`
- `0x42844`: `AutoUpdateDisabled`
- `0x42849`: `AutoUpdateDisabled`
- `0x428c4`: `UpdateConfigurationFile`
- `0x428c9`: `UpdateConfigurationFile`
- `0x428e4`: `ElevationServiceSupport`
- `0x428f4`: `AdministratorUpdatesNotificationsEnabled`
- `0x42904`: `AdministratorUpdateOnCloseOptOut`
- `0x42909`: `AdministratorUpdateOnCloseOptOut`
- `0x42914`: `VSthroughMUUpdatesOptOut`
- `0x42919`: `VSthroughMUUpdatesOptOut`
- `0x42924`: `PreviewAutomaticUpdates`
- `0x42929`: `PreviewAutomaticUpdates`
- `0x42934`: `UpdateNotificationsOptOut`
- `0x42939`: `UpdateNotificationsOptOut`
- `0x428f9`: `AdministratorUpdatesNotifications`

## pseudocode

```c

```

## disassembly

```asm
0x42780  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\VisualStudio\\Setu"...
0x42785  stsfld   string Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryKeyPath
0x4278a  ldstr    aSoftwarePolici_0// "SOFTWARE\\Policies\\Microsoft\\VisualSt"...
0x4278f  stsfld   string Microsoft.VisualStudio.Setup.Services.PolicyService::SetupPolicyKeyPath
0x42794  ldstr    aSoftwarePolici_2// "Software\\Policies\\Microsoft\\VisualSt"...
0x42799  stsfld   string Microsoft.VisualStudio.Setup.Services.PolicyService::FeedbackPolicyKeyPath
0x4279e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x427a3  dup
0x427a4  ldstr    aSharedinstalla// "SharedInstallationPath"
0x427a9  ldstr    aSharedinstalla// "SharedInstallationPath"
0x427ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x427b3  dup
0x427b4  ldstr    aCachepath// "CachePath"
0x427b9  ldstr    aCachepath// "CachePath"
0x427be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x427c3  dup
0x427c4  ldstr    aCompatibilityi// "CompatibilityInstallationPath"
0x427c9  ldstr    aCompatibilityi// "CompatibilityInstallationPath"
0x427ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x427d3  dup
0x427d4  ldstr    aKeepdownloaded// "KeepDownloadedPayloads"
0x427d9  ldstr    aKeepdownloaded// "KeepDownloadedPayloads"
0x427de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x427e3  dup
0x427e4  ldstr    aConcurrentdown// "ConcurrentDownloads"
0x427e9  ldstr    aConcurrentdown// "ConcurrentDownloads"
0x427ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x427f3  dup
0x427f4  ldstr    aAdministratoru// "AdministratorUpdatesEnabled"
0x427f9  ldstr    aAdministratoru// "AdministratorUpdatesEnabled"
0x427fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42803  dup
0x42804  ldstr    aAdministratorp// "AdministratorPromptToClose"
0x42809  ldstr    aAdministratorp// "AdministratorPromptToClose"
0x4280e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42813  dup
0x42814  ldstr    aAdministratoru_0// "AdministratorUpdatesOptOut"
0x42819  ldstr    aAdministratoru_0// "AdministratorUpdatesOptOut"
0x4281e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42823  dup
0x42824  ldstr    aDiagnosticmode// "DiagnosticMode"
0x42829  ldstr    aDiagnosticmode// "DiagnosticMode"
0x4282e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42833  dup
0x42834  ldstr    aChannelupdated// "ChannelUpdateDisabled"
0x42839  ldstr    aChannelupdated// "ChannelUpdateDisabled"
0x4283e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42843  dup
0x42844  ldstr    aAutoupdatedisa// "AutoUpdateDisabled"
0x42849  ldstr    aAutoupdatedisa// "AutoUpdateDisabled"
0x4284e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42853  dup
0x42854  ldstr    aBackgrounddown_1// "BackgroundDownloadDisabled"
0x42859  ldstr    aBackgrounddown_1// "BackgroundDownloadDisabled"
0x4285e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42863  dup
0x42864  ldstr    aDisablemicroso// "DisableMicrosoftChannelFeed"
0x42869  ldstr    aDisablemicroso// "DisableMicrosoftChannelFeed"
0x4286e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42873  dup
0x42874  ldstr    aDisablerollbac// "DisableRollback"
0x42879  ldstr    aDisablerollbac// "DisableRollback"
0x4287e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42883  dup
0x42884  ldstr    aHideavailablet// "HideAvailableTab"
0x42889  ldstr    aHideavailablet// "HideAvailableTab"
0x4288e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42893  dup
0x42894  ldstr    aIgnorechannelf// "IgnoreChannelFeedProductRestriction"
0x42899  ldstr    aIgnorechannelf// "IgnoreChannelFeedProductRestriction"
0x4289e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428a3  dup
0x428a4  ldstr    aRemoveoos// "RemoveOos"
0x428a9  ldstr    aRemoveoos// "RemoveOos"
0x428ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428b3  dup
0x428b4  ldstr    aDisablesound// "DisableSound"
0x428b9  ldstr    aDisablesound// "DisableSound"
0x428be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428c3  dup
0x428c4  ldstr    aUpdateconfigur_0// "UpdateConfigurationFile"
0x428c9  ldstr    aUpdateconfigur_0// "UpdateConfigurationFile"
0x428ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428d3  dup
0x428d4  ldstr    aDisableblocked// "DisableBlockedOSCheck"
0x428d9  ldstr    aDisableblocked// "DisableBlockedOSCheck"
0x428de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428e3  dup
0x428e4  ldstr    aElevationservi// "ElevationServiceSupport"
0x428e9  ldstr    aAllowstandardu// "AllowStandardUserControl"
0x428ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x428f3  dup
0x428f4  ldstr    aAdministratoru_1// "AdministratorUpdatesNotificationsEnable"...
0x428f9  ldstr    aAdministratoru_3// "AdministratorUpdatesNotifications"
0x428fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42903  dup
0x42904  ldstr    aAdministratoru_2// "AdministratorUpdateOnCloseOptOut"
0x42909  ldstr    aAdministratoru_2// "AdministratorUpdateOnCloseOptOut"
0x4290e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42913  dup
0x42914  ldstr    aVsthroughmuupd// "VSthroughMUUpdatesOptOut"
0x42919  ldstr    aVsthroughmuupd// "VSthroughMUUpdatesOptOut"
0x4291e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42923  dup
0x42924  ldstr    aPreviewautomat// "PreviewAutomaticUpdates"
0x42929  ldstr    aPreviewautomat// "PreviewAutomaticUpdates"
0x4292e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42933  dup
0x42934  ldstr    aUpdatenotifica// "UpdateNotificationsOptOut"
0x42939  ldstr    aUpdatenotifica// "UpdateNotificationsOptOut"
0x4293e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42943  dup
0x42944  ldstr    aAvailabletabpr// "AvailableTabProducts"
0x42949  ldstr    aAvailabletabpr// "AvailableTabProducts"
0x4294e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42953  dup
0x42954  ldstr    aProductfeedbac// "ProductFeedbackDisabled"
0x42959  ldstr    aProductfeedbac// "ProductFeedbackDisabled"
0x4295e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42963  dup
0x42964  ldstr    aSurveysdisable// "SurveysDisabled"
0x42969  ldstr    aSurveysdisable// "SurveysDisabled"
0x4296e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42973  dup
0x42974  ldstr    aSkipngenafters// "SkipNgenAfterSetup"
0x42979  ldstr    aSkipngenafters// "SkipNgenAfterSetup"
0x4297e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x42983  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryValueNameLookup
0x42988  ret
```
