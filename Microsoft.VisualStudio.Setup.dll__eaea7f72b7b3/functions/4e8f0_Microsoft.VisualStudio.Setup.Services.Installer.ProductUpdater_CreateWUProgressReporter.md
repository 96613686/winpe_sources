# Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::CreateWUProgressReporter

- ea: `0x4e8f0`
- end: `0x4e983`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::CreateWUProgressReporter`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x4e890`

## callees

- `0x22750`
- `0x48b00`
- `0x4e8f0`
- `0x4ec80`

## string_xrefs

- `0x4e90e`: `The WUProgressCBClsID is empty.`
- `0x4e954`: `Failed to create {0} using {1}: {2}.`
- `0x4e959`: `IUpdateInstallerProgress`
- `0x4e95e`: `WUProgressCBClsID`

## pseudocode

```c

```

## disassembly

```asm
0x4e8f0  ldarg.1
0x4e8f1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_WUProgressCBClsID()
0x4e8f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e8fb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e900  brfalse.s loc_4E91F
0x4e902  ldarg.0
0x4e903  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_Logger()
0x4e908  dup
0x4e909  brtrue.s loc_4E90E
0x4e90b  pop
0x4e90c  br.s     loc_4E91D
0x4e90e  ldstr    aTheWuprogressc// "The WUProgressCBClsID is empty."
0x4e913  call     T0x2B000003
0x4e918  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4e91d  ldnull
0x4e91e  ret
0x4e91f  nop
0x4e920  ldarg.1
0x4e921  callvirt instance valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_WUProgressCBClsID()
0x4e926  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromCLSID(valuetype [mscorlib]System.Guid)
0x4e92b  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x4e930  castclass Microsoft.VisualStudio.Setup.Services.IUpdateInstallerProgress
0x4e935  stloc.0
0x4e936  ldloc.0
0x4e937  brfalse.s loc_4E942
0x4e939  ldarg.0
0x4e93a  ldloc.0
0x4e93b  newobj   instance void Microsoft.VisualStudio.Setup.Services.WindowsUpdateProgressReporter::.ctor(class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Services.IUpdateInstallerProgress cmdLineUpdateInstallerProgress)
0x4e940  br.s     loc_4E943
0x4e942  ldnull
0x4e943  stloc.1
0x4e944  leave.s  loc_4E981
0x4e946  stloc.2
0x4e947  ldarg.0
0x4e948  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_Logger()
0x4e94d  dup
0x4e94e  brtrue.s loc_4E953
0x4e950  pop
0x4e951  br.s     loc_4E97D
0x4e953  ldloc.2
0x4e954  ldstr    aFailedToCreate_12// "Failed to create {0} using {1}: {2}."
0x4e959  ldstr    aIupdateinstall// "IUpdateInstallerProgress"
0x4e95e  ldstr    aWuprogresscbcl// "WUProgressCBClsID"
0x4e963  ldarg.1
0x4e964  callvirt instance valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_WUProgressCBClsID()
0x4e969  box      [mscorlib]System.Guid
0x4e96e  call     string [mscorlib]System.String::Format(string, object, object, object)
0x4e973  call     T0x2B000003
0x4e978  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4e97d  leave.s  loc_4E97F
0x4e97f  ldnull
0x4e980  ret
0x4e981  ldloc.1
0x4e982  ret
```
