# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetDataSourceInfoOperationCompleted

- ea: `0xdee0`
- end: `0xdf19`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetDataSourceInfoOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xdee0`
- `0x122d0`
- `0x12310`

## pseudocode

```c

```

## disassembly

```asm
0xdee0  ldarg.0
0xdee1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetDataSourceInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetDataSourceInfoCompleted
0xdee6  brfalse.s loc_DF18
0xdee8  ldarg.1
0xdee9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xdeee  stloc.0
0xdeef  ldarg.0
0xdef0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetDataSourceInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetDataSourceInfoCompleted
0xdef5  ldarg.0
0xdef6  ldloc.0
0xdef7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xdefc  ldloc.0
0xdefd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xdf02  ldloc.0
0xdf03  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xdf08  ldloc.0
0xdf09  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xdf0e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetDataSourceInfoCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xdf13  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetDataSourceInfoCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetDataSourceInfoCompletedEventArgs e)
0xdf18  ret
```
