# Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::WriteCore

- ea: `0xa150`
- end: `0xa325`
- name: `Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::WriteCore`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9cc0`
- `0x9ce0`
- `0x9e30`
- `0xa150`
- `0xa330`
- `0x2c5d0`
- `0x2c720`

## string_xrefs

- `0xa19c`: `SPChunkedCookieHandler.WriteCore`
- `0xa234`: `Writing cookie(s). Name: '{0}', Domain: '{1}', Path: '{2}', Secure: '{3}', HttpOnly: '{4}', Session: '{5}', Expiration: '{6}'.`
- `0xa291`: `SPChunkedCookieHandler.WriteCore::WifCodeCall`
- `0xa2c3`: `SPChunkedCookieHandler.WriteCore::Fixup`

## pseudocode

```c

```

## disassembly

```asm
0xa150  ldc.i4   0x3105121
0xa155  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xa15a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0xa15f  ldstr    aName// "name"
0xa164  ldarg.2
0xa165  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnWhiteSpace(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, string value)
0xa16a  ldc.i4   0x3105122
0xa16f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xa174  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0xa179  ldstr    aContext_0// "context"
0xa17e  ldarg.s  8
0xa180  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnInvalid(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, class [System.Web]System.Web.HttpContext value)
0xa185  ldc.i4   0x373C
0xa18a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xa18f  brfalse.s loc_A19C
0xa191  ldarg.0
0xa192  ldarg.2
0xa193  ldarg.s  8
0xa195  call     instance string Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::GetNameForRequest(string inputName, class [System.Web]System.Web.HttpContext context)
0xa19a  starg.s  2
0xa19c  ldstr    aSpchunkedcooki_5// "SPChunkedCookieHandler.WriteCore"
0xa1a1  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xa1a6  stloc.2
0xa1a7  ldarg.s  8
0xa1a9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::UseCookieForClaimsAuth(class [System.Web]System.Web.HttpContext)
0xa1ae  brtrue.s loc_A1D9
0xa1b0  ldarg.s  8
0xa1b2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa1b7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsForceWindowsOnlyRequest(class [System.Web]System.Web.HttpRequest)
0xa1bc  brtrue.s loc_A1D9
0xa1be  ldc.i4   0x3105123
0xa1c3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0xa1c8  ldc.i4.s 0x64
0xa1ca  ldstr    aClaimsWindowsS_0// "Claims Windows Sign-In: Not writing a c"...
0xa1cf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xa1d4  leave    loc_A324
0xa1d9  ldsfld   string [System]System.Uri::UriSchemeHttps
0xa1de  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0xa1e3  callvirt instance string [System]System.Uri::get_Scheme()
0xa1e8  ldc.i4.5
0xa1e9  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa1ee  brfalse.s loc_A1F5
0xa1f0  ldc.i4.1
0xa1f1  starg.s  6
0xa1f3  br.s     loc_A1F8
0xa1f5  ldc.i4.0
0xa1f6  starg.s  6
0xa1f8  ldarg.3
0xa1f9  ldstr    asc_2F136// "/"
0xa1fe  ldc.i4.5
0xa1ff  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa204  brtrue.s loc_A20D
0xa206  ldstr    asc_2F136// "/"
0xa20b  starg.s  3
0xa20d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0xa212  ldc.i4.s 0x64
0xa214  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::ShouldTrace(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xa219  brfalse.s loc_A285
0xa21b  ldarga.s 5
0xa21d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xa222  call     instance bool [mscorlib]System.DateTime::Equals(valuetype [mscorlib]System.DateTime)
0xa227  stloc.0
0xa228  ldc.i4   0x3105141
0xa22d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Cookies()
0xa232  ldc.i4.s 0x64
0xa234  ldstr    aWritingCookieS// "Writing cookie(s). Name: '{0}', Domain:"...
0xa239  ldc.i4.7
0xa23a  newarr   [mscorlib]System.Object
0xa23f  stloc.3
0xa240  ldloc.3
0xa241  ldc.i4.0
0xa242  ldarg.2
0xa243  stelem.ref
0xa244  ldloc.3
0xa245  ldc.i4.1
0xa246  ldarg.s  4
0xa248  stelem.ref
0xa249  ldloc.3
0xa24a  ldc.i4.2
0xa24b  ldarg.3
0xa24c  stelem.ref
0xa24d  ldloc.3
0xa24e  ldc.i4.3
0xa24f  ldarg.s  6
0xa251  box      [mscorlib]System.Boolean
0xa256  stelem.ref
0xa257  ldloc.3
0xa258  ldc.i4.4
0xa259  ldarg.s  7
0xa25b  box      [mscorlib]System.Boolean
0xa260  stelem.ref
0xa261  ldloc.3
0xa262  ldc.i4.5
0xa263  ldloc.0
0xa264  box      [mscorlib]System.Boolean
0xa269  stelem.ref
0xa26a  ldloc.3
0xa26b  ldc.i4.6
0xa26c  ldloc.0
0xa26d  brfalse.s loc_A276
0xa26f  ldsfld   string [mscorlib]System.String::Empty
0xa274  br.s     loc_A27E
0xa276  ldarg.0
0xa277  ldarg.s  5
0xa279  call     instance string Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::LogExpiration(valuetype [mscorlib]System.DateTime expirationTime)
0xa27e  stelem.ref
0xa27f  ldloc.3
0xa280  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa285  leave.s  loc_A291
0xa287  ldloc.2
0xa288  brfalse.s loc_A290
0xa28a  ldloc.2
0xa28b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa290  endfinally
0xa291  ldstr    aSpchunkedcooki_6// "SPChunkedCookieHandler.WriteCore::WifCo"...
0xa296  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xa29b  stloc.s  4
0xa29d  ldarg.0
0xa29e  ldfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.ChunkedCookieHandler Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::m_CookieHandler
0xa2a3  ldarg.1
0xa2a4  ldarg.2
0xa2a5  ldarg.3
0xa2a6  ldarg.s  4
0xa2a8  ldarg.s  5
0xa2aa  ldarg.s  6
0xa2ac  ldarg.s  7
0xa2ae  ldarg.s  8
0xa2b0  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::Write(unsigned int8[], string, string, string, valuetype [mscorlib]System.DateTime, bool, bool, class [System.Web]System.Web.HttpContext)
0xa2b5  leave.s  loc_A2C3
0xa2b7  ldloc.s  4
0xa2b9  brfalse.s loc_A2C2
0xa2bb  ldloc.s  4
0xa2bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa2c2  endfinally
0xa2c3  ldstr    aSpchunkedcooki_7// "SPChunkedCookieHandler.WriteCore::Fixup"
0xa2c8  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xa2cd  stloc.s  5
0xa2cf  ldarg.2
0xa2d0  ldarg.s  8
0xa2d2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xa2d7  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web]System.Web.HttpCookie> Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::GetCookies(string name, class [System.Web]System.Web.HttpResponse response)
0xa2dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web]System.Web.HttpCookie>::GetEnumerator()
0xa2e1  stloc.s  6
0xa2e3  br.s     loc_A2FF
0xa2e5  ldloc.s  6
0xa2e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web]System.Web.HttpCookie>::get_Current()
0xa2ec  stloc.1
0xa2ed  ldloc.1
0xa2ee  brfalse.s loc_A2FF
0xa2f0  ldarg.s  8
0xa2f2  ldloc.1
0xa2f3  ldarg.0
0xa2f4  call     instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSameSiteMode Microsoft.SharePoint.IdentityModel.SPChunkedCookieHandler::get_SameSite()
0xa2f9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPCookieSameSiteLogic::SetSameSiteCookieValue(class [System.Web]System.Web.HttpContext, class [System.Web]System.Web.HttpCookie, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSameSiteMode)
0xa2fe  pop
0xa2ff  ldloc.s  6
0xa301  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa306  brtrue.s loc_A2E5
0xa308  leave.s  loc_A316
0xa30a  ldloc.s  6
0xa30c  brfalse.s loc_A315
0xa30e  ldloc.s  6
0xa310  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa315  endfinally
0xa316  leave.s  loc_A324
0xa318  ldloc.s  5
0xa31a  brfalse.s loc_A323
0xa31c  ldloc.s  5
0xa31e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa323  endfinally
0xa324  ret
```
