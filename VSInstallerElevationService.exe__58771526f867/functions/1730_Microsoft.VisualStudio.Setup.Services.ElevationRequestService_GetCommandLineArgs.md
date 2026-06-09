# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::GetCommandLineArgs

- ea: `0x1730`
- end: `0x17db`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::GetCommandLineArgs`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1860`

## callees

- `0x1730`
- `0x17e0`
- `0x1800`

## pseudocode

```c

```

## disassembly

```asm
0x1730  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1735  stloc.0
0x1736  ldloc.0
0x1737  ldstr    aElevate// "elevate"
0x173c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1741  pop
0x1742  ldloc.0
0x1743  ldstr    aPipename0// " --pipeName \"{0}\""
0x1748  ldarg.1
0x1749  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x174e  pop
0x174f  ldloc.0
0x1750  ldstr    aActivityid// "activityId"
0x1755  ldarg.0
0x1756  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_ActivityId()
0x175b  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, string parameterValue)
0x1760  ldloc.0
0x1761  ldstr    aSerializedsess// "serializedSession"
0x1766  ldarg.0
0x1767  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_SerializedSession()
0x176c  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, string parameterValue)
0x1771  ldloc.0
0x1772  ldstr    aLocale// "locale"
0x1777  ldarg.0
0x1778  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_Locale()
0x177d  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, string parameterValue)
0x1782  ldloc.0
0x1783  ldstr    aCampaign// "campaign"
0x1788  ldarg.0
0x1789  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_CampaignId()
0x178e  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, string parameterValue)
0x1793  ldloc.0
0x1794  ldstr    aQuiet// "quiet"
0x1799  ldarg.0
0x179a  callvirt instance bool [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_IsQuiet()
0x179f  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddBooleanParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, bool parameterValue)
0x17a4  ldloc.0
0x17a5  ldstr    aPassive// "passive"
0x17aa  ldarg.0
0x17ab  callvirt instance bool [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_IsPassive()
0x17b0  call     void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddBooleanParameter(class [mscorlib]System.Text.StringBuilder commandLineArgs, string parameterName, bool parameterValue)
0x17b5  ldarg.0
0x17b6  callvirt instance int64 [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_Handle()
0x17bb  brfalse.s loc_17D4
0x17bd  ldloc.0
0x17be  ldstr    aHandle0// " --handle {0}"
0x17c3  ldarg.0
0x17c4  callvirt instance int64 [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::get_Handle()
0x17c9  box      [mscorlib]System.Int64
0x17ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x17d3  pop
0x17d4  ldloc.0
0x17d5  callvirt instance string [mscorlib]System.Object::ToString()
0x17da  ret
```
