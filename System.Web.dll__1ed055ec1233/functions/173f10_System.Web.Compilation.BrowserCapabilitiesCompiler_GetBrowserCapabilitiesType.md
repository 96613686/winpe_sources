# System.Web.Compilation.BrowserCapabilitiesCompiler::GetBrowserCapabilitiesType

- ea: `0x173f10`
- end: `0x174062`
- name: `System.Web.Compilation.BrowserCapabilitiesCompiler::GetBrowserCapabilitiesType`
- size: `338`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x173ea0`
- `0x175e70`

## callees

- `0x2a1b0`
- `0x31260`
- `0x58b10`
- `0x162260`
- `0x173f10`
- `0x174070`
- `0x174b20`
- `0x174b40`
- `0x175fe0`
- `0x176c00`
- `0x176dd0`
- `0x178b70`
- `0x178c30`
- `0x178ea0`
- `0x179a60`
- `0x179b60`
- `0x17a490`
- `0x17a530`

## string_xrefs

- `0x173f1c`: `__browserCapabilitiesCompiler`
- `0x174038`: `__browserCapabilitiesCompiler`

## pseudocode

```c

```

## disassembly

```asm
0x173f10  call     class [mscorlib]System.Security.IStackWalk System.Web.InternalSecurityPermissions::get_Unrestricted()
0x173f15  callvirt instance void [mscorlib]System.Security.IStackWalk::Assert()
0x173f1a  ldnull
0x173f1b  stloc.0
0x173f1c  ldstr    aBrowsercapabil_0// "__browserCapabilitiesCompiler"
0x173f21  call     class System.Web.Compilation.BuildResult System.Web.Compilation.BuildManager::GetBuildResultFromCache(string cacheKey)
0x173f26  stloc.0
0x173f27  ldloc.0
0x173f28  brtrue   loc_174045
0x173f2d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x173f32  stloc.1
0x173f33  ldsfld   class System.Web.VirtualPath System.Web.Compilation.BrowserCapabilitiesCompiler::AppBrowsersVirtualDir
0x173f38  callvirt instance class System.Web.Hosting.VirtualDirectory System.Web.VirtualPath::GetDirectory()
0x173f3d  stloc.2
0x173f3e  ldsfld   class System.Web.VirtualPath System.Web.Compilation.BrowserCapabilitiesCompiler::AppBrowsersVirtualDir
0x173f43  call     string System.Web.Hosting.HostingEnvironment::MapPathInternal(class System.Web.VirtualPath virtualPath)
0x173f48  stloc.3
0x173f49  ldloc.2
0x173f4a  brfalse  loc_174045
0x173f4f  ldloc.3
0x173f50  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x173f55  brfalse  loc_174045
0x173f5a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x173f5f  stloc.s  4
0x173f61  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x173f66  stloc.s  5
0x173f68  ldloc.2
0x173f69  ldloc.s  4
0x173f6b  ldc.i4.0
0x173f6c  call     bool System.Web.Compilation.BrowserCapabilitiesCompiler::AddBrowserFilesToList(class System.Web.Hosting.VirtualDirectory directory, class [mscorlib]System.Collections.IList list, bool doRecurse)
0x173f71  stloc.s  6
0x173f73  ldloc.s  6
0x173f75  brfalse.s loc_173F83
0x173f77  ldloc.2
0x173f78  ldloc.s  5
0x173f7a  ldc.i4.1
0x173f7b  call     bool System.Web.Compilation.BrowserCapabilitiesCompiler::AddBrowserFilesToList(class System.Web.Hosting.VirtualDirectory directory, class [mscorlib]System.Collections.IList list, bool doRecurse)
0x173f80  pop
0x173f81  br.s     loc_173F87
0x173f83  ldloc.s  4
0x173f85  stloc.s  5
0x173f87  ldloc.s  5
0x173f89  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x173f8e  ldc.i4.0
0x173f8f  ble      loc_174045
0x173f94  newobj   instance void System.Web.Compilation.ApplicationBrowserCapabilitiesBuildProvider::.ctor()
0x173f99  stloc.s  7
0x173f9b  ldloc.s  4
0x173f9d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x173fa2  stloc.s  0xC
0x173fa4  br.s     loc_173FBD
0x173fa6  ldloc.s  0xC
0x173fa8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x173fad  castclass [mscorlib]System.String
0x173fb2  stloc.s  0xD
0x173fb4  ldloc.s  7
0x173fb6  ldloc.s  0xD
0x173fb8  callvirt instance void System.Web.Compilation.ApplicationBrowserCapabilitiesBuildProvider::AddFile(string virtualPath)
0x173fbd  ldloc.s  0xC
0x173fbf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x173fc4  brtrue.s loc_173FA6
0x173fc6  leave.s  loc_173FDD
0x173fc8  ldloc.s  0xC
0x173fca  isinst   [mscorlib]System.IDisposable
0x173fcf  stloc.s  0xE
0x173fd1  ldloc.s  0xE
0x173fd3  brfalse.s loc_173FDC
0x173fd5  ldloc.s  0xE
0x173fd7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x173fdc  endfinally
0x173fdd  ldnull
0x173fde  ldstr    aAppBrowsers// "App_Browsers"
0x173fe3  call     string System.Web.Compilation.BuildManager::GenerateRandomAssemblyName(string baseName)
0x173fe8  newobj   instance void System.Web.Compilation.BuildProvidersCompiler::.ctor(class System.Web.VirtualPath configPath, string outputAssemblyName)
0x173fed  stloc.s  8
0x173fef  ldloc.s  8
0x173ff1  ldloc.s  7
0x173ff3  newobj   instance void System.Web.Util.SingleObjectCollection::.ctor(object o)
0x173ff8  callvirt instance void System.Web.Compilation.BuildProvidersCompiler::SetBuildProviders(class [mscorlib]System.Collections.ICollection buildProviders)
0x173ffd  ldloc.s  8
0x173fff  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults System.Web.Compilation.BuildProvidersCompiler::PerformBuild()
0x174004  stloc.s  9
0x174006  ldloc.s  9
0x174008  callvirt instance class [mscorlib]System.Reflection.Assembly [System]System.CodeDom.Compiler.CompilerResults::get_CompiledAssembly()
0x17400d  stloc.s  0xA
0x17400f  ldloc.s  0xA
0x174011  ldstr    aAspApplication// "ASP.ApplicationBrowserCapabilitiesFacto"...
0x174016  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x17401b  stloc.s  0xB
0x17401d  ldloc.s  0xB
0x17401f  newobj   instance void System.Web.Compilation.BuildResultCompiledType::.ctor(class [mscorlib]System.Type t)
0x174024  stloc.0
0x174025  ldloc.0
0x174026  ldsfld   class System.Web.VirtualPath System.Web.Compilation.BrowserCapabilitiesCompiler::AppBrowsersVirtualDir
0x17402b  callvirt instance void System.Web.Compilation.BuildResult::set_VirtualPath(class System.Web.VirtualPath value)
0x174030  ldloc.0
0x174031  ldloc.s  5
0x174033  callvirt instance void System.Web.Compilation.BuildResult::AddVirtualPathDependencies(class [mscorlib]System.Collections.ICollection sourceDependencies)
0x174038  ldstr    aBrowsercapabil_0// "__browserCapabilitiesCompiler"
0x17403d  ldloc.0
0x17403e  ldloc.1
0x17403f  call     bool System.Web.Compilation.BuildManager::CacheBuildResult(string cacheKey, class System.Web.Compilation.BuildResult result, valuetype [mscorlib]System.DateTime utcStart)
0x174044  pop
0x174045  leave.s  loc_17404D
0x174047  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x17404c  endfinally
0x17404d  ldloc.0
0x17404e  brtrue.s loc_174056
0x174050  ldsfld   class [mscorlib]System.Type System.Web.Compilation.BrowserCapabilitiesCompiler::_browserCapabilitiesFactoryBaseType
0x174055  ret
0x174056  ldloc.0
0x174057  castclass System.Web.Compilation.BuildResultCompiledType
0x17405c  callvirt instance class [mscorlib]System.Type System.Web.Compilation.BuildResultCompiledType::get_ResultType()
0x174061  ret
```
