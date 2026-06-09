# System.Web.HttpServerUtility::Execute_2

- ea: `0x253a0`
- end: `0x255a9`
- name: `System.Web.HttpServerUtility::Execute_2`
- size: `521`
- prototype: ``
- caller_count: `5`
- callee_count: `31`
- tags: ``

## callers

- `0x6560`
- `0x25370`
- `0x25380`
- `0x25390`
- `0x25aa0`

## callees

- `0xf5d0`
- `0xf740`
- `0x160d0`
- `0x16330`
- `0x16350`
- `0x16a20`
- `0x16dc0`
- `0x16dd0`
- `0x17950`
- `0x18990`
- `0x189c0`
- `0x189e0`
- `0x18a50`
- `0x1b810`
- `0x1bbd0`
- `0x1d580`
- `0x211d0`
- `0x22270`
- `0x253a0`
- `0x25610`
- `0x25fb0`
- `0x2a1b0`
- `0x2a2d0`
- `0x30f70`
- `0x31110`
- `0x312b0`
- `0x315d0`
- `0x34f20`
- `0x34fa0`
- `0x58dd0`
- `0x59600`

## string_xrefs

- `0x25418`: `Invalid_path_for_child_request`
- `0x25579`: `Error_executing_child_request_for_path`

## pseudocode

```c

```

## disassembly

