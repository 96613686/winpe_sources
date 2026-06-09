# Microsoft.Reporting.WebForms.ReportControl::CreateDeviceInfo

- ea: `0x10ed0`
- end: `0x1105e`
- name: `Microsoft.Reporting.WebForms.ReportControl::CreateDeviceInfo`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x10cc0`

## callees

- `0x1ab0`
- `0x2830`
- `0x2840`
- `0x89c0`
- `0x10ed0`
- `0x110e0`
- `0x11140`

## string_xrefs

- `0x10fad`: `ReplacementRoot`
- `0x10fe4`: `LinkTarget`
- `0x11019`: `UserAgent`

## pseudocode

```c

```

## disassembly

```asm
0x10ed0  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x10ed5  stloc.0
0x10ed6  ldarg.1
0x10ed7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Reporting.WebForms.DeviceInfo>::GetEnumerator()
0x10edc  stloc.3
0x10edd  br.s     loc_10EFB
0x10edf  ldloc.3
0x10ee0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Reporting.WebForms.DeviceInfo>::get_Current()
0x10ee5  stloc.s  4
0x10ee7  ldloc.0
0x10ee8  ldloc.s  4
0x10eea  callvirt instance string Microsoft.Reporting.WebForms.DeviceInfo::get_Name()
0x10eef  ldloc.s  4
0x10ef1  callvirt instance string Microsoft.Reporting.WebForms.DeviceInfo::get_Value()
0x10ef6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x10efb  ldloc.3
0x10efc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10f01  brtrue.s loc_10EDF
0x10f03  leave.s  loc_10F0F
0x10f05  ldloc.3
0x10f06  brfalse.s loc_10F0E
0x10f08  ldloc.3
0x10f09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10f0e  endfinally
0x10f0f  ldloc.0
0x10f10  ldstr    aHtmlfragment// "HTMLFragment"
0x10f15  ldstr    aTrue// "true"
0x10f1a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f1f  ldloc.0
0x10f20  ldstr    aSection// "Section"
0x10f25  ldarga.s 3
0x10f27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10f2c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10f31  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f36  ldarg.2
0x10f37  ldarg.0
0x10f38  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_viewerInstanceIdentifier
0x10f3d  ldc.i4.0
0x10f3e  call     string Microsoft.Reporting.WebForms.ReportImageOperation::CreateUrl(class Microsoft.Reporting.WebForms.Report report, string instanceID, bool isResourceStreamRoot)
0x10f43  stloc.1
0x10f44  ldloc.0
0x10f45  ldstr    aStreamroot// "StreamRoot"
0x10f4a  ldloc.1
0x10f4b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f50  ldarg.2
0x10f51  ldarg.0
0x10f52  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_viewerInstanceIdentifier
0x10f57  ldc.i4.1
0x10f58  call     string Microsoft.Reporting.WebForms.ReportImageOperation::CreateUrl(class Microsoft.Reporting.WebForms.Report report, string instanceID, bool isResourceStreamRoot)
0x10f5d  stloc.2
0x10f5e  ldloc.0
0x10f5f  ldstr    aResourcestream_0// "ResourceStreamRoot"
0x10f64  ldloc.2
0x10f65  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f6a  ldloc.0
0x10f6b  ldstr    aEnablepowerbif// "EnablePowerBIFeatures"
0x10f70  ldarga.s 9
0x10f72  call     instance string [mscorlib]System.Boolean::ToString()
0x10f77  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f7c  ldloc.0
0x10f7d  ldstr    aActionscript// "ActionScript"
0x10f82  ldarg.0
0x10f83  call     instance string Microsoft.Reporting.WebForms.ReportControl::get_ActionScriptMethod()
0x10f88  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10f8d  ldarg.s  4
0x10f8f  brfalse.s loc_10FA3
0x10f91  ldloc.0
0x10f92  ldstr    aFindstring// "FindString"
0x10f97  ldarg.s  4
0x10f99  callvirt instance string Microsoft.Reporting.WebForms.SearchState::get_Text()
0x10f9e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10fa3  ldarg.s  5
0x10fa5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10faa  brtrue.s loc_10FB9
0x10fac  ldloc.0
0x10fad  ldstr    aReplacementroo// "ReplacementRoot"
0x10fb2  ldarg.s  5
0x10fb4  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10fb9  ldloc.0
0x10fba  ldstr    aPrefixid// "PrefixId"
0x10fbf  ldarg.0
0x10fc0  call     instance string Microsoft.Reporting.WebForms.ReportControl::get_UniqueRenderingId()
0x10fc5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10fca  ldloc.0
0x10fcb  ldstr    aStylestream// "StyleStream"
0x10fd0  ldstr    aTrue// "true"
0x10fd5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10fda  ldarg.s  6
0x10fdc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10fe1  brtrue.s loc_10FF0
0x10fe3  ldloc.0
0x10fe4  ldstr    aLinktarget// "LinkTarget"
0x10fe9  ldarg.s  6
0x10feb  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x10ff0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x10ff5  brfalse.s loc_11025
0x10ff7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x10ffc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x11001  brfalse.s loc_11025
0x11003  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x11008  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1100d  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x11012  stloc.s  5
0x11014  ldloc.s  5
0x11016  brfalse.s loc_11025
0x11018  ldloc.0
0x11019  ldstr    aUseragent// "UserAgent"
0x1101e  ldloc.s  5
0x11020  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x11025  ldarg.s  7
0x11027  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1102c  brtrue.s loc_11048
0x1102e  ldloc.0
0x1102f  ldstr    aBrowsermode// "BrowserMode"
0x11034  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11039  brtrue.s loc_11048
0x1103b  ldloc.0
0x1103c  ldstr    aBrowsermode// "BrowserMode"
0x11041  ldarg.s  7
0x11043  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x11048  ldarg.s  8
0x1104a  brtrue.s loc_1105C
0x1104c  ldloc.0
0x1104d  ldstr    aImageconsolida_0// "ImageConsolidation"
0x11052  ldstr    aFalse// "false"
0x11057  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x1105c  ldloc.0
0x1105d  ret
```
