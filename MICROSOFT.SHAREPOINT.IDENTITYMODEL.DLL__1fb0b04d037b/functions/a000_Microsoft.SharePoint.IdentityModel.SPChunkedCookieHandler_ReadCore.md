# Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::ReadCore

- ea: `0xa000`
- end: `0xa14e`
- name: `Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::ReadCore`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9ce0`
- `0xa000`
- `0x22f20`

## string_xrefs

- `0xa01c`: `SPChunkedCookieHandler.DeleteCore: The name is null. Stack: '{0}'.`
- `0xa05c`: `SPChunkedCookieHandler.DeleteCore: The context is null. Stack: '{0}'.`
- `0xa09f`: `SPChunkedCookieHandler.ReadCore::WifCodeCall`
- `0xa0c7`: `SPChunkedCookieHandler.ReadCore`
- `0xa11c`: `SPChunkedCookieHandler: Read cookie(s) with name '{0}' for request '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0xa000  ldarg.1
0xa001  brtrue.s loc_A040
0xa003  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa008  ldc.i4.s 0xA
0xa00a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xa00f  stloc.0
0xa010  ldc.i4   0x20F80F
0xa015  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa01a  ldc.i4.s 0xA
0xa01c  ldstr    aSpchunkedcooki_0// "SPChunkedCookieHandler.DeleteCore: The "...
0xa021  ldc.i4.1
0xa022  newarr   [mscorlib]System.Object
0xa027  stloc.s  4
0xa029  ldloc.s  4
0xa02b  ldc.i4.0
0xa02c  ldloc.0
0xa02d  stelem.ref
0xa02e  ldloc.s  4
0xa030  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa035  ldstr    aName// "name"
0xa03a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa03f  throw
0xa040  ldarg.2
0xa041  brtrue.s loc_A080
0xa043  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa048  ldc.i4.s 0xA
0xa04a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xa04f  stloc.1
0xa050  ldc.i4   0x20F810
0xa055  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa05a  ldc.i4.s 0xA
0xa05c  ldstr    aSpchunkedcooki_1// "SPChunkedCookieHandler.DeleteCore: The "...
0xa061  ldc.i4.1
0xa062  newarr   [mscorlib]System.Object
0xa067  stloc.s  5
0xa069  ldloc.s  5
0xa06b  ldc.i4.0
0xa06c  ldloc.1
0xa06d  stelem.ref
0xa06e  ldloc.s  5
0xa070  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa075  ldstr    aContext_0// "context"
0xa07a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa07f  throw
0xa080  ldc.i4   0x373C
0xa085  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xa08a  brfalse.s loc_A09D
0xa08c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::get_IsSPO()
0xa091  brtrue.s loc_A09D
0xa093  ldarg.0
0xa094  ldarg.1
0xa095  ldarg.2
0xa096  call     instance string Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::GetNameForRequest(string inputName, class [System.Web]System.Web.HttpContext context)
0xa09b  starg.s  1
0xa09d  ldnull
0xa09e  stloc.2
0xa09f  ldstr    aSpchunkedcooki_2// "SPChunkedCookieHandler.ReadCore::WifCod"...
0xa0a4  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xa0a9  stloc.s  6
0xa0ab  ldarg.0
0xa0ac  ldfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.ChunkedCookieHandler Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::m_CookieHandler
0xa0b1  ldarg.1
0xa0b2  ldarg.2
0xa0b3  callvirt instance unsigned int8[] [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::Read(string, class [System.Web]System.Web.HttpContext)
0xa0b8  stloc.2
0xa0b9  leave.s  loc_A0C7
0xa0bb  ldloc.s  6
0xa0bd  brfalse.s loc_A0C6
0xa0bf  ldloc.s  6
0xa0c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa0c6  endfinally
0xa0c7  ldstr    aSpchunkedcooki_3// "SPChunkedCookieHandler.ReadCore"
0xa0cc  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xa0d1  stloc.s  7
0xa0d3  ldarg.2
0xa0d4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::UseCookieForClaimsAuth(class [System.Web]System.Web.HttpContext)
0xa0d9  brtrue.s loc_A10A
0xa0db  ldloc.2
0xa0dc  brfalse.s loc_A0EB
0xa0de  ldarg.2
0xa0df  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa0e4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsForceWindowsOnlyRequest(class [System.Web]System.Web.HttpRequest)
0xa0e9  brtrue.s loc_A13E
0xa0eb  ldarg.2
0xa0ec  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa0f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0xa0f6  ldstr    aAuthUser// "AUTH_USER"
0xa0fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa100  stloc.3
0xa101  ldloc.3
0xa102  call     unsigned int8[] Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenXml(string tokenValue)
0xa107  stloc.2
0xa108  br.s     loc_A13E
0xa10a  ldloc.2
0xa10b  brfalse.s loc_A13E
0xa10d  ldc.i4   0x15D5D1
0xa112  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa117  ldc.i4   0xC8
0xa11c  ldstr    aSpchunkedcooki_4// "SPChunkedCookieHandler: Read cookie(s) "...
0xa121  ldc.i4.2
0xa122  newarr   [mscorlib]System.Object
0xa127  stloc.s  8
0xa129  ldloc.s  8
0xa12b  ldc.i4.0
0xa12c  ldarg.1
0xa12d  stelem.ref
0xa12e  ldloc.s  8
0xa130  ldc.i4.1
0xa131  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0xa136  stelem.ref
0xa137  ldloc.s  8
0xa139  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa13e  leave.s  loc_A14C
0xa140  ldloc.s  7
0xa142  brfalse.s loc_A14B
0xa144  ldloc.s  7
0xa146  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa14b  endfinally
0xa14c  ldloc.2
0xa14d  ret
```
