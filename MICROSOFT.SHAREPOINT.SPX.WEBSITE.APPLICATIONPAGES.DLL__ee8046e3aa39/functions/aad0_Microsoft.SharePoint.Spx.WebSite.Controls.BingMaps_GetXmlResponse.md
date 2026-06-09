# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetXmlResponse

- ea: `0xaad0`
- end: `0xab62`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetXmlResponse`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa380`
- `0xa4b0`

## callees

- `0xaad0`

## string_xrefs

- `0xab32`: `GetXmlResponse`
- `0xab37`: `GetXmlResponse failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xaad0  ldarg.0
0xaad1  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xaad6  isinst   [System]System.Net.HttpWebRequest
0xaadb  stloc.0
0xaadc  ldloc.0
0xaadd  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xaae2  isinst   [System]System.Net.HttpWebResponse
0xaae7  stloc.1
0xaae8  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xaaed  stloc.2
0xaaee  ldloc.1
0xaaef  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xaaf4  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0xaaf9  stloc.3
0xaafa  ldloc.3
0xaafb  ldc.i4.0
0xaafc  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0xab01  ldloc.2
0xab02  ldloc.3
0xab03  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xab08  leave.s  loc_AB14
0xab0a  ldloc.3
0xab0b  brfalse.s loc_AB13
0xab0d  ldloc.3
0xab0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab13  endfinally
0xab14  ldloc.2
0xab15  stloc.s  5
0xab17  leave.s  loc_AB5F
0xab19  ldloc.1
0xab1a  brfalse.s loc_AB22
0xab1c  ldloc.1
0xab1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab22  endfinally
0xab23  stloc.s  4
0xab25  ldc.i4.0
0xab26  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xab2b  ldc.i4.s 0x32
0xab2d  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xab32  ldstr    aGetxmlresponse// "GetXmlResponse"
0xab37  ldstr    aGetxmlresponse_0// "GetXmlResponse failed: {0}"
0xab3c  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xab41  ldc.i4.1
0xab42  newarr   [mscorlib]System.Object
0xab47  stloc.s  6
0xab49  ldloc.s  6
0xab4b  ldc.i4.0
0xab4c  ldloc.s  4
0xab4e  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xab53  stelem.ref
0xab54  ldloc.s  6
0xab56  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xab5b  leave.s  loc_AB5D
0xab5d  ldnull
0xab5e  ret
0xab5f  ldloc.s  5
0xab61  ret
```
