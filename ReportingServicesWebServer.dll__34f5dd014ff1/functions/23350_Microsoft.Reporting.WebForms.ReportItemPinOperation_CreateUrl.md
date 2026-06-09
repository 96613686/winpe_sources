# Microsoft.Reporting.WebForms.ReportItemPinOperation::CreateUrl

- ea: `0x23350`
- end: `0x2338a`
- name: `Microsoft.Reporting.WebForms.ReportItemPinOperation::CreateUrl`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x23390`

## callees

- `0x7e20`
- `0x8480`
- `0x23600`

## string_xrefs

- `0x23361`: `&OpType=ReportItemPin&`
- `0x2336d`: `ReportItemPath=`

## pseudocode

```c

```

## disassembly

```asm
0x23350  call     class Microsoft.Reporting.WebForms.HttpHandler Microsoft.Reporting.WebForms.ReportViewerFactory::get_HttpHandler()
0x23355  callvirt instance class [System]System.UriBuilder Microsoft.Reporting.WebForms.HttpHandler::get_HandlerUri()
0x2335a  ldarg.0
0x2335b  ldarg.1
0x2335c  call     string Microsoft.Reporting.WebForms.ReportDataOperation::BaseQuery(class Microsoft.Reporting.WebForms.Report report, string instanceID)
0x23361  ldstr    aOptypeReportit// "&OpType=ReportItemPin&"
0x23366  call     string [mscorlib]System.String::Concat(string, string)
0x2336b  stloc.0
0x2336c  ldloc.0
0x2336d  ldstr    aReportitempath// "ReportItemPath="
0x23372  call     string [mscorlib]System.String::Concat(string, string)
0x23377  stloc.0
0x23378  dup
0x23379  ldloc.0
0x2337a  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x2337f  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x23384  callvirt instance string [System]System.Uri::get_PathAndQuery()
0x23389  ret
```
