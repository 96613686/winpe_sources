# System.Web.Script.Services.WebServiceData::GetWebServiceData_1

- ea: `0x2e4b0`
- end: `0x2e5d9`
- name: `System.Web.Script.Services.WebServiceData::GetWebServiceData_1`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x2e250`
- `0x2e480`
- `0x2e4a0`

## callees

- `0x2b810`
- `0x2b830`
- `0x2e400`
- `0x2e490`
- `0x2e4b0`
- `0x2e660`

## string_xrefs

- `0x2e55f`: `_AppService.axd`

## pseudocode

```c

```

## disassembly

```asm
0x2e4b0  ldarg.1
0x2e4b1  call     string [System.Web]System.Web.VirtualPathUtility::ToAbsolute(string)
0x2e4b6  starg.s  1
0x2e4b8  ldarg.1
0x2e4b9  call     string System.Web.Script.Services.WebServiceData::GetCacheKey(string virtualPath)
0x2e4be  stloc.0
0x2e4bf  ldarg.0
0x2e4c0  callvirt instance class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpContext::get_Cache()
0x2e4c5  ldloc.0
0x2e4c6  callvirt instance object [System.Web]System.Web.Caching.Cache::get_Item(string)
0x2e4cb  isinst   System.Web.Script.Services.WebServiceData
0x2e4d0  stloc.1
0x2e4d1  ldloc.1
0x2e4d2  brtrue   loc_2E58D
0x2e4d7  call     class [System.Web]System.Web.Hosting.VirtualPathProvider [System.Web]System.Web.Hosting.HostingEnvironment::get_VirtualPathProvider()
0x2e4dc  ldarg.1
0x2e4dd  callvirt instance bool [System.Web]System.Web.Hosting.VirtualPathProvider::FileExists(string)
0x2e4e2  brfalse.s loc_2E55E
0x2e4e4  ldnull
0x2e4e5  stloc.2
0x2e4e6  ldarg.1
0x2e4e7  call     class [mscorlib]System.Type [System.Web]System.Web.Compilation.BuildManager::GetCompiledType(string)
0x2e4ec  stloc.2
0x2e4ed  ldloc.2
0x2e4ee  ldnull
0x2e4ef  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e4f4  brfalse.s loc_2E511
0x2e4f6  ldarg.1
0x2e4f7  ldtoken  [System.Web]System.Web.UI.Page
0x2e4fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e501  call     object [System.Web]System.Web.Compilation.BuildManager::CreateInstanceFromVirtualPath(string, class [mscorlib]System.Type)
0x2e506  stloc.3
0x2e507  ldloc.3
0x2e508  brfalse.s loc_2E511
0x2e50a  ldloc.3
0x2e50b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e510  stloc.2
0x2e511  leave.s  loc_2E516
0x2e513  pop
0x2e514  leave.s  loc_2E516
0x2e516  ldloc.2
0x2e517  ldnull
0x2e518  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e51d  brfalse.s loc_2E58D
0x2e51f  ldloc.2
0x2e520  ldarg.3
0x2e521  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2e526  stloc.1
0x2e527  ldarg.0
0x2e528  ldarg.1
0x2e529  call     class [System.Web]System.Web.Compilation.BuildDependencySet [System.Web]System.Web.Compilation.BuildManager::GetCachedBuildDependencySet(class [System.Web]System.Web.HttpContext, string)
0x2e52e  stloc.s  4
0x2e530  ldloc.s  4
0x2e532  brfalse.s loc_2E58D
0x2e534  call     class [System.Web]System.Web.Hosting.VirtualPathProvider [System.Web]System.Web.Hosting.HostingEnvironment::get_VirtualPathProvider()
0x2e539  ldarg.1
0x2e53a  ldloc.s  4
0x2e53c  callvirt instance class [mscorlib]System.Collections.IEnumerable [System.Web]System.Web.Compilation.BuildDependencySet::get_VirtualPaths()
0x2e541  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2e546  callvirt instance class [System.Web]System.Web.Caching.CacheDependency [System.Web]System.Web.Hosting.VirtualPathProvider::GetCacheDependency(string, class [mscorlib]System.Collections.IEnumerable, valuetype [mscorlib]System.DateTime)
0x2e54b  stloc.s  5
0x2e54d  ldarg.0
0x2e54e  callvirt instance class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpContext::get_Cache()
0x2e553  ldloc.0
0x2e554  ldloc.1
0x2e555  ldloc.s  5
0x2e557  callvirt instance void [System.Web]System.Web.Caching.Cache::Insert(string, object, class [System.Web]System.Web.Caching.CacheDependency)
0x2e55c  br.s     loc_2E58D
0x2e55e  ldarg.1
0x2e55f  ldstr    aAppserviceAxd// "_AppService.axd"
0x2e564  ldc.i4.5
0x2e565  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2e56a  brfalse.s loc_2E58D
0x2e56c  ldarg.0
0x2e56d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2e572  callvirt instance string [System.Web]System.Web.HttpRequest::get_AppRelativeCurrentExecutionFilePath()
0x2e577  call     class System.Web.Script.Services.WebServiceData System.Web.Script.Services.WebServiceData::GetApplicationService(string appRelativePath)
0x2e57c  stloc.1
0x2e57d  ldloc.1
0x2e57e  brfalse.s loc_2E58D
0x2e580  ldarg.0
0x2e581  callvirt instance class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpContext::get_Cache()
0x2e586  ldloc.0
0x2e587  ldloc.1
0x2e588  callvirt instance void [System.Web]System.Web.Caching.Cache::Insert(string, object)
0x2e58d  ldloc.1
0x2e58e  brtrue.s loc_2E5D7
0x2e590  ldarg.2
0x2e591  brfalse.s loc_2E5D5
0x2e593  ldarg.s  4
0x2e595  brfalse.s loc_2E5B6
0x2e597  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e59c  call     string System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceDataInlineScript()
0x2e5a1  ldc.i4.1
0x2e5a2  newarr   [mscorlib]System.Object
0x2e5a7  dup
0x2e5a8  ldc.i4.0
0x2e5a9  ldarg.1
0x2e5aa  stelem.ref
0x2e5ab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e5b0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e5b5  throw
0x2e5b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e5bb  call     string System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceData()
0x2e5c0  ldc.i4.1
0x2e5c1  newarr   [mscorlib]System.Object
0x2e5c6  dup
0x2e5c7  ldc.i4.0
0x2e5c8  ldarg.1
0x2e5c9  stelem.ref
0x2e5ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e5cf  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e5d4  throw
0x2e5d5  ldnull
0x2e5d6  ret
0x2e5d7  ldloc.1
0x2e5d8  ret
```
