# Microsoft.VisualStudio.Setup.Engine::VerifyInstallationPath

- ea: `0x8010`
- end: `0x81be`
- name: `Microsoft.VisualStudio.Setup.Engine::VerifyInstallationPath`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x9200`
- `0x4f380`

## callees

- `0x8010`
- `0x19a90`
- `0x19ab0`
- `0x1a1d0`
- `0x1a250`
- `0x1a670`
- `0x28030`
- `0x292b0`
- `0x563f0`
- `0x57200`

## string_xrefs

- `0x8011`: `services`
- `0x801c`: `installationPath`

## pseudocode

```c

```

## disassembly

```asm
0x8010  ldarg.0
0x8011  ldstr    aServices// "services"
0x8016  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x801b  ldarg.1
0x801c  ldstr    aInstallationpa// "installationPath"
0x8021  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x8026  ldarg.0
0x8027  ldc.i4.1
0x8028  call     T0x2B00000C
0x802d  stloc.0
0x802e  ldloc.0
0x802f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_OperatingSystemDirectory()
0x8034  stloc.1
0x8035  ldarg.1
0x8036  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0x803b  starg.s  1
0x803d  ldarg.1
0x803e  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x8043  brfalse.s loc_8070
0x8045  ldarg.1
0x8046  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsPathRooted(string)
0x804b  brfalse.s loc_8070
0x804d  ldloc.0
0x804e  ldarg.1
0x804f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x8054  brtrue.s loc_8070
0x8056  ldarg.1
0x8057  call     bool Microsoft.VisualStudio.Setup.Utility.IOUtil::IsOpticalDevice(string dir)
0x805c  brtrue.s loc_8070
0x805e  ldloc.0
0x805f  ldarg.1
0x8060  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsDriveFixed(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string)
0x8065  brfalse.s loc_8070
0x8067  ldarg.1
0x8068  ldloc.1
0x8069  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x806e  brfalse.s loc_8081
0x8070  call     string Microsoft.VisualStudio.Setup.Resources::get_InvalidPath_Args1()
0x8075  ldarg.1
0x8076  call     string [mscorlib]System.String::Format(string, object)
0x807b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8080  throw
0x8081  ldarg.1
0x8082  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8087  ldsfld   int32 Microsoft.VisualStudio.Setup.Engine::MaxInstallRootPathLength
0x808c  blt.s    loc_80A3
0x808e  call     string Microsoft.VisualStudio.Setup.Resources::get_InstallPathTooLong()
0x8093  call     T0x2B000003
0x8098  call     string [mscorlib]System.String::Format(string, object[])
0x809d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80a2  throw
0x80a3  ldloc.0
0x80a4  ldarg.1
0x80a5  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x80aa  dup
0x80ab  brtrue.s loc_80B0
0x80ad  ldc.i4.1
0x80ae  br.s     loc_80C1
0x80b0  ldloc.0
0x80b1  ldarg.1
0x80b2  ldstr    asc_81126// "*"
0x80b7  ldc.i4.0
0x80b8  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFileSystemEntries(string, string, bool)
0x80bd  ldlen
0x80be  ldc.i4.0
0x80bf  ceq
0x80c1  stloc.2
0x80c2  brfalse.s loc_80CA
0x80c4  ldloc.2
0x80c5  ldc.i4.0
0x80c6  ceq
0x80c8  br.s     loc_80CB
0x80ca  ldc.i4.0
0x80cb  stloc.3
0x80cc  call     string Microsoft.VisualStudio.Setup.Resources::get_CannotInstallToEmptyDirectory_Args1()
0x80d1  ldarg.1
0x80d2  call     string [mscorlib]System.String::Format(string, object)
0x80d7  stloc.s  4
0x80d9  ldc.i4.0
0x80da  stloc.s  5
0x80dc  ldarg.3
0x80dd  brtrue.s loc_80EA
0x80df  ldarg.0
0x80e0  newobj   instance void Microsoft.VisualStudio.Setup.Cache.Query::.ctor(class [mscorlib]System.IServiceProvider services)
0x80e5  starg.s  3
0x80e7  ldc.i4.1
0x80e8  stloc.s  5
0x80ea  ldnull
0x80eb  stloc.s  6
0x80ed  ldarg.3
0x80ee  ldarg.1
0x80ef  ldc.i4.1
0x80f0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Cache.IQuery::GetInstanceForPath(string path, bool includeIncomplete)
0x80f5  stloc.s  6
0x80f7  leave.s  loc_8104
0x80f9  ldloc.s  5
0x80fb  brfalse.s loc_8103
0x80fd  ldarg.3
0x80fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8103  endfinally
0x8104  ldloc.s  6
0x8106  ldnull
0x8107  ceq
0x8109  ldloc.3
0x810a  and
0x810b  brfalse.s loc_8115
0x810d  ldloc.s  4
0x810f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8114  throw
0x8115  ldloc.s  6
0x8117  brfalse.s loc_816B
0x8119  ldloc.s  6
0x811b  ldnull
0x811c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::GetDisplayName(class [mscorlib]System.Globalization.CultureInfo)
0x8121  ldloc.s  6
0x8123  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_Properties()
0x8128  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::FormatDisplayName(string displayName, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> propertyBag)
0x812d  stloc.s  7
0x812f  ldarg.2
0x8130  brfalse.s loc_8159
0x8132  ldarg.2
0x8133  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x8138  ldloc.s  6
0x813a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x813f  ldc.i4.3
0x8140  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8145  brtrue.s loc_816B
0x8147  call     string Microsoft.VisualStudio.Setup.Resources::get_CannotInstallToAnExistingInstanceDirectory_Args1()
0x814c  ldloc.s  7
0x814e  call     string [mscorlib]System.String::Format(string, object)
0x8153  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8158  throw
0x8159  call     string Microsoft.VisualStudio.Setup.Resources::get_CannotInstallToAnExistingInstanceDirectory_Args1()
0x815e  ldloc.s  7
0x8160  call     string [mscorlib]System.String::Format(string, object)
0x8165  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x816a  throw
0x816b  ldarg.2
0x816c  brfalse.s loc_81BD
0x816e  ldarg.2
0x816f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x8174  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8179  brtrue.s loc_81BD
0x817b  ldarg.1
0x817c  ldc.i4.0
0x817d  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string, bool)
0x8182  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x8187  ldarg.2
0x8188  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x818d  ldc.i4.0
0x818e  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string, bool)
0x8193  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x8198  stloc.s  8
0x819a  ldloc.s  8
0x819c  ldc.i4.3
0x819d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x81a2  brtrue.s loc_81BD
0x81a4  call     string Microsoft.VisualStudio.Setup.Resources::get_PathDoesNotMatchRegisteredPath_Args3()
0x81a9  ldarg.1
0x81aa  ldloc.s  8
0x81ac  ldarg.2
0x81ad  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x81b2  call     string [mscorlib]System.String::Format(string, object, object, object)
0x81b7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x81bc  throw
0x81bd  ret
```
