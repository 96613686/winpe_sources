# Microsoft.VisualStudio.Setup.CommandLine::ParseCommandLine

- ea: `0x1df0`
- end: `0x1fa5`
- name: `Microsoft.VisualStudio.Setup.CommandLine::ParseCommandLine`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5380`

## callees

- `0x1c20`
- `0x1c40`
- `0x1c60`
- `0x1c80`
- `0x1ca0`
- `0x1cc0`
- `0x1ce0`
- `0x1d00`
- `0x1d20`
- `0x1d30`
- `0x1d50`
- `0x1d90`
- `0x1df0`
- `0x20a0`

## string_xrefs

- `0x1e93`: `updateCheck`
- `0x1efb`: `childClientInstallerVersion`
- `0x1f2c`: `installChannelUri`
- `0x1f5a`: `installChannelUri is not a valid absolute URI`

## pseudocode

```c

```

## disassembly

```asm
0x1df0  ldarg.1
0x1df1  brtrue.s loc_1DF9
0x1df3  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::Empty
0x1df8  ret
0x1df9  ldarg.0
0x1dfa  ldarg.1
0x1dfb  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_Args(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> value)
0x1e00  ldc.i4.0
0x1e01  stloc.0
0x1e02  br       loc_1F8D
0x1e07  ldarg.1
0x1e08  ldloc.0
0x1e09  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string>::get_Item(!!T0)
0x1e0e  stloc.1
0x1e0f  ldloc.1
0x1e10  ldloca.s 2
0x1e12  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetParameter(string arg, [out] string& param)
0x1e17  brfalse  loc_1F7D
0x1e1c  ldstr    aChild// "child"
0x1e21  ldloc.2
0x1e22  ldc.i4.5
0x1e23  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1e28  brfalse.s loc_1E36
0x1e2a  ldarg.0
0x1e2b  ldc.i4.1
0x1e2c  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_IsChildProcess(bool value)
0x1e31  br       loc_1F89
0x1e36  ldstr    aActivityid// "activityId"
0x1e3b  ldloc.2
0x1e3c  ldc.i4.5
0x1e3d  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1e42  brfalse.s loc_1E64
0x1e44  ldarg.1
0x1e45  ldloca.s 0
0x1e47  ldloca.s 3
0x1e49  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args, int32& i, [out] string& arg)
0x1e4e  brtrue.s loc_1E58
0x1e50  ldarg.0
0x1e51  ldloc.1
0x1e52  newobj   instance void Microsoft.VisualStudio.Setup.MissingArgumentException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command, string parameter)
0x1e57  throw
0x1e58  ldarg.0
0x1e59  ldloc.3
0x1e5a  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_ActivityId(string value)
0x1e5f  br       loc_1F89
0x1e64  ldstr    aInstanceid// "instanceId"
0x1e69  ldloc.2
0x1e6a  ldc.i4.5
0x1e6b  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1e70  brfalse.s loc_1E93
0x1e72  ldarg.1
0x1e73  ldloca.s 0
0x1e75  ldloca.s 4
0x1e77  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args, int32& i, [out] string& arg)
0x1e7c  brtrue.s loc_1E86
0x1e7e  ldarg.0
0x1e7f  ldloc.1
0x1e80  newobj   instance void Microsoft.VisualStudio.Setup.MissingArgumentException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command, string parameter)
0x1e85  throw
0x1e86  ldarg.0
0x1e87  ldloc.s  4
0x1e89  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_InstanceId(string value)
0x1e8e  br       loc_1F89
0x1e93  ldstr    aUpdatecheck// "updateCheck"
0x1e98  ldloc.2
0x1e99  ldc.i4.5
0x1e9a  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1e9f  brfalse.s loc_1EAD
0x1ea1  ldarg.0
0x1ea2  ldc.i4.1
0x1ea3  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_IsUpdateCheckOnly(bool value)
0x1ea8  br       loc_1F89
0x1ead  ldstr    aNocancel// "noCancel"
0x1eb2  ldloc.2
0x1eb3  ldc.i4.5
0x1eb4  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1eb9  brfalse.s loc_1EC7
0x1ebb  ldarg.0
0x1ebc  ldc.i4.0
0x1ebd  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_CanCancel(bool value)
0x1ec2  br       loc_1F89
0x1ec7  ldstr    aChildclientver// "childClientVersion"
0x1ecc  ldloc.2
0x1ecd  ldc.i4.5
0x1ece  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1ed3  brfalse.s loc_1EFB
0x1ed5  ldarg.1
0x1ed6  ldloca.s 0
0x1ed8  ldloca.s 5
0x1eda  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args, int32& i, [out] string& arg)
0x1edf  brtrue.s loc_1EE9
0x1ee1  ldarg.0
0x1ee2  ldloc.1
0x1ee3  newobj   instance void Microsoft.VisualStudio.Setup.MissingArgumentException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command, string parameter)
0x1ee8  throw
0x1ee9  ldarg.0
0x1eea  ldloc.s  5
0x1eec  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1ef1  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_ChildClientVersion(class [mscorlib]System.Version value)
0x1ef6  br       loc_1F89
0x1efb  ldstr    aChildclientins// "childClientInstallerVersion"
0x1f00  ldloc.2
0x1f01  ldc.i4.5
0x1f02  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1f07  brfalse.s loc_1F2C
0x1f09  ldarg.1
0x1f0a  ldloca.s 0
0x1f0c  ldloca.s 6
0x1f0e  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args, int32& i, [out] string& arg)
0x1f13  brtrue.s loc_1F1D
0x1f15  ldarg.0
0x1f16  ldloc.1
0x1f17  newobj   instance void Microsoft.VisualStudio.Setup.MissingArgumentException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command, string parameter)
0x1f1c  throw
0x1f1d  ldarg.0
0x1f1e  ldloc.s  6
0x1f20  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1f25  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_ChildClientInstallerVersion(class [mscorlib]System.Version value)
0x1f2a  br.s     loc_1F89
0x1f2c  ldstr    aInstallchannel// "installChannelUri"
0x1f31  ldloc.2
0x1f32  ldc.i4.5
0x1f33  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1f38  brfalse.s loc_1F6F
0x1f3a  ldarg.1
0x1f3b  ldloca.s 0
0x1f3d  ldloca.s 7
0x1f3f  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args, int32& i, [out] string& arg)
0x1f44  brtrue.s loc_1F4E
0x1f46  ldarg.0
0x1f47  ldloc.1
0x1f48  newobj   instance void Microsoft.VisualStudio.Setup.MissingArgumentException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command, string parameter)
0x1f4d  throw
0x1f4e  ldloc.s  7
0x1f50  ldc.i4.1
0x1f51  ldloca.s 8
0x1f53  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x1f58  brtrue.s loc_1F65
0x1f5a  ldstr    aInstallchannel_0// "installChannelUri is not a valid absolu"...
0x1f5f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1f64  throw
0x1f65  ldarg.0
0x1f66  ldloc.s  8
0x1f68  call     instance void Microsoft.VisualStudio.Setup.CommandLine::set_InstallChannelUri(class [System]System.Uri value)
0x1f6d  br.s     loc_1F89
0x1f6f  ldarg.0
0x1f70  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CommandLine::get_UnknownArguments()
0x1f75  ldloc.1
0x1f76  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x1f7b  br.s     loc_1F89
0x1f7d  ldarg.0
0x1f7e  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CommandLine::get_UnknownArguments()
0x1f83  ldloc.1
0x1f84  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x1f89  ldloc.0
0x1f8a  ldc.i4.1
0x1f8b  add
0x1f8c  stloc.0
0x1f8d  ldloc.0
0x1f8e  ldarg.1
0x1f8f  callvirt instance int32 class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string>::get_Count()
0x1f94  blt      loc_1E07
0x1f99  ldarg.0
0x1f9a  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CommandLine::get_UnknownArguments()
0x1f9f  castclass class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string>
0x1fa4  ret
```
