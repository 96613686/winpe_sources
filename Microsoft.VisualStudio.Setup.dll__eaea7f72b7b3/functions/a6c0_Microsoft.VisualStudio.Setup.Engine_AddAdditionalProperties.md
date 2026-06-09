# Microsoft.VisualStudio.Setup.Engine::AddAdditionalProperties

- ea: `0xa6c0`
- end: `0xa79e`
- name: `Microsoft.VisualStudio.Setup.Engine::AddAdditionalProperties`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9fe0`

## callees

- `0x7e40`
- `0xa6c0`
- `0x1cda0`
- `0x3eaf0`
- `0x3eb70`

## string_xrefs

- `0xa6c6`: `InstallDir`
- `0xa6dd`: `SharedInstallDir`
- `0xa6f9`: `SharedInstallDrive`
- `0xa72f`: `CompatInstallDir`

## pseudocode

```c

```

## disassembly

```asm
0xa6c0  ldarg.0
0xa6c1  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa6c6  ldstr    aInstalldir// "InstallDir"
0xa6cb  ldarg.1
0xa6cc  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0xa6d1  ldc.i4.0
0xa6d2  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa6d7  ldarg.0
0xa6d8  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa6dd  ldstr    aSharedinstalld// "SharedInstallDir"
0xa6e2  ldarg.0
0xa6e3  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Engine::policy
0xa6e8  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0xa6ed  ldc.i4.0
0xa6ee  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa6f3  ldarg.0
0xa6f4  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa6f9  ldstr    aSharedinstalld_0// "SharedInstallDrive"
0xa6fe  ldarg.0
0xa6ff  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Engine::policy
0xa704  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0xa709  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa70e  brtrue.s loc_A722
0xa710  ldarg.0
0xa711  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Engine::policy
0xa716  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0xa71b  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0xa720  br.s     loc_A723
0xa722  ldnull
0xa723  ldc.i4.0
0xa724  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa729  ldarg.0
0xa72a  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa72f  ldstr    aCompatinstalld// "CompatInstallDir"
0xa734  ldarg.0
0xa735  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Engine::policy
0xa73a  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CompatibilityInstallationPath()
0xa73f  ldc.i4.0
0xa740  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa745  ldarg.0
0xa746  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa74b  ldstr    aProductdisplay// "ProductDisplayVersion"
0xa750  ldarg.1
0xa751  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_CatalogInfo()
0xa756  dup
0xa757  brtrue.s loc_A75D
0xa759  pop
0xa75a  ldnull
0xa75b  br.s     loc_A762
0xa75d  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_ProductDisplayVersion()
0xa762  dup
0xa763  brtrue.s loc_A76B
0xa765  pop
0xa766  ldsfld   string [mscorlib]System.String::Empty
0xa76b  ldc.i4.0
0xa76c  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa771  ldarg.0
0xa772  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xa777  ldstr    aProductsemanti// "ProductSemanticVersion"
0xa77c  ldarg.1
0xa77d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_CatalogInfo()
0xa782  dup
0xa783  brtrue.s loc_A789
0xa785  pop
0xa786  ldnull
0xa787  br.s     loc_A78E
0xa789  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_ProductSemanticVersion()
0xa78e  dup
0xa78f  brtrue.s loc_A797
0xa791  pop
0xa792  ldsfld   string [mscorlib]System.String::Empty
0xa797  ldc.i4.0
0xa798  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0xa79d  ret
```
