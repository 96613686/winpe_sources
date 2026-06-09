# System.Web.HttpServerVarsCollection::GetSimpleServerVar

- ea: `0x267d0`
- end: `0x2696e`
- name: `System.Web.HttpServerVarsCollection::GetSimpleServerVar`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x269b0`

## callees

- `0x1a980`
- `0x1b710`
- `0x1ba50`
- `0x1bbc0`
- `0x1be40`
- `0x1bf10`
- `0x1bfd0`
- `0x1c000`
- `0x1c4b0`
- `0x267d0`
- `0x58d50`

## string_xrefs

- `0x268ba`: `PATH_INFO`
- `0x268d3`: `PATH_TRANSLATED`
- `0x26882`: `HTTP_USER_AGENT`

## pseudocode

```c

```

## disassembly

```asm
0x267d0  ldarg.1
0x267d1  brfalse  loc_2696C
0x267d6  ldarg.1
0x267d7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x267dc  ldc.i4.1
0x267dd  ble      loc_2696C
0x267e2  ldarg.0
0x267e3  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x267e8  brfalse  loc_2696C
0x267ed  ldarg.1
0x267ee  ldc.i4.0
0x267ef  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x267f4  stloc.0
0x267f5  ldloc.0
0x267f6  ldc.i4.s 0x53
0x267f8  bgt.un.s loc_26822
0x267fa  ldloc.0
0x267fb  ldc.i4.s 0x41
0x267fd  beq.s    loc_2684A
0x267ff  ldloc.0
0x26800  ldc.i4.s 0x48
0x26802  beq.s    loc_26881
0x26804  ldloc.0
0x26805  ldc.i4.s 0x50
0x26807  sub
0x26808  switch   loc_268B9, loc_2689D, loc_268EE, loc_26953
0x2681d  br       loc_2696C
0x26822  ldloc.0
0x26823  ldc.i4.s 0x61
0x26825  beq.s    loc_2684A
0x26827  ldloc.0
0x26828  ldc.i4.s 0x68
0x2682a  beq.s    loc_26881
0x2682c  ldloc.0
0x2682d  ldc.i4.s 0x70
0x2682f  sub
0x26830  switch   loc_268B9, loc_2689D, loc_268EE, loc_26953
0x26845  br       loc_2696C
0x2684a  ldarg.1
0x2684b  ldstr    aAuthType// "AUTH_TYPE"
0x26850  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x26855  brfalse.s loc_26864
0x26857  ldarg.0
0x26858  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x2685d  ldc.i4.1
0x2685e  callvirt instance string System.Web.HttpRequest::CalcDynamicServerVariable(valuetype System.Web.DynamicServerVariable var)
0x26863  ret
0x26864  ldarg.1
0x26865  ldstr    aAuthUser// "AUTH_USER"
0x2686a  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x2686f  brfalse  loc_2696C
0x26874  ldarg.0
0x26875  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x2687a  ldc.i4.2
0x2687b  callvirt instance string System.Web.HttpRequest::CalcDynamicServerVariable(valuetype System.Web.DynamicServerVariable var)
0x26880  ret
0x26881  ldarg.1
0x26882  ldstr    aHttpUserAgent// "HTTP_USER_AGENT"
0x26887  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x2688c  brfalse  loc_2696C
0x26891  ldarg.0
0x26892  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x26897  callvirt instance string System.Web.HttpRequest::get_UserAgent()
0x2689c  ret
0x2689d  ldarg.1
0x2689e  ldstr    aQueryString// "QUERY_STRING"
0x268a3  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x268a8  brfalse  loc_2696C
0x268ad  ldarg.0
0x268ae  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x268b3  callvirt instance string System.Web.HttpRequest::get_QueryStringText()
0x268b8  ret
0x268b9  ldarg.1
0x268ba  ldstr    aPathInfo// "PATH_INFO"
0x268bf  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x268c4  brfalse.s loc_268D2
0x268c6  ldarg.0
0x268c7  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x268cc  callvirt instance string System.Web.HttpRequest::get_Path()
0x268d1  ret
0x268d2  ldarg.1
0x268d3  ldstr    aPathTranslated// "PATH_TRANSLATED"
0x268d8  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x268dd  brfalse  loc_2696C
0x268e2  ldarg.0
0x268e3  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x268e8  callvirt instance string System.Web.HttpRequest::get_PhysicalPath()
0x268ed  ret
0x268ee  ldarg.1
0x268ef  ldstr    aRequestMethod// "REQUEST_METHOD"
0x268f4  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x268f9  brfalse.s loc_26907
0x268fb  ldarg.0
0x268fc  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x26901  callvirt instance string System.Web.HttpRequest::get_HttpMethod()
0x26906  ret
0x26907  ldarg.1
0x26908  ldstr    aRemoteUser// "REMOTE_USER"
0x2690d  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x26912  brfalse.s loc_26921
0x26914  ldarg.0
0x26915  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x2691a  ldc.i4.2
0x2691b  callvirt instance string System.Web.HttpRequest::CalcDynamicServerVariable(valuetype System.Web.DynamicServerVariable var)
0x26920  ret
0x26921  ldarg.1
0x26922  ldstr    aRemoteHost// "REMOTE_HOST"
0x26927  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x2692c  brfalse.s loc_2693A
0x2692e  ldarg.0
0x2692f  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x26934  callvirt instance string System.Web.HttpRequest::get_UserHostName()
0x26939  ret
0x2693a  ldarg.1
0x2693b  ldstr    aRemoteAddress// "REMOTE_ADDRESS"
0x26940  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x26945  brfalse.s loc_2696C
0x26947  ldarg.0
0x26948  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x2694d  callvirt instance string System.Web.HttpRequest::get_UserHostAddress()
0x26952  ret
0x26953  ldarg.1
0x26954  ldstr    aScriptName// "SCRIPT_NAME"
0x26959  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x2695e  brfalse.s loc_2696C
0x26960  ldarg.0
0x26961  ldfld    class System.Web.HttpRequest System.Web.HttpServerVarsCollection::_request
0x26966  callvirt instance string System.Web.HttpRequest::get_FilePath()
0x2696b  ret
0x2696c  ldnull
0x2696d  ret
```
