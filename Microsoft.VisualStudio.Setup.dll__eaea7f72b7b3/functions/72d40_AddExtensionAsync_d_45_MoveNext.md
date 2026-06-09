# <AddExtensionAsync>d__45::MoveNext

- ea: `0x72d40`
- end: `0x731e0`
- name: `<AddExtensionAsync>d__45::MoveNext`
- size: `1184`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting`

## callees

- `0x11850`
- `0x11880`
- `0x21b40`
- `0x22630`
- `0x35e00`
- `0x377c0`
- `0x377e0`
- `0x4b310`
- `0x4b320`
- `0x4b330`
- `0x4b340`
- `0x4b650`
- `0x4b780`
- `0x4bf50`
- `0x4c170`
- `0x4c320`
- `0x4c380`
- `0x72470`
- `0x724a0`
- `0x726a0`
- `0x72d40`

## string_xrefs

- `0x72de7`: `Failed to download the extension from {0}`
- `0x72e57`: `Failed to parse the contents of the extension from {0}`
- `0x72ead`: `Extension from {0} has support type: {1}`
- `0x73012`: `Loading catalog for extension from '{0}'`
- `0x730c6`: `Unable to load catalog for extension from '{0}': {1}`
- `0x7314f`: `Unable to load catalog for extension from '{0}': {1}`

## pseudocode

```c

