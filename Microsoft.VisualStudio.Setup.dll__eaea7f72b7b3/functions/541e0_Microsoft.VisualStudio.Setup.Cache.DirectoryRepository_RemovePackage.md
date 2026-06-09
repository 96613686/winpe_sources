# Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::RemovePackage

- ea: `0x541e0`
- end: `0x542e3`
- name: `Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::RemovePackage`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x50b80`
- `0x518b0`

## callees

- `0xffb0`
- `0x54170`
- `0x541e0`
- `0x54300`
- `0x547f0`
- `0x54830`
- `0x79c00`

## string_xrefs

- `0x54232`: `Directory for package `
- `0x54286`: `Directory '{0}' deleted.`
- `0x542ae`: `Directory '{0}' is scheduled for deletion after the reboot.`
- `0x542d3`: `Directory '{0}' could not be deleted nor could it be scheduled for deletion after the reboot.`

## pseudocode

```c

```

## disassembly

```asm
0x541e0  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x541e5  stloc.0
0x541e6  ldloc.0
0x541e7  ldarg.0
0x541e8  stfld    class Microsoft.VisualStudio.Setup.Cache.DirectoryRepository <>c__DisplayClass17_0::<>4__this
0x541ed  ldarg.0
0x541ee  call     void Microsoft.VisualStudio.Setup.Cache.Extensions::ValidateCanWrite(class Microsoft.VisualStudio.Setup.Cache.IReadOnlyRepository repository)
0x541f3  ldarg.1
0x541f4  ldstr    aPackage// "package"
0x541f9  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x541fe  ldarg.0
0x541ff  ldc.i4.2
0x54200  ldc.i4.1
0x54201  call     bool Microsoft.VisualStudio.Setup.Cache.Extensions::Supports(class Microsoft.VisualStudio.Setup.Cache.IPackageRepository repository, valuetype Microsoft.VisualStudio.Setup.RepositoryCapabilities capability, [opt] bool throw)
0x54206  pop
0x54207  ldloc.0
0x54208  ldarg.0
0x54209  ldarg.1
0x5420a  callvirt instance string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackageDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x5420f  stfld    string <>c__DisplayClass17_0::directory
0x54214  ldarg.0
0x54215  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x5421a  ldloc.0
0x5421b  ldfld    string <>c__DisplayClass17_0::directory
0x54220  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x54225  brtrue.s loc_54252
0x54227  ldarg.0
0x54228  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x5422d  dup
0x5422e  brtrue.s loc_54232
0x54230  pop
0x54231  ret
0x54232  ldstr    aDirectoryForPa// "Directory for package "
0x54237  ldarg.1
0x54238  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5423d  ldstr    aDoesNotExist_0// " does not exist."
0x54242  call     string [mscorlib]System.String::Concat(string, string, string)
0x54247  call     T0x2B000003
0x5424c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x54251  ret
0x54252  ldarg.0
0x54253  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x54258  ldloc.0
0x54259  ldfld    string <>c__DisplayClass17_0::directory
0x5425e  ldloca.s 1
0x54260  ldc.i4.1
0x54261  ldc.i4.1
0x54262  ldc.i4.2
0x54263  ldc.i4   0x7D0
0x54268  ldloc.0
0x54269  ldftn    instance bool <>c__DisplayClass17_0::<RemovePackage>b__0(class [mscorlib]System.Exception ex, int32 attempt)
0x5426f  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>::.ctor(object, native int)
0x54274  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x54279  brfalse.s loc_542A0
0x5427b  ldarg.0
0x5427c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x54281  dup
0x54282  brtrue.s loc_54286
0x54284  pop
0x54285  ret
0x54286  ldstr    aDirectory0Dele// "Directory '{0}' deleted."
0x5428b  ldc.i4.1
0x5428c  newarr   [mscorlib]System.Object
0x54291  dup
0x54292  ldc.i4.0
0x54293  ldloc.0
0x54294  ldfld    string <>c__DisplayClass17_0::directory
0x54299  stelem.ref
0x5429a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5429f  ret
0x542a0  ldloc.1
0x542a1  brfalse.s loc_542C8
0x542a3  ldarg.0
0x542a4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x542a9  dup
0x542aa  brtrue.s loc_542AE
0x542ac  pop
0x542ad  ret
0x542ae  ldstr    aDirectory0IsSc// "Directory '{0}' is scheduled for deleti"...
0x542b3  ldc.i4.1
0x542b4  newarr   [mscorlib]System.Object
0x542b9  dup
0x542ba  ldc.i4.0
0x542bb  ldloc.0
0x542bc  ldfld    string <>c__DisplayClass17_0::directory
0x542c1  stelem.ref
0x542c2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x542c7  ret
0x542c8  ldarg.0
0x542c9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x542ce  dup
0x542cf  brtrue.s loc_542D3
0x542d1  pop
0x542d2  ret
0x542d3  ldstr    aDirectory0Coul_0// "Directory '{0}' could not be deleted no"...
0x542d8  call     T0x2B000003
0x542dd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x542e2  ret
```
