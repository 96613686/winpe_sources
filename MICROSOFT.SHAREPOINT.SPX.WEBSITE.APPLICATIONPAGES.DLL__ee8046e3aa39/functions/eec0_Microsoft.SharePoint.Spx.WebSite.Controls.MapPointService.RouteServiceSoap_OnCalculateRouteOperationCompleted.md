# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::OnCalculateRouteOperationCompleted

- ea: `0xeec0`
- end: `0xeef9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::OnCalculateRouteOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xeec0`
- `0x12a50`
- `0x12a90`

## pseudocode

```c

```

## disassembly

```asm
0xeec0  ldarg.0
0xeec1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::CalculateRouteCompleted
0xeec6  brfalse.s loc_EEF8
0xeec8  ldarg.1
0xeec9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xeece  stloc.0
0xeecf  ldarg.0
0xeed0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::CalculateRouteCompleted
0xeed5  ldarg.0
0xeed6  ldloc.0
0xeed7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xeedc  ldloc.0
0xeedd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xeee2  ldloc.0
0xeee3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xeee8  ldloc.0
0xeee9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xeeee  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateRouteCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xeef3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateRouteCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CalculateRouteCompletedEventArgs e)
0xeef8  ret
```
