# Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::DeleteCore

- ea: `0x9e50`
- end: `0x9ff3`
- name: `Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::DeleteCore`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9cc0`
- `0x9ce0`
- `0x9e10`
- `0x9e50`
- `0x2c5d0`
- `0x2c720`

## string_xrefs

- `0x9e9c`: `SPChunkedCookieHandler.DeleteCore`
- `0x9fc3`: `Removed '{0}' cookie(s). NamePrefix: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x9e50  ldc.i4   0x310511C
0x9e55  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x9e5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0x9e5f  ldstr    aName// "name"
0x9e64  ldarg.1
0x9e65  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnWhiteSpace(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, string value)
0x9e6a  ldc.i4   0x310511D
0x9e6f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x9e74  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0x9e79  ldstr    aContext_0// "context"
0x9e7e  ldarg.s  4
0x9e80  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnInvalid(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, class [System.Web]System.Web.HttpContext value)
0x9e85  ldc.i4   0x373C
0x9e8a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x9e8f  brfalse.s loc_9E9C
0x9e91  ldarg.0
0x9e92  ldarg.1
0x9e93  ldarg.s  4
0x9e95  call     instance string Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::GetNameForRequest(string inputName, class [System.Web]System.Web.HttpContext context)
0x9e9a  starg.s  1
0x9e9c  ldstr    aSpchunkedcooki// "SPChunkedCookieHandler.DeleteCore"
0x9ea1  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x9ea6  stloc.2
0x9ea7  ldc.i4.0
0x9ea8  stloc.0
0x9ea9  ldarg.1
0x9eaa  ldarg.s  4
0x9eac  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9eb1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web]System.Web.HttpCookie> Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::GetCookies(string name, class [System.Web]System.Web.HttpRequest request)
0x9eb6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web]System.Web.HttpCookie>::GetEnumerator()
0x9ebb  stloc.3
0x9ebc  br       loc_9FA0
0x9ec1  ldloc.3
0x9ec2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web]System.Web.HttpCookie>::get_Current()
0x9ec7  stloc.1
0x9ec8  ldloc.1
0x9ec9  ldsfld   string [mscorlib]System.String::Empty
0x9ece  callvirt instance void [System.Web]System.Web.HttpCookie::set_Value(string)
0x9ed3  ldloc.1
0x9ed4  ldc.i4   0x7B2
0x9ed9  ldc.i4.1
0x9eda  ldc.i4.1
0x9edb  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x9ee0  callvirt instance void [System.Web]System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime)
0x9ee5  ldloc.1
0x9ee6  ldstr    asc_2F136// "/"
0x9eeb  callvirt instance void [System.Web]System.Web.HttpCookie::set_Path(string)
0x9ef0  ldarg.3
0x9ef1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ef6  brtrue.s loc_9F33
0x9ef8  ldloc.1
0x9ef9  ldarg.3
0x9efa  callvirt instance void [System.Web]System.Web.HttpCookie::set_Domain(string)
0x9eff  ldc.i4   0x310511E
0x9f04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0x9f09  ldc.i4.s 0x64
0x9f0b  ldstr    aSettingDomainO// "Setting domain on cookie. Domain: '{0}'"...
0x9f10  ldc.i4.2
0x9f11  newarr   [mscorlib]System.Object
0x9f16  stloc.s  4
0x9f18  ldloc.s  4
0x9f1a  ldc.i4.0
0x9f1b  ldloc.1
0x9f1c  callvirt instance string [System.Web]System.Web.HttpCookie::get_Domain()
0x9f21  stelem.ref
0x9f22  ldloc.s  4
0x9f24  ldc.i4.1
0x9f25  ldloc.1
0x9f26  callvirt instance string [System.Web]System.Web.HttpCookie::get_Name()
0x9f2b  stelem.ref
0x9f2c  ldloc.s  4
0x9f2e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9f33  ldloc.1
0x9f34  ldarg.0
0x9f35  call     instance bool [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::get_RequireSsl()
0x9f3a  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0x9f3f  ldloc.1
0x9f40  ldarg.0
0x9f41  call     instance bool [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::get_HideFromClientScript()
0x9f46  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0x9f4b  ldarg.s  4
0x9f4d  ldloc.1
0x9f4e  ldarg.0
0x9f4f  call     instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSameSiteMode Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::get_SameSite()
0x9f54  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPCookieSameSiteLogic::SetSameSiteCookieValue(class [System.Web]System.Web.HttpContext, class [System.Web]System.Web.HttpCookie, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSameSiteMode)
0x9f59  pop
0x9f5a  ldarg.s  4
0x9f5c  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x9f61  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x9f66  ldloc.1
0x9f67  callvirt instance string [System.Web]System.Web.HttpCookie::get_Name()
0x9f6c  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Remove(string)
0x9f71  ldarg.s  4
0x9f73  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x9f78  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x9f7d  ldloc.1
0x9f7e  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Add(class [System.Web]System.Web.HttpCookie)
0x9f83  ldc.i4   0x310511F
0x9f88  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0x9f8d  ldc.i4   0xC8
0x9f92  ldstr    aDeletingCookie// "Deleting cookie. Name: '{0}'."
0x9f97  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9f9c  ldloc.0
0x9f9d  ldc.i4.1
0x9f9e  add
0x9f9f  stloc.0
0x9fa0  ldloc.3
0x9fa1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9fa6  brtrue   loc_9EC1
0x9fab  leave.s  loc_9FB7
0x9fad  ldloc.3
0x9fae  brfalse.s loc_9FB6
0x9fb0  ldloc.3
0x9fb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9fb6  endfinally
0x9fb7  ldc.i4   0x3105120
0x9fbc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0x9fc1  ldc.i4.s 0x64
0x9fc3  ldstr    aRemoved0Cookie// "Removed '{0}' cookie(s). NamePrefix: '{"...
0x9fc8  ldc.i4.2
0x9fc9  newarr   [mscorlib]System.Object
0x9fce  stloc.s  5
0x9fd0  ldloc.s  5
0x9fd2  ldc.i4.0
0x9fd3  ldloc.0
0x9fd4  box      [mscorlib]System.Int32
0x9fd9  stelem.ref
0x9fda  ldloc.s  5
0x9fdc  ldc.i4.1
0x9fdd  ldarg.1
0x9fde  stelem.ref
0x9fdf  ldloc.s  5
0x9fe1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9fe6  leave.s  loc_9FF2
0x9fe8  ldloc.2
0x9fe9  brfalse.s loc_9FF1
0x9feb  ldloc.2
0x9fec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ff1  endfinally
0x9ff2  ret
```
