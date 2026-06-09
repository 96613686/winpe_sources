# System.Deployment.Application.ShellExposure::RemoveArpEntry

- ea: `0x1e740`
- end: `0x1e798`
- name: `System.Deployment.Application.ShellExposure::RemoveArpEntry`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d5f0`

## callees

- `0x14700`
- `0x1e740`
- `0x1e7a0`
- `0x1e7d0`
- `0x23020`

## string_xrefs

- `0x1e745`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c

```

## disassembly

```asm
0x1e740  call     class [mscorlib]Microsoft.Win32.RegistryKey System.Deployment.Application.ShellExposure::get_UninstallRoot()
0x1e745  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1e74a  ldc.i4.1
0x1e74b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1e750  stloc.0
0x1e751  ldnull
0x1e752  stloc.1
0x1e753  ldloc.0
0x1e754  brfalse.s loc_1E764
0x1e756  ldarg.0
0x1e757  call     string System.Deployment.Application.ShellExposure::GenerateArpKeyName(class System.Deployment.Application.DefinitionIdentity subId)
0x1e75c  stloc.1
0x1e75d  ldloc.0
0x1e75e  ldloc.1
0x1e75f  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x1e764  leave.s  loc_1E797
0x1e766  stloc.2
0x1e767  ldc.i4.5
0x1e768  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1e76d  ldstr    aExArpentryremo// "Ex_ArpEntryRemovalFailure"
0x1e772  call     string System.Deployment.Application.Resources::GetString(string s)
0x1e777  ldc.i4.1
0x1e778  newarr   [mscorlib]System.Object
0x1e77d  dup
0x1e77e  ldc.i4.0
0x1e77f  ldloc.1
0x1e780  stelem.ref
0x1e781  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e786  ldloc.2
0x1e787  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1e78c  throw
0x1e78d  ldloc.0
0x1e78e  brfalse.s loc_1E796
0x1e790  ldloc.0
0x1e791  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e796  endfinally
0x1e797  ret
```
