# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetBestMapViewOperationCompleted

- ea: `0xf550`
- end: `0xf589`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetBestMapViewOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xf550`
- `0x12cd0`
- `0x12d10`

## pseudocode

```c

```

## disassembly

```asm
0xf550  ldarg.0
0xf551  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetBestMapViewCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetBestMapViewCompleted
0xf556  brfalse.s loc_F588
0xf558  ldarg.1
0xf559  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xf55e  stloc.0
0xf55f  ldarg.0
0xf560  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetBestMapViewCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetBestMapViewCompleted
0xf565  ldarg.0
0xf566  ldloc.0
0xf567  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xf56c  ldloc.0
0xf56d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xf572  ldloc.0
0xf573  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xf578  ldloc.0
0xf579  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xf57e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetBestMapViewCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xf583  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetBestMapViewCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetBestMapViewCompletedEventArgs e)
0xf588  ret
```
