# System.Deployment.Application.Manifest.AssemblyManifest::ValidateSemanticsForApplicationRole

- ea: `0x26250`
- end: `0x2695a`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateSemanticsForApplicationRole`
- size: `1802`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x250e0`

## callees

- `0xdab0`
- `0xdd30`
- `0xdd80`
- `0x10160`
- `0x147a0`
- `0x147b0`
- `0x1b540`
- `0x21910`
- `0x219c0`
- `0x21a80`
- `0x23020`
- `0x23c20`
- `0x23c30`
- `0x23c40`
- `0x23c70`
- `0x23da0`
- `0x23db0`
- `0x23dc0`
- `0x23dd0`
- `0x23df0`
- `0x23ec0`
- `0x24380`
- `0x24390`
- `0x24400`
- `0x24410`
- `0x24420`
- `0x24490`
- `0x244a0`
- `0x244b0`
- `0x244c0`
- `0x24780`
- `0x247b0`
- `0x247e0`
- `0x24970`
- `0x24b10`
- `0x24b20`
- `0x24b30`
- `0x24b90`
- `0x24bf0`
- `0x24c50`
- `0x24d10`
- `0x24dd0`
- `0x24e90`
- `0x24f90`
- `0x26250`
- `0x26af0`
- `0x26ea0`
- `0x27250`

## string_xrefs

- `0x263b9`: `Ex_AppNoCompatibleFrameworksAllowed`
- `0x264d0`: `Ex_DescriptionSupportUrlNotSupportedUriScheme`
- `0x2651f`: `Ex_TooManyFilesInManifest`
- `0x265f7`: `Ex_TooManyFileAssociationsInManifest`
- `0x26672`: `Ex_FileExtensionInfoMissing`
- `0x266ad`: `Ex_FileAssociationExtensionNoDot`
- `0x26731`: `Ex_FileExtensionTooLong`
- `0x267ac`: `Ex_MultipleInstanceFileExtension`
- `0x26802`: `Ex_TooManyAssembliesInManifest`
- `0x268de`: `Ex_DepenedentOSSupportUrlNotSupportedUriScheme`
- `0x26947`: `Ex_SemanticallyInvalidApplicationManifest`

## pseudocode

```c

```

## disassembly

