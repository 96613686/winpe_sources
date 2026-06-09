# System.Web.UI.ViewStateException::Initialize

- ea: `0x86950`
- end: `0x86a77`
- name: `System.Web.UI.ViewStateException::Initialize`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x86930`

## callees

- `0x15e20`
- `0x16330`
- `0x16350`
- `0x1c860`
- `0x1fc20`
- `0x24240`
- `0x34f20`
- `0x86950`
- `0x86a90`

## string_xrefs

- `0x86a01`: `PATH_INFO`
- `0x869d5`: `HTTP_USER_AGENT`
- `0x86a15`: `\n	Client IP: {0}\n	Port: {1}\n	Referer: {2}\n	Path: {3}\n	User-Agent: {4}\n	ViewState: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x86950  ldarg.0
0x86951  ldarg.1
0x86952  stfld    string System.Web.UI.ViewStateException::_persistedState
0x86957  call     class System.Web.HttpContext System.Web.HttpContext::get_Current()
0x8695c  stloc.0
0x8695d  ldloc.0
0x8695e  brtrue.s loc_86963
0x86960  ldnull
0x86961  br.s     loc_86969
0x86963  ldloc.0
0x86964  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x86969  stloc.1
0x8696a  ldloc.0
0x8696b  brtrue.s loc_86970
0x8696d  ldnull
0x8696e  br.s     loc_86976
0x86970  ldloc.0
0x86971  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x86976  stloc.2
0x86977  ldloc.1
0x86978  brfalse.s loc_86989
0x8697a  ldloc.2
0x8697b  brfalse.s loc_86989
0x8697d  ldc.i4   0x12C
0x86982  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0x86987  brtrue.s loc_86996
0x86989  ldarg.0
0x8698a  ldarg.0
0x8698b  call     instance string System.Web.UI.ViewStateException::get_ShortMessage()
0x86990  stfld    string System.Web.UI.ViewStateException::_message
0x86995  ret
0x86996  ldarg.0
0x86997  ldloc.2
0x86998  callvirt instance bool System.Web.HttpResponse::get_IsClientConnected()
0x8699d  stfld    bool System.Web.UI.ViewStateException::_isConnected
0x869a2  ldarg.0
0x869a3  ldloc.1
0x869a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x869a9  ldstr    aRemoteAddr// "REMOTE_ADDR"
0x869ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x869b3  stfld    string System.Web.UI.ViewStateException::_remoteAddr
0x869b8  ldarg.0
0x869b9  ldloc.1
0x869ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x869bf  ldstr    aRemotePort// "REMOTE_PORT"
0x869c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x869c9  stfld    string System.Web.UI.ViewStateException::_remotePort
0x869ce  ldarg.0
0x869cf  ldloc.1
0x869d0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x869d5  ldstr    aHttpUserAgent// "HTTP_USER_AGENT"
0x869da  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x869df  stfld    string System.Web.UI.ViewStateException::_userAgent
0x869e4  ldarg.0
0x869e5  ldloc.1
0x869e6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x869eb  ldstr    aHttpReferer// "HTTP_REFERER"
0x869f0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x869f5  stfld    string System.Web.UI.ViewStateException::_referer
0x869fa  ldarg.0
0x869fb  ldloc.1
0x869fc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x86a01  ldstr    aPathInfo// "PATH_INFO"
0x86a06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86a0b  stfld    string System.Web.UI.ViewStateException::_path
0x86a10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86a15  ldstr    aClientIp0Port1// "\r\n\tClient IP: {0}\r\n\tPort: {1}\r\n"...
0x86a1a  ldc.i4.6
0x86a1b  newarr   [mscorlib]System.Object
0x86a20  dup
0x86a21  ldc.i4.0
0x86a22  ldarg.0
0x86a23  ldfld    string System.Web.UI.ViewStateException::_remoteAddr
0x86a28  stelem.ref
0x86a29  dup
0x86a2a  ldc.i4.1
0x86a2b  ldarg.0
0x86a2c  ldfld    string System.Web.UI.ViewStateException::_remotePort
0x86a31  stelem.ref
0x86a32  dup
0x86a33  ldc.i4.2
0x86a34  ldarg.0
0x86a35  ldfld    string System.Web.UI.ViewStateException::_referer
0x86a3a  stelem.ref
0x86a3b  dup
0x86a3c  ldc.i4.3
0x86a3d  ldarg.0
0x86a3e  ldfld    string System.Web.UI.ViewStateException::_path
0x86a43  stelem.ref
0x86a44  dup
0x86a45  ldc.i4.4
0x86a46  ldarg.0
0x86a47  ldfld    string System.Web.UI.ViewStateException::_userAgent
0x86a4c  stelem.ref
0x86a4d  dup
0x86a4e  ldc.i4.5
0x86a4f  ldarg.0
0x86a50  ldfld    string System.Web.UI.ViewStateException::_persistedState
0x86a55  stelem.ref
0x86a56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x86a5b  stloc.3
0x86a5c  ldarg.0
0x86a5d  ldstr    aViewstateInval_0// "ViewState_InvalidViewStatePlus"
0x86a62  ldc.i4.1
0x86a63  newarr   [mscorlib]System.Object
0x86a68  dup
0x86a69  ldc.i4.0
0x86a6a  ldloc.3
0x86a6b  stelem.ref
0x86a6c  call     string System.Web.SR::GetString(string name, object[] args)
0x86a71  stfld    string System.Web.UI.ViewStateException::_message
0x86a76  ret
```
