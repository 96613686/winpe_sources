# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix

- ea: `0x33010`
- end: `0x330b3`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x322d0`
- `0x328b0`

## callees

- `0xf0e0`
- `0x31e90`
- `0x33010`
- `0x33140`
- `0x6d1c0`

## string_xrefs

- `0x33021`: `[extensiondir]`
- `0x33030`: `[extensiondir]`

## pseudocode

```c

```

## disassembly

```asm
0x33010  ldarg.0
0x33011  ldarg.3
0x33012  ldarg.2
0x33013  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixType(string vsixPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage)
0x33018  stloc.0
0x33019  ldloc.0
0x3301a  ldc.i4.2
0x3301b  bne.un   loc_330B1
0x33020  ldarg.1
0x33021  ldstr    aExtensiondir// "[extensiondir]"
0x33026  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x3302b  brfalse.s loc_33042
0x3302d  ldarg.s  5
0x3302f  ldarg.1
0x33030  ldstr    aExtensiondir// "[extensiondir]"
0x33035  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x3303a  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3303f  stind.ref
0x33040  br.s     loc_33053
0x33042  ldarg.s  5
0x33044  ldarg.2
0x33045  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x3304a  ldarg.1
0x3304b  ldnull
0x3304c  ldc.i4.0
0x3304d  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33052  stind.ref
0x33053  ldarg.s  5
0x33055  ldind.ref
0x33056  ldarg.s  4
0x33058  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x3305d  brtrue.s loc_33065
0x3305f  newobj   instance void InvalidExtensionDirException::.ctor()
0x33064  throw
0x33065  ldarg.0
0x33066  ldarg.1
0x33067  ldarg.2
0x33068  brtrue.s loc_3306D
0x3306a  ldnull
0x3306b  br.s     loc_33073
0x3306d  ldarg.2
0x3306e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_FolderMappings()
0x33073  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetResolvedFolderMappings(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> folderMappings)
0x33078  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x3307d  stloc.1
0x3307e  br.s     loc_3309D
0x33080  ldloc.1
0x33081  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x33086  stloc.2
0x33087  ldloca.s 2
0x33089  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3308e  ldarg.s  4
0x33090  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x33095  brtrue.s loc_3309D
0x33097  newobj   instance void InvalidExtensionDirException::.ctor()
0x3309c  throw
0x3309d  ldloc.1
0x3309e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x330a3  brtrue.s loc_33080
0x330a5  leave.s  loc_330B1
0x330a7  ldloc.1
0x330a8  brfalse.s loc_330B0
0x330aa  ldloc.1
0x330ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x330b0  endfinally
0x330b1  ldloc.0
0x330b2  ret
```