```asm
0x26250  ldarg.0
0x26251  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x26256  call     void System.Deployment.Application.Manifest.AssemblyManifest::ValidateAssemblyIdentity(class System.Deployment.Application.DefinitionIdentity identity)
0x2625b  ldarg.0
0x2625c  call     instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x26261  ldlen
0x26262  conv.i4
0x26263  ldc.i4.1
0x26264  beq.s    loc_26278
0x26266  ldc.i4.s 0xC
0x26268  ldstr    aExApponeentryp// "Ex_AppOneEntryPoint"
0x2626d  call     string System.Deployment.Application.Resources::GetString(string s)
0x26272  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26277  throw
0x26278  ldarg.0
0x26279  call     instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x2627e  ldc.i4.0
0x2627f  ldelem.ref
0x26280  stloc.0
0x26281  ldloc.0
0x26282  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomHostSpecified()
0x26287  brtrue   loc_26350
0x2628c  ldloc.0
0x2628d  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x26292  brfalse  loc_2633E
0x26297  ldloc.0
0x26298  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x2629d  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsOptional()
0x262a2  brtrue   loc_2633E
0x262a7  ldloc.0
0x262a8  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x262ad  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsPreRequisite()
0x262b2  brtrue   loc_2633E
0x262b7  ldloc.0
0x262b8  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x262bd  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x262c2  brfalse.s loc_2633E
0x262c4  ldloc.0
0x262c5  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x262ca  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x262cf  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x262d4  brfalse.s loc_2633E
0x262d6  ldloc.0
0x262d7  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x262dc  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x262e1  call     bool System.Deployment.Application.UriHelper::PathContainDirectorySeparators(string path)
0x262e6  brtrue.s loc_2633E
0x262e8  ldloc.0
0x262e9  callvirt instance string System.Deployment.Application.Manifest.EntryPoint::get_CommandFile()
0x262ee  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x262f3  brfalse.s loc_2633E
0x262f5  ldloc.0
0x262f6  callvirt instance string System.Deployment.Application.Manifest.EntryPoint::get_CommandFile()
0x262fb  call     bool System.Deployment.Application.UriHelper::PathContainDirectorySeparators(string path)
0x26300  brtrue.s loc_2633E
0x26302  ldloc.0
0x26303  callvirt instance string System.Deployment.Application.Manifest.EntryPoint::get_CommandFile()
0x26308  ldloc.0
0x26309  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x2630e  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x26313  ldc.i4.5
0x26314  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x26319  brfalse.s loc_2633E
0x2631b  ldarg.0
0x2631c  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x26321  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x26326  ldloc.0
0x26327  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x2632c  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26331  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_ProcessorArchitecture()
0x26336  ldc.i4.5
0x26337  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2633c  brfalse.s loc_26350
0x2633e  ldc.i4.s 0xC
0x26340  ldstr    aExAppinvaliden// "Ex_AppInvalidEntryPoint"
0x26345  call     string System.Deployment.Application.Resources::GetString(string s)
0x2634a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2634f  throw
0x26350  ldarg.0
0x26351  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_Application()
0x26356  brfalse.s loc_26372
0x26358  ldloc.0
0x26359  callvirt instance string System.Deployment.Application.Manifest.EntryPoint::get_CommandParameters()
0x2635e  brfalse.s loc_26372
0x26360  ldc.i4.s 0xC
0x26362  ldstr    aExAppinvaliden_0// "Ex_AppInvalidEntryPointParameters"
0x26367  call     string System.Deployment.Application.Resources::GetString(string s)
0x2636c  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26371  throw
0x26372  ldarg.0
0x26373  call     instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies()
0x26378  brfalse.s loc_26383
0x2637a  ldarg.0
0x2637b  call     instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies()
0x26380  ldlen
0x26381  brtrue.s loc_26395
0x26383  ldc.i4.s 0xC
0x26385  ldstr    aExAppatleaston// "Ex_AppAtLeastOneDependency"
0x2638a  call     string System.Deployment.Application.Resources::GetString(string s)
0x2638f  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26394  throw
0x26395  ldarg.0
0x26396  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x2639b  brfalse.s loc_263AF
0x2639d  ldc.i4.s 0xC
0x2639f  ldstr    aExAppnodeploym// "Ex_AppNoDeploymentAllowed"
0x263a4  call     string System.Deployment.Application.Resources::GetString(string s)
0x263a9  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x263ae  throw
0x263af  ldarg.0
0x263b0  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x263b5  brfalse.s loc_263C9
0x263b7  ldc.i4.s 0xC
0x263b9  ldstr    aExAppnocompati// "Ex_AppNoCompatibleFrameworksAllowed"
0x263be  call     string System.Deployment.Application.Resources::GetString(string s)
0x263c3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x263c8  throw
0x263c9  ldarg.0
0x263ca  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_UseManifestForTrust()
0x263cf  brfalse.s loc_2640D
0x263d1  ldarg.0
0x263d2  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x263d7  brfalse.s loc_263FB
0x263d9  ldarg.0
0x263da  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x263df  brfalse.s loc_26441
0x263e1  ldarg.0
0x263e2  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x263e7  callvirt instance string System.Deployment.Application.Manifest.Description::get_Publisher()
0x263ec  brfalse.s loc_263FB
0x263ee  ldarg.0
0x263ef  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x263f4  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x263f9  brtrue.s loc_26441
0x263fb  ldc.i4.s 0xC
0x263fd  ldstr    aExAppnooverrid// "Ex_AppNoOverridePublisherProduct"
0x26402  call     string System.Deployment.Application.Resources::GetString(string s)
0x26407  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2640c  throw
0x2640d  ldarg.0
0x2640e  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x26413  brfalse.s loc_26441
0x26415  ldarg.0
0x26416  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x2641b  callvirt instance string System.Deployment.Application.Manifest.Description::get_Publisher()
0x26420  brtrue.s loc_2642F
0x26422  ldarg.0
0x26423  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x26428  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x2642d  brfalse.s loc_26441
0x2642f  ldc.i4.s 0xC
0x26431  ldstr    aExAppnopublish// "Ex_AppNoPublisherProductAllowed"
0x26436  call     string System.Deployment.Application.Resources::GetString(string s)
0x2643b  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26440  throw
0x26441  ldarg.0
0x26442  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x26447  brfalse.s loc_2647A
0x26449  ldarg.0
0x2644a  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x2644f  callvirt instance string System.Deployment.Application.Manifest.Description::get_IconFile()
0x26454  brfalse.s loc_2647A
0x26456  ldarg.0
0x26457  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x2645c  callvirt instance string System.Deployment.Application.Manifest.Description::get_IconFile()
0x26461  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x26466  brtrue.s loc_2647A
0x26468  ldc.i4.s 0xC
0x2646a  ldstr    aExAppinvalidic// "Ex_AppInvalidIconFile"
0x2646f  call     string System.Deployment.Application.Resources::GetString(string s)
0x26474  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26479  throw
0x2647a  ldarg.0
0x2647b  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x26480  brfalse  loc_2650E
0x26485  ldarg.0
0x26486  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x2648b  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x26490  ldnull
0x26491  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x26496  brfalse.s loc_2650E
0x26498  ldarg.0
0x26499  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x2649e  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x264a3  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x264a8  brtrue.s loc_264BC
0x264aa  ldc.i4.s 0xC
0x264ac  ldstr    aExDescriptions_0// "Ex_DescriptionSupportUrlNotAbsolute"
0x264b1  call     string System.Deployment.Application.Resources::GetString(string s)
0x264b6  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x264bb  throw
0x264bc  ldarg.0
0x264bd  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x264c2  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x264c7  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x264cc  brtrue.s loc_264E0
0x264ce  ldc.i4.s 0xC
0x264d0  ldstr    aExDescriptions_1// "Ex_DescriptionSupportUrlNotSupportedUri"...
0x264d5  call     string System.Deployment.Application.Resources::GetString(string s)
0x264da  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x264df  throw
0x264e0  ldarg.0
0x264e1  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x264e6  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x264eb  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x264f0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x264f5  ldc.i4   0x4000
0x264fa  ble.s    loc_2650E
0x264fc  ldc.i4.s 0xC
0x264fe  ldstr    aExDescriptions_2// "Ex_DescriptionSupportUrlTooLong"
0x26503  call     string System.Deployment.Application.Resources::GetString(string s)
0x26508  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2650d  throw
0x2650e  ldarg.0
0x2650f  call     instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::get_Files()
0x26514  ldlen
0x26515  conv.i4
0x26516  ldc.i4   0x6000
0x2651b  ble.s    loc_2652F
0x2651d  ldc.i4.s 0xC
0x2651f  ldstr    aExToomanyfiles// "Ex_TooManyFilesInManifest"
0x26524  call     string System.Deployment.Application.Resources::GetString(string s)
0x26529  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2652e  throw
0x2652f  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x26534  stloc.1
0x26535  ldarg.0
0x26536  call     instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::get_Files()
0x2653b  stloc.s  4
0x2653d  ldc.i4.0
0x2653e  stloc.s  5
0x26540  br.s     loc_26597
0x26542  ldloc.s  4
0x26544  ldloc.s  5
0x26546  ldelem.ref
0x26547  stloc.s  6
0x26549  ldloc.s  6
0x2654b  call     void System.Deployment.Application.Manifest.AssemblyManifest::ValidateFile(class System.Deployment.Application.Manifest.File f)
0x26550  ldloc.s  6
0x26552  callvirt instance bool System.Deployment.Application.Manifest.File::get_IsOptional()
0x26557  brtrue.s loc_2657C
0x26559  ldloc.1
0x2655a  ldloc.s  6
0x2655c  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x26561  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x26566  brtrue.s loc_2657C
0x26568  ldloc.1
0x26569  ldloc.s  6
0x2656b  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x26570  callvirt instance string [mscorlib]System.String::ToLower()
0x26575  ldloc.s  6
0x26577  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2657c  ldloc.s  6
0x2657e  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.File::get_HashCollection()
0x26583  callvirt instance int32 System.Deployment.Application.HashCollection::get_Count()
0x26588  brtrue.s loc_26591
0x2658a  ldarg.0
0x2658b  ldc.i4.1
0x2658c  stfld    bool System.Deployment.Application.Manifest.AssemblyManifest::_unhashedFilePresent
0x26591  ldloc.s  5
0x26593  ldc.i4.1
0x26594  add
0x26595  stloc.s  5
0x26597  ldloc.s  5
0x26599  ldloc.s  4
0x2659b  ldlen
0x2659c  conv.i4
0x2659d  blt.s    loc_26542
0x2659f  ldarg.0
0x265a0  call     instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x265a5  ldlen
0x265a6  brfalse.s loc_265C2
0x265a8  ldloc.0
0x265a9  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_HostInBrowser()
0x265ae  brfalse.s loc_265C2
0x265b0  ldc.i4.s 0xC
0x265b2  ldstr    aExFileassociat_1// "Ex_FileAssociationNotSupportedForHostIn"...
0x265b7  call     string System.Deployment.Application.Resources::GetString(string s)
0x265bc  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x265c1  throw
0x265c2  ldarg.0
0x265c3  call     instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x265c8  ldlen
0x265c9  brfalse.s loc_265E5
0x265cb  ldloc.0
0x265cc  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomHostSpecified()
0x265d1  brfalse.s loc_265E5
0x265d3  ldc.i4.s 0xC
0x265d5  ldstr    aExFileassociat_2// "Ex_FileAssociationNotSupportedForCustom"...
0x265da  call     string System.Deployment.Application.Resources::GetString(string s)
0x265df  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x265e4  throw
0x265e5  ldarg.0
0x265e6  call     instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x265eb  ldlen
0x265ec  conv.i4
0x265ed  ldc.i4.8
0x265ee  ble.s    loc_2661B
0x265f0  ldc.i4.s 0xC
0x265f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
  ... truncated ...
```
