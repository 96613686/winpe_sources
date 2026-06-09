# SummarySection::ToString

- ea: `0x29ab0`
- end: `0x29b6b`
- name: `SummarySection::ToString`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x23020`
- `0x23dc0`
- `0x23fe0`
- `0x23ff0`
- `0x24b90`
- `0x24f90`
- `0x29ab0`

## string_xrefs

- `0x29ae5`: `LogFile_SummaryInstallableApp`

## pseudocode

```c

```

## disassembly

```asm
0x29ab0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x29ab5  stloc.0
0x29ab6  ldarg.0
0x29ab7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest SummarySection::_deploymentManifest
0x29abc  brfalse  loc_29B64
0x29ac1  ldloc.0
0x29ac2  ldstr    aLogfileSummary// "LogFile_Summary"
0x29ac7  call     string System.Deployment.Application.Resources::GetString(string s)
0x29acc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29ad1  pop
0x29ad2  ldarg.0
0x29ad3  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest SummarySection::_deploymentManifest
0x29ad8  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x29add  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x29ae2  brfalse.s loc_29AF7
0x29ae4  ldloc.0
0x29ae5  ldstr    aLogfileSummary_0// "LogFile_SummaryInstallableApp"
0x29aea  call     string System.Deployment.Application.Resources::GetString(string s)
0x29aef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29af4  pop
0x29af5  br.s     loc_29B08
0x29af7  ldloc.0
0x29af8  ldstr    aLogfileSummary_1// "LogFile_SummaryOnlineOnlyApp"
0x29afd  call     string System.Deployment.Application.Resources::GetString(string s)
0x29b02  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29b07  pop
0x29b08  ldarg.0
0x29b09  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest SummarySection::_deploymentManifest
0x29b0e  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x29b13  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_TrustURLParameters()
0x29b18  brfalse.s loc_29B2B
0x29b1a  ldloc.0
0x29b1b  ldstr    aLogfileSummary_2// "LogFile_SummaryTrustUrlParameterSet"
0x29b20  call     string System.Deployment.Application.Resources::GetString(string s)
0x29b25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29b2a  pop
0x29b2b  ldarg.0
0x29b2c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest SummarySection::_applicationManifest
0x29b31  brfalse.s loc_29B58
0x29b33  ldarg.0
0x29b34  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest SummarySection::_applicationManifest
0x29b39  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x29b3e  ldc.i4.0
0x29b3f  ldelem.ref
0x29b40  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_HostInBrowser()
0x29b45  brfalse.s loc_29B58
0x29b47  ldloc.0
0x29b48  ldstr    aLogfileSummary_3// "LogFile_SummaryBrowserHostedApp"
0x29b4d  call     string System.Deployment.Application.Resources::GetString(string s)
0x29b52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29b57  pop
0x29b58  ldloc.0
0x29b59  call     string [mscorlib]System.Environment::get_NewLine()
0x29b5e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29b63  pop
0x29b64  ldloc.0
0x29b65  callvirt instance string [mscorlib]System.Object::ToString()
0x29b6a  ret
```
