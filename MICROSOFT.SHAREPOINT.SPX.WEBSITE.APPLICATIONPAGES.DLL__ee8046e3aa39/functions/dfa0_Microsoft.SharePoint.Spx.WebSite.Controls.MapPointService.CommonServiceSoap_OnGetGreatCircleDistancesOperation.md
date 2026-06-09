# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetGreatCircleDistancesOperationCompleted

- ea: `0xdfa0`
- end: `0xdfd9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetGreatCircleDistancesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xdfa0`
- `0x12370`
- `0x123b0`

## pseudocode

```c

```

## disassembly

```asm
0xdfa0  ldarg.0
0xdfa1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetGreatCircleDistancesCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetGreatCircleDistancesCompleted
0xdfa6  brfalse.s loc_DFD8
0xdfa8  ldarg.1
0xdfa9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xdfae  stloc.0
0xdfaf  ldarg.0
0xdfb0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetGreatCircleDistancesCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetGreatCircleDistancesCompleted
0xdfb5  ldarg.0
0xdfb6  ldloc.0
0xdfb7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xdfbc  ldloc.0
0xdfbd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xdfc2  ldloc.0
0xdfc3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xdfc8  ldloc.0
0xdfc9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xdfce  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetGreatCircleDistancesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xdfd3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetGreatCircleDistancesCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetGreatCircleDistancesCompletedEventArgs e)
0xdfd8  ret
```
