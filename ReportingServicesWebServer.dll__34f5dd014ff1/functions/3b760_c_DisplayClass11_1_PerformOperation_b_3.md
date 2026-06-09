# <>c__DisplayClass11_1::<PerformOperation>b__3

- ea: `0x3b760`
- end: `0x3b7bf`
- name: `<>c__DisplayClass11_1::<PerformOperation>b__3`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x11670`
- `0x3b680`

## string_xrefs

- `0x3b793`: `PinSettings[frequencyOfUpdate]`

## pseudocode

```c

```

## disassembly

```asm
0x3b760  ldarg.0
0x3b761  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x3b766  ldfld    class Microsoft.Reporting.WebForms.ReportItemPinOperation <>c__DisplayClass11_0::<>4__this
0x3b76b  ldfld    class Microsoft.Reporting.WebForms.ReportControlSession Microsoft.Reporting.WebForms.ReportDataOperation::m_reportControlSession
0x3b770  ldarg.0
0x3b771  ldfld    string <>c__DisplayClass11_1::reportItemName
0x3b776  ldarg.0
0x3b777  ldfld    string <>c__DisplayClass11_1::addGroupId
0x3b77c  ldarg.0
0x3b77d  ldfld    string <>c__DisplayClass11_1::dashboardId
0x3b782  ldarg.0
0x3b783  ldfld    string <>c__DisplayClass11_1::dashboardName
0x3b788  ldarg.0
0x3b789  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x3b78e  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x3b793  ldstr    aPinsettingsFre// "PinSettings[frequencyOfUpdate]"
0x3b798  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b79d  callvirt instance void Microsoft.Reporting.WebForms.ReportControlSession::DeliverReportItem(string reportVisualName, string groupId, string dashboardId, string dashboardName, string scheduleInfo)
0x3b7a2  ldarg.0
0x3b7a3  ldfld    string <>c__DisplayClass11_1::dashboardName
0x3b7a8  ldarg.0
0x3b7a9  ldfld    string <>c__DisplayClass11_1::dashboardId
0x3b7ae  ldarg.0
0x3b7af  ldfld    string <>c__DisplayClass11_1::addGroupId
0x3b7b4  call     class [System]System.Uri [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.PBIDashboardAPI::GetDashboardUrl(string, string)
0x3b7b9  newobj   instance void AddToDashboardsResults::.ctor(string dashboardName, class [System]System.Uri dashboardUrl)
0x3b7be  ret
```
