# System.Web.Hosting.ApplicationManager::CreateObjectWithDefaultAppHostAndAppId_1

- ea: `0x15ead0`
- end: `0x15eb89`
- name: `System.Web.Hosting.ApplicationManager::CreateObjectWithDefaultAppHostAndAppId_1`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x15eab0`
- `0x17c690`

## callees

- `0x21db0`
- `0x30f70`
- `0x315d0`
- `0x549e0`
- `0x15e910`
- `0x15ea20`
- `0x15ead0`
- `0x160910`
- `0x160930`
- `0x160950`
- `0x162770`
- `0x162780`
- `0x1664e0`
- `0x1666f0`
- `0x16c480`
- `0x17be90`

## string_xrefs

- `0x15eb5a`: `_precompile`
- `0x15eb6c`: `_precompile_u`

## pseudocode

```c

```

## disassembly

```asm
0x15ead0  ldarg.1
0x15ead1  brtrue.s loc_15EB1B
0x15ead3  call     void System.Web.HttpRuntime::ForceStaticInit()
0x15ead8  ldarg.2
0x15ead9  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x15eade  ldnull
0x15eadf  ldc.i4.1
0x15eae0  ldnull
0x15eae1  ldarg.s  5
0x15eae3  callvirt instance string System.Web.Hosting.HostingEnvironmentParameters::get_IISExpressVersion()
0x15eae8  newobj   instance void System.Web.Hosting.ISAPIApplicationHost::.ctor(string appIdOrVirtualPath, string physicalPath, bool validatePhysicalPath, class System.Web.Hosting.IProcessHostSupportFunctions functions, [opt] string iisVersion)
0x15eaed  stloc.1
0x15eaee  ldarg.s  7
0x15eaf0  ldloc.1
0x15eaf1  stind.ref
0x15eaf2  ldarg.s  6
0x15eaf4  ldloc.1
0x15eaf5  callvirt instance string System.Web.Hosting.ISAPIApplicationHost::get_AppId()
0x15eafa  stind.ref
0x15eafb  ldarg.s  7
0x15eafd  ldind.ref
0x15eafe  callvirt instance string System.Web.Hosting.IApplicationHost::GetVirtualPath()
0x15eb03  call     class System.Web.VirtualPath System.Web.VirtualPath::Create(string virtualPath)
0x15eb08  starg.s  2
0x15eb0a  ldarg.s  7
0x15eb0c  ldind.ref
0x15eb0d  callvirt instance string System.Web.Hosting.IApplicationHost::GetPhysicalPath()
0x15eb12  call     string System.Web.Util.FileUtil::FixUpPhysicalDirectory(string dir)
0x15eb17  starg.s  1
0x15eb19  br.s     loc_15EB31
0x15eb1b  ldarg.s  6
0x15eb1d  ldarg.0
0x15eb1e  ldarg.2
0x15eb1f  ldarg.1
0x15eb20  ldnull
0x15eb21  call     instance string System.Web.Hosting.ApplicationManager::CreateSimpleAppID(class System.Web.VirtualPath virtualPath, string physicalPath, string siteName)
0x15eb26  stind.ref
0x15eb27  ldarg.s  7
0x15eb29  ldarg.2
0x15eb2a  ldarg.1
0x15eb2b  newobj   instance void System.Web.Hosting.SimpleApplicationHost::.ctor(class System.Web.VirtualPath virtualPath, string physicalPath)
0x15eb30  stind.ref
0x15eb31  ldarg.s  5
0x15eb33  callvirt instance string System.Web.Hosting.HostingEnvironmentParameters::get_PrecompilationTargetPhysicalDirectory()
0x15eb38  stloc.0
0x15eb39  ldloc.0
0x15eb3a  brfalse.s loc_15EB77
0x15eb3c  ldarg.s  5
0x15eb3e  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x15eb43  brfalse.s loc_15EB67
0x15eb45  ldarg.s  5
0x15eb47  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x15eb4c  callvirt instance valuetype System.Web.Compilation.PrecompilationFlags System.Web.Compilation.ClientBuildManagerParameter::get_PrecompilationFlags()
0x15eb51  ldc.i4.1
0x15eb52  and
0x15eb53  brtrue.s loc_15EB67
0x15eb55  ldarg.s  6
0x15eb57  ldarg.s  6
0x15eb59  ldind.ref
0x15eb5a  ldstr    aPrecompile// "_precompile"
0x15eb5f  call     string [mscorlib]System.String::Concat(string, string)
0x15eb64  stind.ref
0x15eb65  br.s     loc_15EB77
0x15eb67  ldarg.s  6
0x15eb69  ldarg.s  6
0x15eb6b  ldind.ref
0x15eb6c  ldstr    aPrecompileU// "_precompile_u"
0x15eb71  call     string [mscorlib]System.String::Concat(string, string)
0x15eb76  stind.ref
0x15eb77  ldarg.0
0x15eb78  ldarg.s  6
0x15eb7a  ldind.ref
0x15eb7b  ldarg.3
0x15eb7c  ldarg.s  7
0x15eb7e  ldind.ref
0x15eb7f  ldarg.s  4
0x15eb81  ldarg.s  5
0x15eb83  call     instance class System.Web.Hosting.IRegisteredObject System.Web.Hosting.ApplicationManager::CreateObjectInternal(string appId, class [mscorlib]System.Type type, class System.Web.Hosting.IApplicationHost appHost, bool failIfExists, class System.Web.Hosting.HostingEnvironmentParameters hostingParameters)
0x15eb88  ret
```
