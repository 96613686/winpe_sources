# Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::PrintMembers

- ea: `0x4d660`
- end: `0x4d83c`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::PrintMembers`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x4c7e0`
- `0x4d470`
- `0x4d480`
- `0x4d490`
- `0x4d4b0`
- `0x4d4d0`
- `0x4d4f0`
- `0x4d510`
- `0x4d520`
- `0x4d530`
- `0x4d540`
- `0x4d550`
- `0x4d560`
- `0x4d580`
- `0x4d5a0`
- `0x4d5c0`
- `0x4d5e0`
- `0x4d600`
- `0x4d660`

## string_xrefs

- `0x4d6a8`: `, LayoutPath = `
- `0x4d70c`: `, ChannelUri = `
- `0x4d7b0`: `, AdditionalExtensions = `
- `0x4d7c9`: `, LayoutUri = `
- `0x4d7e2`: `, InstallChannelUri = `
- `0x4d7fb`: `, InstallCatalogUri = `
- `0x4d814`: `, IncludeRecommendedOnUpdate = `

## pseudocode

```c

```

## disassembly

```asm
0x4d660  ldarg.0
0x4d661  ldarg.1
0x4d662  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0x4d667  brfalse.s loc_4D675
0x4d669  ldarg.1
0x4d66a  ldstr    asc_823FC// ", "
0x4d66f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d674  pop
0x4d675  ldarg.1
0x4d676  ldstr    aSelectedpackag_1// "SelectedPackages = "
0x4d67b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d680  pop
0x4d681  ldarg.1
0x4d682  ldarg.0
0x4d683  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState> Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_SelectedPackages()
0x4d688  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d68d  pop
0x4d68e  ldarg.1
0x4d68f  ldstr    aLanguages// ", Languages = "
0x4d694  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d699  pop
0x4d69a  ldarg.1
0x4d69b  ldarg.0
0x4d69c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_Languages()
0x4d6a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d6a6  pop
0x4d6a7  ldarg.1
0x4d6a8  ldstr    aLayoutpath// ", LayoutPath = "
0x4d6ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d6b2  pop
0x4d6b3  ldarg.1
0x4d6b4  ldarg.0
0x4d6b5  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_LayoutPath()
0x4d6ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d6bf  pop
0x4d6c0  ldarg.1
0x4d6c1  ldstr    aProductkey_0// ", ProductKey = "
0x4d6c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d6cb  pop
0x4d6cc  ldarg.1
0x4d6cd  ldarg.0
0x4d6ce  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_ProductKey()
0x4d6d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d6d8  pop
0x4d6d9  ldarg.1
0x4d6da  ldstr    aNickname// ", Nickname = "
0x4d6df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d6e4  pop
0x4d6e5  ldarg.1
0x4d6e6  ldarg.0
0x4d6e7  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_Nickname()
0x4d6ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d6f1  pop
0x4d6f2  ldarg.1
0x4d6f3  ldstr    aMigratefrom_0// ", MigrateFrom = "
0x4d6f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d6fd  pop
0x4d6fe  ldarg.1
0x4d6ff  ldarg.0
0x4d700  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_MigrateFrom()
0x4d705  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d70a  pop
0x4d70b  ldarg.1
0x4d70c  ldstr    aChanneluri_0// ", ChannelUri = "
0x4d711  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d716  pop
0x4d717  ldarg.1
0x4d718  ldarg.0
0x4d719  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_ChannelUri()
0x4d71e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d723  pop
0x4d724  ldarg.1
0x4d725  ldstr    aProductid// ", ProductId = "
0x4d72a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d72f  pop
0x4d730  ldarg.1
0x4d731  ldarg.0
0x4d732  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_ProductId()
0x4d737  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d73c  pop
0x4d73d  ldarg.1
0x4d73e  ldstr    aProductarch// ", ProductArch = "
0x4d743  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d748  pop
0x4d749  ldarg.1
0x4d74a  ldarg.0
0x4d74b  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_ProductArch()
0x4d750  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d755  pop
0x4d756  ldarg.1
0x4d757  ldstr    aOperationmode_0// ", OperationMode = "
0x4d75c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d761  pop
0x4d762  ldarg.1
0x4d763  ldarg.0
0x4d764  call     instance valuetype Microsoft.VisualStudio.Setup.OperationMode Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_OperationMode()
0x4d769  stloc.0
0x4d76a  ldloca.s 0
0x4d76c  constrained. Microsoft.VisualStudio.Setup.OperationMode
0x4d772  callvirt instance string [mscorlib]System.Object::ToString()
0x4d777  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d77c  pop
0x4d77d  ldarg.1
0x4d77e  ldstr    aExpectedversio// ", ExpectedVersion = "
0x4d783  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d788  pop
0x4d789  ldarg.1
0x4d78a  ldarg.0
0x4d78b  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_ExpectedVersion()
0x4d790  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d795  pop
0x4d796  ldarg.1
0x4d797  ldstr    aVisualstudiofl// ", VisualStudioFlights = "
0x4d79c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d7a1  pop
0x4d7a2  ldarg.1
0x4d7a3  ldarg.0
0x4d7a4  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_VisualStudioFlights()
0x4d7a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d7ae  pop
0x4d7af  ldarg.1
0x4d7b0  ldstr    aAdditionalexte// ", AdditionalExtensions = "
0x4d7b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d7ba  pop
0x4d7bb  ldarg.1
0x4d7bc  ldarg.0
0x4d7bd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions> Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_AdditionalExtensions()
0x4d7c2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d7c7  pop
0x4d7c8  ldarg.1
0x4d7c9  ldstr    aLayouturi// ", LayoutUri = "
0x4d7ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d7d3  pop
0x4d7d4  ldarg.1
0x4d7d5  ldarg.0
0x4d7d6  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_LayoutUri()
0x4d7db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d7e0  pop
0x4d7e1  ldarg.1
0x4d7e2  ldstr    aInstallchannel_1// ", InstallChannelUri = "
0x4d7e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d7ec  pop
0x4d7ed  ldarg.1
0x4d7ee  ldarg.0
0x4d7ef  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_InstallChannelUri()
0x4d7f4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d7f9  pop
0x4d7fa  ldarg.1
0x4d7fb  ldstr    aInstallcatalog// ", InstallCatalogUri = "
0x4d800  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d805  pop
0x4d806  ldarg.1
0x4d807  ldarg.0
0x4d808  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_InstallCatalogUri()
0x4d80d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4d812  pop
0x4d813  ldarg.1
0x4d814  ldstr    aIncluderecomme_0// ", IncludeRecommendedOnUpdate = "
0x4d819  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d81e  pop
0x4d81f  ldarg.1
0x4d820  ldarg.0
0x4d821  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions::get_IncludeRecommendedOnUpdate()
0x4d826  stloc.1
0x4d827  ldloca.s 1
0x4d829  constrained. [mscorlib]System.Boolean
0x4d82f  callvirt instance string [mscorlib]System.Object::ToString()
0x4d834  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d839  pop
0x4d83a  ldc.i4.1
0x4d83b  ret
```
