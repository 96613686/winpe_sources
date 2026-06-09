# System.Deployment.Application.ShellExposure::RemoveFileAssociation

- ea: `0x1e340`
- end: `0x1e39d`
- name: `System.Deployment.Application.ShellExposure::RemoveFileAssociation`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1d6f0`

## callees

- `0x17cd0`
- `0x1e340`
- `0x1e3a0`
- `0x1e430`
- `0x1e4e0`

## string_xrefs

- `0x1e356`: `RemoveFileAssociation(`

## pseudocode

```c

```

## disassembly

```asm
0x1e340  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0x1e345  ldstr    aSoftwareClasse_0// "Software\\Classes"
0x1e34a  ldc.i4.1
0x1e34b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1e350  stloc.0
0x1e351  ldloc.0
0x1e352  brtrue.s loc_1E356
0x1e354  leave.s  loc_1E39C
0x1e356  ldstr    aRemovefileasso// "RemoveFileAssociation("
0x1e35b  ldarg.0
0x1e35c  callvirt instance string [mscorlib]System.Object::ToString()
0x1e361  ldstr    aCalled// ") called."
0x1e366  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e36b  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1e370  ldarg.0
0x1e371  ldarg.1
0x1e372  ldloc.0
0x1e373  ldarg.2
0x1e374  call     void System.Deployment.Application.ShellExposure::RemoveFileAssociationExtentionInfo(class System.Deployment.Application.Manifest.FileAssociation fileAssociation, class System.Deployment.Application.DefinitionIdentity subId, class [mscorlib]Microsoft.Win32.RegistryKey classesKey, string productName)
0x1e379  ldarg.0
0x1e37a  ldarg.1
0x1e37b  ldloc.0
0x1e37c  ldarg.2
0x1e37d  call     string System.Deployment.Application.ShellExposure::RemoveFileAssociationProgIDInfo(class System.Deployment.Application.Manifest.FileAssociation fileAssociation, class System.Deployment.Application.DefinitionIdentity subId, class [mscorlib]Microsoft.Win32.RegistryKey classesKey, string productName)
0x1e382  stloc.1
0x1e383  ldloc.1
0x1e384  brfalse.s loc_1E390
0x1e386  ldarg.0
0x1e387  ldarg.1
0x1e388  ldloc.0
0x1e389  ldloc.1
0x1e38a  ldarg.2
0x1e38b  call     void System.Deployment.Application.ShellExposure::RemoveFileAssociationCLSIDInfo(class System.Deployment.Application.Manifest.FileAssociation fileAssociation, class System.Deployment.Application.DefinitionIdentity subId, class [mscorlib]Microsoft.Win32.RegistryKey classesKey, string clsIdString, string productName)
0x1e390  leave.s  loc_1E39C
0x1e392  ldloc.0
0x1e393  brfalse.s loc_1E39B
0x1e395  ldloc.0
0x1e396  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e39b  endfinally
0x1e39c  ret
```