```

## disassembly

```asm
0x72d40  ldarg.0
0x72d41  ldfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72d46  stloc.0
0x72d47  ldarg.0
0x72d48  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase <AddExtensionAsync>d__45::<>4__this
0x72d4d  stloc.1
0x72d4e  ldloc.0
0x72d4f  switch   loc_72DA0, loc_72F32, loc_72F60
0x72d60  ldloc.1
0x72d61  ldarg.0
0x72d62  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x72d67  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class ExtensionStreamInformation> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::DownloadExtensionAsync(class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions extension)
0x72d6c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class ExtensionStreamInformation>::GetAwaiter()
0x72d71  stloc.s  5
0x72d73  ldloca.s 5
0x72d75  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation>::get_IsCompleted()
0x72d7a  brtrue.s loc_72DBD
0x72d7c  ldarg.0
0x72d7d  ldc.i4.0
0x72d7e  dup
0x72d7f  stloc.0
0x72d80  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72d85  ldarg.0
0x72d86  ldloc.s  5
0x72d88  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation> <AddExtensionAsync>d__45::<>u__1
0x72d8d  ldarg.0
0x72d8e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentInformation> <AddExtensionAsync>d__45::<>t__builder
0x72d93  ldloca.s 5
0x72d95  ldarg.0
0x72d96  call     T0x2B000320
0x72d9b  leave    loc_731DF
0x72da0  ldarg.0
0x72da1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation> <AddExtensionAsync>d__45::<>u__1
0x72da6  stloc.s  5
0x72da8  ldarg.0
0x72da9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation> <AddExtensionAsync>d__45::<>u__1
0x72dae  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation>
0x72db4  ldarg.0
0x72db5  ldc.i4.m1
0x72db6  dup
0x72db7  stloc.0
0x72db8  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72dbd  ldloca.s 5
0x72dbf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class ExtensionStreamInformation>::GetResult()
0x72dc4  stloc.s  4
0x72dc6  ldarg.0
0x72dc7  ldloc.s  4
0x72dc9  stfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72dce  ldarg.0
0x72dcf  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72dd4  callvirt instance class [mscorlib]System.IO.Stream ExtensionStreamInformation::get_Stream()
0x72dd9  brtrue.s loc_72E17
0x72ddb  ldloc.1
0x72ddc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x72de1  dup
0x72de2  brtrue.s loc_72DE7
0x72de4  pop
0x72de5  br.s     loc_72E05
0x72de7  ldstr    aFailedToDownlo_7// "Failed to download the extension from {"...
0x72dec  ldc.i4.1
0x72ded  newarr   [mscorlib]System.Object
0x72df2  dup
0x72df3  ldc.i4.0
0x72df4  ldarg.0
0x72df5  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x72dfa  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_ExtensionUri()
0x72dff  stelem.ref
0x72e00  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x72e05  ldnull
0x72e06  ldarg.0
0x72e07  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72e0c  newobj   instance void ExtensionContentInformation::.ctor(class Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class ExtensionStreamInformation StreamInformation)
0x72e11  stloc.2
0x72e12  leave    loc_731B6
0x72e17  ldarg.0
0x72e18  ldloc.1
0x72e19  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x72e1e  callvirt instance class Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ExtensionService()
0x72e23  ldarg.0
0x72e24  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72e29  callvirt instance class [mscorlib]System.IO.Stream ExtensionStreamInformation::get_Stream()
0x72e2e  ldarg.0
0x72e2f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <AddExtensionAsync>d__45::product
0x72e34  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x72e39  callvirt instance class Microsoft.VisualStudio.Setup.Extension.ExtensionContents Microsoft.VisualStudio.Setup.Extension.IExtensionService::ParseExtension(class [mscorlib]System.IO.Stream, class [mscorlib]System.Version vsixStream)
0x72e3e  stfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x72e43  ldarg.0
0x72e44  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x72e49  brtrue.s loc_72E87
0x72e4b  ldloc.1
0x72e4c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x72e51  dup
0x72e52  brtrue.s loc_72E57
0x72e54  pop
0x72e55  br.s     loc_72E75
0x72e57  ldstr    aFailedToParseT_1// "Failed to parse the contents of the ext"...
0x72e5c  ldc.i4.1
0x72e5d  newarr   [mscorlib]System.Object
0x72e62  dup
0x72e63  ldc.i4.0
0x72e64  ldarg.0
0x72e65  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x72e6a  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_ExtensionUri()
0x72e6f  stelem.ref
0x72e70  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x72e75  ldnull
0x72e76  ldarg.0
0x72e77  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72e7c  newobj   instance void ExtensionContentInformation::.ctor(class Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class ExtensionStreamInformation StreamInformation)
0x72e81  stloc.2
0x72e82  leave    loc_731B6
0x72e87  ldloc.1
0x72e88  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x72e8d  callvirt instance class Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ExtensionService()
0x72e92  ldarg.0
0x72e93  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x72e98  callvirt instance valuetype Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult Microsoft.VisualStudio.Setup.Extension.IExtensionService::IsSupportedExtension(class Microsoft.VisualStudio.Setup.Extension.ExtensionContents extensionContents)
0x72e9d  stloc.3
0x72e9e  ldloc.3
0x72e9f  brfalse.s loc_72EF8
0x72ea1  ldloc.1
0x72ea2  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x72ea7  dup
0x72ea8  brtrue.s loc_72EAD
0x72eaa  pop
0x72eab  br.s     loc_72EDB
0x72ead  ldstr    aExtensionFrom0// "Extension from {0} has support type: {1"...
0x72eb2  ldc.i4.2
0x72eb3  newarr   [mscorlib]System.Object
0x72eb8  dup
0x72eb9  ldc.i4.0
0x72eba  ldarg.0
0x72ebb  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x72ec0  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_ExtensionUri()
0x72ec5  stelem.ref
0x72ec6  dup
0x72ec7  ldc.i4.1
0x72ec8  ldloca.s 3
0x72eca  constrained. Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult
0x72ed0  callvirt instance string [mscorlib]System.Object::ToString()
0x72ed5  stelem.ref
0x72ed6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x72edb  ldnull
0x72edc  ldarg.0
0x72edd  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72ee2  callvirt instance class [mscorlib]System.IO.Stream ExtensionStreamInformation::get_Stream()
0x72ee7  ldc.i4.0
0x72ee8  newobj   instance void ExtensionStreamInformation::.ctor(class [mscorlib]System.IO.Stream Stream, valuetype Microsoft.VisualStudio.Setup.Services.Installer.ExtensionDownloadFailureReason DownloadFailureReason)
0x72eed  newobj   instance void ExtensionContentInformation::.ctor(class Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class ExtensionStreamInformation StreamInformation)
0x72ef2  stloc.2
0x72ef3  leave    loc_731B6
0x72ef8  ldloc.1
0x72ef9  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IEngine> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::GetEngineAsync()
0x72efe  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IEngine>::GetAwaiter()
0x72f03  stloc.s  7
0x72f05  ldloca.s 7
0x72f07  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine>::get_IsCompleted()
0x72f0c  brtrue.s loc_72F4F
0x72f0e  ldarg.0
0x72f0f  ldc.i4.1
0x72f10  dup
0x72f11  stloc.0
0x72f12  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72f17  ldarg.0
0x72f18  ldloc.s  7
0x72f1a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine> <AddExtensionAsync>d__45::<>u__2
0x72f1f  ldarg.0
0x72f20  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentInformation> <AddExtensionAsync>d__45::<>t__builder
0x72f25  ldloca.s 7
0x72f27  ldarg.0
0x72f28  call     T0x2B000321
0x72f2d  leave    loc_731DF
0x72f32  ldarg.0
0x72f33  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine> <AddExtensionAsync>d__45::<>u__2
0x72f38  stloc.s  7
0x72f3a  ldarg.0
0x72f3b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine> <AddExtensionAsync>d__45::<>u__2
0x72f40  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine>
0x72f46  ldarg.0
0x72f47  ldc.i4.m1
0x72f48  dup
0x72f49  stloc.0
0x72f4a  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72f4f  ldloca.s 7
0x72f51  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IEngine>::GetResult()
0x72f56  stloc.s  6
0x72f58  ldarg.0
0x72f59  ldloc.s  6
0x72f5b  stfld    class Microsoft.VisualStudio.Setup.IEngine <AddExtensionAsync>d__45::<engine>5__4
0x72f60  nop
0x72f61  ldloc.0
0x72f62  ldc.i4.2
0x72f63  beq.s    loc_72FB7
0x72f65  ldloc.1
0x72f66  ldarg.0
0x72f67  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x72f6c  ldarg.0
0x72f6d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <AddExtensionAsync>d__45::product
0x72f72  ldarg.0
0x72f73  ldfld    class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository <AddExtensionAsync>d__45::extensionsRepo
0x72f78  ldarg.0
0x72f79  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions> <AddExtensionAsync>d__45::extensionsFromPacks
0x72f7e  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::ExpandExtensionPack(class Microsoft.VisualStudio.Setup.Extension.ExtensionContents contents, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository extensionsRepo, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions> extensionsFromPacks)
0x72f83  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.List`1<string>>::GetAwaiter()
0x72f88  stloc.s  0xA
0x72f8a  ldloca.s 0xA
0x72f8c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>>::get_IsCompleted()
0x72f91  brtrue.s loc_72FD4
0x72f93  ldarg.0
0x72f94  ldc.i4.2
0x72f95  dup
0x72f96  stloc.0
0x72f97  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72f9c  ldarg.0
0x72f9d  ldloc.s  0xA
0x72f9f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>> <AddExtensionAsync>d__45::<>u__3
0x72fa4  ldarg.0
0x72fa5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentInformation> <AddExtensionAsync>d__45::<>t__builder
0x72faa  ldloca.s 0xA
0x72fac  ldarg.0
0x72fad  call     T0x2B000322
0x72fb2  leave    loc_731DF
0x72fb7  ldarg.0
0x72fb8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>> <AddExtensionAsync>d__45::<>u__3
0x72fbd  stloc.s  0xA
0x72fbf  ldarg.0
0x72fc0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>> <AddExtensionAsync>d__45::<>u__3
0x72fc5  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>>
0x72fcb  ldarg.0
0x72fcc  ldc.i4.m1
0x72fcd  dup
0x72fce  stloc.0
0x72fcf  stfld    int32 <AddExtensionAsync>d__45::<>1__state
0x72fd4  ldloca.s 0xA
0x72fd6  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.List`1<string>>::GetResult()
0x72fdb  stloc.s  8
0x72fdd  ldloc.1
0x72fde  ldarg.0
0x72fdf  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x72fe4  callvirt instance class [mscorlib]System.IO.Stream ExtensionStreamInformation::get_Stream()
0x72fe9  ldarg.0
0x72fea  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x72fef  ldarg.0
0x72ff0  ldfld    class Microsoft.VisualStudio.Setup.IEngine <AddExtensionAsync>d__45::<engine>5__4
0x72ff5  ldarg.0
0x72ff6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <AddExtensionAsync>d__45::product
0x72ffb  ldarg.0
0x72ffc  ldfld    class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository <AddExtensionAsync>d__45::extensionsRepo
0x73001  call     instance void Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SetupRequiredExtensionDependencies(class [mscorlib]System.IO.Stream parentStream, class Microsoft.VisualStudio.Setup.Extension.ExtensionContents parentContents, class Microsoft.VisualStudio.Setup.IEngine engine, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository extensionsRepo)
0x73006  ldloc.1
0x73007  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x7300c  dup
0x7300d  brtrue.s loc_73012
0x7300f  pop
0x73010  br.s     loc_73030
0x73012  ldstr    aLoadingCatalog_0// "Loading catalog for extension from '{0}"...
0x73017  ldc.i4.1
0x73018  newarr   [mscorlib]System.Object
0x7301d  dup
0x7301e  ldc.i4.0
0x7301f  ldarg.0
0x73020  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x73025  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_ExtensionUri()
0x7302a  stelem.ref
0x7302b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x73030  ldarg.0
0x73031  ldfld    class Microsoft.VisualStudio.Setup.IEngine <AddExtensionAsync>d__45::<engine>5__4
0x73036  ldarg.0
0x73037  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x7303c  callvirt instance string Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x73041  callvirt instance void Microsoft.VisualStudio.Setup.IEngine::LoadPartialJson(string catalogJson)
0x73046  ldarg.0
0x73047  ldfld    class Microsoft.VisualStudio.Setup.IEngine <AddExtensionAsync>d__45::<engine>5__4
0x7304c  ldarg.0
0x7304d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <AddExtensionAsync>d__45::product
0x73052  ldc.i4.1
0x73053  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph Microsoft.VisualStudio.Setup.IEngine::GetProductDependencyGraph(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, [opt] bool overwrite)
0x73058  stloc.s  9
0x7305a  ldloc.1
0x7305b  ldarg.0
0x7305c  ldfld    class ExtensionStreamInformation <AddExtensionAsync>d__45::<extensionStream>5__2
0x73061  callvirt instance class [mscorlib]System.IO.Stream ExtensionStreamInformation::get_Stream()
0x73066  ldarg.0
0x73067  ldfld    class Microsoft.VisualStudio.Setup.Extension.ExtensionContents <AddExtensionAsync>d__45::<contents>5__3
0x7306c  callvirt instance string Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x73071  ldarg.0
0x73072  ldfld    class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository <AddExtensionAsync>d__45::extensionsRepo
0x73077  ldloc.s  9
0x73079  ldarg.0
0x7307a  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x7307f  callvirt instance string Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_Sha256Hash()
0x73084  ldarg.0
0x73085  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x7308a  callvirt instance bool Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_AddedByExtensionPack()
0x7308f  ldloc.s  8
0x73091  ldarg.0
0x73092  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions <AddExtensionAsync>d__45::extension
0x73097  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions::get_SelectionState()
0x7309c  call     instance void Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SetupExtensionForInstallation(class [mscorlib]System.IO.Stream extensionStream, string catalogJson, class Microsoft.VisualStudio.Setup.Cache.ExtensionsRepository extensionsRepository, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph graph, string extensionHash, bool addedByExtensionPack, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> packedExtensions, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState selectionState)
0x730a1  ldarg.0
  ... truncated ...
```
