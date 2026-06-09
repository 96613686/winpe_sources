# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::OnCalculateSimpleRouteOperationCompleted

- ea: `0xee00`
- end: `0xee39`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::OnCalculateSimpleRouteOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xee00`
- `0x129b0`
- `0x129f0`

## pseudocode

```c

```

## disassembly

```asm
0xee00  ldarg.0
0xee01  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateSimpleRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::CalculateSimpleRouteCompleted
0xee06  brfalse.s loc_EE38
0xee08  ldarg.1
0xee09  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xee0e  stloc.0
0xee0f  ldarg.0
0xee10  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateSimpleRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::CalculateSimpleRouteCompleted
0xee15  ldarg.0
0xee16  ldloc.0
0xee17  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xee1c  ldloc.0
0xee1d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xee22  ldloc.0
0xee23  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xee28  ldloc.0
0xee29  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xee2e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateSimpleRouteCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xee33  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateSimpleRouteCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateSimpleRouteCompletedEventArgs e)
0xee38  ret
```
