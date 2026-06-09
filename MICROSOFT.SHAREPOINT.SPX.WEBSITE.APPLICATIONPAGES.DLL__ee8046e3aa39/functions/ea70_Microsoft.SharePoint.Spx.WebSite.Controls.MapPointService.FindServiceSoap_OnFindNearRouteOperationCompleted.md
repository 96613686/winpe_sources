# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindNearRouteOperationCompleted

- ea: `0xea70`
- end: `0xeaa9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindNearRouteOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xea70`
- `0x12870`
- `0x128b0`

## pseudocode

```c

```

## disassembly

```asm
0xea70  ldarg.0
0xea71  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindNearRouteCompleted
0xea76  brfalse.s loc_EAA8
0xea78  ldarg.1
0xea79  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xea7e  stloc.0
0xea7f  ldarg.0
0xea80  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearRouteCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindNearRouteCompleted
0xea85  ldarg.0
0xea86  ldloc.0
0xea87  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xea8c  ldloc.0
0xea8d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xea92  ldloc.0
0xea93  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xea98  ldloc.0
0xea99  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xea9e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearRouteCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xeaa3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearRouteCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearRouteCompletedEventArgs e)
0xeaa8  ret
```
