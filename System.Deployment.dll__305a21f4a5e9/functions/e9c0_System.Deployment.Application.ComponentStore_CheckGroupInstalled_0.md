# System.Deployment.Application.ComponentStore::CheckGroupInstalled_0

- ea: `0xe9c0`
- end: `0xea98`
- name: `System.Deployment.Application.ComponentStore::CheckGroupInstalled_0`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe9a0`
- `0x1fc20`

## callees

- `0xe920`
- `0xe9c0`
- `0x14780`
- `0x23020`
- `0x243c0`
- `0x247d0`
- `0x25100`
- `0x251a0`
- `0x27fb0`

## pseudocode

```c

```

## disassembly

```asm
0xe9c0  ldnull
0xe9c1  stloc.0
0xe9c2  ldarg.0
0xe9c3  ldarg.1
0xe9c4  call     instance class IPathLock System.Deployment.Application.ComponentStore::LockApplicationPath(class System.Deployment.Application.DefinitionAppId definitionAppId)
0xe9c9  stloc.0
0xe9ca  ldloc.0
0xe9cb  callvirt instance string IPathLock::get_Path()
0xe9d0  stloc.1
0xe9d1  ldarg.2
0xe9d2  ldarg.3
0xe9d3  ldc.i4.1
0xe9d4  callvirt instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::GetFilesInGroup(string group, bool optionalOnly)
0xe9d9  stloc.2
0xe9da  ldloc.2
0xe9db  stloc.s  4
0xe9dd  ldc.i4.0
0xe9de  stloc.s  5
0xe9e0  br.s     loc_EA0F
0xe9e2  ldloc.s  4
0xe9e4  ldloc.s  5
0xe9e6  ldelem.ref
0xe9e7  stloc.s  6
0xe9e9  ldloc.1
0xe9ea  ldloc.s  6
0xe9ec  callvirt instance string System.Deployment.Application.Manifest.File::get_NameFS()
0xe9f1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xe9f6  stloc.s  7
0xe9f8  ldloc.s  7
0xe9fa  call     bool [mscorlib]System.IO.File::Exists(string)
0xe9ff  brtrue.s loc_EA09
0xea01  ldc.i4.0
0xea02  stloc.s  8
0xea04  leave    loc_EA95
0xea09  ldloc.s  5
0xea0b  ldc.i4.1
0xea0c  add
0xea0d  stloc.s  5
0xea0f  ldloc.s  5
0xea11  ldloc.s  4
0xea13  ldlen
0xea14  conv.i4
0xea15  blt.s    loc_E9E2
0xea17  ldarg.2
0xea18  ldarg.3
0xea19  ldc.i4.1
0xea1a  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::GetPrivateAssembliesInGroup(string group, bool optionalOnly)
0xea1f  stloc.3
0xea20  ldloc.3
0xea21  stloc.s  9
0xea23  ldc.i4.0
0xea24  stloc.s  0xA
0xea26  br.s     loc_EA52
0xea28  ldloc.s  9
0xea2a  ldloc.s  0xA
0xea2c  ldelem.ref
0xea2d  stloc.s  0xB
0xea2f  ldloc.1
0xea30  ldloc.s  0xB
0xea32  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_CodebaseFS()
0xea37  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xea3c  stloc.s  0xC
0xea3e  ldloc.s  0xC
0xea40  call     bool [mscorlib]System.IO.File::Exists(string)
0xea45  brtrue.s loc_EA4C
0xea47  ldc.i4.0
0xea48  stloc.s  8
0xea4a  leave.s  loc_EA95
0xea4c  ldloc.s  0xA
0xea4e  ldc.i4.1
0xea4f  add
0xea50  stloc.s  0xA
0xea52  ldloc.s  0xA
0xea54  ldloc.s  9
0xea56  ldlen
0xea57  conv.i4
0xea58  blt.s    loc_EA28
0xea5a  ldloc.2
0xea5b  ldlen
0xea5c  conv.i4
0xea5d  ldloc.3
0xea5e  ldlen
0xea5f  conv.i4
0xea60  add
0xea61  brtrue.s loc_EA87
0xea63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xea68  ldstr    aExNosuchdownlo// "Ex_NoSuchDownloadGroup"
0xea6d  call     string System.Deployment.Application.Resources::GetString(string s)
0xea72  ldc.i4.1
0xea73  newarr   [mscorlib]System.Object
0xea78  dup
0xea79  ldc.i4.0
0xea7a  ldarg.3
0xea7b  stelem.ref
0xea7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xea81  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xea86  throw
0xea87  leave.s  loc_EA93
0xea89  ldloc.0
0xea8a  brfalse.s loc_EA92
0xea8c  ldloc.0
0xea8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xea92  endfinally
0xea93  ldc.i4.1
0xea94  ret
0xea95  ldloc.s  8
0xea97  ret
```
