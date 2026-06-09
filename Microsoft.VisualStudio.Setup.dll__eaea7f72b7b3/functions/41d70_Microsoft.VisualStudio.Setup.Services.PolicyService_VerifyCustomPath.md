# Microsoft.VisualStudio.Setup.Services.PolicyService::VerifyCustomPath

- ea: `0x41d70`
- end: `0x41ef1`
- name: `Microsoft.VisualStudio.Setup.Services.PolicyService::VerifyCustomPath`
- size: `385`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1bb40`
- `0x41f80`
- `0x4f410`
- `0x4f430`

## callees

- `0x199a0`
- `0x41d70`

## string_xrefs

- `0x41d71`: `services`
- `0x41edb`: `DirectoryNotEmpty_Args1`
- `0x41dcd`: `InvalidDirectory_Args1`
- `0x41def`: `PathNotRooted_Args1`
- `0x41e4c`: `PathToLongMaxAllowed_Cache_Args1`
- `0x41e6b`: `PathToLongMaxAllowed_Shared_Args1`
- `0x41e8a`: `PathToLongMaxAllowedIs_Args1`
- `0x41d7c`: `customPath`

## pseudocode

```c

```

## disassembly

```asm
0x41d70  ldarg.0
0x41d71  ldstr    aServices// "services"
0x41d76  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x41d7b  ldarg.1
0x41d7c  ldstr    aCustompath// "customPath"
0x41d81  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x41d86  ldarg.0
0x41d87  ldc.i4.0
0x41d88  call     T0x2B00000C
0x41d8d  dup
0x41d8e  brtrue.s loc_41D96
0x41d90  pop
0x41d91  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x41d96  stloc.0
0x41d97  ldarg.1
0x41d98  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0x41d9d  starg.s  1
0x41d9f  ldarg.1
0x41da0  ldc.i4.0
0x41da1  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string, bool)
0x41da6  starg.s  1
0x41da8  ldloc.0
0x41da9  ldarg.1
0x41daa  callvirt instance valuetype [mscorlib]System.IO.DriveType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDriveType(string)
0x41daf  stloc.1
0x41db0  ldc.i4.s 0x32
0x41db2  stloc.2
0x41db3  ldarg.2
0x41db4  brfalse.s loc_41DC0
0x41db6  ldarg.2
0x41db7  ldc.i4.1
0x41db8  bne.un.s loc_41DC0
0x41dba  ldc.i4   0x96
0x41dbf  stloc.2
0x41dc0  ldarg.1
0x41dc1  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x41dc6  brtrue.s loc_41DE2
0x41dc8  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41dcd  ldstr    aInvaliddirecto// "InvalidDirectory_Args1"
0x41dd2  ldc.i4.1
0x41dd3  newarr   [mscorlib]System.Object
0x41dd8  dup
0x41dd9  ldc.i4.0
0x41dda  ldarg.1
0x41ddb  stelem.ref
0x41ddc  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41de1  throw
0x41de2  ldarg.1
0x41de3  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsPathRooted(string)
0x41de8  brtrue.s loc_41E04
0x41dea  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41def  ldstr    aPathnotrootedA// "PathNotRooted_Args1"
0x41df4  ldc.i4.1
0x41df5  newarr   [mscorlib]System.Object
0x41dfa  dup
0x41dfb  ldc.i4.0
0x41dfc  ldarg.1
0x41dfd  stelem.ref
0x41dfe  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41e03  throw
0x41e04  ldloc.1
0x41e05  ldc.i4.3
0x41e06  beq.s    loc_41E22
0x41e08  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41e0d  ldstr    aDrivetypenotfi// "DriveTypeNotFixed_Args1"
0x41e12  ldc.i4.1
0x41e13  newarr   [mscorlib]System.Object
0x41e18  dup
0x41e19  ldc.i4.0
0x41e1a  ldarg.1
0x41e1b  stelem.ref
0x41e1c  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41e21  throw
0x41e22  ldarg.1
0x41e23  callvirt instance int32 [mscorlib]System.String::get_Length()
0x41e28  ldloc.2
0x41e29  ble.s    loc_41EA4
0x41e2b  ldarg.2
0x41e2c  switch   loc_41E47, loc_41E66, loc_41E85, loc_41E85, loc_41E85
0x41e45  br.s     loc_41E85
0x41e47  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41e4c  ldstr    aPathtolongmaxa// "PathToLongMaxAllowed_Cache_Args1"
0x41e51  ldc.i4.1
0x41e52  newarr   [mscorlib]System.Object
0x41e57  dup
0x41e58  ldc.i4.0
0x41e59  ldloc.2
0x41e5a  box      [mscorlib]System.Int32
0x41e5f  stelem.ref
0x41e60  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41e65  throw
0x41e66  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41e6b  ldstr    aPathtolongmaxa_0// "PathToLongMaxAllowed_Shared_Args1"
0x41e70  ldc.i4.1
0x41e71  newarr   [mscorlib]System.Object
0x41e76  dup
0x41e77  ldc.i4.0
0x41e78  ldloc.2
0x41e79  box      [mscorlib]System.Int32
0x41e7e  stelem.ref
0x41e7f  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41e84  throw
0x41e85  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41e8a  ldstr    aPathtolongmaxa_1// "PathToLongMaxAllowedIs_Args1"
0x41e8f  ldc.i4.1
0x41e90  newarr   [mscorlib]System.Object
0x41e95  dup
0x41e96  ldc.i4.0
0x41e97  ldloc.2
0x41e98  box      [mscorlib]System.Int32
0x41e9d  stelem.ref
0x41e9e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41ea3  throw
0x41ea4  ldarg.2
0x41ea5  ldc.i4.1
0x41ea6  beq.s    loc_41EF0
0x41ea8  ldarg.2
0x41ea9  brfalse.s loc_41EF0
0x41eab  ldloc.0
0x41eac  ldarg.1
0x41ead  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x41eb2  ldc.i4.1
0x41eb3  stloc.3
0x41eb4  dup
0x41eb5  brfalse.s loc_41ED1
0x41eb7  ldloc.0
0x41eb8  ldarg.1
0x41eb9  ldstr    asc_81126// "*"
0x41ebe  ldc.i4.0
0x41ebf  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFileSystemEntries(string, string, bool)
0x41ec4  stloc.s  4
0x41ec6  ldloc.s  4
0x41ec8  brfalse.s loc_41ED1
0x41eca  ldloc.s  4
0x41ecc  ldlen
0x41ecd  ldc.i4.0
0x41ece  ceq
0x41ed0  stloc.3
0x41ed1  brfalse.s loc_41EF0
0x41ed3  ldloc.3
0x41ed4  brtrue.s loc_41EF0
0x41ed6  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41edb  ldstr    aDirectorynotem// "DirectoryNotEmpty_Args1"
0x41ee0  ldc.i4.1
0x41ee1  newarr   [mscorlib]System.Object
0x41ee6  dup
0x41ee7  ldc.i4.0
0x41ee8  ldarg.1
0x41ee9  stelem.ref
0x41eea  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41eef  throw
0x41ef0  ret
```
