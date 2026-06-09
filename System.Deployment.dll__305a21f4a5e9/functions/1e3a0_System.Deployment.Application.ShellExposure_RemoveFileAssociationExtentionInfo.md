# System.Deployment.Application.ShellExposure::RemoveFileAssociationExtentionInfo

- ea: `0x1e3a0`
- end: `0x1e42b`
- name: `System.Deployment.Application.ShellExposure::RemoveFileAssociationExtentionInfo`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1e340`

## callees

- `0x14700`
- `0x1e3a0`
- `0x23020`
- `0x24490`

## string_xrefs

- `0x1e3f7`: `Ex_FileAssocExtDeleteFailed`

## pseudocode

```c

```

## disassembly

```asm
0x1e3a0  ldarg.2
0x1e3a1  ldarg.0
0x1e3a2  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e3a7  ldc.i4.1
0x1e3a8  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1e3ad  stloc.0
0x1e3ae  ldloc.0
0x1e3af  brtrue.s loc_1E3B3
0x1e3b1  leave.s  loc_1E42A
0x1e3b3  ldloc.0
0x1e3b4  ldstr    aAppid_0// "AppId"
0x1e3b9  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1e3be  stloc.1
0x1e3bf  ldloc.1
0x1e3c0  isinst   [mscorlib]System.String
0x1e3c5  brtrue.s loc_1E3C9
0x1e3c7  leave.s  loc_1E42A
0x1e3c9  ldloc.1
0x1e3ca  castclass [mscorlib]System.String
0x1e3cf  stloc.2
0x1e3d0  ldloc.2
0x1e3d1  ldarg.1
0x1e3d2  callvirt instance string [mscorlib]System.Object::ToString()
0x1e3d7  ldc.i4.4
0x1e3d8  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1e3dd  brtrue.s loc_1E3E1
0x1e3df  leave.s  loc_1E42A
0x1e3e1  nop
0x1e3e2  ldarg.2
0x1e3e3  ldarg.0
0x1e3e4  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e3e9  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x1e3ee  leave.s  loc_1E42A
0x1e3f0  stloc.3
0x1e3f1  ldc.i4.5
0x1e3f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1e3f7  ldstr    aExFileassocext// "Ex_FileAssocExtDeleteFailed"
0x1e3fc  call     string System.Deployment.Application.Resources::GetString(string s)
0x1e401  ldc.i4.2
0x1e402  newarr   [mscorlib]System.Object
0x1e407  dup
0x1e408  ldc.i4.0
0x1e409  ldarg.0
0x1e40a  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e40f  stelem.ref
0x1e410  dup
0x1e411  ldc.i4.1
0x1e412  ldarg.3
0x1e413  stelem.ref
0x1e414  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e419  ldloc.3
0x1e41a  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1e41f  throw
0x1e420  ldloc.0
0x1e421  brfalse.s loc_1E429
0x1e423  ldloc.0
0x1e424  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e429  endfinally
0x1e42a  ret
```
