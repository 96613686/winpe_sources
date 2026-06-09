# System.Deployment.Application.ShellExposure::RemoveFileAssociationCLSIDInfo

- ea: `0x1e4e0`
- end: `0x1e57d`
- name: `System.Deployment.Application.ShellExposure::RemoveFileAssociationCLSIDInfo`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1e340`

## callees

- `0x14700`
- `0x1e4e0`
- `0x23020`

## string_xrefs

- `0x1e4e1`: `CLSID`
- `0x1e542`: `Ex_FileAssocCLSIDDeleteFailed`

## pseudocode

```c

```

## disassembly

```asm
0x1e4e0  ldarg.2
0x1e4e1  ldstr    aClsid// "CLSID"
0x1e4e6  ldc.i4.1
0x1e4e7  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1e4ec  stloc.0
0x1e4ed  ldloc.0
0x1e4ee  brtrue.s loc_1E4F5
0x1e4f0  leave    loc_1E57C
0x1e4f5  ldloc.0
0x1e4f6  ldarg.3
0x1e4f7  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1e4fc  stloc.1
0x1e4fd  ldloc.1
0x1e4fe  brtrue.s loc_1E502
0x1e500  leave.s  loc_1E57C
0x1e502  ldloc.1
0x1e503  ldstr    aAppid_0// "AppId"
0x1e508  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1e50d  stloc.2
0x1e50e  ldloc.2
0x1e50f  isinst   [mscorlib]System.String
0x1e514  brtrue.s loc_1E518
0x1e516  leave.s  loc_1E57C
0x1e518  ldloc.2
0x1e519  castclass [mscorlib]System.String
0x1e51e  stloc.3
0x1e51f  ldloc.3
0x1e520  ldarg.1
0x1e521  callvirt instance string [mscorlib]System.Object::ToString()
0x1e526  ldc.i4.4
0x1e527  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1e52c  brtrue.s loc_1E530
0x1e52e  leave.s  loc_1E57C
0x1e530  nop
0x1e531  ldloc.0
0x1e532  ldarg.3
0x1e533  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x1e538  leave.s  loc_1E57C
0x1e53a  stloc.s  4
0x1e53c  ldc.i4.5
0x1e53d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1e542  ldstr    aExFileassoccls// "Ex_FileAssocCLSIDDeleteFailed"
0x1e547  call     string System.Deployment.Application.Resources::GetString(string s)
0x1e54c  ldc.i4.2
0x1e54d  newarr   [mscorlib]System.Object
0x1e552  dup
0x1e553  ldc.i4.0
0x1e554  ldarg.3
0x1e555  stelem.ref
0x1e556  dup
0x1e557  ldc.i4.1
0x1e558  ldarg.s  4
0x1e55a  stelem.ref
0x1e55b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e560  ldloc.s  4
0x1e562  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1e567  throw
0x1e568  ldloc.1
0x1e569  brfalse.s loc_1E571
0x1e56b  ldloc.1
0x1e56c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e571  endfinally
0x1e572  ldloc.0
0x1e573  brfalse.s loc_1E57B
0x1e575  ldloc.0
0x1e576  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e57b  endfinally
0x1e57c  ret
```
