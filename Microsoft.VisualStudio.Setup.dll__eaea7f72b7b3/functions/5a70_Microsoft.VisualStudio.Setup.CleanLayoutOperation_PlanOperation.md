# Microsoft.VisualStudio.Setup.CleanLayoutOperation::PlanOperation

- ea: `0x5a70`
- end: `0x5d8e`
- name: `Microsoft.VisualStudio.Setup.CleanLayoutOperation::PlanOperation`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x5a70`
- `0x5d90`
- `0x14c00`
- `0x14e10`
- `0x15c20`
- `0x15c30`
- `0x15c70`
- `0x15c90`
- `0x15cd0`
- `0x15cf0`
- `0x19cb0`
- `0x29280`
- `0x5ae70`
- `0x5aed0`
- `0x5b550`
- `0x5b860`

## string_xrefs

- `0x5b6a`: `CleanLayoutDeleteCurrentCatalogNotSupported_Args1`
- `0x5bb6`: `It's not supported to clean up the current installer manifest.`
- `0x5c80`: `' will not be deleted because it is outside of the layout directory '`

## pseudocode

```c

```

## disassembly

```asm
0x5a70  ldarg.0
0x5a71  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Cacher()
0x5a76  ldarg.0
0x5a77  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5a7c  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5a81  ldc.i4.1
0x5a82  ldc.i4.1
0x5a83  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::SetLayoutDirectory(string, bool, bool)
0x5a88  pop
0x5a89  ldarg.0
0x5a8a  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5a8f  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5a94  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::ArchiveFolder
0x5a99  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5a9e  stloc.0
0x5a9f  ldarg.0
0x5aa0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.LayoutOperationBase::get_FileSystem()
0x5aa5  ldloc.0
0x5aa6  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x5aab  ldc.i4.1
0x5aac  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFiles(string, string, bool)
0x5ab1  ldarg.0
0x5ab2  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5ab7  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5abc  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x5ac1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5ac6  stloc.1
0x5ac7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x5acc  dup
0x5acd  ldloc.1
0x5ace  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5ad3  stloc.2
0x5ad4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5ad9  stloc.3
0x5ada  ldarg.0
0x5adb  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5ae0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.LayoutContext::get_CatalogsToClean()
0x5ae5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x5aea  stloc.s  6
0x5aec  br       loc_5BCF
0x5af1  ldloc.s  6
0x5af3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x5af8  stloc.s  7
0x5afa  ldloc.s  7
0x5afc  stloc.s  8
0x5afe  ldloc.s  8
0x5b00  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsPathRooted(string)
0x5b05  brtrue.s loc_5B20
0x5b07  ldarg.0
0x5b08  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5b0d  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5b12  ldloc.s  7
0x5b14  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5b19  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x5b1e  stloc.s  8
0x5b20  ldarg.0
0x5b21  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5b26  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5b2b  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x5b30  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5b35  stloc.s  9
0x5b37  ldloc.s  8
0x5b39  ldloc.s  9
0x5b3b  ldc.i4.5
0x5b3c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5b41  brfalse  loc_5BC7
0x5b46  ldloca.s 0xB
0x5b48  initobj  [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message
0x5b4e  ldloca.s 0xB
0x5b50  ldc.i4.2
0x5b51  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Type
0x5b56  ldloca.s 0xB
0x5b58  ldc.i4.7
0x5b59  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType>::.ctor(var<u1>)
0x5b5e  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Activity
0x5b63  ldloca.s 0xB
0x5b65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5b6a  ldstr    aCleanlayoutdel// "CleanLayoutDeleteCurrentCatalogNotSuppo"...
0x5b6f  ldnull
0x5b70  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x5b75  ldloc.s  9
0x5b77  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x5b7c  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::NeutralString
0x5b81  ldloca.s 0xB
0x5b83  call     string Microsoft.VisualStudio.Setup.Resources::get_CleanLayoutDeleteCurrentCatalogNotSupported_Args1()
0x5b88  ldloc.s  9
0x5b8a  call     string [mscorlib]System.String::Format(string, object)
0x5b8f  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::LocalizedString
0x5b94  ldloc.s  0xB
0x5b96  stloc.s  0xA
0x5b98  ldarg.0
0x5b99  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.LayoutOperationBase::get_MessageBus()
0x5b9e  ldloc.s  0xA
0x5ba0  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus::NotifyMessageAsync(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message)
0x5ba5  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x5baa  ldarg.0
0x5bab  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x5bb0  dup
0x5bb1  brtrue.s loc_5BB6
0x5bb3  pop
0x5bb4  br.s     loc_5BCF
0x5bb6  ldstr    aItSNotSupporte// "It's not supported to clean up the curr"...
0x5bbb  call     T0x2B000003
0x5bc0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bc5  br.s     loc_5BCF
0x5bc7  ldloc.3
0x5bc8  ldloc.s  8
0x5bca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5bcf  ldloc.s  6
0x5bd1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bd6  brtrue   loc_5AF1
0x5bdb  leave.s  loc_5BE9
0x5bdd  ldloc.s  6
0x5bdf  brfalse.s loc_5BE8
0x5be1  ldloc.s  6
0x5be3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5be8  endfinally
0x5be9  ldloc.2
0x5bea  ldloc.3
0x5beb  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x5bf0  call     T0x2B000014
0x5bf5  stloc.s  4
0x5bf7  ldarg.0
0x5bf8  ldloc.s  4
0x5bfa  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.CleanLayoutOperation::GetPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> catalogs)
0x5bff  stloc.s  5
0x5c01  ldarg.0
0x5c02  ldloc.3
0x5c03  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.CleanLayoutOperation::GetPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> catalogs)
0x5c08  ldloc.s  5
0x5c0a  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x5c0f  call     T0x2B000047
0x5c14  call     T0x2B000048
0x5c19  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage>::GetEnumerator()
0x5c1e  stloc.s  0xC
0x5c20  br       loc_5D00
0x5c25  ldloc.s  0xC
0x5c27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Current()
0x5c2c  stloc.s  0xD
0x5c2e  ldarg.0
0x5c2f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Services()
0x5c34  ldloc.s  0xD
0x5c36  newobj   instance void Microsoft.VisualStudio.Setup.Activities.CleanPackage::.ctor(class [mscorlib]System.IServiceProvider services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package)
0x5c3b  stloc.s  0xE
0x5c3d  ldloc.s  0xE
0x5c3f  callvirt instance string Microsoft.VisualStudio.Setup.Activities.CleanPackage::get_Directory()
0x5c44  ldarg.0
0x5c45  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5c4a  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5c4f  ldc.i4.1
0x5c50  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string, bool)
0x5c55  brtrue.s loc_5CAD
0x5c57  ldarg.0
0x5c58  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x5c5d  dup
0x5c5e  brtrue.s loc_5C66
0x5c60  pop
0x5c61  br       loc_5D00
0x5c66  ldc.i4.5
0x5c67  newarr   [mscorlib]System.String
0x5c6c  dup
0x5c6d  ldc.i4.0
0x5c6e  ldstr    asc_7FEB6// "'"
0x5c73  stelem.ref
0x5c74  dup
0x5c75  ldc.i4.1
0x5c76  ldloc.s  0xE
0x5c78  callvirt instance string Microsoft.VisualStudio.Setup.Activities.CleanPackage::get_Directory()
0x5c7d  stelem.ref
0x5c7e  dup
0x5c7f  ldc.i4.2
0x5c80  ldstr    aWillNotBeDelet// "' will not be deleted because it is out"...
0x5c85  stelem.ref
0x5c86  dup
0x5c87  ldc.i4.3
0x5c88  ldarg.0
0x5c89  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x5c8e  callvirt instance string Microsoft.VisualStudio.Setup.LayoutContext::get_Destination()
0x5c93  stelem.ref
0x5c94  dup
0x5c95  ldc.i4.4
0x5c96  ldstr    asc_7F7FA// "'."
0x5c9b  stelem.ref
0x5c9c  call     string [mscorlib]System.String::Concat(string[])
0x5ca1  call     T0x2B000003
0x5ca6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5cab  br.s     loc_5D00
0x5cad  ldarg.0
0x5cae  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.LayoutOperationBase::get_FileSystem()
0x5cb3  ldloc.s  0xE
0x5cb5  callvirt instance string Microsoft.VisualStudio.Setup.Activities.CleanPackage::get_Directory()
0x5cba  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x5cbf  brfalse.s loc_5D00
0x5cc1  ldarg.0
0x5cc2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Activities.CleanPackage> Microsoft.VisualStudio.Setup.CleanLayoutOperation::cleanPackages
0x5cc7  ldloc.s  0xE
0x5cc9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Activities.CleanPackage>::Add(var<u1>)
0x5cce  ldarg.0
0x5ccf  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.CleanLayoutOperation::parallelCleans
0x5cd4  ldloc.s  0xE
0x5cd6  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Coordinator::Queue(class Microsoft.VisualStudio.Setup.Activities.IActivity activity)
0x5cdb  ldarg.0
0x5cdc  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5ce1  brtrue.s loc_5CEE
0x5ce3  ldarg.0
0x5ce4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5ce9  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5cee  ldarg.0
0x5cef  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5cf4  ldloc.s  0xE
0x5cf6  callvirt instance string Microsoft.VisualStudio.Setup.Activities.CleanPackage::get_Directory()
0x5cfb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5d00  ldloc.s  0xC
0x5d02  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5d07  brtrue   loc_5C25
0x5d0c  leave.s  loc_5D1A
0x5d0e  ldloc.s  0xC
0x5d10  brfalse.s loc_5D19
0x5d12  ldloc.s  0xC
0x5d14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d19  endfinally
0x5d1a  ldarg.0
0x5d1b  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5d20  brfalse.s loc_5D8D
0x5d22  ldarg.0
0x5d23  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5d28  call     T0x2B000015
0x5d2d  brfalse.s loc_5D8D
0x5d2f  ldloc.3
0x5d30  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x5d35  stloc.s  0xF
0x5d37  br.s     loc_5D74
0x5d39  ldloca.s 0xF
0x5d3b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x5d40  stloc.s  0x10
0x5d42  ldloc.s  0x10
0x5d44  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x5d49  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CleanedCatalogFileName
0x5d4e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5d53  stloc.s  0x11
0x5d55  ldarg.0
0x5d56  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Services()
0x5d5b  ldloc.s  0x10
0x5d5d  ldloc.s  0x11
0x5d5f  ldc.i4.1
0x5d60  newobj   instance void Microsoft.VisualStudio.Setup.Activities.CopyFile::.ctor(class [mscorlib]System.IServiceProvider services, string source, string destination, [opt] bool deleteSource)
0x5d65  stloc.s  0x12
0x5d67  ldarg.0
0x5d68  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.CleanLayoutOperation::parallelCleans
0x5d6d  ldloc.s  0x12
0x5d6f  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Coordinator::Queue(class Microsoft.VisualStudio.Setup.Activities.IActivity activity)
0x5d74  ldloca.s 0xF
0x5d76  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x5d7b  brtrue.s loc_5D39
0x5d7d  leave.s  loc_5D8D
0x5d7f  ldloca.s 0xF
0x5d81  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x5d87  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d8c  endfinally
0x5d8d  ret
```
