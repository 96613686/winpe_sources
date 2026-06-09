# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::GetCuiDataSource

- ea: `0x3630`
- end: `0x375e`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::GetCuiDataSource`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x34f0`

## callees

- `0x3630`

## pseudocode

```c

```

## disassembly

```asm
0x3630  ldc.i4.0
0x3631  stloc.0
0x3632  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3637  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x363c  stloc.1
0x363d  ldloc.1
0x363e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3643  ldstr    aQt// "qt"
0x3648  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x364d  dup
0x364e  stloc.s  8
0x3650  brfalse.s loc_36AE
0x3652  ldloc.s  8
0x3654  ldstr    aRibbonvisiblet// "ribbonvisibletabdeep"
0x3659  call     bool [mscorlib]System.String::op_Equality(string, string)
0x365e  brtrue.s loc_369A
0x3660  ldloc.s  8
0x3662  ldstr    aRibbonshallow// "ribbonshallow"
0x3667  call     bool [mscorlib]System.String::op_Equality(string, string)
0x366c  brtrue.s loc_369E
0x366e  ldloc.s  8
0x3670  ldstr    aRibbontab// "ribbontab"
0x3675  call     bool [mscorlib]System.String::op_Equality(string, string)
0x367a  brtrue.s loc_36A2
0x367c  ldloc.s  8
0x367e  ldstr    aRoot// "root"
0x3683  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3688  brtrue.s loc_36A6
0x368a  ldloc.s  8
0x368c  ldstr    aAll// "all"
0x3691  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3696  brtrue.s loc_36AA
0x3698  br.s     loc_36AE
0x369a  ldc.i4.2
0x369b  stloc.0
0x369c  br.s     loc_36B0
0x369e  ldc.i4.3
0x369f  stloc.0
0x36a0  br.s     loc_36B0
0x36a2  ldc.i4.4
0x36a3  stloc.0
0x36a4  br.s     loc_36B0
0x36a6  ldc.i4.5
0x36a7  stloc.0
0x36a8  br.s     loc_36B0
0x36aa  ldc.i4.1
0x36ab  stloc.0
0x36ac  br.s     loc_36B0
0x36ae  ldc.i4.0
0x36af  stloc.0
0x36b0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x36b5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x36ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x36bf  ldstr    aId// "id"
0x36c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x36c9  stloc.2
0x36ca  ldloc.1
0x36cb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x36d0  ldstr    aLcid// "lcid"
0x36d5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x36da  stloc.3
0x36db  ldc.i4.0
0x36dc  stloc.s  4
0x36de  ldloc.3
0x36df  brfalse.s loc_36EE
0x36e1  ldloc.3
0x36e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36e7  call     unsigned int32 [mscorlib]System.Convert::ToUInt32(string, class [mscorlib]System.IFormatProvider)
0x36ec  stloc.s  4
0x36ee  ldc.i4.0
0x36ef  stloc.s  5
0x36f1  ldloc.1
0x36f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x36f7  ldstr    aRf// "rf"
0x36fc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3701  stloc.s  6
0x3703  ldloc.s  6
0x3705  brfalse.s loc_3718
0x3707  ldloc.s  6
0x3709  ldstr    aXml// "xml"
0x370e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3713  brfalse.s loc_3718
0x3715  ldc.i4.1
0x3716  stloc.s  5
0x3718  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x371d  ldloc.s  4
0x371f  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x3724  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0x3729  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x372e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x3733  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3738  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Locale()
0x373d  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x3742  newobj   instance void [Microsoft.SharePoint.Spx.WebSite.Ribbon]Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WHCUIDataSource::.ctor()
0x3747  stloc.s  7
0x3749  ldloc.s  7
0x374b  ldloc.0
0x374c  ldloc.2
0x374d  ldloc.s  4
0x374f  ldloc.s  5
0x3751  newobj   instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.UIQuery::.ctor(valuetype [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.UIQueryType, string, unsigned int32, valuetype [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.UIQueryResultFormat)
0x3756  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.CUIDataSource::RunQuery(class [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.UIQuery)
0x375b  ldloc.s  7
0x375d  ret
```
