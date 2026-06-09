# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validateXML

- ea: `0x15f0`
- end: `0x1665`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validateXML`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1580`

## callees

- `0x15f0`

## string_xrefs

- `0x1618`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0x161d`: `ValidateXML`
- `0x1622`: `Exception thrown when validating XML`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.0
0x15f1  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x15f6  stloc.0
0x15f7  ldloc.0
0x15f8  ldarg.1
0x15f9  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x15fe  stloc.1
0x15ff  ldc.i4.1
0x1600  stloc.2
0x1601  ldloc.1
0x1602  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1607  brtrue.s loc_1601
0x1609  leave.s  loc_1649
0x160b  stloc.3
0x160c  ldc.i4   0x67363936
0x1611  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x1616  ldc.i4.s 0x32
0x1618  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0x161d  ldstr    aValidatexml// "ValidateXML"
0x1622  ldstr    aExceptionThrow_0// "Exception thrown when validating XML"
0x1627  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x162c  ldc.i4.1
0x162d  newarr   [mscorlib]System.Object
0x1632  stloc.s  5
0x1634  ldloc.s  5
0x1636  ldc.i4.0
0x1637  ldloc.3
0x1638  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x163d  stelem.ref
0x163e  ldloc.s  5
0x1640  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1645  ldc.i4.0
0x1646  stloc.2
0x1647  leave.s  loc_1649
0x1649  ldloc.2
0x164a  stloc.s  4
0x164c  leave.s  loc_1662
0x164e  ldloc.1
0x164f  brfalse.s loc_1657
0x1651  ldloc.1
0x1652  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1657  endfinally
0x1658  ldloc.0
0x1659  brfalse.s loc_1661
0x165b  ldloc.0
0x165c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1661  endfinally
0x1662  ldloc.s  4
0x1664  ret
```
