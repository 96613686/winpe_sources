# <>c__DisplayClass32_0::<SynchronizedInvoke>b__0

- ea: `0x7be60`
- end: `0x7c01d`
- name: `<>c__DisplayClass32_0::<SynchronizedInvoke>b__0`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x199a0`
- `0x19d50`
- `0x29280`
- `0x596f0`
- `0x5c650`
- `0x5c950`
- `0x7be60`

## string_xrefs

- `0x7bfa2`: `DownloadHelpLinkText`
- `0x7bf37`: `MidInstall_DownloadFailed_Args3`
- `0x7bee8`: `MidInstall_DownloadNineTimes`
- `0x7beef`: `MidInstall_DownloadThreeTimes`
- `0x7bf06`: `MidInstall_VitalDownloadFailed_Args3`

## pseudocode

```c

```

## disassembly

```asm
0x7be60  ldarg.0
0x7be61  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7be66  ldc.i4.0
0x7be67  stfld    bool Microsoft.VisualStudio.Setup.Activities.Download::failed
0x7be6c  ldarg.0
0x7be6d  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7be72  ldc.i4.0
0x7be73  stfld    bool Microsoft.VisualStudio.Setup.Activities.Download::isNoSuitableEngineFound
0x7be78  ldarg.0
0x7be79  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7be7e  ldc.i4.0
0x7be7f  stfld    bool Microsoft.VisualStudio.Setup.Activities.Download::authenticationFailed
0x7be84  ldarg.0
0x7be85  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7be8a  ldarg.0
0x7be8b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass32_0::token
0x7be90  call     instance void Microsoft.VisualStudio.Setup.Activities.Download::DownloadAction(valuetype [mscorlib]System.Threading.CancellationToken token)
0x7be95  ldarg.0
0x7be96  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7be9b  ldfld    bool Microsoft.VisualStudio.Setup.Activities.Download::failed
0x7bea0  brfalse  loc_7C012
0x7bea5  ldarg.0
0x7bea6  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7beab  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x7beb0  ldc.i4.0
0x7beb1  call     T0x2B00008C
0x7beb6  stloc.0
0x7beb7  ldloc.0
0x7beb8  brfalse.s loc_7BEDD
0x7beba  ldloc.0
0x7bebb  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService::get_NoWeb()
0x7bec0  brfalse.s loc_7BEDD
0x7bec2  ldloc.0
0x7bec3  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService::get_NoWeb()
0x7bec8  brfalse  loc_7C012
0x7becd  ldarg.0
0x7bece  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7bed3  ldfld    bool Microsoft.VisualStudio.Setup.Activities.Download::isNoSuitableEngineFound
0x7bed8  brtrue   loc_7C012
0x7bedd  ldloc.0
0x7bede  brfalse.s loc_7BEE8
0x7bee0  ldloc.0
0x7bee1  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService::get_NoWeb()
0x7bee6  brtrue.s loc_7BEEF
0x7bee8  ldstr    aMidinstallDown_0// "MidInstall_DownloadNineTimes"
0x7beed  br.s     loc_7BEF4
0x7beef  ldstr    aMidinstallDown_1// "MidInstall_DownloadThreeTimes"
0x7bef4  stloc.1
0x7bef5  ldc.i4.6
0x7bef6  stloc.2
0x7bef7  ldloc.2
0x7bef8  stloc.3
0x7bef9  ldarg.0
0x7befa  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7beff  ldfld    bool Microsoft.VisualStudio.Setup.Activities.Download::authenticationFailed
0x7bf04  brtrue.s loc_7BF0D
0x7bf06  ldstr    aMidinstallVita// "MidInstall_VitalDownloadFailed_Args3"
0x7bf0b  br.s     loc_7BF12
0x7bf0d  ldstr    aErrorAuthentic// "Error_AuthenticationFailed_Message"
0x7bf12  stloc.s  4
0x7bf14  ldarg.0
0x7bf15  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7bf1a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Download::package
0x7bf1f  brfalse.s loc_7BF33
0x7bf21  ldarg.0
0x7bf22  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7bf27  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Download::package
0x7bf2c  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsVitalToInstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x7bf31  brtrue.s loc_7BF3E
0x7bf33  ldloc.2
0x7bf34  ldc.i4.8
0x7bf35  or
0x7bf36  stloc.3
0x7bf37  ldstr    aMidinstallDown// "MidInstall_DownloadFailed_Args3"
0x7bf3c  stloc.s  4
0x7bf3e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7bf43  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x7bf48  ldloc.s  4
0x7bf4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7bf4f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7bf54  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x7bf59  ldloc.1
0x7bf5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7bf5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7bf64  ldarg.0
0x7bf65  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7bf6a  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Activities.Download::get_Uri()
0x7bf6f  call     string Microsoft.VisualStudio.Setup.Resources::get_DownloadHelpLinkText()
0x7bf74  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x7bf79  stloc.s  5
0x7bf7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7bf80  ldloc.s  4
0x7bf82  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x7bf87  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x7bf8c  ldloc.1
0x7bf8d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x7bf92  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x7bf97  ldarg.0
0x7bf98  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7bf9d  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Activities.Download::get_Uri()
0x7bfa2  ldstr    aDownloadhelpli// "DownloadHelpLinkText"
0x7bfa7  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x7bfac  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x7bfb1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x7bfb6  stloc.s  6
0x7bfb8  ldloca.s 7
0x7bfba  initobj  [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message
0x7bfc0  ldloca.s 7
0x7bfc2  ldc.i4.2
0x7bfc3  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType>::.ctor(var<u1>)
0x7bfc8  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Activity
0x7bfcd  ldloca.s 7
0x7bfcf  ldc.i4.2
0x7bfd0  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Type
0x7bfd5  ldloca.s 7
0x7bfd7  ldloc.3
0x7bfd8  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResultTypes [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::AcceptsResultTypes
0x7bfdd  ldloca.s 7
0x7bfdf  ldc.i4.8
0x7bfe0  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResultTypes [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::DefaultResultType
0x7bfe5  ldloca.s 7
0x7bfe7  ldloc.s  5
0x7bfe9  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::LocalizedString
0x7bfee  ldloca.s 7
0x7bff0  ldloc.s  6
0x7bff2  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::NeutralString
0x7bff7  ldloca.s 7
0x7bff9  ldc.i4.0
0x7bffa  ldarg.0
0x7bffb  ldfld    class Microsoft.VisualStudio.Setup.Activities.Download <>c__DisplayClass32_0::<>4__this
0x7c000  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.RetryMessageContext::.ctor(int32, object)
0x7c005  stfld    object [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Context
0x7c00a  ldloc.s  7
0x7c00c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message>::.ctor(var<u1>)
0x7c011  ret
0x7c012  ldloca.s 8
0x7c014  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message>
0x7c01a  ldloc.s  8
0x7c01c  ret
```
