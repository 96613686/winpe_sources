# System.Deployment.Application.ShellExposure::AddFileAssociation

- ea: `0x1e0d0`
- end: `0x1e33a`
- name: `System.Deployment.Application.ShellExposure::AddFileAssociation`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1dfc0`

## callees

- `0x17d40`
- `0x1dff0`
- `0x1e0d0`
- `0x24490`
- `0x244a0`
- `0x244b0`
- `0x244c0`

## string_xrefs

- `0x1e1be`: `open\command`
- `0x1e1cd`: `rundll32.exe dfshim.dll, ShOpenVerbExtension `
- `0x1e1ea`: `File association created. Extension=`
- `0x1e1fb`: ` value=rundll32.exe dfshim.dll, ShOpenVerbExtension `
- `0x1e23c`: `File association icon handler created. Extension=`
- `0x1e27e`: `CLSID`
- `0x1e2ee`: `dfshim.dll`
- `0x1e2fa`: `ThreadingModel`

## pseudocode

```c

```

## disassembly

```asm
0x1e0d0  ldarg.0
0x1e0d1  call     bool System.Deployment.Application.ShellExposure::CanAddFileAssociation(class System.Deployment.Application.Manifest.FileAssociation fileAssociation)
0x1e0d6  brtrue.s loc_1E0D9
0x1e0d8  ret
0x1e0d9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1e0de  stloc.0
0x1e0df  ldloca.s 0
0x1e0e1  ldstr    aB// "B"
0x1e0e6  call     instance string [mscorlib]System.Guid::ToString(string)
0x1e0eb  stloc.1
0x1e0ec  ldarg.1
0x1e0ed  callvirt instance string [mscorlib]System.Object::ToString()
0x1e0f2  stloc.2
0x1e0f3  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0x1e0f8  ldstr    aSoftwareClasse_0// "Software\\Classes"
0x1e0fd  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e102  stloc.3
0x1e103  ldloc.3
0x1e104  ldarg.0
0x1e105  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e10a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e10f  stloc.s  4
0x1e111  ldloc.s  4
0x1e113  ldnull
0x1e114  ldarg.0
0x1e115  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e11a  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e11f  ldloc.s  4
0x1e121  ldstr    aAppid_0// "AppId"
0x1e126  ldloc.2
0x1e127  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e12c  ldloc.s  4
0x1e12e  ldstr    aGuid// "Guid"
0x1e133  ldloc.1
0x1e134  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e139  ldloc.s  4
0x1e13b  ldstr    aDeploymentprov_1// "DeploymentProviderUrl"
0x1e140  ldarg.2
0x1e141  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1e146  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e14b  leave.s  loc_1E159
0x1e14d  ldloc.s  4
0x1e14f  brfalse.s loc_1E158
0x1e151  ldloc.s  4
0x1e153  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e158  endfinally
0x1e159  ldloc.3
0x1e15a  ldarg.0
0x1e15b  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e160  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e165  stloc.s  5
0x1e167  ldloc.s  5
0x1e169  ldnull
0x1e16a  ldarg.0
0x1e16b  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Description()
0x1e170  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e175  ldloc.s  5
0x1e177  ldstr    aAppid_0// "AppId"
0x1e17c  ldloc.2
0x1e17d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e182  ldloc.s  5
0x1e184  ldstr    aGuid// "Guid"
0x1e189  ldloc.1
0x1e18a  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e18f  ldloc.s  5
0x1e191  ldstr    aDeploymentprov_1// "DeploymentProviderUrl"
0x1e196  ldarg.2
0x1e197  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1e19c  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e1a1  ldloc.s  5
0x1e1a3  ldstr    aShell// "shell"
0x1e1a8  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e1ad  stloc.s  6
0x1e1af  ldloc.s  6
0x1e1b1  ldnull
0x1e1b2  ldstr    aOpen// "open"
0x1e1b7  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e1bc  ldloc.s  6
0x1e1be  ldstr    aOpenCommand// "open\\command"
0x1e1c3  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e1c8  stloc.s  7
0x1e1ca  ldloc.s  7
0x1e1cc  ldnull
0x1e1cd  ldstr    aRundll32ExeDfs// "rundll32.exe dfshim.dll, ShOpenVerbExte"...
0x1e1d2  ldloc.1
0x1e1d3  ldstr    a1// " %1"
0x1e1d8  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e1dd  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e1e2  ldc.i4.5
0x1e1e3  newarr   [mscorlib]System.String
0x1e1e8  dup
0x1e1e9  ldc.i4.0
0x1e1ea  ldstr    aFileAssociatio_0// "File association created. Extension="
0x1e1ef  stelem.ref
0x1e1f0  dup
0x1e1f1  ldc.i4.1
0x1e1f2  ldarg.0
0x1e1f3  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e1f8  stelem.ref
0x1e1f9  dup
0x1e1fa  ldc.i4.2
0x1e1fb  ldstr    aValueRundll32E// " value=rundll32.exe dfshim.dll, ShOpenV"...
0x1e200  stelem.ref
0x1e201  dup
0x1e202  ldc.i4.3
0x1e203  ldloc.1
0x1e204  stelem.ref
0x1e205  dup
0x1e206  ldc.i4.4
0x1e207  ldstr    a1// " %1"
0x1e20c  stelem.ref
0x1e20d  call     string [mscorlib]System.String::Concat(string[])
0x1e212  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e217  leave.s  loc_1E225
0x1e219  ldloc.s  7
0x1e21b  brfalse.s loc_1E224
0x1e21d  ldloc.s  7
0x1e21f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e224  endfinally
0x1e225  ldloc.s  5
0x1e227  ldstr    aShellexIconhan// "shellex\\IconHandler"
0x1e22c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e231  stloc.s  8
0x1e233  ldloc.s  8
0x1e235  ldnull
0x1e236  ldloc.1
0x1e237  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e23c  ldstr    aFileAssociatio_1// "File association icon handler created. "...
0x1e241  ldarg.0
0x1e242  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e247  ldstr    aValue_0// " value="
0x1e24c  ldloc.1
0x1e24d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1e252  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e257  leave.s  loc_1E27D
0x1e259  ldloc.s  8
0x1e25b  brfalse.s loc_1E264
0x1e25d  ldloc.s  8
0x1e25f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e264  endfinally
0x1e265  ldloc.s  6
0x1e267  brfalse.s loc_1E270
0x1e269  ldloc.s  6
0x1e26b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e270  endfinally
0x1e271  ldloc.s  5
0x1e273  brfalse.s loc_1E27C
0x1e275  ldloc.s  5
0x1e277  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e27c  endfinally
0x1e27d  ldloc.3
0x1e27e  ldstr    aClsid// "CLSID"
0x1e283  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e288  stloc.s  9
0x1e28a  ldloc.s  9
0x1e28c  ldloc.1
0x1e28d  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e292  stloc.s  0xA
0x1e294  ldloc.s  0xA
0x1e296  ldnull
0x1e297  ldstr    aShellIconHandl// "Shell Icon Handler For "
0x1e29c  ldarg.0
0x1e29d  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Description()
0x1e2a2  call     string [mscorlib]System.String::Concat(string, string)
0x1e2a7  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e2ac  ldloc.s  0xA
0x1e2ae  ldstr    aAppid_0// "AppId"
0x1e2b3  ldloc.2
0x1e2b4  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e2b9  ldloc.s  0xA
0x1e2bb  ldstr    aDeploymentprov_1// "DeploymentProviderUrl"
0x1e2c0  ldarg.2
0x1e2c1  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1e2c6  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e2cb  ldloc.s  0xA
0x1e2cd  ldstr    aIconfile_0// "IconFile"
0x1e2d2  ldarg.0
0x1e2d3  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_DefaultIcon()
0x1e2d8  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e2dd  ldloc.s  0xA
0x1e2df  ldstr    aInprocserver32// "InProcServer32"
0x1e2e4  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e2e9  stloc.s  0xB
0x1e2eb  ldloc.s  0xB
0x1e2ed  ldnull
0x1e2ee  ldstr    aDfshimDll// "dfshim.dll"
0x1e2f3  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e2f8  ldloc.s  0xB
0x1e2fa  ldstr    aThreadingmodel// "ThreadingModel"
0x1e2ff  ldstr    aApartment// "Apartment"
0x1e304  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e309  leave.s  loc_1E339
0x1e30b  ldloc.s  0xB
0x1e30d  brfalse.s loc_1E316
0x1e30f  ldloc.s  0xB
0x1e311  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e316  endfinally
0x1e317  ldloc.s  0xA
0x1e319  brfalse.s loc_1E322
0x1e31b  ldloc.s  0xA
0x1e31d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e322  endfinally
0x1e323  ldloc.s  9
0x1e325  brfalse.s loc_1E32E
0x1e327  ldloc.s  9
0x1e329  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e32e  endfinally
0x1e32f  ldloc.3
0x1e330  brfalse.s loc_1E338
0x1e332  ldloc.3
0x1e333  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e338  endfinally
0x1e339  ret
```
