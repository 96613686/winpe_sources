# Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryReadInstance

- ea: `0x54a50`
- end: `0x54c8a`
- name: `Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryReadInstance`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x199a0`
- `0x54a50`
- `0x54ec0`
- `0x55070`
- `0x550a0`

## string_xrefs

- `0x54ac8`: `Failed to deserialize instance state: {0}`
- `0x54c68`: `Failed to deserialize instance state: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x54a50  ldarg.0
0x54a51  ldarg.1
0x54a52  ldloca.s 0
0x54a54  ldloca.s 1
0x54a56  ldloca.s 3
0x54a58  ldloca.s 2
0x54a5a  call     instance void Microsoft.VisualStudio.Setup.Cache.FileStateManager::ComputeInstanceDirectoryAndStateFilePath(string instanceId, [out] string& directory, [out] string& stateFilePath, [out] string& userDirectory, [out] string& userFilePath)
0x54a5f  ldarg.0
0x54a60  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.FileStateManager::fileSystem
0x54a65  ldloc.1
0x54a66  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x54a6b  brfalse  loc_54C42
0x54a70  ldarg.0
0x54a71  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.FileStateManager::fileSystem
0x54a76  ldloc.1
0x54a77  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x54a7c  stloc.s  5
0x54a7e  ldarg.0
0x54a7f  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.FileStateManager::services
0x54a84  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.InstanceSerializer::.ctor(class [mscorlib]System.IServiceProvider)
0x54a89  dup
0x54a8a  ldloc.1
0x54a8b  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance>::set_Location(string)
0x54a90  stloc.s  6
0x54a92  ldarg.2
0x54a93  ldloc.s  6
0x54a95  ldloc.s  5
0x54a97  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance>::Deserialize(!!T0)
0x54a9c  dup
0x54a9d  brtrue.s loc_54AB5
0x54a9f  pop
0x54aa0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x54aa5  ldstr    aInstancecorrup// "InstanceCorrupt"
0x54aaa  call     T0x2B000003
0x54aaf  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x54ab4  throw
0x54ab5  stind.ref
0x54ab6  leave.s  loc_54AF9
0x54ab8  stloc.s  7
0x54aba  ldarg.0
0x54abb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.FileStateManager::logger
0x54ac0  dup
0x54ac1  brtrue.s loc_54AC6
0x54ac3  pop
0x54ac4  br.s     loc_54AE2
0x54ac6  ldloc.s  7
0x54ac8  ldstr    aFailedToDeseri_0// "Failed to deserialize instance state: {"...
0x54acd  ldc.i4.1
0x54ace  newarr   [mscorlib]System.Object
0x54ad3  dup
0x54ad4  ldc.i4.0
0x54ad5  ldloc.s  7
0x54ad7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x54adc  stelem.ref
0x54add  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x54ae2  ldarg.2
0x54ae3  ldnull
0x54ae4  stind.ref
0x54ae5  ldc.i4.0
0x54ae6  stloc.s  8
0x54ae8  leave    loc_54C87
0x54aed  ldloc.s  5
0x54aef  brfalse.s loc_54AF8
0x54af1  ldloc.s  5
0x54af3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54af8  endfinally
0x54af9  nop
0x54afa  ldarg.0
0x54afb  ldloc.0
0x54afc  ldsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StatePackagesFileName
0x54b01  ldc.i4.2
0x54b02  ldloca.s 9
0x54b04  call     instance bool Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryDeserializeContext(string directory, string fileName, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance& deserialized)
0x54b09  brfalse.s loc_54B1E
0x54b0b  ldarg.2
0x54b0c  ldind.ref
0x54b0d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x54b12  ldloc.s  9
0x54b14  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x54b19  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.PackageReference>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x54b1e  ldarg.0
0x54b1f  ldloc.0
0x54b20  ldsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateErrorsFileName
0x54b25  ldc.i4.4
0x54b26  ldloca.s 9
0x54b28  call     instance bool Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryDeserializeContext(string directory, string fileName, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance& deserialized)
0x54b2d  brfalse.s loc_54B3D
0x54b2f  ldarg.2
0x54b30  ldind.ref
0x54b31  ldloc.s  9
0x54b33  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ErrorState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x54b38  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ErrorState)
0x54b3d  ldarg.0
0x54b3e  ldloc.0
0x54b3f  ldsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateGroupConfigsFileName
0x54b44  ldc.i4.s 0x10
0x54b46  ldloca.s 9
0x54b48  call     instance bool Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryDeserializeContext(string directory, string fileName, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance& deserialized)
0x54b4d  brfalse.s loc_54B88
0x54b4f  ldarg.2
0x54b50  ldind.ref
0x54b51  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_GroupConfigFiles()
0x54b56  ldloc.s  9
0x54b58  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_GroupConfigFiles()
0x54b5d  call     T0x2B000093
0x54b62  ldarg.2
0x54b63  ldind.ref
0x54b64  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_UsingGroupConfigFiles()
0x54b69  ldloc.s  9
0x54b6b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_UsingGroupConfigFiles()
0x54b70  call     T0x2B000093
0x54b75  ldarg.2
0x54b76  ldind.ref
0x54b77  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_PendingGroupFileRenames()
0x54b7c  ldloc.s  9
0x54b7e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_PendingGroupFileRenames()
0x54b83  call     T0x2B000093
0x54b88  ldarg.0
0x54b89  ldloc.0
0x54b8a  ldsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateNgenFileName
0x54b8f  ldc.i4.s 0x20
0x54b91  ldloca.s 9
0x54b93  call     instance bool Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryDeserializeContext(string directory, string fileName, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance& deserialized)
0x54b98  brfalse.s loc_54BF1
0x54b9a  ldarg.2
0x54b9b  ldind.ref
0x54b9c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54ba1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority1()
0x54ba6  ldloc.s  9
0x54ba8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54bad  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority1()
0x54bb2  call     T0x2B000272
0x54bb7  ldarg.2
0x54bb8  ldind.ref
0x54bb9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54bbe  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority2()
0x54bc3  ldloc.s  9
0x54bc5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54bca  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority2()
0x54bcf  call     T0x2B000272
0x54bd4  ldarg.2
0x54bd5  ldind.ref
0x54bd6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54bdb  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority3()
0x54be0  ldloc.s  9
0x54be2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x54be7  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority3()
0x54bec  call     T0x2B000272
0x54bf1  leave.s  loc_54BF6
0x54bf3  pop
0x54bf4  leave.s  loc_54BF6
0x54bf6  ldarg.0
0x54bf7  ldloc.2
0x54bf8  ldc.i4.8
0x54bf9  ldloca.s 4
0x54bfb  call     instance bool Microsoft.VisualStudio.Setup.Cache.FileStateManager::TryDeserializeContext(string filePath, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance& deserialized)
0x54c00  brfalse.s loc_54C31
0x54c02  ldloc.s  4
0x54c04  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_TemporaryCache()
0x54c09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x54c0e  brtrue.s loc_54C1E
0x54c10  ldarg.2
0x54c11  ldind.ref
0x54c12  ldloc.s  4
0x54c14  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_TemporaryCache()
0x54c19  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::set_TemporaryCache(string)
0x54c1e  ldarg.2
0x54c1f  ldind.ref
0x54c20  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_UserProperties()
0x54c25  ldloc.s  4
0x54c27  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_UserProperties()
0x54c2c  call     T0x2B000161
0x54c31  ldarg.2
0x54c32  ldind.ref
0x54c33  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::ResetChanged()
0x54c38  ldarg.2
0x54c39  ldind.ref
0x54c3a  ldarg.1
0x54c3b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::set_InstanceId(string)
0x54c40  ldc.i4.1
0x54c41  ret
0x54c42  ldarg.0
0x54c43  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.FileStateManager::logger
0x54c48  brfalse.s loc_54C82
0x54c4a  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x54c4f  ldstr    aInstancecorrup// "InstanceCorrupt"
0x54c54  call     T0x2B000003
0x54c59  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x54c5e  stloc.s  0xA
0x54c60  ldarg.0
0x54c61  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.FileStateManager::logger
0x54c66  ldloc.s  0xA
0x54c68  ldstr    aFailedToDeseri_0// "Failed to deserialize instance state: {"...
0x54c6d  ldc.i4.1
0x54c6e  newarr   [mscorlib]System.Object
0x54c73  dup
0x54c74  ldc.i4.0
0x54c75  ldloc.s  0xA
0x54c77  callvirt instance string [mscorlib]System.Exception::get_Message()
0x54c7c  stelem.ref
0x54c7d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x54c82  ldarg.2
0x54c83  ldnull
0x54c84  stind.ref
0x54c85  ldc.i4.0
0x54c86  ret
0x54c87  ldloc.s  8
0x54c89  ret
```
