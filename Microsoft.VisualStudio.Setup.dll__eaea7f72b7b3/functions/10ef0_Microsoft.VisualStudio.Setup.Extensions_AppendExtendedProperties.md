# Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties

- ea: `0x10ef0`
- end: `0x10f5e`
- name: `Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x32270`
- `0x322d0`
- `0x328b0`
- `0x5e000`

## callees

- `0xf0e0`
- `0x10ef0`

## string_xrefs

- `0x10ef9`: `[installdir]`
- `0x10f06`: `[installdir]`
- `0x10f2d`: `[extensiondir]`
- `0x10f52`: `[extensiondir]`

## pseudocode

```c

```

## disassembly

```asm
0x10ef0  ldarg.2
0x10ef1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10ef6  brtrue.s loc_10F11
0x10ef8  ldarg.0
0x10ef9  ldstr    aInstalldir_0// "[installdir]"
0x10efe  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x10f03  brtrue.s loc_10F11
0x10f05  ldarg.0
0x10f06  ldstr    aInstalldir_0// "[installdir]"
0x10f0b  ldarg.2
0x10f0c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x10f11  ldarg.2
0x10f12  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10f17  brtrue.s loc_10F5D
0x10f19  ldarg.1
0x10f1a  brtrue.s loc_10F1F
0x10f1c  ldnull
0x10f1d  br.s     loc_10F25
0x10f1f  ldarg.1
0x10f20  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x10f25  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10f2a  brtrue.s loc_10F5D
0x10f2c  ldarg.0
0x10f2d  ldstr    aExtensiondir// "[extensiondir]"
0x10f32  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x10f37  brtrue.s loc_10F5D
0x10f39  ldarg.1
0x10f3a  brtrue.s loc_10F3F
0x10f3c  ldnull
0x10f3d  br.s     loc_10F4D
0x10f3f  ldarg.1
0x10f40  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x10f45  ldarg.0
0x10f46  ldnull
0x10f47  ldc.i4.0
0x10f48  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x10f4d  stloc.0
0x10f4e  ldloc.0
0x10f4f  brfalse.s loc_10F5D
0x10f51  ldarg.0
0x10f52  ldstr    aExtensiondir// "[extensiondir]"
0x10f57  ldloc.0
0x10f58  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x10f5d  ret
```
