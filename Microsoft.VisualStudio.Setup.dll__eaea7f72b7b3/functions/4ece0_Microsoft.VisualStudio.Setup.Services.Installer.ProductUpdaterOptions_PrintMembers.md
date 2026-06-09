# Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::PrintMembers

- ea: `0x4ece0`
- end: `0x4eeb4`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::PrintMembers`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x4c7e0`
- `0x4eb10`
- `0x4eb30`
- `0x4eb50`
- `0x4eb70`
- `0x4eb90`
- `0x4eba0`
- `0x4ebb0`
- `0x4ebc0`
- `0x4ebd0`
- `0x4ebe0`
- `0x4ec00`
- `0x4ec20`
- `0x4ec40`
- `0x4ec60`
- `0x4ec80`
- `0x4ece0`

## string_xrefs

- `0x4ee28`: `, ChannelUri = `
- `0x4ee73`: `, LayoutUri = `
- `0x4ee41`: `, InstallChannelUri = `
- `0x4ee5a`: `, InstallCatalogUri = `
- `0x4ecf6`: `LayoutPath = `
- `0x4ed0f`: `, InstallLayoutPath = `
- `0x4ed5a`: `, UpdateFromVS = `
- `0x4ed81`: `, RemoveOos = `
- `0x4eda8`: `, IncludeRecommended = `
- `0x4edcf`: `, UpdateVersion = `
- `0x4ee8c`: `, WUProgressCBClsID = `

## pseudocode

```c

```

## disassembly

```asm
0x4ece0  ldarg.0
0x4ece1  ldarg.1
0x4ece2  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0x4ece7  brfalse.s loc_4ECF5
0x4ece9  ldarg.1
0x4ecea  ldstr    asc_823FC// ", "
0x4ecef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ecf4  pop
0x4ecf5  ldarg.1
0x4ecf6  ldstr    aLayoutpath_0// "LayoutPath = "
0x4ecfb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed00  pop
0x4ed01  ldarg.1
0x4ed02  ldarg.0
0x4ed03  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_LayoutPath()
0x4ed08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ed0d  pop
0x4ed0e  ldarg.1
0x4ed0f  ldstr    aInstalllayoutp// ", InstallLayoutPath = "
0x4ed14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed19  pop
0x4ed1a  ldarg.1
0x4ed1b  ldarg.0
0x4ed1c  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallLayoutPath()
0x4ed21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ed26  pop
0x4ed27  ldarg.1
0x4ed28  ldstr    aProductkey_0// ", ProductKey = "
0x4ed2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed32  pop
0x4ed33  ldarg.1
0x4ed34  ldarg.0
0x4ed35  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ProductKey()
0x4ed3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ed3f  pop
0x4ed40  ldarg.1
0x4ed41  ldstr    aNickname// ", Nickname = "
0x4ed46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed4b  pop
0x4ed4c  ldarg.1
0x4ed4d  ldarg.0
0x4ed4e  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_Nickname()
0x4ed53  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ed58  pop
0x4ed59  ldarg.1
0x4ed5a  ldstr    aUpdatefromvs// ", UpdateFromVS = "
0x4ed5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed64  pop
0x4ed65  ldarg.1
0x4ed66  ldarg.0
0x4ed67  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_UpdateFromVS()
0x4ed6c  stloc.0
0x4ed6d  ldloca.s 0
0x4ed6f  constrained. [mscorlib]System.Boolean
0x4ed75  callvirt instance string [mscorlib]System.Object::ToString()
0x4ed7a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed7f  pop
0x4ed80  ldarg.1
0x4ed81  ldstr    aRemoveoos_0// ", RemoveOos = "
0x4ed86  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ed8b  pop
0x4ed8c  ldarg.1
0x4ed8d  ldarg.0
0x4ed8e  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_RemoveOos()
0x4ed93  stloc.0
0x4ed94  ldloca.s 0
0x4ed96  constrained. [mscorlib]System.Boolean
0x4ed9c  callvirt instance string [mscorlib]System.Object::ToString()
0x4eda1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4eda6  pop
0x4eda7  ldarg.1
0x4eda8  ldstr    aIncluderecomme_1// ", IncludeRecommended = "
0x4edad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4edb2  pop
0x4edb3  ldarg.1
0x4edb4  ldarg.0
0x4edb5  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_IncludeRecommended()
0x4edba  stloc.0
0x4edbb  ldloca.s 0
0x4edbd  constrained. [mscorlib]System.Boolean
0x4edc3  callvirt instance string [mscorlib]System.Object::ToString()
0x4edc8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4edcd  pop
0x4edce  ldarg.1
0x4edcf  ldstr    aUpdateversion// ", UpdateVersion = "
0x4edd4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4edd9  pop
0x4edda  ldarg.1
0x4eddb  ldarg.0
0x4eddc  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_UpdateVersion()
0x4ede1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ede6  pop
0x4ede7  ldarg.1
0x4ede8  ldstr    aOperationmode_0// ", OperationMode = "
0x4eded  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4edf2  pop
0x4edf3  ldarg.1
0x4edf4  ldarg.0
0x4edf5  call     instance valuetype Microsoft.VisualStudio.Setup.OperationMode Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_OperationMode()
0x4edfa  stloc.1
0x4edfb  ldloca.s 1
0x4edfd  constrained. Microsoft.VisualStudio.Setup.OperationMode
0x4ee03  callvirt instance string [mscorlib]System.Object::ToString()
0x4ee08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee0d  pop
0x4ee0e  ldarg.1
0x4ee0f  ldstr    aVisualstudiofl// ", VisualStudioFlights = "
0x4ee14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee19  pop
0x4ee1a  ldarg.1
0x4ee1b  ldarg.0
0x4ee1c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_VisualStudioFlights()
0x4ee21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ee26  pop
0x4ee27  ldarg.1
0x4ee28  ldstr    aChanneluri_0// ", ChannelUri = "
0x4ee2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee32  pop
0x4ee33  ldarg.1
0x4ee34  ldarg.0
0x4ee35  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x4ee3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ee3f  pop
0x4ee40  ldarg.1
0x4ee41  ldstr    aInstallchannel_1// ", InstallChannelUri = "
0x4ee46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee4b  pop
0x4ee4c  ldarg.1
0x4ee4d  ldarg.0
0x4ee4e  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallChannelUri()
0x4ee53  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ee58  pop
0x4ee59  ldarg.1
0x4ee5a  ldstr    aInstallcatalog// ", InstallCatalogUri = "
0x4ee5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee64  pop
0x4ee65  ldarg.1
0x4ee66  ldarg.0
0x4ee67  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallCatalogUri()
0x4ee6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ee71  pop
0x4ee72  ldarg.1
0x4ee73  ldstr    aLayouturi// ", LayoutUri = "
0x4ee78  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee7d  pop
0x4ee7e  ldarg.1
0x4ee7f  ldarg.0
0x4ee80  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_LayoutUri()
0x4ee85  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4ee8a  pop
0x4ee8b  ldarg.1
0x4ee8c  ldstr    aWuprogresscbcl_0// ", WUProgressCBClsID = "
0x4ee91  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee96  pop
0x4ee97  ldarg.1
0x4ee98  ldarg.0
0x4ee99  call     instance valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_WUProgressCBClsID()
0x4ee9e  stloc.2
0x4ee9f  ldloca.s 2
0x4eea1  constrained. [mscorlib]System.Guid
0x4eea7  callvirt instance string [mscorlib]System.Object::ToString()
0x4eeac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4eeb1  pop
0x4eeb2  ldc.i4.1
0x4eeb3  ret
```