```asm
0x253a0  ldarg.0
0x253a1  call     instance void System.Web.HttpServerUtility::EnsureHasNotTransitionedToWebSocket()
0x253a6  ldarg.0
0x253a7  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x253ac  brtrue.s loc_253BE
0x253ae  ldstr    aServerNotAvail// "Server_not_available"
0x253b3  call     string System.Web.SR::GetString(string name)
0x253b8  newobj   instance void System.Web.HttpException::.ctor(string message)
0x253bd  throw
0x253be  ldarg.1
0x253bf  brtrue.s loc_253CC
0x253c1  ldstr    aPath// "path"
0x253c6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x253cb  throw
0x253cc  ldnull
0x253cd  stloc.0
0x253ce  ldarg.0
0x253cf  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x253d4  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x253d9  stloc.1
0x253da  ldarg.0
0x253db  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x253e0  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x253e5  stloc.2
0x253e6  ldloc.2
0x253e7  ldarg.1
0x253e8  callvirt instance string System.Web.HttpResponse::RemoveAppPathModifier(string virtualPath)
0x253ed  starg.s  1
0x253ef  ldarg.1
0x253f0  ldc.i4.s 0x3F
0x253f2  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x253f7  stloc.3
0x253f8  ldloc.3
0x253f9  ldc.i4.0
0x253fa  blt.s    loc_25410
0x253fc  ldarg.1
0x253fd  ldloc.3
0x253fe  ldc.i4.1
0x253ff  add
0x25400  callvirt instance string [mscorlib]System.String::Substring(int32)
0x25405  stloc.0
0x25406  ldarg.1
0x25407  ldc.i4.0
0x25408  ldloc.3
0x25409  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2540e  starg.s  1
0x25410  ldarg.1
0x25411  call     bool System.Web.Util.UrlPath::IsValidVirtualPathWithoutProtocol(string path)
0x25416  brtrue.s loc_25432
0x25418  ldstr    aInvalidPathFor_1// "Invalid_path_for_child_request"
0x2541d  ldc.i4.1
0x2541e  newarr   [mscorlib]System.Object
0x25423  dup
0x25424  ldc.i4.0
0x25425  ldarg.1
0x25426  stelem.ref
0x25427  call     string System.Web.SR::GetString(string name, object[] args)
0x2542c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x25431  throw
0x25432  ldarg.1
0x25433  call     class System.Web.VirtualPath System.Web.VirtualPath::Create(string virtualPath)
0x25438  stloc.s  4
0x2543a  ldnull
0x2543b  stloc.s  5
0x2543d  ldloc.1
0x2543e  ldloc.s  4
0x25440  callvirt instance string System.Web.HttpRequest::MapPath(class System.Web.VirtualPath virtualPath)
0x25445  stloc.s  6
0x25447  ldloc.1
0x25448  callvirt instance class System.Web.VirtualPath System.Web.HttpRequest::get_FilePathObject()
0x2544d  ldloc.s  4
0x2544f  callvirt instance class System.Web.VirtualPath System.Web.VirtualPath::Combine(class System.Web.VirtualPath relativePath)
0x25454  stloc.s  7
0x25456  ldloc.s  6
0x25458  call     class [mscorlib]System.Security.IStackWalk System.Web.InternalSecurityPermissions::FileReadAccess(string filename)
0x2545d  callvirt instance void [mscorlib]System.Security.IStackWalk::Demand()
0x25462  call     bool System.Web.HttpRuntime::get_IsLegacyCas()
0x25467  brfalse.s loc_25473
0x25469  call     class [mscorlib]System.Security.IStackWalk System.Web.InternalSecurityPermissions::get_Unrestricted()
0x2546e  callvirt instance void [mscorlib]System.Security.IStackWalk::Assert()
0x25473  nop
0x25474  ldloc.s  4
0x25476  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x2547b  ldc.i4.s 0x2E
0x2547d  call     bool System.Web.Util.StringUtil::StringEndsWith(string s, char c)
0x25482  brfalse.s loc_25494
0x25484  ldc.i4   0x194
0x25489  ldsfld   string [mscorlib]System.String::Empty
0x2548e  newobj   instance void System.Web.HttpException::.ctor(int32 httpCode, string message)
0x25493  throw
0x25494  ldloc.s  7
0x25496  callvirt instance bool System.Web.VirtualPath::get_IsWithinAppRoot()
0x2549b  ldc.i4.0
0x2549c  ceq
0x2549e  stloc.s  8
0x254a0  ldarg.0
0x254a1  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x254a6  newobj   instance void System.Web.DisposableHttpContextWrapper::.ctor(class System.Web.HttpContext context)
0x254ab  stloc.s  9
0x254ad  ldarg.0
0x254ae  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x254b3  dup
0x254b4  callvirt instance int32 System.Web.HttpContext::get_ServerExecuteDepth()
0x254b9  stloc.s  0xA
0x254bb  ldloc.s  0xA
0x254bd  ldc.i4.1
0x254be  add
0x254bf  callvirt instance void System.Web.HttpContext::set_ServerExecuteDepth(int32 value)
0x254c4  ldarg.0
0x254c5  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x254ca  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x254cf  isinst   System.Web.Hosting.IIS7WorkerRequest
0x254d4  brfalse.s loc_254FD
0x254d6  ldarg.0
0x254d7  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x254dc  callvirt instance class System.Web.HttpApplication System.Web.HttpContext::get_ApplicationInstance()
0x254e1  ldarg.0
0x254e2  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x254e7  ldloc.1
0x254e8  callvirt instance string System.Web.HttpRequest::get_RequestType()
0x254ed  ldloc.s  7
0x254ef  ldloc.s  6
0x254f1  ldloc.s  8
0x254f3  ldc.i4.1
0x254f4  callvirt instance class System.Web.IHttpHandler System.Web.HttpApplication::MapIntegratedHttpHandler(class System.Web.HttpContext context, string requestType, class System.Web.VirtualPath path, string pathTranslated, bool useAppConfig, bool convertNativeStaticFileModule)
0x254f9  stloc.s  5
0x254fb  br.s     loc_25521
0x254fd  ldarg.0
0x254fe  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x25503  callvirt instance class System.Web.HttpApplication System.Web.HttpContext::get_ApplicationInstance()
0x25508  ldarg.0
0x25509  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x2550e  ldloc.1
0x2550f  callvirt instance string System.Web.HttpRequest::get_RequestType()
0x25514  ldloc.s  7
0x25516  ldloc.s  6
0x25518  ldloc.s  8
0x2551a  callvirt instance class System.Web.IHttpHandler System.Web.HttpApplication::MapHttpHandler(class System.Web.HttpContext context, string requestType, class System.Web.VirtualPath path, string pathTranslated, bool useAppConfig)
0x2551f  stloc.s  5
0x25521  leave.s  loc_2553B
0x25523  ldarg.0
0x25524  ldfld    class System.Web.HttpContext System.Web.HttpServerUtility::_context
0x25529  dup
0x2552a  callvirt instance int32 System.Web.HttpContext::get_ServerExecuteDepth()
0x2552f  stloc.s  0xA
0x25531  ldloc.s  0xA
0x25533  ldc.i4.1
0x25534  sub
0x25535  callvirt instance void System.Web.HttpContext::set_ServerExecuteDepth(int32 value)
0x2553a  endfinally
0x2553b  leave.s  loc_25549
0x2553d  ldloc.s  9
0x2553f  brfalse.s loc_25548
0x25541  ldloc.s  9
0x25543  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25548  endfinally
0x25549  leave.s  loc_25595
0x2554b  stloc.s  0xB
0x2554d  ldloc.s  0xB
0x2554f  isinst   System.Web.HttpException
0x25554  brfalse.s loc_25579
0x25556  ldloc.s  0xB
0x25558  castclass System.Web.HttpException
0x2555d  callvirt instance int32 System.Web.HttpException::GetHttpCode()
0x25562  stloc.s  0xC
0x25564  ldloc.s  0xC
0x25566  ldc.i4   0x1F4
0x2556b  beq.s    loc_25579
0x2556d  ldloc.s  0xC
0x2556f  ldc.i4   0x194
0x25574  beq.s    loc_25579
0x25576  ldnull
0x25577  stloc.s  0xB
0x25579  ldstr    aErrorExecuting// "Error_executing_child_request_for_path"
0x2557e  ldc.i4.1
0x2557f  newarr   [mscorlib]System.Object
0x25584  dup
0x25585  ldc.i4.0
0x25586  ldarg.1
0x25587  stelem.ref
0x25588  call     string System.Web.SR::GetString(string name, object[] args)
0x2558d  ldloc.s  0xB
0x2558f  newobj   instance void System.Web.HttpException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x25594  throw
0x25595  ldarg.0
0x25596  ldloc.s  5
0x25598  ldarg.2
0x25599  ldarg.3
0x2559a  ldc.i4.1
0x2559b  ldloc.s  4
0x2559d  ldloc.s  7
0x2559f  ldloc.s  6
0x255a1  ldnull
0x255a2  ldloc.0
0x255a3  call     instance void System.Web.HttpServerUtility::ExecuteInternal(class System.Web.IHttpHandler handler, class [mscorlib]System.IO.TextWriter writer, bool preserveForm, bool setPreviousPage, class System.Web.VirtualPath path, class System.Web.VirtualPath filePath, string physPath, class [mscorlib]System.Exception error, string queryStringOverride)
0x255a8  ret
```
