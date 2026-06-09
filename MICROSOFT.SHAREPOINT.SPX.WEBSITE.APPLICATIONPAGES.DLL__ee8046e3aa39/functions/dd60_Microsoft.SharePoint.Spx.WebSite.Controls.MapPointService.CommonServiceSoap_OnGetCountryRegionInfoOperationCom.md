# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetCountryRegionInfoOperationCompleted

- ea: `0xdd60`
- end: `0xdd99`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetCountryRegionInfoOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xdd60`
- `0x12190`
- `0x121d0`

## pseudocode

```c

```

## disassembly

```asm
0xdd60  ldarg.0
0xdd61  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetCountryRegionInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetCountryRegionInfoCompleted
0xdd66  brfalse.s loc_DD98
0xdd68  ldarg.1
0xdd69  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xdd6e  stloc.0
0xdd6f  ldarg.0
0xdd70  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetCountryRegionInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetCountryRegionInfoCompleted
0xdd75  ldarg.0
0xdd76  ldloc.0
0xdd77  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xdd7c  ldloc.0
0xdd7d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xdd82  ldloc.0
0xdd83  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xdd88  ldloc.0
0xdd89  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xdd8e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetCountryRegionInfoCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xdd93  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetCountryRegionInfoCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetCountryRegionInfoCompletedEventArgs e)
0xdd98  ret
```
