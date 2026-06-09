# Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SetupExtensionForInstallation

- ea: `0x4c380`
- end: `0x4c52a`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SetupExtensionForInstallation`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x4c170`
- `0x72d40`

## callees

- `0x102d0`
- `0x22730`
- `0x4b780`
- `0x4c380`
- `0x54170`
- `0x72bf0`

## string_xrefs

- `0x4c418`: `Copying extension to the extensions repository at {0}`
- `0x4c463`: `Setting the payload hash for the extension`
- `0x4c4c8`: `Extension package not found.`

## pseudocode

```c

```

## disassembly

```asm
0x4c380  newobj   instance void <>c__DisplayClass62_0::.ctor()
0x4c385  stloc.0
0x4c386  ldarg.0
0x4c387  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x4c38c  ldarg.2
0x4c38d  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::ParseJson(class [mscorlib]System.IServiceProvider, string)
0x4c392  stloc.1
0x4c393  ldloc.0
0x4c394  ldloc.1
0x4c395  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x4c39a  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__62_0
0x4c39f  dup
0x4c3a0  brtrue.s loc_4C3B9
0x4c3a2  pop
0x4c3a3  ldsfld   class <>c <>c::<>9
0x4c3a8  ldftn    instance bool <>c::<SetupExtensionForInstallation>b__62_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage x)
0x4c3ae  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x4c3b3  dup
0x4c3b4  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__62_0
0x4c3b9  call     T0x2B000232
0x4c3be  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage <>c__DisplayClass62_0::vsixPackage
0x4c3c3  ldloc.0
0x4c3c4  ldloc.1
0x4c3c5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x4c3ca  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__62_1
0x4c3cf  dup
0x4c3d0  brtrue.s loc_4C3E9
0x4c3d2  pop
0x4c3d3  ldsfld   class <>c <>c::<>9
0x4c3d8  ldftn    instance bool <>c::<SetupExtensionForInstallation>b__62_1(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage x)
0x4c3de  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x4c3e3  dup
0x4c3e4  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__62_1
0x4c3e9  call     T0x2B000232
0x4c3ee  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage <>c__DisplayClass62_0::componentPackage
0x4c3f3  ldarg.3
0x4c3f4  ldloc.0
0x4c3f5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage <>c__DisplayClass62_0::vsixPackage
0x4c3fa  callvirt instance string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackageDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x4c3ff  stloc.2
0x4c400  ldloc.2
0x4c401  ldsfld   string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::VsixPayloadName
0x4c406  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4c40b  stloc.3
0x4c40c  ldarg.0
0x4c40d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x4c412  dup
0x4c413  brtrue.s loc_4C418
0x4c415  pop
0x4c416  br.s     loc_4C42C
0x4c418  ldstr    aCopyingExtensi// "Copying extension to the extensions rep"...
0x4c41d  ldc.i4.1
0x4c41e  newarr   [mscorlib]System.Object
0x4c423  dup
0x4c424  ldc.i4.0
0x4c425  ldloc.3
0x4c426  stelem.ref
0x4c427  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4c42c  ldarg.1
0x4c42d  ldc.i4.0
0x4c42e  conv.i8
0x4c42f  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x4c434  ldarg.0
0x4c435  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x4c43a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_FileSystem()
0x4c43f  ldloc.2
0x4c440  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x4c445  ldarg.0
0x4c446  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x4c44b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_FileSystem()
0x4c450  ldarg.1
0x4c451  ldloc.3
0x4c452  call     void Microsoft.VisualStudio.Setup.Extensions::CreateFileFromStream(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [mscorlib]System.IO.Stream input, string targetFile)
0x4c457  ldarg.0
0x4c458  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x4c45d  dup
0x4c45e  brtrue.s loc_4C463
0x4c460  pop
0x4c461  br.s     loc_4C472
0x4c463  ldstr    aSettingThePayl// "Setting the payload hash for the extens"...
0x4c468  call     T0x2B000003
0x4c46d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4c472  ldarg.s  4
0x4c474  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::get_InstallOrder()
0x4c479  ldloc.0
0x4c47a  ldftn    instance bool <>c__DisplayClass62_0::<SetupExtensionForInstallation>b__2(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode x)
0x4c480  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, bool>::.ctor(object, native int)
0x4c485  call     T0x2B000234
0x4c48a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x4c48f  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetPayloads(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x4c494  call     T0x2B000235
0x4c499  ldarg.s  5
0x4c49b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload::set_Sha256(string)
0x4c4a0  ldarg.s  4
0x4c4a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::get_InstallOrder()
0x4c4a7  ldloc.0
0x4c4a8  ldftn    instance bool <>c__DisplayClass62_0::<SetupExtensionForInstallation>b__3(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode x)
0x4c4ae  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, bool>::.ctor(object, native int)
0x4c4b3  call     T0x2B000234
0x4c4b8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x4c4bd  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Component
0x4c4c2  stloc.s  4
0x4c4c4  ldloc.s  4
0x4c4c6  brtrue.s loc_4C4D3
0x4c4c8  ldstr    aExtensionPacka// "Extension package not found."
0x4c4cd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4c4d2  throw
0x4c4d3  ldloc.s  4
0x4c4d5  ldarg.s  6
0x4c4d7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Component::set_AutomaticallyAddedByExtensionPack(bool)
0x4c4dc  ldloc.s  4
0x4c4de  ldarg.s  7
0x4c4e0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4c4e5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Component::set_PackedExtensions(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x4c4ea  ldarg.s  8
0x4c4ec  brfalse.s loc_4C529
0x4c4ee  ldloc.s  4
0x4c4f0  ldarg.s  8
0x4c4f2  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x4c4f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectableGroup::set_SelectedState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState)
0x4c4fc  ldloc.s  4
0x4c4fe  ldarg.s  8
0x4c500  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_UserSelectedState()
0x4c505  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectableGroup::set_UserSelectedState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState)
0x4c50a  ldloc.s  4
0x4c50c  ldarg.s  8
0x4c50e  brfalse.s loc_4C51C
0x4c510  ldarg.s  8
0x4c512  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x4c517  brfalse.s loc_4C51C
0x4c519  ldc.i4.3
0x4c51a  br.s     loc_4C51D
0x4c51c  ldc.i4.1
0x4c51d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::set_RequestedState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState)
0x4c522  ldarg.s  4
0x4c524  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::UpdateSelection()
0x4c529  ret
```
