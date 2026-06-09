# System.Web.HttpDebugHandler::ProcessRequest

- ea: `0x18580`
- end: `0x18841`
- name: `System.Web.HttpDebugHandler::ProcessRequest`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x16330`
- `0x16350`
- `0x16a20`
- `0x18580`
- `0x1ba50`
- `0x1c6a0`
- `0x1c780`
- `0x1f6e0`
- `0x207d0`
- `0x24810`
- `0x27240`
- `0x2ae20`
- `0x303d0`
- `0x31fa0`
- `0x32230`
- `0x34f20`
- `0x34fa0`
- `0x58d50`

## string_xrefs

- `0x185d0`: `Command`
- `0x186a6`: `Debug_Access_Denied`
- `0x1878d`: `Debug_Access_Denied`
- `0x18744`: `autoattachclsid`

## pseudocode

```c

```

## disassembly

```asm
0x18580  call     bool System.Web.HttpRuntime::get_DebuggingEnabled()
0x18585  brtrue.s loc_185C5
0x18587  ldarg.1
0x18588  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x1858d  ldstr    aDebuggingForbi// "Debugging_forbidden"
0x18592  ldc.i4.1
0x18593  newarr   [mscorlib]System.Object
0x18598  dup
0x18599  ldc.i4.0
0x1859a  ldarg.1
0x1859b  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x185a0  callvirt instance string System.Web.HttpRequest::get_Path()
0x185a5  stelem.ref
0x185a6  call     string System.Web.SR::GetString(string name, object[] args)
0x185ab  callvirt instance void System.Web.HttpResponse::Write(string s)
0x185b0  ldarg.1
0x185b1  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x185b6  ldc.i4   0x193
0x185bb  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x185c0  leave    loc_18840
0x185c5  ldarg.1
0x185c6  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x185cb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_Headers()
0x185d0  ldstr    aCommand// "Command"
0x185d5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x185da  stloc.0
0x185db  ldloc.0
0x185dc  brtrue.s loc_18608
0x185de  ldarg.1
0x185df  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x185e4  ldstr    aInvalidDebugRe// "Invalid_Debug_Request"
0x185e9  call     string System.Web.SR::GetString(string name)
0x185ee  callvirt instance void System.Web.HttpResponse::Write(string s)
0x185f3  ldarg.1
0x185f4  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x185f9  ldc.i4   0x1F4
0x185fe  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x18603  leave    loc_18840
0x18608  ldloc.0
0x18609  ldstr    aStopDebug// "stop-debug"
0x1860e  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x18613  brfalse.s loc_1862A
0x18615  ldarg.1
0x18616  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x1861b  ldstr    aOk// "OK"
0x18620  callvirt instance void System.Web.HttpResponse::Write(string s)
0x18625  leave    loc_18840
0x1862a  ldloc.0
0x1862b  ldstr    aStartDebug// "start-debug"
0x18630  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x18635  brtrue.s loc_18661
0x18637  ldarg.1
0x18638  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x1863d  ldstr    aInvalidDebugRe// "Invalid_Debug_Request"
0x18642  call     string System.Web.SR::GetString(string name)
0x18647  callvirt instance void System.Web.HttpResponse::Write(string s)
0x1864c  ldarg.1
0x1864d  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x18652  ldc.i4   0x1F4
0x18657  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x1865c  leave    loc_18840
0x18661  ldarg.1
0x18662  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x18667  ldstr    aAuthType// "AUTH_TYPE"
0x1866c  callvirt instance string System.Web.HttpWorkerRequest::GetServerVariable(string name)
0x18671  stloc.1
0x18672  ldarg.1
0x18673  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x18678  ldstr    aLogonUser// "LOGON_USER"
0x1867d  callvirt instance string System.Web.HttpWorkerRequest::GetServerVariable(string name)
0x18682  stloc.2
0x18683  ldloc.2
0x18684  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18689  brtrue.s loc_186A0
0x1868b  ldloc.1
0x1868c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18691  brtrue.s loc_186A0
0x18693  ldloc.1
0x18694  ldstr    aBasic// "basic"
0x18699  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x1869e  brfalse.s loc_186DE
0x186a0  ldarg.1
0x186a1  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x186a6  ldstr    aDebugAccessDen// "Debug_Access_Denied"
0x186ab  ldc.i4.1
0x186ac  newarr   [mscorlib]System.Object
0x186b1  dup
0x186b2  ldc.i4.0
0x186b3  ldarg.1
0x186b4  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x186b9  callvirt instance string System.Web.HttpRequest::get_Path()
0x186be  stelem.ref
0x186bf  call     string System.Web.SR::GetString(string name, object[] args)
0x186c4  callvirt instance void System.Web.HttpResponse::Write(string s)
0x186c9  ldarg.1
0x186ca  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x186cf  ldc.i4   0x191
0x186d4  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x186d9  leave    loc_18840
0x186de  ldarg.1
0x186df  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x186e4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_Form()
0x186e9  ldstr    aDebugsessionid// "DebugSessionID"
0x186ee  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x186f3  stloc.3
0x186f4  ldloc.3
0x186f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x186fa  brfalse.s loc_18726
0x186fc  ldarg.1
0x186fd  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x18702  ldstr    aInvalidDebugId// "Invalid_Debug_ID"
0x18707  call     string System.Web.SR::GetString(string name)
0x1870c  callvirt instance void System.Web.HttpResponse::Write(string s)
0x18711  ldarg.1
0x18712  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x18717  ldc.i4   0x1F4
0x1871c  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x18721  leave    loc_18840
0x18726  ldloc.3
0x18727  ldc.i4.s 0x3B
0x18729  ldc.i4.s 0x26
0x1872b  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x18730  stloc.s  4
0x18732  ldloc.s  4
0x18734  ldc.i4.1
0x18735  ldc.i4.1
0x18736  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1873b  newobj   instance void System.Web.HttpValueCollection::.ctor(string str, bool readOnly, bool urlencoded, class [mscorlib]System.Text.Encoding encoding)
0x18740  stloc.s  5
0x18742  ldloc.s  5
0x18744  ldstr    aAutoattachclsi// "autoattachclsid"
0x18749  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1874e  stloc.s  6
0x18750  ldc.i4.0
0x18751  stloc.s  7
0x18753  ldloc.s  6
0x18755  brfalse.s loc_18783
0x18757  ldc.i4.0
0x18758  stloc.s  9
0x1875a  br.s     loc_18778
0x1875c  ldloc.s  6
0x1875e  ldsfld   string[] System.Web.HttpDebugHandler::validClsIds
0x18763  ldloc.s  9
0x18765  ldelem.ref
0x18766  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x1876b  brfalse.s loc_18772
0x1876d  ldc.i4.1
0x1876e  stloc.s  7
0x18770  br.s     loc_18783
0x18772  ldloc.s  9
0x18774  ldc.i4.1
0x18775  add
0x18776  stloc.s  9
0x18778  ldloc.s  9
0x1877a  ldsfld   string[] System.Web.HttpDebugHandler::validClsIds
0x1877f  ldlen
0x18780  conv.i4
0x18781  blt.s    loc_1875C
0x18783  ldloc.s  7
0x18785  brtrue.s loc_187C2
0x18787  ldarg.1
0x18788  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x1878d  ldstr    aDebugAccessDen// "Debug_Access_Denied"
0x18792  ldc.i4.1
0x18793  newarr   [mscorlib]System.Object
0x18798  dup
0x18799  ldc.i4.0
0x1879a  ldarg.1
0x1879b  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x187a0  callvirt instance string System.Web.HttpRequest::get_Path()
0x187a5  stelem.ref
0x187a6  call     string System.Web.SR::GetString(string name, object[] args)
0x187ab  callvirt instance void System.Web.HttpResponse::Write(string s)
0x187b0  ldarg.1
0x187b1  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x187b6  ldc.i4   0x191
0x187bb  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x187c0  leave.s  loc_18840
0x187c2  ldloc.s  6
0x187c4  ldloc.3
0x187c5  ldarg.1
0x187c6  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x187cb  callvirt instance native int System.Web.HttpWorkerRequest::GetUserToken()
0x187d0  call     int32 System.Web.UnsafeNativeMethods::AttachDebugger(string clsId, string sessId, native int userToken)
0x187d5  stloc.s  8
0x187d7  ldloc.s  8
0x187d9  brfalse.s loc_18826
0x187db  ldarg.1
0x187dc  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x187e1  ldstr    aErrorAttaching// "Error_Attaching_with_MDM"
0x187e6  ldc.i4.1
0x187e7  newarr   [mscorlib]System.Object
0x187ec  dup
0x187ed  ldc.i4.0
0x187ee  ldstr    a0x_0// "0x"
0x187f3  ldloca.s 8
0x187f5  ldstr    aX8// "X8"
0x187fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x187ff  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18804  call     string [mscorlib]System.String::Concat(string, string)
0x18809  stelem.ref
0x1880a  call     string System.Web.SR::GetString(string name, object[] args)
0x1880f  callvirt instance void System.Web.HttpResponse::Write(string s)
0x18814  ldarg.1
0x18815  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x1881a  ldc.i4   0x1F4
0x1881f  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x18824  leave.s  loc_18840
0x18826  ldc.i4.s 0x25
0x18828  call     void System.Web.PerfCounters::IncrementCounter(valuetype System.Web.AppPerfCounter counter)
0x1882d  ldarg.1
0x1882e  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x18833  ldstr    aOk// "OK"
0x18838  callvirt instance void System.Web.HttpResponse::Write(string s)
0x1883d  leave.s  loc_18840
0x1883f  endfinally
0x18840  ret
```
