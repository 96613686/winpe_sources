# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetRsLibDetailsFromSoapException

- ea: `0x6850`
- end: `0x6968`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetRsLibDetailsFromSoapException`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1930`
- `0x6490`

## callees

- `0x6810`
- `0x6850`
- `0x6e60`
- `0xb1c0`

## string_xrefs

- `0x687a`: `http://www.microsoft.com/sql/reportingservices`

## pseudocode

```c

```

## disassembly

```asm
0x6850  ldarg.0
0x6851  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x6856  brfalse  loc_6967
0x685b  ldc.i4.0
0x685c  stloc.0
0x685d  ldarg.0
0x685e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x6863  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x6868  dup
0x6869  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0x686e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6873  stloc.1
0x6874  ldloc.1
0x6875  ldstr    aRs// "rs"
0x687a  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/sql/reportings"...
0x687f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6884  dup
0x6885  ldstr    aRsErrorcode// "./rs:ErrorCode"
0x688a  ldloc.1
0x688b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0x6890  stloc.2
0x6891  ldloc.2
0x6892  brfalse.s loc_68D9
0x6894  ldloc.2
0x6895  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x689a  ldloca.s 0
0x689c  call     T0x2B000096
0x68a1  brfalse.s loc_68D9
0x68a3  ldarg.1
0x68a4  ldloc.0
0x68a5  ldc.i4   0x3E8
0x68aa  add
0x68ab  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x68b0  ldstr    aD// "D"
0x68b5  call     instance string [mscorlib]System.Enum::ToString(string)
0x68ba  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x68bf  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::get_HttpStatusCodeMap()
0x68c4  ldloc.0
0x68c5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode>::ContainsKey(var<u1>)
0x68ca  brfalse.s loc_68D9
0x68cc  ldarg.2
0x68cd  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::get_HttpStatusCodeMap()
0x68d2  ldloc.0
0x68d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode>::get_Item(void)
0x68d8  stind.i4
0x68d9  ldstr    aRsMessage// ".//rs:Message"
0x68de  ldloc.1
0x68df  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0x68e4  call     T0x2B000097
0x68e9  ldsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XPath.XPathNavigator, string> <>c::<>9__10_0
0x68ee  dup
0x68ef  brtrue.s loc_6908
0x68f1  pop
0x68f2  ldsfld   class <>c <>c::<>9
0x68f7  ldftn    instance string <>c::<GetRsLibDetailsFromSoapException>b__10_0(class [System.Xml]System.Xml.XPath.XPathNavigator n)
0x68fd  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XPath.XPathNavigator, string>::.ctor(object, native int)
0x6902  dup
0x6903  stsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XPath.XPathNavigator, string> <>c::<>9__10_0
0x6908  call     T0x2B000098
0x690d  call     T0x2B000099
0x6912  call     T0x2B00009A
0x6917  stloc.3
0x6918  ldloc.3
0x6919  call     T0x2B00009B
0x691e  stloc.s  4
0x6920  ldloc.s  4
0x6922  brfalse.s loc_692C
0x6924  ldarg.1
0x6925  ldloc.s  4
0x6927  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x692c  ldarg.0
0x692d  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x6932  ldloc.0
0x6933  call     string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetSoapDetailDataName(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x6938  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x693d  brfalse.s loc_6967
0x693f  ldc.i4.1
0x6940  stloc.s  5
0x6942  br.s     loc_6960
0x6944  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6949  dup
0x694a  ldloc.3
0x694b  ldloc.s  5
0x694d  ldelem.ref
0x694e  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6953  ldarga.s 1
0x6955  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x695a  ldloc.s  5
0x695c  ldc.i4.1
0x695d  add
0x695e  stloc.s  5
0x6960  ldloc.s  5
0x6962  ldloc.3
0x6963  ldlen
0x6964  conv.i4
0x6965  blt.s    loc_6944
0x6967  ret
```
