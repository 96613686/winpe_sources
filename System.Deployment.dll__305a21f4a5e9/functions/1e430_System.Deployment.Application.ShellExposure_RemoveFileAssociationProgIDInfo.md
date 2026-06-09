# System.Deployment.Application.ShellExposure::RemoveFileAssociationProgIDInfo

- ea: `0x1e430`
- end: `0x1e4df`
- name: `System.Deployment.Application.ShellExposure::RemoveFileAssociationProgIDInfo`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1e340`

## callees

- `0x14700`
- `0x1e430`
- `0x23020`
- `0x244b0`

## string_xrefs

- `0x1e4a6`: `Ex_FileAssocProgIdDeleteFailed`

## pseudocode

```c

```

## disassembly

```asm
0x1e430  ldnull
0x1e431  stloc.0
0x1e432  ldarg.2
0x1e433  ldarg.0
0x1e434  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e439  ldc.i4.1
0x1e43a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1e43f  stloc.1
0x1e440  ldloc.1
0x1e441  brtrue.s loc_1E44B
0x1e443  ldnull
0x1e444  stloc.s  4
0x1e446  leave    loc_1E4DC
0x1e44b  ldloc.1
0x1e44c  ldstr    aAppid_0// "AppId"
0x1e451  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1e456  stloc.2
0x1e457  ldloc.2
0x1e458  isinst   [mscorlib]System.String
0x1e45d  brtrue.s loc_1E464
0x1e45f  ldnull
0x1e460  stloc.s  4
0x1e462  leave.s  loc_1E4DC
0x1e464  ldloc.2
0x1e465  castclass [mscorlib]System.String
0x1e46a  stloc.3
0x1e46b  ldloc.3
0x1e46c  ldarg.1
0x1e46d  callvirt instance string [mscorlib]System.Object::ToString()
0x1e472  ldc.i4.4
0x1e473  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1e478  brtrue.s loc_1E47F
0x1e47a  ldnull
0x1e47b  stloc.s  4
0x1e47d  leave.s  loc_1E4DC
0x1e47f  ldloc.1
0x1e480  ldstr    aGuid// "Guid"
0x1e485  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1e48a  castclass [mscorlib]System.String
0x1e48f  stloc.0
0x1e490  ldarg.2
0x1e491  ldarg.0
0x1e492  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e497  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x1e49c  leave.s  loc_1E4DA
0x1e49e  stloc.s  5
0x1e4a0  ldc.i4.5
0x1e4a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1e4a6  ldstr    aExFileassocpro// "Ex_FileAssocProgIdDeleteFailed"
0x1e4ab  call     string System.Deployment.Application.Resources::GetString(string s)
0x1e4b0  ldc.i4.2
0x1e4b1  newarr   [mscorlib]System.Object
0x1e4b6  dup
0x1e4b7  ldc.i4.0
0x1e4b8  ldarg.0
0x1e4b9  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e4be  stelem.ref
0x1e4bf  dup
0x1e4c0  ldc.i4.1
0x1e4c1  ldarg.3
0x1e4c2  stelem.ref
0x1e4c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e4c8  ldloc.s  5
0x1e4ca  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1e4cf  throw
0x1e4d0  ldloc.1
0x1e4d1  brfalse.s loc_1E4D9
0x1e4d3  ldloc.1
0x1e4d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e4d9  endfinally
0x1e4da  ldloc.0
0x1e4db  ret
0x1e4dc  ldloc.s  4
0x1e4de  ret
```
